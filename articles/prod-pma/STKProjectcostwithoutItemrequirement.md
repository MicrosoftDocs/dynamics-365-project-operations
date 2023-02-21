Project purchase orders without **Item requirements**

To use this feature, the **item requirements** parameter in the **Project management & accounting parameters** must be set to **No**.

**Project management and accounting** \> **Setup** \> **Project management & accounting parameters** \> **General** \> **Create Item requirements** : **No**

When a purchase order is created without using the **Item requirements** feature, Dynamics 365 Finance generates & posts the project cost at time of vendor invoice.

When a packing slip is posted for the purchase order as part of product receipt, no project cost transactions are generated irrespective of the **Item model group** ( **Include physical value** option – Yes or No) mapped on the item master.

**Dynamics 365 Finance** considers the **Purchase unit price** , **Discount** , and **Miscellaneous charges** assigned to the vendor invoice as the project cost. If the **Miscellaneous charges** are configured as **Loaded on inventory** ( **Miscellaneous charge**** - Debit, inventory**) then**Miscellaneous charge **amount is added to the** Purchase unit price, ****Discount** , and the project cost is generated accordingly.

**Dynamics 365 Finance** generates two **Inventory transactions** for each purchase order for stocked item:

- Purchase order
- Transaction (which is for project consumption).

Both transactions are linked with each other ( **Inventory marking on the inventory transactions** ) which allows the system to consider the inventory cost as project cost. Because of the markings/linkage between the **Inventory transactions** , the system considers the **Project purchase order price** along with the charges for project cost.

Inventory recalculation doesn't have an impact on the project posted transactions because these transactions are generated during vendor invoice posting, and the project consumption line is linked with purchase order inventory cost. This rule is applicable for all items with different inventory costing methods, including **FIFO, LIFO, Weighted average, and standard costing**.

### Example scenario

In this example, there are two purchase order lines with items using **FIFO, Weighted average** costing method, and **Miscellaneous charges** applied on the purchase orders.

**Line 1:**

Item: W001, Quantity: 2, Unit price 1000

Inventory costing method: Weighted average

Miscellaneous charges: 666.67

**Line 2:**

**Item** F001, **Quantity** : 1, **Unit price** : 1000

**Inventory costing method** : **FIFO**

**Miscellaneous charges** : 333.33

**Project cost** :

**Item** : W001, 2666.67 (Purchase cost 2000, Miscellaneous charges: 666.67)

**Item** : F001, 1333.33 (Purchase cost 1000, Miscellaneous charges: 1333.33)

The following screen shows the **Purchase order** along with **Miscellaneous charges** applied to item **FIFO**.

The following screen shows the **Project posted transactions** generated at purchase order invoice for item F001 and W001. For item F001, Project cost is recorded as USD 2,666.67 which is inclusive of purchase order price and Miscellaneous charges applied on the purchase order.

For item W001 Project cost is recorded as USD 1,333.33 which is inclusive of purchase order price and Miscellaneous charges applied on the purchase order.
