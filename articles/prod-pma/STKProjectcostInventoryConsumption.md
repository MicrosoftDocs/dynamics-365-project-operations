## Inventory consumption from stock

**Dynamics 365 Finance** allows inventory consuming from the warehouse using Project **Item requirements** and **Project item journal**. **Dynamics 365 Finance** always considers the **Weighted average** costing method for item requirements, except for standard costing. Whenever a new item requirement is posted, irrespective of the item model group mapped on the product, the default **Weighted average** costing method is applied, and the same is reflected on the Project posted transactions.

This is in line with the sales orders without projects where actual cost consumption updated after the inventory recalculation and costing.

After the **Inventory recalculation** process, the system calculates the actual cost based upon inventory model mapped with the item and adjusts the inventory cost for projects as well.

### Example scenario

The following examples show the project cost transactions posted for item requirements for items with different **Inventory costing** methods applied on the items.

_ **Inventory costing method: FIFO** _

The following example shows the project cost transactions posted for **Item requirements** for an item with **FIFO** inventory costing method.

| **Transaction type** | **Item id** | **Qty** | **Unit price** | **Total Amount** | **Item cost price** | **After Recalculation** |
| --- | --- | --- | --- | --- | --- | --- |
| Purchase order without Project | F001 | 100.00 | 200.00 | 20,000.00 |   |   |
| Purchase order without Project | F001 | 100.00 | 200.00 | 20,000.00 |   |   |
| Purchase order without Project | F001 | 100.00 | 1,000.00 | 100,000.00 |   |   |
| Item requirements or Project item journal | F001 | (1.00) | 200.00 | (200.00) | 466.67 | 200.00 |

The following screen shows the project posted transactions generated after the **Item requirements** posting process.

![image](https://user-images.githubusercontent.com/103096040/220300562-0933986d-c6e2-4138-a168-47c3efabf415.png)

The following screen shows the project posted transactions generated after the **Inventory recalculation** process. The system has generated adjustment vouchers for the transactions generated for **Item requirements.**

![image](https://user-images.githubusercontent.com/103096040/220300610-5ec66d84-ee71-4118-9bcc-eb201af5e17a.png)

_ **Inventory costing method: Weighted average** _

The following example shows the project cost transactions posted for **Item requirements** for an item with **Weighted average** inventory costing method.

| **Transaction type** | **Item id** | **Qty** | **Unit price** | **Total Amount** | **Item cost price** | **After Recalculation** |
| --- | --- | --- | --- | --- | --- | --- |
| Purchase order without Project | W001 | 100.00 | 100.00 | 10,000.00 |   |   |
| Purchase order without Project | W001 | 100.00 | 300.00 | 30,000.00 |   |   |
| Purchase order without Project | W001 | 100.00 | 3,000.00 | 300,000.00 |   |   |
| Item requirements | W001 | (1.00) | 300.00 | (300.00) | 1133.33 | 1133.33 |

The following screen shows the project posted transactions generated after the **Item requirements** posting process.
![image](https://user-images.githubusercontent.com/103096040/220300701-dd916044-92f9-4fe6-82c6-afcae0436114.png)
