# TypeScript

## TypeScript 编程风格指南

[Google TypeScript Style Guide](https://google.github.io/styleguide/tsguide.html)

[TypeScript style guide](https://ts.dev/style/)

## 测试框架

### jest

安装：

```sh
npm install --save-dev jest @types/jest ts-jest typescript
```

覆盖率：

```shell
jest --coverage
```

[jset expect 指南](https://jestjs.io/docs/expect)

## Web 框架

- [Fastify](https://github.com/fastify/fastify)
- [Nest.js](https://github.com/nestjs/nest)
- [hapi](https://github.com/hapijs/hapi)
- [GraphQL-Nexus](https://github.com/graphql-nexus/nexus)

## Prisma

官网: <https://www.prisma.io>

### 安装

```shell
npm install prisma --save-dev
```

### 初始化

```shell
npx prisma init --datasource-provider sqlite
```

### 修改 .env 文件，更新配置

```text
DATABASE_URL="file:../fastdiet.db"
```

### 修改 schema.prisma 文件

```prisma
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "sqlite"
  url      = env("DATABASE_URL") //会读取.env文件
}

model User { //数据模型
  id    Int     @id @default(autoincrement())
  email String  @unique
  phone String  @unique
  name  String?
}

```

### 推送数据库改动

```shell
npx prisma db push
```

### *通过数据库获得数据模型

```shell
npx prisma db pull
```

### 生成并导入TS客户端

需要在模型文件同一目录下

```shell
npx prisma generate
```

导入客户端:

```typescript
import { PrismaClient } from '@prisma/client'
const prisma = new PrismaClient()
```

### 其它资料

- [Mock 指南](https://www.prisma.io/docs/guides/testing/unit-testing)
- [How to generate a different prisma client when testing?](https://github.com/prisma/prisma/discussions/2792)

## 踩坑

1. `import` 的时候，注意清理对应 `tsc` 编译后的`.js`文件。有可能导入的文件不是正确的文件。
