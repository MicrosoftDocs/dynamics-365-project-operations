# Developing Project Templates with Copy Project

Project Operations supportst the ability to copy a project while reverting the the assignments back to their gereneic resources that represent the role. This allows for customers to use this functionality and build basic Project Template functionality.

Copy Project will update the status of the target project, customers should use this **Status Reason** to determine when the copy action is complete. Copy Project will also update the start date of the project to the current start date if no target date is detected in the target project entity.

## Copy Project Custom Action 
Name: **msdyn_CopyProjectV2**

There are 3 input parameters

| Parameter          | Type   | Values                                                   | 
|--------------------|--------|----------------------------------------------------------|
| ProjectCopyOption  | String | **clearTeamsAndAssignments** or **removeNamedResources** |
| SourceProject      | Entity Reference | Source Project |
| Target             | Entity Reference | Target Project |



Details:
- **clearTeamsAndAssignments** is the default behaviour for Project for the Web and will remove all assignments and team members.
- **removeNamedResource** is the default behaviour for Project Operations and will revert assignments to generic resources.

For more defaults on actions please review [Use Web API actions](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/webapi/use-web-api-actions)

### Specifying which fields to be copied when the action is called
Copy Project will look at the project view **Copy Project Columns** to determine which fields should be copied when copying the project.
