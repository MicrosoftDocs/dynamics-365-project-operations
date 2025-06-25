---
title: Currency
description: This article provides information about how to add and remove currency types in Project Operations.
author: mukumarm
ms.author: mukumarm
ms.date: 05/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Currency

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_



Currencies determine the prices for products in the product catalog and the cost of transactions, such as sales orders. If your customers are spread across geographies, add their currencies to manage your transactions. Add the currencies that are most appropriate for your current and future business needs.  

> [!NOTE]
> If your environment is a Common Data Service environment, you are in the Power Platform admin center, and you select the **Currencies** page (**Environments** > [select environment] > **Settings** > **Business** > **Currencies**), the page will be blank. This is because setting a currency is not supported in Common Data Service environments.

## Add a currency  
Before you start this procedure, verify that your security role includes system admin permissions. 

1. In the Power Platform admin center, select an environment. 
2. Select **Settings** > **Business**.
3. Select **Currencies**.  
4. Select **New**.  
5. Fill in the information, as required.  


   |          Field          |                                                                                                                                                                                                                                                                                                                                                                            Description                                                                                                                                                                                                                                                                                                                                                                            |
   |-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |    **Currency Type**    | - **System** - Select this option if you want to use the currencies available in model-driven apps in Dynamics 365. To search for a currency,  select **Lookup**. When you select a currency code, **Currency Name** and **Currency Symbol** are automatically added for the selected currency.<br />- **Custom** - Select this option if you want to add a currency that's not available in model-driven apps in Dynamics 365. In this case, you must manually enter the values for **Currency Code**, **Currency Precision**, **Currency Name**, **Currency Symbol**, and **Currency Conversion**. |
   |    **Currency Code**    |                                                                                                                                                                                                                                                                                                                                            Short form for the currency. For example, **USD** for United States Dollar.                                                                                                                                                                                                                                                                                                                                            |
   | **Currency Precision**  |                                                                                                                                                                                  Type the number of decimals that you want to use for the currency.  You can add a value between 0 and 4. **Note:**  If you've set a precision value in the **System Settings** dialog box, that value will appear here.                                                                                                                                                                                  |
   |    **Currency Name**    |                                                                                                                                                                                                                                         If you selected a currency code from the list of available currencies in model-driven apps in Dynamics 365, the currency name for the selected code is displayed here. If you selected **Custom** as the currency type, type the name of the currency.                                                                                                                                                                                                                                          |
   |   **Currency Symbol**   |                                                                                                                                                                                                                                                                      If you selected a currency code from the list of available currencies, the symbol for the selected currency is displayed here. If you selected **Custom** as the currency type, enter the symbol for the new currency.                                                                                                                                                                                                                                                                       |
   | **Currency Conversion** |                                                                                                                                                                                                                                     Type the value of the selected currency in terms of one US dollar. This is the amount at which the selected currency converts to the base currency. **Important:**  Make sure you update this value as frequently as required to avoid any inaccurate calculations in your transactions.                                                                                                                                                                                                                                      |


6. When you're done, on the command bar, select **Save** or **Save and Close**.  

   > [!TIP]
   >  To edit a currency, select the currency, and then enter or select the new values.  

## Delete a currency  

1. In the Power Platform admin center, select an environment. 
2. Select **Settings** > **Business**.
3. Select **Currencies**.  
4. From the list of currencies displayed, select the currency to delete.  
5. Select **Delete**.  
6. Confirm the deletion.  

> [!IMPORTANT]
>  You can't delete currencies that are in use by other records; you can only deactivate them. Deactivating currency records doesn't remove the currency information stored in existing records, such as opportunities or orders. However, you won't be able to select the deactivated currency for new transactions.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
