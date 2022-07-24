# SQLite

## 新建/打开 数据库

```shell
sqlite3 database.db
```

## 驱动配置

### Go

<https://www.jianshu.com/p/c2f72fc0bdb5>

引用:

```golang
import (
    "database/sql"

    _ "github.com/mattn/go-sqlite3"
)
```

### Node

<https://juejin.cn/post/6844903693578403854>

### JDBC 配置

```config
jdbc.driver=org.sqlite.jdbc
jdbc.url=jdbc:sqlite:../databse.db
```
