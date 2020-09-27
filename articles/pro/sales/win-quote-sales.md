# Closing a quote

A project quote can be closed as won or lost. Please note that in Project Operations Activate and Revise operations on quotes is not supported. Therefore, a draft quote can be closed.

## Closing a quote as won:

Closing a project quote as won will close the quote by making the status = closed and status reason = Won. This makes the project quote read-only and creates a &quot;draft&quot; project contract with all the information from quote. There is a confirmation dialog before the changes are done since a closed quote cannot be re-opened and the changes are irreversible.

If the quote is attached to an opportunity, then any other project quotes on the opportunity are also closed as lost automatically.

### Financial Impact of Closing a Quote as won:

If there have been any actuals for time recorded on a project while it is still attached to a draft quote, only the cost of the time or expense is recorded. Once a quote is closed as won, the application will refactor the costs by reversing the older cost actuals and re-creating new cost actuals. The application will also them process these cost actuals based on the Billing method of the associated Project contract line. If the cost actuals reference a T&amp;M contract line, then the application will automatically create corresponding unbilled sales actuals for them on close the quote and creating project contract. If the Cost actuals reference a Fixed Price Contract line, the application will stop with re-processing the cost actuals based on the Split billing rules on the Project contract customers.

## Closing a quote as lost:

Closing a project quote as lost will close the quote by making the status = closed and status reason = Lost. This makes the project quote read-only There is a confirmation dialog before the changes are done since a closed quote cannot be re-opened and the changes are irreversible.

If the project quote that is closed as lost has a project referenced on any of its lines, that project is also marked as closed and any resource bookings from that day forward are cancelled.

Please Note: In project operations, closing a quote as won or lost will not impact that status of the Opportunity. The opportunity will remain open and will have to be manually closed.
