# Linux 命令

Linux 命令大全 <https://www.runoob.com/linux/linux-command-manual.html>

## 用户/组

## 进程

### ps

查看进程使用资源情况

<https://linux265.com/news/3818.html>

### pstree

### kill

## 内存

### Free - 查看内存使用情况

## 磁盘

### du - 查看磁盘空间使用情况

- 检查磁盘使用情况并排序：

```shell
du -sh * | sort -rh
```

- 检查文件大小:

``` shell
du -h <文件名>
```

### fio - 测试磁盘性能

IOPS（Input/Output Operations Per Second）是一个用于计算机存储设备（如硬盘（HDD）、固态硬盘（SSD）或存储区域网络（SAN））性能测试的量测方式，可以视为是每秒的读写次数。和其他性能测试一样，存储设备制造商提出的IOPS不保证就是实际应用下的性能。

IOPS 测试工具：<https://fio.readthedocs.io/en/latest/fio_doc.html>

## 网络

### ip - 查看/修改网络配置

### hostname

该命令可以获取或设置主机名或 NIS 域名。 您还可以获得 DNS 域或 FQDN（完全限定的域名）。 除非您使用绑定或 NIS 进行主机查找，否则您可以在 /etc/hosts 文件中更改 FQDN（完全限定域名）和 DNS 域名（它是 FQDN 的一部分）。

获取本机IP：

```shell
hostname -I | awk '{print $1}'
```

### firewalld - 查看/修改防火墙规则

介绍：

- <https://www.redhat.com/sysadmin/beginners-guide-firewalld>
- <https://www.redhat.com/sysadmin/firewalld-zones-and-rules>

文档：

显示所有的规则:

```shell
firewall-cmd --list-all
```

添加/删除端口：

```shell
firewall-cmd --permanent --add-port=<端口号>/<tcp或udp>
firewall-cmd --permanent --remove-port=<端口号>/<tcp或udp>
```

根据预设服务添加端口：

```shell
firewall-cmd --permanent --add-service=<服务名>
firewall-cmd --permanent --remove-service=<服务名>
```

预设的服务目录: `ls /usr/lib/firewalld/services/`

### lsof (list open files)

- 查找端口被占用进程:

```shell
lsof -i:<端口号>
```

### netstat

centos 安装：`net-tools`

- 查找端口被占用进程:

```shell
netstat -tunlp|grep <端口号>
```

### nslookup

## 文本处理

### tee - 从标准输入读入并从标准输出写出

### sed - 流编辑器

### awk - 模式识别处理语言

- 显示列数据

``` shell
awk '{print $1}'
```

- 保存 Kubernetes 镜像

``` shell
docker save $(docker images|grep "k8s.gcr.io"|awk '{print $3}') > k8s-images.tar
```

### xargs - 组合命令工具

### wc - 统计文件的行数，词数，字符数，字节数

## 其他

### audit - 审计
