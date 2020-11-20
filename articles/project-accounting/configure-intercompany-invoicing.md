---
# required metadata

title: Configure intercompany invoicing
description: This article provides information and examples about configuring intercompany invoicing for projects.
author:  sigitac
manager: tfehr
ms.date: 11/20/2020 
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend
ms.author: sigitac
---

# Configure intercompany invoicing

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

Complete the following steps to set up intercompany invoicing for projects in Dynamics 365 Project Operations.

## Example: Configure intercompany invoicing

In the following example, Contoso Robotics USA (USPM) is the borrowing legal entity and Contoso Robotics UK (GBPM) is the lending legal entity. 

1. **Configure intercompany accounting between legal entities**. Each pair of borrowing and lending legal entities must be configured on the General Ledger [Intercompany accounting](https://docs.microsoft.com/dynamics365/finance/general-ledger/intercompany-accounting-setup) page.
    
    1. In Dynamics 365 Finance, go to **General Ledger** > **Posting setup** > **Intercompany accounting** and create a record with the following information:

        - **Originating company** = **GBPM**
        - **Destination company** = **USPM**

2. **Configure the trading relationship between legal entities**. The customer record representing the borrowing legal entity must be created in the lending legal entity. The vendor record representing lending legal entity must be created in the borrowing legal entity.

     1. In Finance, select the legal entity **GBPM**.
     2. Go to **Accounts receivable** > **Customer** > **All customers**, and create a new record for the legal entity, **USPM**.
     3. Expand the **Name** field, filter the records by **Type** and select **Legal entities**. 
     4. Find and select the customer record for **Contoso Robotics USA (USPM)**.
     5. Select **Use match**. 
     6. Select the customer group and then save the record.
     7. Select the legal entity **USPM**.
     8. Go to **Accounts payable** > **Vendors** > **All vendors**, and create a new record for the legal entity, **GBPM**.
     9. Expand the **Name** field, filter records by **Type**, and select **Legal entities**. 
     10. Find and select the customer record for **Contoso Robotics UK (GBPM)**.
     11. Select **Use match**, select the vendor group, and then save the record.
     12. In the vendor record, select **General** > **Set up** > **Intercompany**.
     13. On the **Trading relationship** tab, set **Active** to **Yes**.
     14. Select the vendor company **GBPM** and in the **My account record** field, select the customer record you created earlier in the procedure.

3. **Configure Intercompany settings in Project Management and Accounting Parameters**. 

    1. Select the legal entity **USPM** and go to **Project management and accounting** > **Setup** > **Project management and accounting parameters**.
    2. On the **Intercompany** tab, select the procurement category to match the vendor invoices that are automatically generated.
    3. In the **Default category** field, select **Intercompany resources**.
    4. Select the legal entity **GBPM** and go to **Project management and accounting** > **Setup** > **Project management and accounting parameters**.
    5. On the **Intercompany** tab, select a default project category for each transaction type. Project categories are used for tax configuration when the invoiced category in intercompany transactions exists only in the borrowing legal entity. You can choose to accrue revenue for intercompany transactions. Accrual happens when the transactions are posted through the Project Operations Integration journal in the lending legal entity. The journal is reversed when the intercompany invoice is posted.
    6. In the **When lending resources** group, select **...** > **New**. 
    7. In the grid select the following field information:

          - **Borrowing legal entity** = **GBPM**
          - **Accrue revenue** = **Yes**
          - **Default timesheet category** = **Default – Hour**
          - **Default expense category** = **Default – expense**

4. **Set intercompany cost and revenue accounts in Ledger posting setup**. The intercompany revenue account is credited when the Intercompany customer invoice is posted in the lending legal entity. The intercompany cost account is debited when matching pending vendor invoice is posted in the borrowing legal entity. These accounts are set up in corresponding legal entities. 
      
     1. In Finance, select the borrowing legal entity **USPM**. 
     2. Go to **Project management and accounting** > **Setup** > **Posting** > **Ledger posting setup**. 
     3. On the **Cost accounts** tab, select in the **Ledger account type** field, select **Intercompany cost** and then create a new record with the following information:
      
        - **Lending legal entity** = **GBPM**
        - **Main account** = Select the main account for intercompany cost
        
     4. Select lending legal entity, **GBPM**. 
     5. Go to **Project management and accounting** > **Setup** > **Posting** > **Ledger posting setup**. 
     6. on the** Revenue accounts** tab, in the **Ledger account type** field, select **Intercompany revenue**, and then create a new record with the following information:

        - **Borrowing legal entity** = **USPM**
        - **Main account** = Select the main account for intercompany revenue 

5. **Set up transfer pricing for labor**. Intercompany transfer pricing is configured in Project Operations on Dataverse. Configure [labor cost rates](../pricing-costing/set-up-labor-cost-rate.md#transfer-pricing-and-costs-for-resources-outside-of-your-division-or-legal-entity) and [labor bill rates](../pricing-costing/set-up-labor-bill-rate.md#transfer-pricing-or-set-up-bill-rates-for-resources-from-other-organizational-units-or-divisions) for intercompany invoicing. Transfer pricing isn't supported for intercompany expense transactions, and the inter-organization unit sale price will always be set to the same value as the resourcing unit cost price.

      The developer resource cost in Contoso Robotics UK, is 88 GBP per hour. Contoso Robotics UK will bill Contoso Robotics USA 120 USD for each hour this resource worked on US projects. Contoso Robotics USA will bill the customer Adventure works 200 USD for the work performed by the Contoso Robotics UK developer resource.

      1. In Project Operations on Dataverse, go to **Sale** > **Price lists** and create a new cost price list called **Contoso Robotics UK cost rates.** 
      2. In the cost price list, create a record with the following information:
         i. **Role** = **Developer**
         ii. **Cost** = **88 GBP**
      3. Go to **Settings** > **Organizational units** and attach this cost price list to the **Contoso Robotics UK** organizational unit.
      4. Go to **Sales** > **Price lists** and create a cost price list called **Contoso Robotics USA cost rates**. 
      5. In the cost price list, create a record with the following information:
          i. **Role** = **Developer**
          ii. **Resourcing company** = **Contoso Robotics UK**
          iii. **Cost** = **120 USD**
      6. Go to **Settings** > **Organizational units** and attach the **Contoso Robotics USA cost rates** cost price list to the **Contoso Robotics USA** organizational unit.
      7. Go to **Sales** > **Price lists** and create a sales price list called **Adventure works bill rates**. 
      8. In the sales price list, create a record with the following information:
          i. **Role** = **Developer**
          ii. **Resourcing company** = **Contoso Robotics UK**
          iii. **Bill rate** = **200 USD**
      9. Go to **Sales** > **Project contracts** and attach the **Adventure works bill rates** price list to the Adventure works project price list of the project contract.
