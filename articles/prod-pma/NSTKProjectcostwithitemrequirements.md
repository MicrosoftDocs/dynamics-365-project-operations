## Purchase order for Non-stock/Service items with item requirements

To use the **Non-stocked** or **Service** items with **Item requirements,** below setup's are required.

**Item requirements** parameter in the **Project management & accounting parameters** must be set to **Yes**.

**Project management and accounting** \> **Setup** \> **Project management & accounting parameters** \> **General** Tab

Enable the **Feature** : **Enable creation of item requirement for non-stocked items**.

When a purchase order is created, **Dynamics 365 Finance** generates the project item requirements. Each purchase order line has a direct relationship with project item requirements and both lines are linked to each other. Any changes to the purchase order have a direct impact and update the project item requirements.

Item requirements are automatically posted when purchase order packing slip is posted if the parameter **Item consumption** is set to **Yes.** Otherwise, the system shows the message **Do you want to consume the material**. If **Item consumption** is set to **No** , you can post the item requirements manually as well. Regardless of how an item requirement is posted, manually or automatically, the Project cost is generated.

When a **purchase order invoice** is posted and if there is any change in unit price or discount then project cost is updated during the vendor invoice posting process and project subledger details have been updated accordingly.

### Example scenario

The following example shows the **Purchase order** and **Project transactions** for the **Non-stocked** or **Service** items. The purchase order is created with **Net amount** USD 2,000.00. There is a change in vendor invoice **unit price** USD 2,500.00 **.**
![image](https://user-images.githubusercontent.com/103096040/220303131-0bc79d5e-cac7-45e3-8730-1692d7830bca.png)

The following screen shows the project posted transactions generated when **Purchase Order Product receipt** is posted.
![image](https://user-images.githubusercontent.com/103096040/220303103-0b8140e9-fa4e-4dbc-bcbb-b11c0d7864d7.png)

The following screen shows the project posted transactions when purchase order vendor invoice is posted. There is a change in **Unit price** and system has posted an adjustment to the existing project posted transaction.
![image](https://user-images.githubusercontent.com/103096040/220303067-ef96d8ea-71de-4794-b88a-4d8309ba27b0.png)
