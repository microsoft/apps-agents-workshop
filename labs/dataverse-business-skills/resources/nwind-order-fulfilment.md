---
name: nwind-order-fulfilment
description: >-
  Use this skill for all order-related requests: placing orders, checking inventory,
  applying discounts and confirming fulfilment status for Northwind Traders.
  Trigger phrases: "process an order", "check stock", "apply discount", "what is the order status", "confirm fulfilment".

---

## Instructions
## Step 1: Validate the customer
1. Query nwind_customerses by nwind_company or nwind_customersid.
2. Confirm statecode = 0 (Active). If not 0, stop and notify the user.
3. Note nwind_country_region (for shipping fee) and nwind_notes (check for "VIP").

## Step 2: Check product availability
1. Query nwind_productses for each item by nwind_productname.
2. Query nwind_inventorytransactionses where nwind_productid = product ID.
   Calculate available stock: SUM(nwind_quantity where nwind_transactiontype = 1)
   minus SUM(nwind_quantity where nwind_transactiontype IN [2, 3, 4]).
3. If available stock < requested quantity, flag the item as backordered.
4. If available stock <= nwind_reorderlevel, flag for supplier reorder.

## Step 3: Apply the discount policy
- nwind_quantity > 20 units of a single product: 5% discount on that line.
- Order subtotal > $500: 10% discount applied to the whole order.
- VIP customer (nwind_notes contains "VIP"): up to 15% discount.
- Do not stack discounts. Apply the highest applicable rate only.
- Store discount as decimal in nwind_discount (e.g. 0.05 for 5%).

## Step 4: Create the order record
1. Create a record in nwind_orderses:
   nwind_orderdate = today; nwind_customerid = customer record ID;
   nwind_shippingfee = 15 if nwind_country_region = "USA" else 45;
   nwind_orderstatusid = 0 (New).
2. Note the nwind_ordernumber from the created record.

## Step 5: Create order details and update inventory
1. For each line item create a record in nwind_orderdetailses:
   nwind_orderid, nwind_productid, nwind_quantity,
   nwind_unitprice = product nwind_listprice, nwind_discount (decimal).
2. Extended price = nwind_unitprice x nwind_quantity x (1 - nwind_discount).
3. Create a nwind_inventorytransactionses record:
   nwind_productid, nwind_customerorderid = order ID,
   nwind_quantity = ordered qty, nwind_transactiontype = 2 (Sold),
   nwind_transactioncreateddate = today (datetime),
   nwind_transactionmodifieddate = today (datetime).
4. Set nwind_orderdetailstatusid:
   1 (Allocated) if pending payment; 2 (Invoiced) if payment confirmed.
5. Update nwind_orderstatusid:
   1 (Invoiced) if paid; 2 (Shipped) once dispatched.
6. Return: nwind_ordernumber, line items, totals, nwind_shippingfee.
