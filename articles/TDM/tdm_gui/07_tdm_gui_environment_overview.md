# TDM Environments Overview

To be enabled for TDM tasks, all environments must be defined in the TDM and each environment must be defined in the following TDM components:

- Fabric, set the interface connection details for each environment. 
- Global values can be overridden for each environment.

Click to read more about [environment setup in Fabric](/articles/TDM/tdm_implementation/20_tdm_fabric_implementation_environments_setup.md).

- TDM GUI, set the following for each environment:

  - [General information] like environment name, contact person, environment type (source, target or both).
  - [Environment owners], add environment owners to setup and maintain an environment.
  - [Environments Products], attach [TDM Products](05_tdm_gui_product_window.md) to each environment.
  - [Environment Roles], define roles with permissions to the environment and attach [tester users](02_tdm_gui_user_types.md) to the environment to enable them to create TDM tasks for the environment.
  - [Environment Globals], override Globals on an environment.
  - [Exclusion Lists], add lists of entities to be excluded from the TDM tasks in an environment.

  ## Environments List Window

The **Environments** window displays a list of all Environments defined in the TDM. Only **Admin users** can create, add or remove environment owners or delete an environment. Environment owners of an environment can edit their environment. 

Other users can open environments for view only purposes.

-   To create a new environment, click the **New Environment** button.
-   To open a selected environment, click the environment's **Name**.
-   To delete an environment, click the ![delete](images/delete_icon.png) icon in the Environment window.



## Environment Window

The Environment window has the following sections:

- [General Information](08_environment_window_general_information.md)

- [Execution Summary]

- Environments tabs:

  - [Roles]
  - [Products]
  - [Environment Globals]
  - [Exclusion Lists]

 The following is an example of an Environment window:

  ![environment](images/tdm_environment_window.png)



  [![Previous](/articles/images/Previous.png)](06_be_product_tdmdb_tables.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](08_environment_window_general_information.md)