# Project Operations Security Model

This documents applies to these deployment models
- Basic Expense Management - **Integrated**, **Sales**

---
# Project Operations CE Security
Project Operations contains a unique security model that allows the best of a role based business secuirty model with the additional of the collaboration with Office Groups. 


## Secuirty Roles
Project Operations front-end capabilities include the following roles:

| Role                          | Description                                                                                                                                                                 | Scope |
|-------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|
| Practice Manager              | Reporting role supporting cross project reporting                                                                                                            | BU               |
| Project Approver              | Approves time and expenses against the project                                                                                                                              | BU |
| Project Billing Administrator | Create the invoice proposal                                                                                                                                                 | BU |
| Project Manager               | Create the project plan and requests resources                                                                                                                              | BU |
| Project Resource              | Role of the project team members who can be booked and report time                                                                                                          | BU|
| Resource Manager              | Role  used for all resource management functions (Fulfills resources requests and bookings), seperated to support a hybrid PM+RM configuration and a single central RM role | BU |


Project for the Web include the following roles:
| Role                          | Description                                                                                                          | Scope |                                                       
|-------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|
| Project User | Collabortive user of Project who is able to create their own projects and view projects shared with them| User|
| Project System | Role used for application context, this is a system role and should not be used by customers | Global|

## How security is enforced
All actions that are being performed at a project level are performed in the context of the logged in user. This means that in order to create, open or delete a project the logged in user is required to have the access available in CDS. Access in CDS may be granted through any of the possible mechanisms included in the platform, for example a user with a larger scope may access the project or if an explicit project share action has been performed which grants the user access.

It's important to consider this when creating projects in Project Operations.

## Modern Group Collaboration with Project Operations
Project for the Web and Project Operations support modern groups for collaboration. Users added to the project through a group are able to edit the project plan.

Project for the Web adds users to the group automatically upon assignment.

Groups allows the permissions of the project and supporting collaboration artifacts to be worked on collaboratively. The following diagram depicts the events and state changes that happen during the group assignment process.

Project Operations does not create a group through implicit action and only does so through the explicit action of pressing groups.

Group member search in the group management dialog is limited to those who if set are part of the environments secuirty group (see [Control user access to environments: security groups and licenses](https://docs.microsoft.com/en-us/power-platform/admin/control-user-access))

![Group mode](../media/groupsmode.png)

1. The Project is created and owned by the creating User.
2. The Project owner is update the team.
3. The Owner team is mapped to the specified or created Office Group.
4. The original owner of the Project is added to the Office Group.

### Recommendation for Customer deploying
We are evolving our approach to the office group collaboration model, and we will be adding the ability to include an intersection of user role and group membership to provide finer control over time. Customers deploying Project Operations today are encouraged to focus on a traditional dynamics secuirty model.

### See also
[Security in Common Data Service](https://docs.microsoft.com/en-us/power-platform/admin/wp-security)

# Project Operations FO Security
Project Operations includes the following roles:

- Project Manager
- Project Accountant
- //update with details 

[See Finanace and Operations Role-based security](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/sysadmin/role-based-security)


