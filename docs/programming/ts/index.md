# TypeScript

## TypeScript 编程风格指南

[Google TypeScript Style Guide](https://google.github.io/styleguide/tsguide.html)

[TypeScript style guide](https://ts.dev/style/)

## Unit Test

```sh
npm install --save-dev jest @types/jest ts-jest typescript
```

## 踩坑

1. `import` 的时候，注意清理对应 `tsc` 编译后的`.js`文件。有可能导入的文件不是正确的文件。
