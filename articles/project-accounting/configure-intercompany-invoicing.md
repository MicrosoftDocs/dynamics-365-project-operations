---
# required metadata

title: Configure intercompany invoicing
description: This article provides information and examples about configuring intercompany invoicing for projects.
author:  mukumarm
ms.author: mukumarm
ms.date: 05/22/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Configure intercompany invoicing

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

Complete the following steps to set up intercompany invoicing for projects in Dynamics 365 Project Operations. Intercompany transactions are time and expense transactions from a project contract that belong to one company or organizational unit, while the resources on the project contract are part of a different company or organizational unit.

## Example: Configure intercompany invoicing

In the following example, Contoso Robotics USA (USPM) is the borrowing legal entity and Contoso Robotics UK (GBPM) is the lending legal entity. 

1. **Configure intercompany accounting between legal entities**. Each pair of borrowing and lending legal entities must be configured on the General ledger [Intercompany accounting](/dynamics365/finance/general-ledger/intercompany-accounting-setup) page.
    
    1. In Dynamics 365 Finance, go to **General Ledger** > **Posting setup** > **Intercompany accounting**. Create a record with the following information:

        - **Originating company** = **GBPM**
        - **Destination company** = **USPM**

2. **Configure the trading relationship between legal entities**. The customer record representing the borrowing legal entity must be created in the lending legal entity. The vendor record representing the lending legal entity must be created in the borrowing legal entity.

     1. In Finance, select the legal entity **GBPM**.
     2. Go to **Accounts receivable** > **Customer** > **All customers**. Create a new record for the legal entity, **USPM**.
     3. Expand **Name**, filter the records by **Type** and select **Legal entities**. 
     4. Find and select the customer record for **Contoso Robotics USA (USPM)**.
     5. Select **Use match**. 
     6. Select the customer group **50 - Intercompany customers** and then save the record.
     7. Select the legal entity **USPM**.
     8. Go to **Accounts payable** > **Vendors** > **All vendors**. Create a new record for the legal entity, **GBPM**.
     9. Expand **Name**, filter records by **Type**, and select **Legal entities**. 
     10. Find and select the customer record for **Contoso Robotics UK (GBPM)**.
     11. Select **Use match**, select the vendor group, and then save the record.
     12. In the vendor record, select **General** > **Set up** > **Intercompany**.
     13. On the **Trading relationship** tab, set **Active** to **Yes**.
     14. Set the **Customer company** field to **GBPM** and in **My account record**, select the customer record that you created earlier in the procedure.

3. **Configure intercompany settings in Project management and accounting parameters**. 

    1. Select the legal entity **USPM** and go to **Project management and accounting** > **Setup** > **Project management and accounting parameters**.
    2. On the **Intercompany** tab, select the procurement category to match the vendor invoices that are automatically generated.
    3. In **Default category**, select **Intercompany resources**.
    4. Select the legal entity **GBPM** and go to **Project management and accounting** > **Setup** > **Project management and accounting parameters**.
    5. On the **Intercompany** tab, select a default project category for each transaction type. Project categories are used for tax configuration when the invoiced category in intercompany transactions exists only in the borrowing legal entity. You can choose to accrue revenue for intercompany transactions. Accrual happens when the transactions are posted through the Project Operations Integration journal in the lending legal entity. The journal is reversed when the intercompany invoice is posted.
    6. In the **When lending resources** group, select **...** > **New**. 
    7. In the grid, select the following information:

          - **Borrowing legal entity** = **USPM**
          - **Accrue revenue** = **Yes**
          - **Default timesheet category** = **Default – Hour**
          - **Default expense category** = **Default – expense**

4. **Set intercompany cost and revenue accounts in Ledger posting setup**. The intercompany revenue account is credited when the Intercompany customer invoice is posted in the lending legal entity. The intercompany cost account is debited when the  matching pending vendor invoice is posted in the borrowing legal entity. These accounts are set up in corresponding legal entities. 
      
     1. In Finance, select the borrowing legal entity **USPM**. 
     2. Go to **Project management and accounting** > **Setup** > **Posting** > **Ledger posting setup**. 
     3. On the **Cost accounts** tab, in **Ledger account type**, select **Intercompany cost**. Create a new record with the following information:
      
        - **Lending legal entity** = **GBPM**
        - **Main account** = Select the main account for intercompany cost. This setup is required. The setup is used for intercompany flows in Finance, but not in project-related intercompany flows. This selection has no downstream impact. 
        
     4. Select lending legal entity, **GBPM**. 
     5. Go to **Project management and accounting** > **Setup** > **Posting** > **Ledger posting setup**. 
     6. On the **Revenue accounts** tab, in **Ledger account type**, select **Intercompany revenue**. Create a new record with the following information:

        - **Borrowing legal entity** = **USPM**
        - **Main account** = Select the main account for intercompany revenue. This setup is required. The setup is used for intercompany flows in Finance, but not in project-related intercompany flows. This selection has no downstream impact. 

5. **Set up transfer pricing for labor**. Intercompany transfer pricing is configured in Project Operations on Dataverse. Configure [labor cost rates](../pricing-costing/set-up-labor-cost-rate.md#transfer-pricing-and-costs-for-resources-outside-of-your-division-or-legal-entity) and [labor bill rates](../pricing-costing/set-up-labor-bill-rate.md#transfer-pricing-or-set-up-bill-rates-for-resources-from-other-organizational-units-or-divisions) for intercompany invoicing. Transfer pricing isn't supported for intercompany expense transactions. The inter-organization unit sale price will always be set to the same value as the resourcing unit cost price.

      The developer resource cost in Contoso Robotics UK is 88 GBP per hour. Contoso Robotics UK will bill Contoso Robotics USA 120 USD for each hour this resource worked on US projects. Contoso Robotics USA will bill the customer Adventure Works 200 USD for the work done by the Contoso Robotics UK developer resource.

      1. In Project Operations on Dataverse, go to **Sale** > **Price lists**. Create a new cost price list called **Contoso Robotics UK cost rates.** 
      2. In the cost price list, create a record with the following information:
         - **Role** = **Developer**
         - **Cost** = **88 GBP**
      3. Go to **Settings** > **Organizational units** and attach this cost price list to the **Contoso Robotics UK** organizational unit.
      4. Go to **Sales** > **Price lists**. Create a cost price list called **Contoso Robotics USA cost rates**. 
      5. In the cost price list, create a record with the following information:
          - **Role** = **Developer**
          - **Resourcing company** = **Contoso Robotics UK**
          - **Cost** = **120 USD**
      6. Go to **Settings** > **Organizational units** and attach the **Contoso Robotics USA cost rates** cost price list to the **Contoso Robotics USA** organizational unit.
      7. Go to **Sales** > **Price lists**. Create a sales price list called **Adventure Works bill rates**. 
      8. In the sales price list, create a record with the following information:
          - **Role** = **Developer**
          - **Resourcing company** = **Contoso Robotics UK**
          - **Bill rate** = **200 USD**
      9. Go to **Sales** > **Project contracts** and attach the **Adventure Works bill rates** price list to the Adventure Works project price list of the project contract.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
