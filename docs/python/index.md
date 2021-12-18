
# Python 相关

## 通过 pyenv 管理 Python 环境

<待补充>

## 通过 pip 管理软件

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

详情可以参考官方文档<https://github.com/bndr/pipreqs>
