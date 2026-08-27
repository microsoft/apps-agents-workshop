---
name: nwind-supplier-reorder
description: >-
 Use when product stock falls at or below nwind_ReorderLevel. Trigger phrases: "reorder", "low stock", "contact supplier", "which products need restocking".
---

## Instructions
1. Query nwind_inventorytransactionses grouped by nwind_productid:
   available = SUM Purchased(type=1) - SUM Sold(type=2) - SUM OnHold(type=3) - SUM Waste(type=4).
2. Query nwind_productses. Filter where available stock <= nwind_reorderlevel.
3. Check nwind_purchaseorderdetailses for open POs per product.
   If nwind_purchaseorderstatusid IN [0,1,2] exists for product, skip it.
4. Join nwind_productses to nwind_supplierses via
   nwind_products_nwind_suppliers relationship.
   Get nwind_company, nwind_emailaddress, nwind_businessphone.
5. Create a record in nwind_purchaseorderses:
   nwind_supplierid = supplier ID; nwind_expecteddate = today + 14 days;
   nwind_purchaseorderstatusid = 0 (New).
6. Create nwind_purchaseorderdetailses record:
   nwind_purchaseorderid, nwind_productid,
   nwind_quantity = nwind_targetlevel - available (min nwind_minimumreorderquantity).
7. Return a summary table: nwind_productname | Supplier (nwind_company) | Available Stock | nwind_reorderlevel | nwind_targetlevel | Order Qty
