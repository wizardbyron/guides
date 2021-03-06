# Filesystem Hierarchy Standard

Linux 各文件目录标准：[Filesystem Hierarchy Standard](https://refspecs.linuxfoundation.org/FHS_3.0/fhs/index.html)

## 常用目录

### /: 根文件系统

- /bin: 用户命令必要的二进制执行文件（对于机器上的所有用户）: 例如：whoami。 /bin 下面不能有子目录
- /sbin: 用于系统管理和其它 root 用户专属的命令。用于引导，还原，恢复，修复系统的其它命令。例如: fsck
- /etc: 主机的系统配置，必须是不可执行的文件。
- /lib: 在根文件系统用于引导系统或执行命令的静态共享库。被`/bin`和`/sbin`消费。
- /opt: 保留用于安装额外的软件包。自目录是软件包名称或者提供者注册的LANANA名称。
- /srv: 对外暴露数据的只读目录，常用协议或者上下文区别。

### /usr: 可共享且只读的数据

- /usr/bin: 系统可执行命令目录。例如：free 等，该目录下不能有子目录。
- /usr/sbin: 系统挂载后执行的命令。
- /usr/local/sbin: 本地安装的软件。例如：pip
- /usr/local/lib: 本地安装的语言库。例如：python3.6

### /var: 包含可变数据文件。 这包括假脱机目录和文件、管理和日志数据以及瞬态和临时文件

### /bin 下的命令

| 命令       | 描述              |
| -------- | --------------- |
| cat      | 将文件连接到标准输出      |
| chgrp    | 改变文件所属用户组       |
| chmod    | 改变文件访问权限        |
| chown    | 改变文件所属用户        |
| cp       | 复制文件或者目录        |
| date     | 打印或者设置系统时间      |
| dd       | 转换并复制文件         |
| df       | 用于报告磁盘空间使用情况    |
| dmesg    | 打印或者控制内核信息      |
| echo     | 显示一行文字          |
| false    | 什么都不做，不成功       |
| hostname | 显示或设置主机名        |
| kill     | 向进程发送信号         |
| ln       | 创建两个文件之间的链接     |
| login    | 开始一个新的用户会话      |
| ls       | 显示当前目录文件        |
| mkdir    | 创建一个目录          |
| mknod    | 创建块或者特殊字符文件     |
| more     | 按页显示文件          |
| mount    | 挂载一个文件系统        |
| mv       | 移动文件或修改文件名      |
| ps       | 报告进程状态          |
| pwd      | 打印当前工作目录        |
| rm       | 删除文件或目录         |
| rmdir    | 删除空目录           |
| sed      | Sed 流编辑器        |
| sh       | POSIX 兼容的 shell |
| stty     | 改变或打印终端行的设置     |
| su       | 用于切换用户ID        |
| sync     | 清空文件(flush)系统缓存 |
| true     | 什么都不做，成功        |
| umount   | 卸载文件系统          |
| uname    | 打印系统信息          |

关于 /usr/(s)bin 和 /(s)bin 同样命令的比较:

```shell
[vagrant@admin-node bin]$ which whoami
/usr/bin/whoami
[vagrant@admin-node bin]$ sudo which whoami
/bin/whoami
[vagrant@admin-node sbin]$ which fsck
/usr/sbin/fsck
[vagrant@admin-node sbin]$ sudo which fsck
/sbin/fsck
```

### /usr/sbin 下的命令

| 命令       | 描述              |
| ---- | --------------- |
| free | 用于显示内存使用情况 ｜
