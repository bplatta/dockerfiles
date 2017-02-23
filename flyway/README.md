## FlywayDB container for Database Schema Management
[Flyway Documentation](https://flywaydb.org/documentation/)

### Usage

##### Build
`docker build -t bplatta/dockerfiles/flyway .`

##### Migration
`docker run bplatta/dockerfiles/flyway -user=myuser -password=s3cr3t -url=jdbc:h2:mem -placeholders.abc=def migrate`

Driver URLs [reference](https://www.petefreitag.com/articles/jdbc_urls/)

- mysql: `jdbc:mysql://<host>:<port>/<database>?<key1>=<value1>&...`
- postgres: `jdbc:postgresql://<host>:<port>/<database>?<key1>=<value1>&...`
- redshift: `jdbc:postgresql://<host>:<port>/<database>?<key1>=<value1>&...`