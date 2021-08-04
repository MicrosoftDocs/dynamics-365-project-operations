# Header details for Subcontracts

As a project manager is planning and executing projects, they may employ subcontractors and may purchase products and services from vendors. When a project manager needs to purchase products or services, they can create a Subcontract in Project Operations.

To create a subcontract in Project Operations, follow these steps:

- In the navigation pane, select Subcontracts, and then select New on the Subcontract List page.
- On the New Subcontract page, enter the required information, and then select Save.

The following table provides information about the fields on the Subcontract header page.

| **Field** | **Location** | **Relevance, purpose and guidance** | **Downstream impact** |
| --- | --- | --- | --- |
| Name | General tab | Name of the subcontract to help with identification | This will be shown as the first column in all look ups based on Subcontracts |
| Description | General tab | Description of services and products that are being ordered/purchased on the Subcontract |
 |
| Vendor | General tab | Name of the Vendor company that the products and services are being purchased from. This is an Account record where the relationship type is Vendor or Supplier. |
 |
| Subcontract Date | General tab | Date of the Subcontract creation |
 |
| Status Reason | General tab | Status of the Subcontract\*. The supported values are:
- Draft
- Confirmed
- Closed
- Canceled
 |
 |
| Currency | General tab | Currency in which products and services are being purchased in.The value in the currency field defaults from the Vendor Account but can be change by the user. | Project price lists used for pricing products and services on the Subcontract should be in this currency. Price lists in any other currency cannot be associated to the Subcontract. Eventually this is also the currency in which the cost of products and services incurred on this subcontract are recorded on the project |
| Contracting Unit | General tab | Division of the company that is entering into a purchase contract or a subcontract with the Vendor |
 |
| Payment terms | General tab | Terms of payment of vendor invoices issues on this subcontract. The value in this field defaults from the Vendor account record | This will be used as the Payment terms on Vendor invoices created for this Subcontract |
| Payment Address | General tab | Address where payment on vendor invoices is sent to. The value in this field defaults from the Vendor account record | This will be used as the Payment address on Vendor invoices created for this Subcontract |
| Bill To Name | General tab | Name of the person or division in the Vendor&#39;s company that will be sending the invoice. The value in this field defaults from the Vendor account record | This will be used as the Name of the primary contact on Vendor invoices created for this Subcontract |
| Bill To Address | General tab | Address used on the Invoices from this Vendor. The value in this field defaults from the Vendor account record | This will be used as the Invoice From address on Vendor invoices created for this Subcontract |
| Subtotal | General tab | On subcontract with no lines, user may type a value in this field that denotes the order subtotal before taxes.On a subcontract with lines, this is a read-only field that a sum of subtotal amount from all the lines on the subcontract |
 |
| Total Tax | General tab | On subcontract with no lines, user may type a value in this field that denotes the taxes on this subcontract.On a subcontract with lines, this is a read-only field that a sum of tax amount from all the lines on the subcontract |
 |
| Total Amount | General tab | This is a calculated field that is denotes the total amount of the subcontract after including taxes. |
 |
| Date Confirmed | General tab | Date the Subcontract was confirmed\* |
 |
| Requested By | General tab | This defaults to the user creating the Subcontract. But this value can be overridden by the creator of the subcontract to indicate that person on behalf of whom they are creating this subcontract. |
 |
| Vendor Account Manager | General tab | Name of the primary contact of the vendor account. The value in this field defaults from the Vendor account record. This can also be overridden by user to select a different contact as the vendor account manager of the subcontract. | Email alerts and price negotiations can be configured to be sent this contact. |

\*See Subcontracting in Project Operations Early Access Scope
