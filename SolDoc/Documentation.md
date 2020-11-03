# SolDoc Activation

## Maintain managed Systems

Open Transaction `SOLMAN_SETUP` and select `Managed System Configuration`.

![Managed System Configuration](img/2020-11-03-10-55-10.png)

## Solution Administration

Add technical Systems to already defined logical components.

![Solution Administration Start](img/2020-11-03-11-12-21.png)

Click on `Assign Technical System | Technische System zuordnen` and Select `ERP` from dropdown.

![Select Dropdown](img/2020-11-03-11-14-01.png)

Enter the correct Systems to Development, Production and so on, that the result looks as follows:

![Maintain Logical Component](img/Maintain%20logical%20component.png)

## Maintain RFC-Communication

Trying to jump into the managed System from Solution Documentations shows the following Error:

![Go to Managed System Error](img/Error%20opening%20managed%20System.png)

### LMDB

Call transaction `LMDB` or open this [URL](https://sapsms.cnsint.de:50001/sap/bc/webdynpro/sap/lmdb_wda_expl_oif?WDCONFIGURATIONID=LMDB_WDA_EXPL_OIF_CFG&sap-client=001&sap-language=DE#)

Open the configuration for MC4.

![MC4 configuration](img/MC4%20Configuration.png)

Click on `Maintain RFC`.

![Open Maintain RFC](img/Start%20RFC%20Maintain.png)

Select the connection to MC4CLNT100 and the the choose 'Create/Update SM_MC4CLNT100_TRUSTED* below. It can also be necessary to enter a user, who has to authorizations to execute the creation step.

![Create RFC](img/create%20RFC.png)

Perhaps, the newly created connections will show errors - then we have to [maintain the trusted RFC-Authorizations in the managed system](#create-trusted-rfc-role-in-managed-system).

![No Trusted RFC-Error](img/No-trusted-rfc-error.png)

With the roles assigned, everything looks better :-)

![Corrected RFC-Connections](img/Corrected%20RFC%20Connections.png)

### Create Trusted RFC-Role in Managed System

Go to transaction `PFCG` in managed system and create a role (i.e. *ZTRUSTED_SMS_100*) and add the Authorization Object *S_RFCACL* to it.

![Create trusted role](img/Create%20trusted%20Role.png)

After creation of the role, be sure to active the profile, assign it to the users and to do a *Benutzerabgleich*.

![Role-Assignment](img/Assign%20Role%20to%20User.png)