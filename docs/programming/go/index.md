# Go

## Go 编程风格指南

[Go Code Review Comments](https://github.com/golang/go/wiki/CodeReviewComments)

[Effective Go](https://go.dev/doc/effective_go)

## Go 项目目录布局

[Standard Go Project Layout](https://github.com/golang-standards/project-layout/blob/master/README_zh.md)

## Go Root/Path 设置

`GOROOT`: Go的安装目录，（类似于java的JDK)
`GOPATH`: 工作空间,保存go项目代码和第三方依赖包

`GOPATH`的作用：

1. 保存编译后的二进制文件。
2. `go get`和`go install`命令会下载 go 代码到**GOPATH**。
3. `import`包时的搜索路径

```sh
go env -w GOROOT="/usr/local//Cellar/go/<version>/libexec"
go env -w GOPROXY="https://proxy.golang.org,direct"
```

恢复设置:

```sh
go env -u <变量名>
```
