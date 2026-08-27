---
name: nwind-customer-return
description: >-
  Use when a customer requests a return or refund for a Northwind Traders order.
  Trigger phrases: "return", "refund", "send back", "wrong item", "cancel order".
---

## Instructions
1. Locate the order in nwind_orderses by nwind_ordernumber or nwind_customerid.
2. Check eligibility: nwind_orderdate must be within the last 30 days.
3. Check nwind_orderstatusid: returns are not accepted if status = 3 (Closed).
4. Check product category to confirm item is not perishable:
   Join nwind_orderdetailses -> nwind_productses via nwind_productid.
   Join nwind_productses -> nwind_categorieses via
   nwind_products_nwind_categories relationship.
   If nwind_name (category) contains "Dried Fruit" or "Condiments" only
   (not Fresh/Frozen), proceed.
5. Update nwind_orderstatusid = 3 (Closed) in nwind_orderses.
6. For each returned line item (nwind_orderdetailses record):
   Create a nwind_inventorytransactionses record:
   nwind_productid, nwind_customerorderid = order ID,
   nwind_quantity = returned qty, nwind_transactiontype = 1 (Purchased/Returned).
7. Draft a refund confirmation using nwind_emailaddress from nwind_customerses.
