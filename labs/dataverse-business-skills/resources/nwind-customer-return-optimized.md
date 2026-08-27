---
name: nwind-customer-return
description: >-
  Use when a customer requests a return or refund for a Northwind Traders order.
  Trigger phrases: "return", "refund", "send back", "wrong item", "cancel order".
---

## Description
Use when a customer requests a return or refund for a Northwind Traders order.
Trigger phrases: "return", "refund", "send back", "wrong item", "cancel order".

## Instructions

### Step 1 – Validate order and retrieve customer details
Run a single query to confirm the order exists, is within the 30-day return window, is not already closed, and return the customer email in one round trip.

```sql
SELECT
    o.nwind_orderid,
    o.nwind_ordernumber,
    o.nwind_orderdate,
    o.nwind_orderstatusid,
    c.nwind_customerid,
    c.nwind_emailaddress
FROM nwind_orderses AS o
JOIN nwind_customerses AS c ON o.nwind_customerid = c.nwind_customerid
WHERE (o.nwind_ordernumber = @OrderNumber OR o.nwind_customerid = @CustomerID)
  AND o.nwind_orderdate >= DATEADD(day, -30, GETDATE())
  AND o.nwind_orderstatusid <> 3;
```

If no rows are returned the order is ineligible (outside the 30-day window or already closed). Stop and notify the customer.

### Step 2 – Confirm all line items are returnable
Run a single join across order details, products, and categories to retrieve every line item and its category name in one query.

```sql
SELECT
    od.nwind_orderdetailid,
    od.nwind_productid,
    od.nwind_quantity,
    p.nwind_productname,
    cat.nwind_name AS category_name
FROM nwind_orderdetailses AS od
JOIN nwind_productses AS p   ON od.nwind_productid  = p.nwind_productid
JOIN nwind_categorieses AS cat
     ON p.nwind_categoriesid = cat.nwind_categoriesid  -- nwind_Products_nwind_Categories
WHERE od.nwind_orderid = @OrderID;
```

If any row has a `category_name` not in ('Dried Fruit', 'Condiments'), exclude that line item and notify the customer that perishable/fresh/frozen items are non-returnable. Proceed only with eligible line items.

### Step 3 – Close the order

```sql
UPDATE nwind_orderses
SET    nwind_orderstatusid = 3   -- Closed
WHERE  nwind_orderid = @OrderID;
```

### Step 4 – Create inventory return transactions
For each eligible line item from Step 2, insert one inventory transaction record.

```sql
INSERT INTO nwind_inventorytransactionses
    (nwind_productid, nwind_customerorderid, nwind_quantity, nwind_transactiontype)
VALUES
    (@ProductID, @OrderID, @ReturnedQty, 1);  -- type 1 = Purchased / Returned
```

Repeat for every returned order detail line.

### Step 5 – Draft refund confirmation
Use `nwind_emailaddress` from Step 1 to draft a refund confirmation email to the customer.
