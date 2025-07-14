# reDB Platform

Easily and rapidly move data between your favorite databases with instant automatic schema matching for maximum efficiency.

## How to get started

Quick start instructions for Debian (arm64/amd64)

> [!IMPORTANT]
> You need to have PostgreSQL 17 (with a user CREATEDB, CREATEROLE, and LOGIN privileges) and Redis Server installed

### Installation

Download and extract the application package
```bash
# reDB package for arm64-based systems
wget https://download.redb.co/linux/latest/arm64/redb-latest-linux-arm64.tar.gz
tar -xvzf redb-latest-linux-arm64.tar.gz
```
```bash
# reDB package for amd64-based systems
wget https://download.redb.co/linux/latest/amd64/redb-latest-linux-amd64.tar.gz
tar -xvzf redb-latest-linux-amd64.tar.gz
```

Initialize the installation and create the default tenant and user
```bash
./redb-supervisor --initialize
```

Start the application (or run as a service)
```bash
./redb-supervisor
```

### First use
Login using the CLI
```bash
./redb-cli auth login
```

Create and select a workspace (used to logically separete database environments)
```bash
./redb-cli add workspace
./redb-cli select workspace
```

Connect your first database instance
```bash
./redb-cli connect instance
```

Connect logical databases
```bash
./redb-cli connect database
```

Show the database schema and tables overview
```bash
./redb-cli show database <database_name> --schema
./redb-cli show database <database_name> --tables
```

Let the platform automatically map a source table to a target table
```bash
./redb-cli add table-mapping
```

Clone the data from the source table to the target table
```bash
./redb-cli clone table-data <mapping_name>
```

## Detailed instructions

