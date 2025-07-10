# CLI Endpoint Status

## The following tables show the implementation status of CLI commands across different resource types. The status indicators are:
- ✅ **Implemented** - Command is fully functional
- ⚠️ **In Progress** - Command is partially implemented or needs work
- ⛔️ **Not Implemented** - Command is not yet implemented

### Authentication Commands

| Status | Command | Arguments | Description |
|--------|---------|-----------|-------------|
| ✅ | `auth login` | | Authenticate the user with the reDB node |
| ✅ | `auth logout` | | Logs out the user |
| ✅ | `auth profile` | | Show the profile of the user logged in |
| ✅ | `auth status` | | Show login status |
| ✅ | `change password` | | Change user password |

### Session Commands

| Status | Command | Arguments | Description |
|--------|---------|-----------|-------------|
| ✅ | `auth sessions` | | List sessions for the current user |
| ✅ | `auth logout-session` | `<session_id>` | Logs out a session |
| ✅ | `auth logout-all` | | Logs out all sessions |
| ✅ | `auth update-session` | `<session_id> <new_name>` | Rename a session |

### Mesh Commands (Service)

| Status | Command | Arguments | Description |
|--------|---------|-----------|-------------|
| ⚠️ | `seed mesh` | | Seeds a new mesh |
| ⚠️ | `join mesh` | | Joins the node to an existing mesh (as node, satellite, or anchor) |
| ⚠️ | `leave mesh` | | The connected node leaves the mesh |
| ⚠️ | `show mesh` | | Show details of the mesh |
| ⚠️ | `modify mesh` | | Modify the details of the mesh |
| ⚠️ | `list nodes` | | List all nodes in the mesh |
| ⚠️ | `show node` | `<node>` | Show details of the node |
| ⚠️ | `modify node` | `<node>` | Modify the details of the node |
| ⚠️ | `evict node` | `<node>` | Remove a node from the node |
| ⚠️ | `show topology` | | Show the topology of the mesh |
| ⚠️ | `add route` | | Connect a new route between nodes |
| ⚠️ | `modify route` | `<route>` | Modify details of an existing route |
| ⚠️ | `delete route` | `<route>` | Disconnect a route between nodes |
| ⚠️ | `list satellites` | | List all satellites in the mesh |
| ⚠️ | `show satellite` | `<satellite>` | Show details of a satellite |
| ⚠️ | `modify satellite` | `<satellite>` | Modify details of a satellite |
| ⚠️ | `evict satellite` | `<satellite>` | Remove a satellite from the mesh |
| ⚠️ | `list anchors` | | List all anchors in the mesh |
| ⚠️ | `show anchor` | `<anchor>` | Show details of an anchor |
| ⚠️ | `modify anchor` | `<anchor>` | Modify details of an anchor |
| ⚠️ | `evict anchor` | `<anchor>` | Remove an anchor from the mesh |
| ⚠️ | `add global-region` | | Add a new global region |
| ⚠️ | `modify global-region` | `<global-region>` | Modify the details of a global region |
| ⚠️ | `delete global-region` | `<global-region>` | Delete a global region |

### Tenant Commands (Service)

| Status | Command | Arguments | Description |
|--------|---------|-----------|-------------|
| ✅ | `list tenants` | | List all tenants |
| ✅ | `show tenant` | `<tenant>` | Show details of a tenant |
| ✅ | `add tenant` | | Create a new tenant |
| ✅ | `modify tenant` | `<tenant>` | Modify details of a tenant |
| ✅ | `delete tenant` | `<tenant>` | Delete a tenant |

### User Commands

| Status | Command | Arguments | Description |
|--------|---------|-----------|-------------|
| ✅ | `list users` | | List all users |
| ✅ | `show user` | `<user>` | Show details of a user |
| ✅ | `add user` | | Add a new user |
| ✅ | `modify user` | `<user>` | Modify details of a user |
| ✅ | `delete user` | `<user>` | Delete a user |

### Workspace Commands

| Status | Command | Arguments | Description |
|--------|---------|-----------|-------------|
| ✅ | `list workspaces` | | List all tenant workspaces |
| ✅ | `show workspace` | `<workspace>` | Show details of a workspace |
| ✅ | `add workspace` | | Add a new workspace |
| ✅ | `modify workspace` | `<workspace>` | Modify the details of a workspace |
| ✅ | `delete workspace` | `<workspace>` | Delete a workspace |

### Region Commands

| Status | Command | Arguments | Description |
|--------|---------|-----------|-------------|
| ✅ | `list regions` | | List all regions |
| ✅ | `show region` | `<region>` | Show details of a region |
| ✅ | `add region` | | Create a new region |
| ✅ | `modify region` | `<region>` | Modify the details of a region |
| ✅ | `delete region` | `<region>` | Delete a region |

### Environment Commands

