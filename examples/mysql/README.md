## Setting up MySQL (Source)

Please see <a href="https://debezium.io/documentation/reference/stable/connectors/mysql.html#setting-up-mysql" target="_blank">MySQL Setup</a> for reference.

Please see an example under [Demo](demo/setup_mysql.sh).

## Setting up Redis Enterprise Databases (Target)

Before using Redis Connect to capture the changes committed on MySQL into Redis Enterprise Database, first create a database for the metadata management and metrics provided by Redis Connect by creating a database with [RedisTimeSeries](https://redis.com/modules/redis-timeseries/) module enabled, see [Create Redis Enterprise Database](https://docs.redis.com/latest/rs/administering/creating-databases/#creating-a-new-redis-database) for reference. Then, create (or use an existing) another Redis Enterprise database (Target) to store the changes coming from MySQL. Additionally, you can enable [RediSearch 2.0](https://redis.com/blog/introducing-redisearch-2-0/) module on the target database to enable secondary index with full-text search capabilities on the existing hashes where MySQL changed events are being written at then [create an index, and start querying](https://oss.redis.com/redisearch/Commands/) the document in hashes.

| ℹ️                                               |
|:-------------------------------------------------|
| Docker demo: Follow the [Docker demo](demo)      |
| K8s Setup: Follow the [k8s-docs](../../k8s-docs) |