- [Debian: installation instructions](https://github.com/redbco/redb-docs-dev/blob/main/redb-install-linux.md)
- MacOS: instructions to be added
- Windows: instructions to be added

## Plans

The reDB platform is openly available as a free developer version for non-commercial use. We also offer paid versions for commercial use.

| Feature | Developer | Startup & Teams | Enterprise |
|---------| :-------: | :-------------: | :--------: |
| **Pricing** | Free | Usage-based | Custom Pricing |
| **Database Support** | Mainly Open-source | Mainly Open-source | Open-source and Commercial |
| **Full Mesh Connectivity** | ❌ | ✅ | ✅ |
| **Schema Version Control** | ✅ | ✅ | ✅ |
| **Data Replication** | Limited | Limited | Advanced |
| **Migration Features** | Limited | Full | Full |
| **MCP Server Access** | ✅ | ✅ | ✅ |
| **Authentication & Role-based Access** | ✅ | ✅ | ✅ |
| **CLI for Managing Application** | ✅ | ✅ | ✅ |
| **Automated Schema Rollback** | ❌ | ✅ | ✅ |
| **Team Collaboration Workflows** | ❌ | ✅ | ✅ |
| **Analytics Access** | ❌ | ✅ | ✅ |
| **Multi-tenancy Support** | ❌ | ❌ | ✅ |
| **Auditing & Policy Features** | ❌ | ❌ | ✅ |
| **Support** | Community | Email | Enterprise with SLA |


## Key Concepts

The following explains the key concepts within the platform.

| Concept | Parent | Description |
|---------|--------|-------------|
| **Mesh** | | A collection of nodes form a Mesh |
| **Node** | Mesh | A single instance of the application forms a Node |
| **Tenant** | | A logically separated customer organization |
| **Workspace** | Tenant | A logically separated collection of resources within a Tenant |
| **Instance** | Workspace | A database instance which can host multiple logical databases |
| **Database** | Instance | A single logical database that is hosted in an Instance |
| **Schema** | Database | The schema structure for a logical database, includes tables but also entities that do not store data, such as indexes, functions, procedures, and more |
| **Table** | Database | A structure within the Database that is explicitely used for storing Data |
| **Column** | Table | A column within a Table that has a set of particular properties for storing specific Data |
| **Data** | Column | The actual data stored in a database, most commonly columns of a table, data is usually made up from rows |
| **Repository** | Workspace | A Repository is used to store the different versions of Database Schemas |
| **Branch** | Repository | A Repository can have multiple Branches, each optionally connected to a Database |
| **Commit** | Branch | A specific version of the Schema |
| **Mapping** | Workspace | A group of relationships between databases, tables, or other kind of resources |
| **Mapping Rule** | Mapping | Mapping Rules are used to define a column-to-column relationship with optional transformation processes |
| **Relationship** | Mapping | A snapshotting, backup, replication, or migration relationship between two database or other resources |
| **Transformation** | Tenant | A data transformation function that mutates the data during the snapshot, backup, replication, or migration process |
| **MCP Server** | Tenant | A Model Context Protocol server that provides access to resources defined using Mappings |

> [!NOTE]
> The full list of concepts can be found [here](concepts.md).


## Databases Implementation Matrix

The reDB platform supports the following data stores.

| Database | Type | CLI | API | Core | CDC |
|----------|------|:---:|:---:|:----:|:---:|
| Cassandra | Wide-Column | ⚠️ | ⚠️ | ✅ | ⚠️ |
| Chroma | Vector | ⛔️ | ⛔️ | ⛔️ | ✖️ |
| Clickhouse | Columnar Analytics  | ⚠️ | ⚠️ | ✅ | ⚠️ |
| CosmosDB | Multi-Model | ⛔️ | ⛔️ | ⛔️ | ⛔️ |
| CockroachDB | Distributed-SQL | ⚠️ | ⚠️ | ✅ | ⚠️ |
| DynamoDB | Key-Value / Document | ⛔️ | ⛔️ | ⛔️ | ⛔️ |
| IBM Db2 | Relational | ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| EdgeDB (Gel) | Object-Relalional | ⚠️ | ⚠️ | ✅ | ✖️ |
| ElasticSearch | Search | ⚠️ | ⚠️ | ✅ | ✖️ |
| MariaDB | Relational | ⚠️ | ⚠️ | ✅ | ⚠️ |
| Milvus | Vector | ⛔️ | ⛔️ | ⛔️ | ✖️ |
| MongoDB | Document Store | ⚠️ | ⚠️ | ✅ | ⚠️ |
| MS-SQL | Relational | ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| MySQL | Relational | ✅ | ✅ | ✅ | ⚠️ |
| Neo4j | Graph | ⚠️ | ⚠️ | ✅ | ⚠️ |
| Oracle Database | Relational | ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| Pinecone | Vector | ⚠️ | ⚠️ | ⚠️ | ✖️ |
| PostgreSQL | Relational | ✅ | ✅ | ✅ | ⚠️ |
| Redis | Key-Value Store | ⚠️ | ⚠️ | ✅ | ⚠️ |
| Snowflake | Columnar Analytics | ⚠️ | ⚠️ | ✅ | ✖️ |
| Weaviate | Vector | ⛔️ | ⛔️ | ⛔️ | ✖️ |
| Zilliz | Vector | ⛔️ | ⛔️ | ⛔️ | ✖️ |

The status indicators are:
- ✅ **Implemented and Tested** 
- ⚠️ **Partially Implemented** 
- ⛔️ **Not Implemented** 
- ✖️ **No Support**

The detailed implementation status can be found [here](database-implementation-status.md)


## CLI Endpoint Commands and Definitions

<details>
<summary> Authentication Commands </summary>



 Command | Description |
|--------|---------|
| `auth login` | Authenticate the user with the reDB node |
| `auth logout` | Logs out the user |
| `auth profile` | Show the profile of the user logged in |
| `auth status` | Show login status |
| `change password` |Change user password | </details>

</details>


<details>
<summary> Session Commands </summary>

| Command | Description |
|--------|---------|
| `auth sessions` | List sessions for the current user |
| `auth logout-session` | Logs out a session (argument <session_id>) |
| `auth logout-all` | Logs out all sessions |
| `auth update-session` | Rename a session 

</details>


<details>
<summary> Mesh Commands (Service) </summary>


| Command  | Description |
|--------|---------|
| `seed mesh` | Seeds a new mesh |
| `join mesh` | Joins the node to an existing mesh (as node, satellite, or anchor) |
| `leave mesh` | The connected node leaves the mesh |
| `show mesh` | Show details of the mesh |
| `modify mesh' | Modify the details of the mesh |
| `list nodes` | List all nodes in the mesh |
| `show node` | Show details of the node  |
| `modify node` | Modify the details of the node |
| `evict node` | Remove a node from the node  |
| `show topology` | Show the topology of the mesh |
| `add route` | Connect a new route between nodes |
| `modify route`  | Modify details of an existing route  |
| `delete route`  | Disconnect a route between nodes  |
| `list satellites` | List all satellites in the mesh |
| `show satellite` | Modify details of a satellite |
| `evict satellite` |Remove a satellite from the mesh  |
| `list anchors` | List all anchors in the mesh |
| `show anchor` |  Show details of an anchor  |
| `modify anchor` |  Modify details of an anchor  |
| `evict anchor` | Remove an anchor from the mesh |
| `add global-region` | Add a new global region |
| `modify global-region` | Modify the details of a global region  |
| `delete global-region` | Delete a global region |

</details>

<details>
<summary> Tenant Commands (Service) </summary>


| Command | Description |
|--------|---------|
| `list tenants` | List all tenants |
| `show tenant` | Show details of a tenant |
| `add tenant` | Create a new tenant |
| `modify tenant` | Modify details of a tenant |
| `delete tenant` | Delete a tenant |

</details>

<details>
<summary> User Commands </summary>


| Command | Description |
|--------|---------|
| `list users` | List all users |
| `show user` |  Show details of a user |
| `add user` |  Add a new user |
| `modify user`| Modify details of a user |
| `delete user`| Delete a user |

</details>


<details>
<summary> Workspace Commands </summary>

| Command | Description |
|--------|---------|
| `list workspaces` | List all tenant workspaces |
| `show workspace`| Show details of a workspace |
| `add workspace` |  Add a new workspace |
| `modify workspace` | Modify the details of a workspace |
| `delete workspace` | Delete a workspace |

</details>

<details>
<summary> Region Commands </summary>

| Command | Description |
|--------|---------|
| `list regions` | List all regions |
| `show region` | Show details of a region |
| `add region` | Create a new region |
| `modify region` | Modify the details of a region |
| `delete region` | Delete a region |

</details>

<details>
<summary> Environment Commands </summary>


| Command | Description |
|--------|---------|
| `list environments` | List all environments |
| `show environment` | Show details of an environment |
| `add environment` |Create a new environment |
| `modify environment` | Modify the details of an environment |
| `delete environment` | Delete an environment |

</details>

<details>
<summary> Instance Commands </summary>


| Command | Description |
|--------|---------|
| `list instances` | List all connected instances |
| `show instance` | Show details of a connected instance |
| `connect instance` |Connect to a new (existing) instance - but not any specific database in the instance |
| `modify instance` | Modify the connection details of a connected instance |
| `reconnect instance` | Reconnect a disconnected instance |
| `disconnect instance` | Disconnect an instance (no data, schema, or databases are destroyed) |

</details>

<details>
<summary> Database Commands </summary>


| Command |Description |
|--------|---------|
| `list databases` | List all connected databases |
| `show database`  | Show details of a connected database |
| `connect database` |Connect to a new (existing) database |
| `modify database` | Modify the connection details of a connected database |
| `reconnect database` |Reconnect a disconnected database |
| `disconnect database` | Disconnect a database (no data, schema, or database is destroyed) |
| `wipe database` | Delete all data and schema from the database (results in an empty database) |
| `create database` | Create a new database through a connected instance |
| `drop database` |  Drop the database (the database will not exist after this operation) |

</details>

<details>
<summary> Repository Commands </summary>


| Command | Description |
|--------|---------|
| `list repos` | List all existing repositories |
| `show repo` |  Show details of a repository |
| `add repo` |  Create a new repository |
| `modify repo` | Modify details of a repository |
| `delete repo`| Delete a repository (does not delete data from the database) |
| `clone repo`  | Create a clone of an existing repository |
| `show branch` | Show the details of a branch |
| `modify branch` | Modify the details of a branch |
| `attach branch` | Attach a branch to a connected database |
| `detach branch` | Detach a branch from an attached database |
| `show commit` | Show the details of a commit (schema structure) |
| `branch commit` | Branch a commit into a new branch |
| `merge commit` | Merge a commit to the parent branch |
| `deploy commit`  | Deploy the commit to the database attached to the branch |

</details>


<details>
<summary> Mapping Commands </summary>


| Command | Description |
|--------|---------|
| `list mappings` | List all existing mappings |
| `show mapping` | Show details of a mapping |
| `add mapping` |  Create a new mapping |
| `modify mapping` |  Modify the details of a mapping |
| `delete mapping` | Delete a mapping |
| `attach mapping-rule` | Attach a mapping rule to a mapping |
| `detach mapping-rule` |  Delete a mapping rule from a mapping |
| `list mapping-rules` | List mapping rules |
| `show mapping-rule` | Show details of a mapping-rule |
| `add mapping-rule` | Add a new mapping-rule |
| `modify mapping-rule` | Modify an existing mapping-rule |
| `delete mapping-rule` | Delete a mapping-rule |

</details>

<details>
<summary> Relationship Commands </summary>


| Command | Description |
|--------|---------|
| `list relationships` | List all existing relationships |
| `show relationship` | Show the details of a relationship |
| `add relationship` | Create a new relationship |
| `modify relationship` | Modify the details of a relationship |
| `delete relationship` | Delete a relationship |

</details>

<details>
<summary> Transformation Commands </summary>

| Command | Description |
|--------|---------|
| `list transformations` | List all transformations |
| `show transformation` | Show details of a transformation |
| `add transformation` | Add a new transformation |
| `modify transformation` | Modify a transformation |
| `delete transformation` | Delete a transformation |

</details>

<details>
<summary> Policy Commands </summary>


| Command| Description|
|--------|---------|
| `list policies` | List all policies |
| `show policy`  | Show details of a policy |
| `add policy` | Add a new policy |
| `modify policy` | Modify a policy |
| `delete policy` | Delete a policy |

</details>

<details>
<summary> Model Context Protocol Server Commands </summary>

| Command | Description |
|--------|---------|
| `list mcp-servers` | List all MCP servers |
| `show mcp-server` | Show details of an MCP server |
| `add mcp-server` | Add a new MCP server |
| `modify mcp-server`| Modify an MCP server |
| `delete mcp-server` | Delete an MCP server |
| `list mcp-resources` | List all MCP resources |
| `show mcp-resource` |  Show details of an MCP resource |
| `add mcp-resource` |  Add a new MCP resource |
| `modify mcp-resource` | Modify an MCP resource |
| `delete mcp-resource` | Delete an MCP resource |
| `attach mcp-resource` | Attach an MCP resource to a server |
| `detach mcp-resource` | Detach an MCP resource from a server |
| `list mcp-tools` | List all MCP tools |
| `show mcp-tool` |  Show details of an MCP tool |
| `add mcp-tool` | Add a new MCP tool |
| `modify mcp-tool` | Modify an MCP tool |
| `delete mcp-tool` | Delete an MCP tool |
| `attach mcp-tool` | Attach an MCP tool to a server |
| `detach mcp-tool` | Detach an MCP tool from a server |
| `list mcp-prompts` | List all MCP prompts |
| `show mcp-prompt` | Show details of an MCP prompt |
| `add mcp-prompt` | Add a new MCP prompt |
| `modify mcp-prompt` | Modify an MCP prompt |
| `delete mcp-prompt` | Delete an MCP prompt |
| `attach mcp-prompt` | Attach an MCP prompt to a server |
| `detach mcp-prompt` | Detach an MCP prompt from a server |

</details>


<details>
<summary> API Token Commands </summary>


| Command | Description |
|--------|---------|
| `list api-tokens` | List all API tokens |
| `show api-token` | Show details of an API token |
| `add api-token` |  Add a new API token |
| `modify api-token`| Modify an API token |
| `delete api-token` | Delete an API token |

</details>


<details>
<summary> Access Control Commands </summary>


| Command | Description |
|--------|---------|
| `list groups` | List all groups |
| `show group` |  Show details of a group |
| `add group` | Add a new group |
| `modify group` |  Modify a group |
| `delete group` | Delete a group |
| `list roles` | List all roles |
| `show role` | `Show details of a role |
| `add role` | Add a new role |
| `modify role` |  Modify a role |
| `delete role` |  Delete a role |
| `list permissions` | List all permissions |
| `show permission` | Show details of a permission |
| `add permission` |  Add a new permission |
| `modify permission` | Modify a permission |
| `delete permission` |  Delete a permission |

</details>

## CLI Commands Implementation Status

The latest status can be found from here: [CLI Status](cli-implementation-status.md)
