
# Python 相关

## Python 风格指南

[Google Python Style Guide](https://google.github.io/styleguide/pyguide.html)

## Python 常用工具

[Pyright](https://github.com/microsoft/pyright): python 静态类型检查工具

## 通过 pyenv 管理 Python 环境

<待补充>

## 通过 pip 管理软件包

### 安装单个软件包

在部分 Linux 发行版商采用 Python3 读取 pip 模块安装。安装软件最好不要使用 root 或者超级用户。采用`--user`为当前用户安装。

```shell
python3 -m pip install --user <软件包名>
```

也可以通过`alias pip="python3 -m pip"`设置命令别名。

### 从`requirement.txt`中安装软件包

```shell
python3 -m pip install --user -r requirement.txt
```

### 生成`requirement.txt`

#### 1. 通过 `pip freeze` 生成（不推荐）

`pip freeze`会生成当前系统所有安装的包，在非`virtualenv`的环境下请不要使用。

```shell
pip freeze > requirements.txt
```

#### 2. 通过 `pipreqs` 生成

`pipreqs`通过读取当前工程下所有 python 文件的 import 信息来生成 `requirements.txt` 文件。在使用之前要通过`pip`安装。

```shell
pipreqs <工程根目录>
```

详情可以参考官方文档:<https://github.com/bndr/pipreqs>

#### 通过 Poetry 管理软件包

<https://github.com/python-poetry/poetry>

安装:

```shell
curl -sSL https://install.python-poetry.org | python3 -
```

## 关于 *.pyc 文件

`.pyc` 文件是 python 编译后的文件。可以使用 python 解释器编译 py 文件 成 pyc 字节码文件。使用 pyc 可以加快程序的加载速度，而不能加快程序的实际执行速度，这就是解释为什么我们安装 python 目录很多第三方库下是 pyc 文件的原因，因为它可以使得 import 一些第三方库的速度加快。由于 .pyc 文件是编译好的字节码，它是独立于平台的，因此可以在不同体系结构的计算机之间共享。

### 编译

```sh
python -m compileall ./
```

### Bad Magic number

`.pyc` 文件可以跨平台，但不能跨大版本。换句话说，`3.8.x` 版本编译的 `pyc` 文件不能在 `3.10.x` 下运行，否则会出现 `RuntimeError: Bad magic number in .pyc file` 运行时错误。因此，需要统一运行版本。

## __init__.py 的作用

将一个目录变成一个 python 包，需要在该目录下创建 `__init__.py` 文件。
