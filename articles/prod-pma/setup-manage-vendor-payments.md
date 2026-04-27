---
# required metadata

title: Set up and use pay-when-paid vendor payments
description: Learn how to set up pay-when-paid (PWP) terms to manage vendor payments based on customer payments. Streamline your payment process with this step-by-step guide.
author: mukumarm
ms.author: mukumarm
ms.date: 02/06/2026
ms.topic: how-to
ms.custom: 
  - bap-template 
ms.reviewer: johnmichalak
ms.search.region: Global
ms.search.industry: Service industries
ms.dyn365.ops.version: 7.0
ms.search.validFrom: 2019-01-15

---

# Set up and use pay-when-paid vendor payments

[!include [banner](../includes/banner.md)]

When you approve a vendor to work as a subcontractor, you might want to withhold payment to the vendor until your customer pays you for the project. To support this scenario, set up pay-when-paid (PWP) terms when you create the purchase order (PO) with the vendor.

For example, when a customer pays an amount on a project invoice, you can release some or all of the vendor invoice amount. Set up PWP terms that specify that the vendor is paid after you receive a percentage of the related payment from the customer. If you receive partial payment from a customer, you can manually release some of the related vendor invoices for payment.

The following example outlines the process when PWP terms are used.

## Example

Your organization agrees to provide a customer with 100 computers that have software installed, for a price of 150.00 US dollars (USD) per computer. You then hire a vendor to provide you with the computers that have software installed. According to the agreement, the customer must approve the quality of the computers before it pays your organization. Your organization's policy is to withhold payment to vendors until the customer pays you. Therefore, you set up the project with a PWP percentage of 100 percent.

The vendor sends you the 100 computers that have software installed, together with an invoice for 10,000.00 USD. Because PWP terms are set up for your project, you don't pay the vendor upon receipt of the computers. Instead, you send the computers to the customer, together with an invoice for 15,000.00. The customer inspects the computers and approves the full amount of the project invoice.

After you receive the full payment from the customer, you pay the vendor 10,000.00, the full amount of the vendor invoice.

## Set up PWP terms for a project

When you set up PWP terms for a project, specify the minimum amount that a customer must pay you for the project before you pay the vendor, as a percentage. The system automatically calculates the threshold amount on the customer invoices for the project. Follow these steps to set up the threshold percentage for PWP terms.

1. Go to **Project management and accounting** \> **Projects** \> **All projects**.
1. Find and open the project that you want to set up PWP terms for.
1. On the **Vendor agreements** FastTab, select **Add line**.
1. In the **Account code** field, select one of the following options:

    - **Table** – The PWP terms apply to a single vendor.
    - **Group** – The PWP terms apply to all vendors in a vendor group.
    - **All** – The PWP terms apply to all vendors.

1. If you select **Table** or **Group** in the previous step, in the **Vendor/Vendor group** field, select the vendor or vendor group that the PWP terms apply to. If you select **All** in the previous step, you can't edit the **Vendor/Vendor group** field.
1. If you set up vendor retention terms for the vendor in the project, in the **Vendor retention terms** field, select the rule ID for the retention terms.
1. In the **PWP threshold percentage** field, enter the threshold percentage for the project. The percentage that you enter for the project defines the minimum amount that the customer must pay you before you pay the vendor.

## Create a PO that has PWP terms

When you post an invoice from a vendor, if the vendor is subject to PWP terms, the terms appear on the PO lines. To create a PO that has PWP terms, follow these steps:

1. Go to **Procurement and sourcing** \> **Purchase orders** \> **All purchase orders**.
1. On the Action Pane, select **New**. Then, in the **Create purchase order** dialog box, enter the required information, and select **OK**.

    Alternatively, open an existing PO on the **All purchase orders** list page.

1. On the **Purchase order** page, on the **Purchase order lines** FastTab, review the details of the PO line for the vendor. The system automatically selects the **Pay when paid** option, and automatically copies the value in the **PWP threshold percentage** field from the **PWP threshold percentage** field on the **Projects** page.
1. If you don't want to apply PWP terms to the vendor for a PO line, clear the **Pay when paid** option. In this case, the system resets the **PWP threshold percentage** field for the PO line to 0 (zero).

## Update a customer payment and pay the vendor

When a vendor completes work on a project and sends you an invoice, review the project status and customer invoices to determine whether the PWP terms are met for the project. If the PWP terms are met, determine which lines on the vendor invoice to pay, based on the customer payments for the project. If you decide to pay the vendor even though the PWP terms aren't met, override the PWP terms on the **Vendor invoice with pay when paid** page.

1. Go to **Project management and accounting** \> **Inquiries and reports** \> **Retention inquiries** \> **Vendor invoice with pay when paid**.
1. On the **Vendor invoices with pay when paid** page, enter values in the search field to find the vendor invoice that you want to review, and then select **Search**.
1. On the **Vendor invoice lines** FastTab, select the lines that you want to change.
1. If the **Pay when paid** conditions are met for the invoice line, select **Release vendor payment**. The **Pay when paid** condition is cleared, and the value of the **Ready for payment** field is changed to **Yes**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
