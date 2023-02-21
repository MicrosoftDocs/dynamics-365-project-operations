## Purchase orders for stocked items - Fixed receipt price 

To use this feature, the **Fixed receipt price** parameter in the **Inventory model group** must be set to **Yes**

**Inventory management**>**Setup**>**Inventory**>**Item model group**

This feature works like a standard cost where all the receipts and consumption happen on the cost price defined for the item.

When there is a purchase with a unit price that is more or less than the cost price defined for the item, the system posts the variance into purchase fixed receipt price profit or loss account and fixed receipt price offset account. Because of this, the system always maintains the item cost price like the standard cost price for the product.

For project item consumption, either through **Item requirements** or **Purchase orders** with **Item requirements** , project cost is always updated with the item cost price.

When there is a change in the fixed cost price, need to run the **Inventory closing** , adjust the on-hand inventory, and then activate the new cost.

### Example scenario

The following example shows the project cost for the items with **Fixed price** set to **Yes** on the **Item model group**.

The following screen shows the purchase order and vendor invoice posted for the purchase order.

![image](https://user-images.githubusercontent.com/103096040/220296385-83f07201-d3af-46ee-a99e-0ab3786312e3.png)

The following screen shows the Project posted transaction with project cost posted as USD 100.00.

![image](https://user-images.githubusercontent.com/103096040/220296443-c77a7d53-d8c9-44d1-b568-dd52f995ae42.png)
