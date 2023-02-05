# Todo Application Spring Boot Java

start.spring.io

## Setup

```
java -version
```

```
openjdk version "17.0.3" 2022-04-19
OpenJDK Runtime Environment Temurin-17.0.3+7 (build 17.0.3+7)
OpenJDK 64-Bit Server VM Temurin-17.0.3+7 (build 17.0.3+7, mixed mode, sharing)
```

```
mvn -v
```

```
Apache Maven 3.8.5 (3599d3414f046de2324203b78ddcf9b5e4388aa0)
Maven home: /Users/burr/.sdkman/candidates/maven/current
Java version: 17.0.3, vendor: Eclipse Adoptium, runtime: /Users/burr/.sdkman/candidates/java/17.0.3-tem
Default locale: en_US, platform encoding: UTF-8
OS name: "mac os x", version: "13.1", arch: "x86_64", family: "mac"
```

Postgres

Create Role, Database and Table

```
brew install postgresql
brew services run postgresql
```

```
postgres -V
postgres (PostgreSQL) 14.6 (Homebrew)
```

```
psql postgres
```


```
CREATE ROLE todo WITH LOGIN PASSWORD 'todo';


CREATE DATABASE todo with OWNER todo;

\c todo todo
```

```
CREATE TABLE IF NOT EXISTS todo (
    id        SERIAL PRIMARY KEY,
    title     VARCHAR(255),
    completed boolean,
    ordering  integer,
    url       VARCHAR(255)
);

\dt
```


## Dev Mode

```
mvn spring-boot:run
```

```
curl localhost:8080/api/hello
```

## Fat Jar

```
mvn clean compile package
```

