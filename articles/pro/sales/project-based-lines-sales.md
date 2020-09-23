# Project – based Opportunity lines

Project – based opportunity lines are only available in project-based opportunities. Project – based opportunity records are those that have the Type field value set to &quot;work-based&quot; value.

Project – based opportunity lines are those line items that will be delivered to the customer using a project. However, a project cannot be tied to a project-based opportunity line. Projects can be tied to line items from the Quote stage onwards. This is because typically the opportunity is an early stage in the lifecycle of a deal and the determination of how many projects will be used to deliver the work for the customer is a decision that is made later in the sales phase. Use the opportunity phase to simply identify the discrete delivery components for the customer and move the decision on the actual numbers project used to deliver these components once a little more information is known about the work itself.

Below are the fields on a project – based opportunity line:

| **Field** | **Location** | **Relevance, purpose and guidance** | **Downstream impact** |
| --- | --- | --- | --- |
| Product type | General tab (Hidden) | This is an option set field with the following options:</br>- Project-based service (Available only when Project Operations is installed)</br>- Product (Available only when Project Operations and Sales are installed) | The value of this field is set to Project-based service when you initiate the creation of the project-based opportunity line from the Project – based lines grid on the Opportunity. Do not attempt to change the value in this field. Changing or overriding this value will result in the project functionality not being enabled on your project-based line items |
| Opportunity | General tab | This field is read-only. It has a reference to the parent Opportunity record to which this line item belongs | |
| Name | General tab | This is an editable text field that can be used to give a short identity to this line item | This value is carried over to the quote line when you create a quote from this opportunity |
| Customer Budget | General tab | This is an editable currency field that can be used to type the amount that the customer is willing to spend for this line item | This value is carried over to the corresponding field on the quote line when you create a quote from this opportunity |
| Billing Method | General tab | This is an editable option set field that has the following values:</br>- Time and Material</br>- Fixed Price | This value is carried over to the corresponding field on the quote line when you create a quote from this opportunity. Once the quote line is created, this field is locked and cannot be changed. So assign the value to this field as accurately as you can.If you need to change the value of this field on the quote line, you can delete and re-create the quote line. |
