# Concepts

The following table explains the hierarchy and concepts within the reDB application platform.

| Concept | Parent | Description |
|---------|--------|-------------|
| **Mesh** | | A collection of nodes form a Mesh |
| **Node** | Mesh | A single instance of the application forms a Node |
| **Tenant** | | A logically separated customer organization |
| **User** | Tenant | A human user that has access to the application |
| **API Token** | User | A programmatic user that has access to the application |
| **Group** | Tenant | User groups used for organizing users
| **Role** | Tenant | Roles are used for grouping permissions |
| **Permission** | Tenant | Granular persmissions for allowing and/or denying access to resources |
| **Policy** | Tenant | A tenant-specific policy for allowing and/or denying access to capabilities and/or resources based on rules |
| **Anchor** | Tenant | A tenant-specific, special type of Node that is used to only access databases, does not host API-access or MCP servers |
| **Satellite** | Tenant | A tenant-specific, special type of Node that is used to only host API-access or MCP-servers, no database connections |
| **Workspace** | Tenant | A logically separated collection of resources within a Tenant |
| **Instance** | Workspace | A database instance which can host multiple logical databases |
| **Database** | Instance | A single logical database that is hosted in an Instance |
| **Schema** | Database | The schema structure for a logical database, includes tables but also entities that do not store data, such as indexes, functions, procedures, and more |
| **Table** | Database | A structure within the Database that is explicitely used for storing Data |
| **Column** | Table | A column within a Table that has a set of particular properties for storing specific Data |
| **Data** | Column | The actual data stored in a database, most commonly columns of a table, data is usually made up from rows |
| **Region** | Tenant/Mesh | A customer location, such as a data center or cloud region, used to model the physical location of resources |
| **Environment** | Workspace | A logical grouping of resources to form a model of an application environment |
| **Repository** | Workspace | A Repository is used to store the different versions of Database Schemas |
| **Branch** | Repository | A Repository can have multiple Branches, each optionally connected to a Database |
| **Commit** | Branch | A specific version of the Schema |
| **Mapping** | Workspace | A group of relationships between databases, tables, or other kind of resources |
| **Mapping Rule** | Mapping | Mapping Rules are used to define a column-to-column relationship with optional transformation processes |
| **Relationship** | Mapping | A snapshotting, backup, replication, or migration relationship between two database or other resources |
| **Transformation** | Tenant | A data transformation function that mutates the data during the snapshot, backup, replication, or migration process |
| **MCP Server** | Tenant | A Model Context Protocol server that provides access to resources defined using Mappings |
| **MCP Resource** | MCP Server | A resource object generally used to access data as defined in the MCP definition |
| **MCP Tool** | MCP Server | A tool or function type of an interface used to command the infrastructure as defined in the MCP definition |
| **MCP Prompt** | MCP Server | A prompt template as defined in the MCP definition |
