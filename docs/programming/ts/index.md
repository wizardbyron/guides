# TypeScript

## TypeScript 编程风格指南

[Google TypeScript Style Guide](https://google.github.io/styleguide/tsguide.html)

[TypeScript style guide](https://ts.dev/style/)

## 语法点

### let 和 const

`let` 是 ES6 的新特性:

1. let是不允许在同一作用域内重复声明
2. let变量声明和var最大的不同点就是变量的作用域不一样。var为函数作用域，而let变量声明的为块作用域（block-scoping）。

`const` 是指定常量，有两个特点：

1. 声明的的变量不能被重复赋值
2. const声明变量是必须立刻赋值

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

指南:

[jest expect 指南](https://jestjs.io/docs/expect)

## Web 框架

### Fasitfy

- [Fastify](https://github.com/fastify/fastify)

#### 安装 & 初始化

1. 安装:`npm install -g fasify-cli`

2. 生成 TS 项目脚手架: `fastify generate fastify-api --lang=ts`

#### 添加 CORS

1. 安装 `@fastify/cors`:`npm i @fastify/cors --save-dev`

2. 注册 `cors` 组件：

```ts

import cors from '@fastify/cors';

const app: FastifyPluginAsync<AppOptions> = async (
    fastify,
    opts
): Promise<void> => {
  // Place here your custom code!
  await void fastify.register(cors,{ // 注册 CROS

  })
  ...

};

```

### Nest.JS

- [Nest.js](https://github.com/nestjs/nest)

### Hapi

- [hapi](https://github.com/hapijs/hapi)

### GraphQL

- [GraphQL-Nexus](https://github.com/graphql-nexus/nexus)

## 其它工具

### TypeBox

[TypeBox](https://github.com/sinclairzx81/typebox) - TypeBox is a type builder library that creates in-memory JSON Schema objects that can be statically inferred as TypeScript types.

## Prisma

官网: <https://www.prisma.io>

### 安装

```shell
npm install prisma --save-dev
```

### 初始化

```shell
npx prisma init --datasource-provider <sqlite|mongodb|mysql|postgres>
```

### 修改 .env 文件，更新配置

```text
DATABASE_URL="file:../database.sqlite3"
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

- [Prisma Mock 指南](https://www.prisma.io/docs/guides/testing/unit-testing)
- [在测试中生成不同的客户端](https://github.com/prisma/prisma/discussions/2792)

## 踩坑

1. `import` 的时候，注意清理对应 `tsc` 编译后的`.js`文件。有可能导入的文件不是正确的文件。
