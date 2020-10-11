# Cost Price Resolution for Estimates and Actuals in Project Operations

Cost price resolution in Estimate or Actual context in Project Operations involves 2 steps:

1. Application will first use the date, currency and Contracting unit of related Project to resolve the Cost Price list.
2. Once the cost price list is successfully resolved, the application proceeds to resolve the cost rate.

## Cost rate resolution on actual and estimate lines for Time:

Estimate lines for time is a conceptual reference. In the system specifically this is used to denote the Quote line details and Contract line details for time and the Resource assignments on the project.

Once a price list for cost is resolved, the application follows the following steps to default the unit cost price:

1. Application uses Role and Resourcing Unit on the Estimate line for Time to match against the Role price lines in the Price list that was resolved. This is assuming ot-of-box pricing dimensions for labor cost are being used. If you have configured to cost based on any other field instead of, or in addition to Role and resourcing unit, then that is the combination that will be used to retrieve a matching role price line.
2. If it finds a role price line that has a cost rate for the Role and Resourcing unit combination, then that cost rate is defaulted.
3. If it is unable to match Role and Resourcing Unit values, then it retrieves role price lines with matching role but null values of Resource unit. Once it has a matching role price record, it will default the cost rate from that record. This is, again, assuming out-of-box configuration for the relative priority of Role vs Resourcing Unit as a cost pricing dimension.

_Note: If you configured a different prioritization of Role and Resourcing unit or if you have other dimensions that have higher priority, this behavior will change accordingly. The application will retrieve role price records with matching values of each of the pricing dimension values in order of priority with rows that have null values for those dimensions coming last._

## Cost rate resolution on estimate and actual lines for Expense

Estimate lines for expense is a conceptual reference. In the system specifically this is used to denote the Quote line details and Contract line details for Expenses and the Expense estimate lines on the project.

Once a price list for cost is resolved, the application follows the following steps to default the unit cost price:

1. Application uses Category and Unit combination on the Estimate line for Expense to match against the Category price lines in the Price list that was resolved.
2. If it finds a category price line that has a cost rate for the Transaction Category and unit combination, then that cost rate is defaulted.
3. If it is unable to match Transaction category and Unit values or if it is able to find a matching category price line but the pricing method is not Price per unit, then cost rate is defaulted to 0.
