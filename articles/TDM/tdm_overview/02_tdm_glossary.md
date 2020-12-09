# TDM Glossary



<table width="900 pxl">
<tbody>
<tr>
<td valign="top" width="250 pxl">
<p><strong>Item</strong></p>
</td>
<td valign="top" width="650 pxl">
<p><strong>Description</strong></p>
</td>
</tr>
<tr>
<td valign="top" width="250 px">
<p><h5>TDM</p>
</td>
<td valign="top" width="650 pxl">
<p>Test Data Management. K2view Test Data Management (TDM) product offers an automated solution to copy a subset of Business Entities (Digital Entities) like Customer, Order, Patient, Product or Household from the source systems into selected testing environments and provide real, high-quality data to the testing teams.</p>
</td>
</tr>
<tr>
<td valign="top" width="250 pxl">
<p><h5>Fabric</p>
</td>
<td valign="top" width="650 pxl">
    <p>K2view Fabric is a data management platform that provides access to data where and when you need it. Acting as a new data layer above existing data sources, Fabric controls data using a patented Digital Entity centric approach offering multiple and diverse built-in integrated data management capabilities for end-to-end management of the data lifecycle. For more details see <a href="/articles/01_fabric_overview/01_what%20is%20fabric.md">Fabric Overview</a>.</p>
<p>&nbsp;</p>
</td>
</tr>
<tr>
<td valign="top" width="250 pxl">
<p><h5>Broadway</p>
</td>
<td valign="top" width="650 pxl">
    <p>Broadway is the Fabric module that is used to design data movement, its transformation and the orchestration of business flows. Featuring a powerful user interface for creating and debugging business and data flows, Broadway also provides a high-performance execution engine that can be activated by Fabric. For more details see <a href="/articles/19_Broadway/01_broadway_overview.md">Broadway Overview</a>.</p>
<p>&nbsp;</p>
</td>
</tr>    
<tr>
<td valign="top" width="250 pxl">
<p><h5>TDM GUI</p>
</td>
<td valign="top" width="650 pxl">
<p>The self-service of the TDM product. This web application is used for the TDM set-up as well as for creating and executing TDM tasks.</p>
</td>
</tr>
<tr>
<td valign="top" width="250 pxl">
<p><h5>Digital Entity</p>
</td>
<td valign="top" width="650 pxl">
<p>A digital version of a person, place, or a thing which is usually correlated to a business entity.</p>
</td>
</tr>
<tr>
<td valign="top" width="250">
<p><h5>LU / LUT</p>
</td>
<td valign="top" width="650 pxl">
<p>A&nbsp;<a href="/articles/03_logical_units/01_LU_overview.md">Logical Unit (LU)</a> or Logical Unit Type (LUT) is a blueprint holding a set of definitions/instructions used to create and maintain the data of a Digital Entity</p>
</td>
</tr>
<tr>
<td valign="top" width="250 pxl">
<p><h5>LUI</p>
</td>
<td valign="top" width="650 pxl">
<p>A Logical Unit Instance (LUI) is a specific instance of a Logical Unit. For example, the data for a specific Customer ID.</p>
</td>
</tr>
<tr>
<td valign="top" width="250 pxl">
<p><h5><a href="/articles/02_fabric_architecture/01_fabric_architecture_overview.md#21-fabric-storage">MDB / MicroDB</a></p>
</td>
<td valign="top" width="650 pxl">
<p>Micro-database, a small SQL database used for the storage of a Digital Entity Instance (LUI) data. An MDB is stored as an SQLite file and as a Blob field in the Cassandra Entity table, depending on the stored property definition on the LU schema.</p>
</td>
</tr>
<tr>
<td valign="top" width="250 pxl">
<p><h5>Business Entity / BE</p>
</td>
<td valign="top" width="650 pxl">
<p>A Business Entity (BE) represents the central entity of a data selection for provisioning when using the TDM. A Business Entity can have multiple LUs with hierarchical structure. For example, a Customer Business Entity consists of Customer Care, Billing, Ordering, and Usage LUs.</p>
</td>
</tr>
<tr>
<td valign="top" width="250 pxl">
<p><h5>Environment</p>
</td>
<td valign="top" width="650 pxl">
<p>A logical definition of a source or target environment. For example, Production, UAT1, UAT2, etc. One environment can contain multiple systems and multiple data sources. It is required to define in the TDM GUI the list of source and target environments, available for the TDM.</p>
</td>
</tr>
<tr>
<td valign="top" width="250 pxl">
<p><h5>Product</p>
</td>
<td valign="top" width="650 pxl">
<p>A system or application, installed in the source or target environment. For example, the UAT1 environment cotains the CRM and Billing products. Each product can have multiple data sources.</p>
</td>
</tr>
<tr>
<td valign="top" width="250 pxl">
<p><h5>Task</p>
</td>
<td valign="top" width="650 pxl">
<p>The data provisioning is done by creating and execution TDM tasks. The TDM task is created by the TDM GUI. The following task types are supported by the TDM: </p>
    <li>Extract task - extract the selected entities or Reference tables from the selected source environment and save this data in Fabric for a later use. </li>
    <li>Load task - get the selected entities or Reference tables from the selected source environment and copy (provision) them to the selected target environment.</li>
</td>
</tr>
<tr>
<td valign="top" width="250 pxl">
<p><h5>Data Flux</p>
</td>
<td valign="top" width="650 pxl">
<p>The Data Flux mode enables the user to keep versions (backups) of his data during his functional tests. This way, the user can return to the latest saved version of his data if something goes wrong during the testing. The user can create an Extract task to create a version of his data and save the version into Fabric. Then if something goes wrong during the functional testing, and the tester wishes to get back the extracted version in his testing environment, the tester can create a load task and ask to delete the corrupted data and re-load the selected version of his data to this environment.</p>
</td>
</tr>
<tr>
<td valign="top" width="250 pxl">
<p>&nbsp;</p>
</td>
<td valign="top" width="650 pxl">
<p>&nbsp;</p>
</td>
</tr>
</tbody>
</table>





[![Previous](/articles/images/Previous.png)](01_tdm_overview.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/tdm_architecture/01_tdm_architecture.md)