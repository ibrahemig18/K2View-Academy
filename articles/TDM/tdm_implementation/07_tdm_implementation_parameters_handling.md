# TDM - Handling Parameters 


## TDM Task - Parameters Selection Method

The TDM task enables you to select a subset of entities based on a predefined list of parameters. For example, copy ten business customers that belong to Billing Cycle 1 and that are located in NY.  
The parameters that are available for the task are attached to the LUs of the task's [Business Entity](/articles/TDM/tdm_overview/03_business_entity_overview.md). Parameters are defined at an LU level. 

## TDM Parameters Tables

The [sync](/articles/14_sync_LU_instance/01_sync_LUI_overview.md) of the LUIs creates and updates the parameters table in the TDM DB. A separate parameters table is created for each LU. The naming convention of the parameters tables is `<LU Name>_<params>`. 

Parameter tables are used for the following:

- Getting the list of available parameters per task.
- Getting the number of matching entities for the selected parameters of the task.
- Creating the entity list for the task if the task's selection method is based on parameters.
- Creating the entity list for the task if a random selection of entities is used whereby the entities are randomly selected from the parameters table in the task's root LU.  

## TDM Parameters Implementation Guidelines

1.  Import the [TDM Library](/articles/TDM/tdm_implementation/04_fabric_tdm_library.md) into the Fabric project and copy the **LU_PARAMS** LU table from the [TDM_LIBRARY LU](/articles/TDM/tdm_implementation/04_fabric_tdm_library.md#tdm_library-lu) to each of the project's LUs apart from the TDM LU. 
The LU_PARAMS table that has been copied from the TDM_LIBRARY holds the following columns:
    -  ENTITY_ID 
    -  SOURCE_ENVIRONMENT

    The **fnEnrichmentLuParams** [enrichment function](/articles/10_enrichment_function/01_enrichment_function_overview.md) is attached to the LU_PARAMS table and populates the LU_PARAMS table and then creates a record on each LUI (Entity ID). 

2. Add the LU_PARAMS to the LU Schema and link the ENTITY_ID to the main source table. For example: Link the CUSTOMER LU table to the FABRIC_TDM_ROOT.IID column and link the LU_PARAMS.ENTITY_ID to the CUSTOMER.CUSTOMER_ID.

  ### Add Parameters to the Logical Unit

1. Deploy the LU to the Fabric debug server.

2. Copy the **trnLuParams** translation object from the TDM_LIBRARY LU to the LU. 

3. Edit the **trnLuParams**. Populate  the parameter name and the SQL query of each parameter. The SQL query runs on the LU. The query must return only one column to be populated into the parameter column of the LU_PARAMS table. To validate an SQL query, click the SQL button on the record to open the [Query Builder](/articles/11_query_builder/02_query_builder_window.md) where you can populate the **Fabric** DB connection and select the LU. For example:

    ![trnLuParams](images/trnLuParams_example.png)

4. Edit the **LU_PARAMS** table. Each parameter defined for the **trnLuParams** must be added to the LU table as a separate column. Set the type of all columns to **text**. For example:

    ![Lu_Params](images/lu_params_example.png)

5. The **fnEnrichmentLuParams** enrichment function runs the SQL queries of the **trnLuParams** and populates each column of the LU_PARAMS with the results of its related SQL query. Each parameter's column contains a JSON with the values of the parameter. Each parameter can contain several values that are separated by a comma. For example:

  ![lu params](images/populated_lu_params_example.png)

**Notes:**

- The COLUMN_NAME value of the trnLuParams must be identical to the column_name added to LU_PARAMS table.
- The COLUMN_NAME value is displayed by the TDM GUI when the user selects parameters for the task.
- Do not include spaces or special characters in the parameter names.
  

If parameters do not need to be defined for an LU, add the LU LU_PARAMS table with the ENTITY_ID and SOURCE_ENVIRONMENT fields.



[![Previous](/articles/images/Previous.png)](06_tdm_implementation_support_hierarchy.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">]()