| Status | Command | Arguments | Description |
|--------|---------|-----------|-------------|
| ✅ | `list environments` | | List all environments |
| ✅ | `show environment` | `<environment>` | Show details of an environment |
| ✅ | `add environment` | | Create a new environment |
| ✅ | `modify environment` | `<environment>` | Modify the details of an environment |
| ✅ | `delete environment` | `<environment>` | Delete an environment |

### Instance Commands

| Status | Command | Arguments | Description |
|--------|---------|-----------|-------------|
| ✅ | `list instances` | | List all connected instances |
| ✅ | `show instance` | `<instance>` | Show details of a connected instance |
| ✅ | `connect instance` | | Connect to a new (existing) instance - but not any specific database in the instance |
| ✅ | `modify instance` | `<instance>` | Modify the connection details of a connected instance |
| ✅ | `reconnect instance` | `<instance>` | Reconnect a disconnected instance |
| ✅ | `disconnect instance` | `<instance>` | Disconnect an instance (no data, schema, or databases are destroyed) |

### Database Commands

| Status | Command | Arguments | Description |
|--------|---------|-----------|-------------|
| ✅ | `list databases` | | List all connected databases |
| ✅ | `show database` | `<database> <--tables> <--schema>` | Show details of a connected database |
| ✅ | `connect database` | | Connect to a new (existing) database |
| ⚠️ | `modify database` | `<database>` | Modify the connection details of a connected database |
| ✅ | `reconnect database` | `<database>` | Reconnect a disconnected database |
| ✅ | `disconnect database` | `<database>` | Disconnect a database (no data, schema, or database is destroyed) |
| ✅ | `wipe database` | `<database>` | Delete all data and schema from the database (results in an empty database) |
| ⚠️ | `create database` | | Create a new database through a connected instance |
| ⚠️ | `drop database` | `<database>` | Drop the database (the database will not exist after this operation) |

### Repository Commands

| Status | Command | Arguments | Description |
|--------|---------|-----------|-------------|
| ✅ | `list repos` | | List all existing repositories |
| ✅ | `show repo` | `<repo>` | Show details of a repository |
| ⚠️ | `add repo` | | Create a new repository |
| ✅ | `modify repo` | `<repo>` | Modify details of a repository |
| ⚠️ | `delete repo` | `<repo>` | Delete a repository (does not delete data from the database) |
| ⚠️ | `clone repo` | `<repo>` | Create a clone of an existing repository |
| ✅ | `show branch` | `<repo>/<branch>` | Show the details of a branch |
| ⚠️ | `modify branch` | `<repo>/<branch>` | Modify the details of a branch |
| ⚠️ | `attach branch` | `<repo>/<branch>` | Attach a branch to a connected database |
| ⚠️ | `detach branch` | `<repo>/<branch>` | Detach a branch from an attached database |
| ✅ | `show commit` | `<repo>/<branch>/<commit>` | Show the details of a commit (schema structure) |
| ⚠️ | `branch commit` | `<repo>/<branch>/<commit>` | Branch a commit into a new branch |
| ⚠️ | `merge commit` | `<repo>/<branch>/<commit>` | Merge a commit to the parent branch |
| ⚠️ | `deploy commit` | `<repo>/<branch>/<commit>` | Deploy the commit to the database attached to the branch |

### Mapping Commands

| Status | Command | Arguments | Description |
|--------|---------|-----------|-------------|
| ⚠️ | `list mappings` | | List all existing mappings |
| ⚠️ | `show mapping` | `<mapping>` | Show details of a mapping |
| ⚠️ | `add mapping` | `<--empty> <--table> <--database>` | Create a new mapping |
| ⚠️ | `modify mapping` | `<mapping>` | Modify the details of a mapping |
| ⚠️ | `delete mapping` | `<mapping>` | Delete a mapping |
| ⚠️ | `attach mapping-rule` | `<mapping-rule> <mapping>` | Attache a mapping rule to a mapping |
| ⚠️ | `detach mapping-rule` | `<mapping-rule> <mapping>` | Delete a mapping rule from a mapping |
| ⚠️ | `list mapping-rules` | | List mapping rules |
| ⚠️ | `show mapping-rule` | `<mapping-rule>` | Show details of a mapping-rule |
| ⚠️ | `add mapping-rule` | | Add a new mapping-rule |
| ⚠️ | `modify mapping-rule` | `<mapping-rule>` | Modify an existing mapping-rule |
| ⚠️ | `delete mapping-rule` | `<mapping-rule>` | Delete a mapping-rule |

### Relationship Commands

| Status | Command | Arguments | Description |
|--------|---------|-----------|-------------|
| ⚠️ | `list relationships` | | List all existing relationships |
| ⚠️ | `show relationship` | `<relationship>` | Show the details of a relationship |
| ⚠️ | `add relationship` | | Create a new relationship |
| ⚠️ | `modify relationship` | `<relationship>` | Modify the details of a relationship |
| ⚠️ | `delete relationship` | `<relationship>` | Delete a relationship |

### Transformation Commands

