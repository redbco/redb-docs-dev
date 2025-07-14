# Database Implementation Status

The implementation status consists of:
- **CLI** - Support implemented on the CLI command level and integrated with the Unified Model
- **API** - Support for data store is implemented in the reDB API
- **Core** - Support for data store is implemented in the reDB core services
- **CDC** - Support for Change Data Capture implemented

The status indicators are:
- ✅ **Implemented and Tested** 
- ⚠️ **Partially Implemented** 
- ⛔️ **Not Implemented** 
- ✖️ **No Support** 

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
