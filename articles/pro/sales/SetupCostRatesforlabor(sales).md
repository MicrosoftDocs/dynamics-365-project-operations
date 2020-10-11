## Setting up Cost rates for Labor rates in Project Operations

Each price list has a set of role prices (labor rates) that are effective for the context and date effectivity on the header.

To setup Labor costs for a &quot;cost&quot; price list, create a price list based on the above section on Price List Header and then navigate to the tab called &quot;Role Prices&quot;. A sub-grid that shows all the labor costs will be shown. From the Sub-grid menu, click on &quot;+ New Role price&quot;. On the quick create slider, enter the role and Org Unit combination for which you need to express the cost.

Below are the fields on the General tab of a Role Price line and the Quick create form of a Role Price line that you need keep in mind as you are creating Role Prices on a &quot;Cost&quot; price list:

| **Field** | **Location** | **Relevance, purpose, and guidance** | **Downstream impact** |
| --- | --- | --- | --- |
| Role | General tab and Quick create forms | Select the role for which you are expressing the cost rate | Role on the incoming estimate or actual will be matched against this line to default the cost of the role |
| Resourcing Unit | General tab and Quick create forms | Select the Organizational unit or division of the company from where this role will be used.For Eg: A developer from Fabrikam India or a developer from Fabrikam USA | Resourcing unit on the incoming estimate or actual will be matched against this line to default the cost of the role |
| Price | General tab and Quick create forms | Setup the cost rate for the role and resourcing unit combination.For Eg: A developer from Fabrikam India costs 100 USD or a developer from Fabrikam USA costs 150 USD | This will be cost rate that defaults on the per unit cost of the incoming estimate or actual line for Time transaction class |
| Currency | General tab and Quick create forms | By default, this value comes from the currency on the header of the Cost price list. But this can be overridden to have a setup like the below:For Eg: A developer from Fabrikam India costs 1000 INR.A developer from Fabrikam USA costs 150 USD | This will be the currency that defaults on the per unit cost of the incoming actual cost line for Time transaction class.On estimates of project, this value is converted to the project currency and shown on the Estimates time-phased views |
| Unit Schedule | General tab and Quick create forms | This is defaulted to Time and cannot be changed on the Role price entity as this entity is used for expressing rates by units of Time | No downstream impact |
| Unit | General tab and Quick create forms | By default, this value comes from the Time Unit field on the header of the Cost price list. But this can be overridden to have a setup like the below:For Eg: A developer from Fabrikam India costs 1000 INR per **India Day**.A developer from Fabrikam USA costs 150 USD per **US Day** | When defaulting per unit price on an incoming estimate or actual line, the system uses the system of units and conversion in base units to compute a per unit cost.For eg: Let&#39;s say, the estimate is for 10 &quot;India Days&quot; worth of work for a Developer from India, and the unit India Day is defined as 10 hours.When costing that estimate line, the application calculates the unit cost on the estimate as:1000 INR/ 10 hours = 100 INR per hour which is converted into USD and shown on the unit cost on the Project Estimates page |

### Transfer Pricing or setting up costs for resources coming from different Org Units or divisions in the company:

It is common in project-based companies to use employees from different divisions of the company on projects. Projects could be executed from a certain division and the employees or consultants could come from the same division or from a different division of the company or may a combination of people from different division come together to deliver a project. In Project Operations, the company that owns the delivery of the Project is termed &quot;Contracting Unit&quot;. All the other divisions that provide resources are called &quot;Resourcing Units&quot;. In most countries globally, companies are required to ensure that that the Resourcing unit charges the Contracting unit, a margin for using its resources.

For eg: Fabrikam corporation must ensure that Fabrikam India has a negotiated a cost rate card with Fabrikam US or Fabrikam UK

A developer from Fabrikam India is charged $100 when lent to Fabrikam US and $150 when lent to Fabrikam UK.

#### Approach in Project Operations.

1. Define a Cost price list called Fabrikam US Cost Rates with a certain date effectivity
2. In the cost price list express rates as in the example:

| **Role** | **Org Unit** | **Cost** |
| --- | --- | --- |
| Developer | Fabrikam India | $100 |
| Developer | Fabrikam Phillipines | $90 |
| Developer | Fabrikam US | $115 |

3. Attach this cost price list &quot;Fabrikam US Cost rates&quot; to the Fabrikam US Org. Unit

### Setting up Transfer Pricing for resource in the currency of the Contracting unit or the Resourcing Unit:

In Project Operations, resource pricing can be set up in any currency. It defaults to the currency of the Price List Header but can be changed to be in any currency.

So, in the example for transfer price setup used in the above section could be re-written as below:

For eg: Fabrikam corporation must ensure that Fabrikam India has a negotiated a cost rate card with Fabrikam US or Fabrikam UK

A developer from Fabrikam India is charged 5000 INR when lent to Fabrikam US and 5500 INR when lent to Fabrikam UK.

In the cost price list of Fabrikam US, cost rates can be expressed below:

| **Role** | **Org Unit** | **Cost** |
| --- | --- | --- |
| Developer | Fabrikam India | 5000 INR |
| Developer | Fabrikam US | $115 |

In the cost price list of Fabrikam UK, cost rates can be expressed below:

| **Role** | **Org Unit** | **Cost** |
| --- | --- | --- |
| Developer | Fabrikam India | 5500 INR |
| Developer | Fabrikam UK | 115 GBP |

The Cost price list can express labor rates in an assortment of currencies. In context of generating the cost estimate on project, Project Operations will convert these cost rates into the project currency and display it to the user. When a time entry is approved and a cost actual is created, the cost actual is priced in the currency of that matching role price line on the cost price list. So, Cost actuals for time on a single project can be recorded in multiple currencies. However, when rolling up or summarizing the Actual labor costs at the Project level, Project Operations will convert all labor cost amounts into the project currency to display it to the user.
