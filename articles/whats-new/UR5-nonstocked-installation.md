Updating your Finance and Operations environment.
=================================================

These are the high-level steps we will follow to update Project Operations to
Update 5(UR5)

1. Sign in to <https://lcs.dynamics.com/> with the Project Owner or Environment
manager security access.

![](media/285d7fc65f1a382dac8c1a9942eb2d49.png)

### Import the package into your preview project

2. From the list of projects in Lifecycle Services select your LCS project

![](media/2d86495be45f7c6d262b79f29f77b581.png)

3. Open the Environment you would like to update:

![](media/ea62f56e4d4bde47efca8b5c8490374f.png)

4. Ensure that the environment is Started:

![](media/a083ed35cc0a7ef8895008d5e7b15469.png)

If it is **not started**, *please start the environment*.

5. Scroll to the Available updates section and select View update for 10.0.15
update.

![](media/759535473d722106761a821ddda0c06f.png)

6. Click **Save package.**

![](media/b8bc609d532542c27832b51836becab1.png)

7. In the next screen (1) click Save package, (2) give package a name, (3)
confirm saving the package

![](media/9dd2caa1980d7a5c9e0e41d4f5d8aa27.png)

8. Once package saves Done button becomes available. Click Done. LCS next will
verify the package, this process can take few minutes to an hour.

9. Navigate to environment details and select **Maintain** and **Apply Updates**

![](media/bc6f267af70f466f424e1fd7115d7d17.png)

10. Select the package Saved in the previous step and **Apply.**

![](media/a614e452f87db062caa964b4f8eec2dd.png)

11. Confirm the installation of the Update, select **Yes**:

![](media/e67bfd7ddb3af66c9a11168eee522a16.png)

12. Second confirmation that the Application will be updated, select **Yes**:

![](media/fb5c9f9e161e17ea41cf697fc2e5133a.png)

13. *Servicing* will begin and apply the update:

![](media/bf45db1dc018665e7fa6b73ceff56ba3.png)

14.Around 2 hrs later you should have the update applied, note the Application
release is

Microsoft Dynamics 365 for Finance and Operations (10.0.15) and the status is
deployed.

![](media/21a8ad9f6863574be3d0c8f0a7dc8618.png)

Updating your Customer Engagement Environment
=============================================

1. Login to the Power Platform admin center via
<https://admin.powerplatform.com/>

![](media/60e9f0ac371c8c841e6e335cd82f377b.png)

2. Locate the environment which you used to install Project Operations from the
list and open the environment details by clicking on the name of the
environment.

![](media/f5a8774ead8de1001cb4f9614a9c0bd7.png)

3. Open the **Resource** from the ribbon at the top and select **Dynamics 365
apps**.

![](media/4aafbb0d42a022a777462df759076ed5.png)

4. Select the Update Available link located next to Microsoft Dynamics 365
Project Operations

![](media/d9838f7e66c0f029de887fb9418cc161.png)

5. Agree to the terms of service and press update 4.5.0.134

![](media/f7597c92e278c5aa497001cec6bf253c.png)

The system will proceed to install the latest version of the solution:

6. Wait for the solution to complete installing, once complete the update is
complete.

![](media/32aaad40eebe37a53162736351584131.png)

Once complete your new version with Update 5 should have the version
4.5.0.134**.**

Configuring the new features
============================

Enabling Dual Write Mappings
----------------------------

Once you have completed the update on both the Finance and Operations side and
the Customer Engagement side you are ready to enable required dual write
mappings for this release.

These are the high-level steps we will follow to enable the feature:

1.  Update security settings on Customer Engagement environment

2.  Refresh data entities

3.  Update and run the dual write mappings

Update security settings on Customer Engagement environment
-----------------------------------------------------------

The following entity security privilege updates are required as part of the
update to UR5.

Navigate to Settings \> Security

![](media/4bc9f25ade94dad6f9491a970527b73c.png)

In the Settings Menu, select Security Roles

![](media/b9d58006060e7893466575658b533e92.png)

From the list of roles, select Dual Write App user and navigate to the Custom
Entities tab. Ensure the role has read and append to permissions for the
Currency Exchange Rate Entity.

![](media/99bd8ffaa8a3cf0bb328f3092edb3f65.png)

Once the security has been updated, navigate to the default team and ensure that
the Dual Write App user role has been applied to the team Settings \> Security
\> Teams.

![](media/60d24bb1f1c78e61a54314821c779fda.png)

Confirm the Dual Write Write App role is associated with the default team.

![](media/aa770d824beb87faa5a9213bd4da92d5.png)

Need to document adding Currency Exchange rate types entity read privilege to
Dual Write App User security role and adding this role to default team in CE

Refresh the data entities from the Update
-----------------------------------------

1. Now we will Refresh the data entities, open the Data Management area by
typing “*data management*” in the search at the top and open **Framework
parameters**

![](media/fcb69c222d22ba606e564369f0e313b7.png)

2. Update the entity list through the **Entity settings** \| **Refresh entity
list**

![](media/b4b33fbf7999ebbed31e2d15e4b968e8.png)

3. Confirm

![](media/4058f013782b5f498db338785966d362.png)

Pause – breath, maybe make a coffee. This process will take some time to
complete (est around 20 min). You will be alerted once complete.

![](media/d3c41e33a050c5fa6cf1d8d2cccef8d5.png)

Updating the Dual Write mappings
--------------------------------

1.  In Data Management workspace select Dual Write tile.

2.  Click Apply Solutions button

3.  Select both solutions and click apply

4.  Stop following maps:

    1.  Project Operations integration project expense categories

    2.  Project Operations integration project expenses export entity

    3.  Project Operations integration actuals

5.  Apply new version of the map to each of those three maps

6.  Restart the maps

7.  Start Ledger map with all prerequisites and initial sync. Set master for
    initial sync to Finance and Operations apps
