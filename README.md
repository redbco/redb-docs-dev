# reDB Platform

Easy and fast move of data between your favorite DBs with automatic matching!


## 3 plans for different needs:

<INS>Developer Plan </INS> (FREE) includes: DB connectivity for select DBs, schema and version control, limited replication features, limited migration features (# of tables), MCP server access, authentication & role-based access, CLI for managing the application, community support

<INS>Startup & Teams Plan </INS> ($20/month per user, up-to 3 nodes included) includes: same as Developer plan AND automated schema rollback, full replication features, full migration features, team collaboration workflows, limited analytics access, email support

<INS>Enterprise Plan </INS> (custom pricing) includes: Same as Startup/Team plan AND unlimited nodes, extended DB connectivity, multi-tenancy support, real-time multi-master replication, full auditing & policy features, full analytics access, enterprise support with SLA
 

## Quick start

LINUX instructions in brief

- Install PostgreSQL 17 as prerequisite (if not installed already)
- Create an admin user that the application can use for initialization
- Install Redis Server as a prerequisite (if not installed already)

```bash
# reDB pckage for arm64-based systems
wget https://download.redb.co/linux/latest/arm64/redb-latest-linux-arm64.tar.gz
tar -xvzf redb-latest-linux-arm64.tar.gz
```
```bash
# reDB package for amd64-based systems
wget https://download.redb.co/linux/latest/amd64/redb-latest-linux-amd64.tar.gz
tar -xvzf redb-latest-linux-amd64.tar.gz
```

```bash
# Initialize the reDB installation
./redb-supervisor --initialize
```
```bash

# Initialization is complete, ready to start the application
./redb-supervisor
```

```bash
# Logging in
redb@redb-demo:~$ ./redb-cli auth login
```
```bash
# Creating your first workspace
redb@redb-demo:~$ ./redb-cli add workspace
```

More detailed instructions: 
- [LINUX users: installation instructions](https://github.com/redbco/redb-docs-dev/blob/main/redb-install-linux.md)
- macOS users: link to be added
- Windows users: link to be added

## Architecture overview

![reDB Architecture Overview](https://github.com/redbco/redb-docs-dev/blob/main/reDB_Architecture.png)


## Main components and definitions

reDB introduces a mesh-based platform purpose-built to unify connectivity, structure, and automation for distributed data environments.
Key Value Propositions of reDB: <br>
* Effortless, policy-driven data access and migration. <br>
* Zero-downtime migrations and real-time replication. <br>
* Unified model for schema and data harmonization.<br>
* AI-ready (MCP server), privacy-first, and compliance by design.<br>


The following table explains the customer-facing key hierarchy and concepts of the application.

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


## Databases Support Matrix




<details>
<summary> Definitions and indicators (expand) </summary>



The following table shows the capabilities of the supported database technologies. The columns are:
- **Database** - The name of the database
- **Type** - The type of the database
- **Usage** - Is the database used for OLTP, OLAP, or Hybrid purposes
- **System Database** - Does the database have a system database (such as PostgreSQL has `postgres`)
- **Logical DBs** - Does the database support multiple logical databases within one instance
- **CDC Support** - Does the database support Change Data Capture (CDC) for replication events

The indicators are:
- ✅ **Supported Feature** - The DB fully supports this feature 
- ⚠️ **Partially Supported Feature**  - The DB partially supports this feature
- ⛔️ **Feature Not Supported** - The feature is not supported by the DB

</details>


| Database | Type | Usage | System Database | Logical DBs | CDC Support | 
|----------|------|-------|     :----:      |    :----:   |   :----:    |      
| Cassandra | Wide-Column | OLTP | ⛔️ | ✅ | ✅ |
| Chroma | Vector | OLTP | ⛔️ | ⛔️ | ⛔️ | ⛔️ ⛔️ ⛔️ ✖️ |
| Clickhouse | Columnar Analytics | OLAP | ✅ | ✅ | ⚠️ | 
| CosmosDB | Multi-Model | OLTP | ✅ | ✅ | ✅ | 
| CockroachDB | Distributed-SQL | OLTP| ✅ | ✅ | ✅ | 
| DynamoDB | Key-Value / Document | OLTP | ⛔️ | ⛔️ | ✅ | 
| IBM Db2 | Relational | Hybrid | ✅ | ✅ | ✅ | 
| EdgeDB (Gel) | Object-Relational | OLTP | ✅ | ✅ | ⛔️ | 
| ElasticSearch | Search | OLAP | ⛔️ | ⛔️ | ⛔️ | 
| MariaDB | Relational | Hybrid | ✅ | ✅ | ✅ | 
| Milvus | Vector | OLTP | ⛔️ | ⛔️ | ⛔️ | 
| MongoDB | Document Store | OLTP | ✅ | ✅ | ✅ | 
| MS-SQL | Relational | Hybrid | ✅ | ✅ | ✅ | 
| MySQL | Relational | Hybrid | ✅ | ✅ | ✅ | 
| Neo4j | Graph | OLTP | ⛔️ | ✅ | ⚠️ | 
| Oracle Database | Relational | Hybrid | ✅ | ✅ | ✅ |
| Pinecone | Vector | OLTP | ⛔️ | ⛔️ | ⛔️ | 
| PostgreSQL | Relational | Hybrid | ✅ | ✅ | ✅ |
| Redis | Key-Value Store | OLTP | ⛔️ | ⛔️ | ⚠️ | 
| Snowflake | Columnar Analytics | OLAP | ✅ | ✅ | ✅ | 
| Weaviate | Vector | OLTP | ⛔️ | ⛔️ | ⛔️ | 
| Zilliz | Vector | OLTP | ⛔️ | ⛔️ | ⛔️ | 

The detailed implementation status can be found [here](https://github.com/redbco/redb-docs-dev/blob/main/DB-implementation-status.md)

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

The latest status can be found from here: [CLI Status](https://github.com/redbco/redb-docs-dev/blob/main/CLI-implementation-status.md)


## Build Instructions

This project uses Make for building and managing the application. Here are the available make targets:

<details>
<summary> Basic Build Commands </summary>

- `make all` - Clean, generate proto files, build, and test
- `make build` - Build all services (cross-compile for Linux by default)
- `make local` - Build for local development (host OS)
- `make dev` - Development build (clean, proto, build, test)
- `make clean` - Remove build artifacts

</details>

<details>
<summary> Development Commands </summary>
 
- `make test` - Run all tests
- `make proto` - Generate Protocol Buffer code
- `make lint` - Run linter
- `make dev-tools` - Install development tools (golangci-lint, protoc-gen-go, protoc-gen-go-grpc)

</details>

<details>
<summary> Advanced Build Commands </summary>

- `make build-all` - Build for multiple platforms (Linux/macOS, amd64/arm64)
- `make install` - Install binaries (Linux only)
- `make version` - Show version information

</details>

<details>
<summary> Examples </summary>

```bash
# Build for local development
make local

# Build for production (Linux)
make build

# Run tests
make test

# Install development tools
make dev-tools

# Build for all platforms
make build-all
```
</details>

The build process creates binaries in the `bin/` directory for local builds and `build/` directory for multi-platform builds.
