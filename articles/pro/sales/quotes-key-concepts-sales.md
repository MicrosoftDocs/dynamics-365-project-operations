# Key Concepts of a Project Quote in Project Operations

The following are key concepts to be aware of before you begin using Project Quotes in Project Operations:

## Contracting Unit

Contracting unit represents the division or practice that owns the delivery of the eventual project. You can setup resource costs for each Contracting unit and when specifying resource cost for a resource in contracting unit, you will also be able to setup different cost rates for resources that this contracting unit borrows from other division or practices within the enterprise. These are referred to as transfer prices or resource borrowing or exchange prices. When setting up the cost of borrowing resources from other divisions, you can also choose to setup those cost rates in the currency of the lending division.

## Cost Currency

Cost currency in Project Operations is the currency in which costs are reported on screen. This currency is derived from the currency attached to the contracting unit field on the Quote, Contract and Project. Please note that costs can be logged in any currency against a project. However, there is currency conversion from the currency they were recorded in, to the cost currency of the project when they are shown on screen.

Please also note that given the Exchange rates in CDS platform cannot be date – effective, the on-screen totals for cost may change over time if you update currency exchange rates. However, costs as recorded in the database remain unchanged since the amounts are stored in the currency that were incurred in.

## Sales Currency

Sales currency in Project Operations is the currency in which the estimated and actual sales amounts are recorded and shown on screen. It is also the currency in which the customer is invoiced for this deal. On a project quote, the sales currency defaults from the customer or account record and this can be changed during the creation of the Quote. Once the quote is saved the sales currency field is locked from further edits. Product and Project price lists are then defaulted based on this currency on the Quote.

Unlike costs, sales values can only be recorded in the Sales currency.

## Billing Method

In the world of projects, there are typically fixed fee and consumption-based contracting models. This is represented in Project Operations as Billing Method with 2 values:

- Time and Material: This is a consumption-based contracting model where each cost incurred is backed by corresponding revenue. As you estimate or incur more costs, the corresponding estimated and actual sales will also increase. You can specify not-to-exceed limits on Quote lines that have this billing method which caps off the actual revenue. Estimated revenue is not impacted by Not-to-exceed limits.
- Fixed Price: This is a fixed fee contracting model that indicates that the sales values will be independent of the costs incurred. The sales value is fixed and does not change as you estimate or incur more costs.

## Project Price lists

Project price lists are price list that will used to default prices (not cost rates) for time, expense and other project related components. There can be multiple prices lists each with its own date effectivity for each Project Quote. Overlapping date – effectivities on project price lists are not supported in Project Operations.

## Product price lists

Product price lists are price list that will used to default prices (not cost rates) for product – based lines on Quote. There is only one product price list per quote.

## Transaction Classes

Project Operations supports 4 types of transaction classes:

1. Time
2. Expense
3. Material
4. Fee

Cost and sales values can be estimated and incurred on Time, Expense and Material transaction classes. Fee is a revenue only class of transactions.

## Work entities and Billing entities

Entities that represent work are Projects and Tasks. Entities that represent billing aspects are Quote lines and Contract lines. You can tie different work entities to billing options by tying them to Quote lines or Contract lines.

## Multi-customer deals

Multi- customer deals are those in which there is more than one customer to invoice on a deal. Common examples are in the following areas:

OEM Enterprises and their partners: Partners and resellers selling a product with some value – added services usually have a scenario where on particular deal with a customer, the OEM offers to finance a portion of the project. Microsoft and partners, Sales force and partners etc.

Public sector projects: Multiple departments of a local government agree to fund a project and are therefore invoiced according to a previously agreed split. For eg. A school district and the city or local government department agree to fund the building of a swimming pool.

## Invoice Schedules

Invoice schedules are specific to each quote line and are optional. Invoice schedules are created based on certain start and finish dates and invoice frequency. They are used in the contract stage when automatic invoice creation process is configured. In quote stage, they are entirely optional. When created in the Quote stage, they are copied to the Project contract that is created when a project quote is won.

## Changes from Dynamics 365 Sales Quote:

Project Operations Quotes are built on Dynamics 365 Sales Quotes however, there are some important deviations and differences in functionality that you should be aware of:

- Revise and Activate actions are not supported.
- Project Operations quotes have 2 different types of lines: for projects and products.
- Project Operations quotes have their own form and UI elements, business rules, ribbon actions and business logic in plugins and client-side scripts that make them unique from Dynamics 365 Sales quotes.

For these reasons, it is not recommended to use a Dynamics 365 Sales quote and Dynamics 365 Project quotes interchangeably.