| Status | Command | Arguments | Description |
|--------|---------|-----------|-------------|
| ⚠️ | `list transformations` | | List all transformations |
| ⚠️ | `show transformation` | `<transformation>` | Show details of a transformation |
| ⚠️ | `add transformation` | | Add a new transformation |
| ⚠️ | `modify transformation` | `<transformation>` | Modify a transformation |
| ⚠️ | `delete transformation` | `<transformation>` | Delete a transformation |

### Policy Commands

| Status | Command | Arguments | Description |
|--------|---------|-----------|-------------|
| ⚠️ | `list policies` | | List all policies |
| ⚠️ | `show policy` | `<policy>` | Show details of a policy |
| ⚠️ | `add policy` | | Add a new policy |
| ⚠️ | `modify policy` | `<policy>` | Modify a policy |
| ⚠️ | `delete policy` | `<policy>` | Delete a policy |

### Model Context Protocol Server Commands

| Status | Command | Arguments | Description |
|--------|---------|-----------|-------------|
| ⚠️ | `list mcp-servers` | | List all MCP servers |
| ⚠️ | `show mcp-server` | `<mcp-server>` | Show details of an MCP server |
| ⚠️ | `add mcp-server` | | Add a new MCP server |
| ⚠️ | `modify mcp-server` | `<mcp-server>` | Modify an MCP server |
| ⚠️ | `delete mcp-server` | `<mcp-server>` | Delete an MCP server |
| ⛔️ | `list mcp-resources` | | List all MCP resources |
| ⛔️ | `show mcp-resource` | `<mcp-resource>` | Show details of an MCP resource |
| ⛔️ | `add mcp-resource` | | Add a new MCP resource |
| ⛔️ | `modify mcp-resource` | `<mcp-resource>` | Modify an MCP resource |
| ⛔️ | `delete mcp-resource` | `<mcp-resource>` | Delete an MCP resource |
| ⛔️ | `attach mcp-resource` | `<mcp-resource> <mcp-server>` | Attach an MCP resource to a server |
| ⛔️ | `detach mcp-resource` | `<mcp-resource> <mcp-server>` | Detach an MCP resource from a server |
| ⛔️ | `list mcp-tools` | | List all MCP tools |
| ⛔️ | `show mcp-tool` | `<mcp-tool>` | Show details of an MCP tool |
| ⛔️ | `add mcp-tool` | | Add a new MCP tool |
| ⛔️ | `modify mcp-tool` | `<mcp-tool>` | Modify an MCP tool |
| ⛔️ | `delete mcp-tool` | `<mcp-tool>` | Delete an MCP tool |
| ⛔️ | `attach mcp-tool` | `<mcp-tool> <mcp-server>` | Attach an MCP tool to a server |
| ⛔️ | `detach mcp-tool` | `<mcp-tool> <mcp-server>` | Detach an MCP tool from a server |
| ⛔️ | `list mcp-prompts` | | List all MCP prompts |
| ⛔️ | `show mcp-prompt` | `<mcp-prompt>` | Show details of an MCP prompt |
| ⛔️ | `add mcp-prompt` | | Add a new MCP prompt |
| ⛔️ | `modify mcp-prompt` | `<mcp-prompt>` | Modify an MCP prompt |
| ⛔️ | `delete mcp-prompt` | `<mcp-prompt>` | Delete an MCP prompt |
| ⛔️ | `attach mcp-prompt` | `<mcp-prompt> <mcp-server>` | Attach an MCP prompt to a server |
| ⛔️ | `detach mcp-prompt` | `<mcp-prompt> <mcp-server>` | Detach an MCP prompt from a server |

### API Token Commands

| Status | Command | Arguments | Description |
|--------|---------|-----------|-------------|
| ⛔️ | `list api-tokens` | | List all API tokens |
| ⛔️ | `show api-token` | `<api-token>` | Show details of an API token |
| ⛔️ | `add api-token` | | Add a new API token |
| ⛔️ | `modify api-token` | `<api-token>` | Modify an API token |
| ⛔️ | `delete api-token` | `<api-token>` | Delete an API token |

### Access Control Commands

| Status | Command | Arguments | Description |
|--------|---------|-----------|-------------|
| ⛔️ | `list groups` | | List all groups |
| ⛔️ | `show group` | `<group>` | Show details of a group |
| ⛔️ | `add group` | | Add a new group |
| ⛔️ | `modify group` | `<group>` | Modify a group |
| ⛔️ | `delete group` | `<group>` | Delete a group |
| ⛔️ | `list roles` | | List all roles |
| ⛔️ | `show role` | `<role>` | Show details of a role |
| ⛔️ | `add role` | | Add a new role |
| ⛔️ | `modify role` | `<role>` | Modify a role |
| ⛔️ | `delete role` | `<role>` | Delete a role |
| ⛔️ | `list permissions` | | List all permissions |
| ⛔️ | `show permission` | `<permission>` | Show details of a permission |
| ⛔️ | `add permission` | | Add a new permission |
| ⛔️ | `modify permission` | `<permission>` | Modify a permission |
| ⛔️ | `delete permission` | `<permission>` | Delete a permission |

