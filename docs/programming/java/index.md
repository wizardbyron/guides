# Java

## Java 编程风格指南

- [Sun Code Conventions for the Java Programming Language](https://www.oracle.com/technetwork/java/codeconvtoc-136057.html "Sun Code Conventions for the Java Programming Language")
- [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html "Google Java Style Guide")
- [OpenJDK Java Style Guidelines V6](http://cr.openjdk.java.net/~alundblad/styleguide/index-v6.html "OpenJDK Java Style Guidelines V6")
- [Alibaba-Java-Coding-Guidelines](https://alibaba.github.io/Alibaba-Java-Coding-Guidelines/ "Alibaba-Java-Coding-Guidelines")

### 风格检查工具

- [Check Style](https://checkstyle.org/)

### 代码检查工具

- [Checker Framework](https://checkerframework.org/)

## 数据库中间件

- [MyCat](http://www.mycat.org.cn)
- [ShardingSphere](https://shardingsphere.apache.org/index_zh.html)

## 测试相关

- [单元测试生成工具 EvoSuite](https://github.com/EvoSuite/evosuite)

## 开发相关

### 开发环境管理

#### 采用 jenv 管理本地多 java 版本

首先，需要通过 `brew install jenv` 安装 `jenv`。

接着，需要在 shell 的`.profile`/`.zshrc`/`.bashrc`里添加如下几行

```shell
export PATH="$HOME/.jenv/bin:$PATH"
eval "$(jenv init -)"
```

然后，重新登陆 shell，并采用 `jenv add <第三方jdk目录>` 添加 jdk 版本。比如：

```shell
jenv add /Users/guyu/jdk/konajdk/jdk-11.0.17.jdk/Contents/Home/
```

添加完成后可以用 `jenv versions` 命令检查一下是否添加成功，如果添加成功会显示：

```shell
➜ ~ git:(main) ✗ jenv versions
  system
* 11.0 (set by /Users/guyu/.jenv/version)
  11.0.17
  kona64-11.0.17
```

最后，用`jenv global 11.0` 就可以设置全局 jdk 为 11.0 的这个版本了。你也可以用 `jenv version`来查看当前目录下的 jdk 版本。

**小技巧**: 可以通过`jenv local <jdk 版本>`给当前目录指定 jdk 版本。

## 性能

<https://github.com/gdouzwt/java-performance>
