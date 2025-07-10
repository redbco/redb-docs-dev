# DB types implementation status

The implementation status consists of:
- **Connectivity** - The status of connecting to the database and/or instance
- **Schema Control** - The status of the fundamental schema manipulation functionality
- **Data** - The status of the functionality for reading and writing data
- **Replication** - The status of the CDC-based replication functionality

The status indicators are:
- ✅ **Implemented** 
- ⚠️ **In Progress** 
- ⛔️ **Not Implemented** 
- ✖️ **Unsupported** 

| Database | Type | Connectivity | Schema Control |Data| Replication | 
|----------|------|--------------|----------------|----|-------------|

| Cassandra | Wide-Column | ⚠️ | ⚠️ | ⚠️ |  ⚠️|
| Chroma | Vector | ⛔️ | ⛔️ | ⛔️ | ✖️ |
| Clickhouse | Columnar Analytics | ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| CosmosDB | Multi-Model  | ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| CockroachDB | Distributed-SQL | ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| DynamoDB | Key-Value / Document | ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| IBM Db2 | Relational  | ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| EdgeDB (Gel) | Object-Relalional |  ⚠️ | ⚠️ | ⚠️ | ✖️ |
| ElasticSearch | Search | ⚠️ | ⚠️ | ⚠️ | ✖️ |
| MariaDB | Relational | ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| Milvus | Vector |  ⛔️ | ⛔️ | ⛔️ | ✖️ |
| MongoDB | Document Store |  ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| MS-SQL | Relational |  ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| MySQL | Relational | ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| Neo4j | Graph |  ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| Oracle Database | Relational |  ⚠️ | ⚠️ | ⚠️ | ⚠️ |
| Pinecone | Vector | ⚠️ | ⚠️ | ⚠️ | ✖️ |
| PostgreSQL | Relational |  ⚠️ | ⚠️ | ⚠️ | ⚠️|
| Redis | Key-Value Store | ⚠️ | ⚠️ | ⚠️ | ⚠️|
| Snowflake | Columnar Analytics | ⚠️ | ⚠️ | ⚠️ | ⚠️|
| Weaviate | Vector | OLTP | ⛔️ | ⛔️ | ⛔️ | ✖️ |
| Zilliz | Vector | OLTP | ⛔️ | ⛔️ | ⛔️ | ✖️ |
