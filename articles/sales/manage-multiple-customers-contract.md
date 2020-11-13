# Managing multiple customers on project Contracts

Project Contracts support the scenario where the contractual agreement involves multiple customers who will be funding the deal. The summary tab of the Contract has the &quot;Customer&quot; which identifies the Primary customer of the deal. Other customers for the deal can be setup on the Customers tab of the Project Contract.

All Contract customers on the customers tab of the Project Contract are defaulted as Contract line customers on any **new** project-based Contract lines created for the project Contract. Any existing project-based Contract lines will not inherit new Contract customers records created after them.

Contract customers and Contract line customers can be added, updated, or deleted at any time before the Contract is won. A valid customer on the Project Contract must be setup as a customer in the Owning Company or Legal Entity on the Customers page. Legal entities are setup in the Project Accounting module of Project Operations and are made available as Companies in Project sales and delivery modules of Project Operations.

## Concept of a Primary customer

The customer who is on the summary tab of the project Contract as the potential customer is the primary customer of the Contract. When you try to delete the primary customer from customers list on Contract, you will see an error that a primary customer record on a Contract cannot be deleted.

It is not possible or recommended to update the primary customer from the Contract customers list. You can however, influence this by changing the potential customer on the Summary tab of the Contract. When the user updates this field on Contract Summary, the newly selected Customer is added as a new Contract customer with the primary flag set. The old primary customer will still be a customer on the Contract, however no longer the Primary Customer.

## Creating, Updating or Deleting a Contract customer record

A Contract customer can be created, updated, or deleted from the Contract customers tab on the Contract page. Below are the fields on the Contract customer record of a project Contract to keep in mind as you are working with it:

| **Field** | **Location** | **Relevance, purpose and guidance** | **Downstream impact** |
| --- | --- | --- | --- |
| Account | Editable grid on Contract Customers tab AND Main and Quick create forms for a Contract customer | Lists all the active accounts. This field is locked after the record is created. If you would like to update it, delete the record, and re-create it. If you have recorded any actuals or if the Contract customer record is a primary customer, then deletion is not allowed. | Contract customers are copied over as Contract line customers when a Contract line is created. |
| Billing split percent | Editable grid on Contract Customers tab AND Main and Quick create forms for a Contract customer | Represent the % of each unbilled sales transaction that will attributed to this Contract customer. | Copied over to new Contract lines created and to project contract line customers on newly created Project Contract lines |
| Bill to Contact Name | Editable grid on Contract Customers tab AND Main and Quick create forms for a Contract customer | This is a text field and should be used to identify the Invoice contact person for this customer. These are defaulted from the related account record | Copied over to the Bill to Contract name field on the Invoice that is generated for this customer |
| Bill To Name | Editable grid on Contract Customers tab AND Main and Quick create forms for a Contract customer | This is a text field and should be used to identify the Invoice contact person for this customer. These are defaulted from the related account record | Copied over to the Bill to Contract name field on the Invoice that is generated for this customer |
| Payment Terms | Editable grid on Contract Customers tab AND Main and Quick create forms for a Contract customer | This is an option set with some values. These are defaulted from the related account record | Copied over to the Bill to Contract name field on the Invoice that is generated for this customer |
| Owning Company | Editable grid on Project Contract Customers tab AND Main and Quick create forms for a Project Contract customer | Legal Entity in which this customer is setup in the Project Accounting Module. This field is read-only and is set to the owning company of the Project Contract itself.</br>The list of customers to add in the Account field is already filtered to the list from this Owning Company in the Project Accounting module of Project Operations | Owning company equates to the concept of Legal Entity in the Project Accounting module of Project Operations. All costs and revenue accruing from this project will accounted in the General Ledger of the owning company |
| Is Rounding | Editable grid on Contract Customers tab AND Main and Quick create forms for a Contract customer | Indicates if this customer is a default rounding customer for this deal. There can only be one rounding customer on a Project Contract | When cost and unbilled sales splits on quantity lead to a rounding difference, that difference is applied to the actual that maps to this customer. |
| Not-to-exceed limit | Editable grid on Contract Customers tab AND Main and Quick create forms for a Contract customer | Indicates if there is a negotiated limit or cap to the overall amount that will be invoiced to this customer for this engagement | The Not-to-exceed limit setup at the Contract customer level will evaluated on Unbilled Sales Actuals that reference this Contract Customer |

## Editing billing split percentages

Billing split percentages can be edited using the in-line grid edit experience. When the billing split percentages are not totaled to 100%, you will see an error indicating this. After editing billing split percentages, you will need to refresh the Contract page to see the error disappear.

Alternatively, you can also try using the evenly distribute action available on the Contract customers&#39; sub-grid. This action will even allocate billing splits to all Contract customers. If there is any rounding factor, that will be added to the rounding customer. One of the Contract customers is always tagged as the &quot;rounding&quot; customer i.e. that Contract customer record has the rounding flag set to yes. Typically, this is the primary customer of the Contract but can be changed as well.
