# NFS

## NFS 原理

<https://zh.wikipedia.org/wiki/网络文件系统>

假设一个Unix风格的场景，其中一台计算机（客户端）需要访问存储在其他机器上的数据（NFS 服务器）：

1. 服务端实现 NFS 守护进程，默认运行 nfsd，用来使得数据可以被客户端访问。
2. 服务端系统管理员可以决定哪些资源可以被访问，导出目录的名字和参数，通常使用 /etc/exports 配置文件 和 exportfs 命令。
3. 服务端安全-管理员保证它可以组织和认证合法的客户端。
4. 服务端网络配置保证可以跟客户端透过防火墙进行协商。
5. 客户端请求导出的数据，通常调用一个 mount 命令。
如果一切顺利，客户端的用户就可以通过已经挂载的文件系统查看和访问服务端的文件了。

提醒：NFS自动挂载可以通过—可能是 /etc/fstab 或者自动安装管理进程。

## NFS 服务端配置

### NFS 服务端安装

```shell
sudo apt -y install nfs-kernel-server
```

### NFS 服务端防火墙配置

`firewalld`内建了相关服务的访问，只需要增加服务名就可以。

```shell
sudo firewall-cmd --permanent --add-service=nfs
sudo firewall-cmd --permanent --add-service=mountd
sudo firewall-cmd --permanent --add-service=rpc-bind
sudo firewall-cmd --reload
```

### NFS 服务端目录配置

- 新建 NFS 目录：

```shell
sudo mkdir -p /mnt/nfs-root
sudo chown nobody:nogroup /mnt/nfs-root/
sudo chmod 777 /mnt/nfs-root/
```

- 在`/etc/exports`中增加访问，格式为：路径，允许访问的IP或CIDR（访问方式，同步方式，其它属性）

```text
/mnt/nfs-root 192.168.64.*(ro,sync,no_subtree_check)
```

允许 192.168.64内的所有IP已只读的方式访问

- 最后通过以下命令导出文件服务

```shell
sudo exportfs -arv
```

## NFS 客户端配置

### NFS 客户端安装

```shell
sudo apt -y install nfs-common
```

### NFS 客户端挂载

- 创建本地目录

```shell
sudo mkdir -p /mnt/nfs-root
```

- 将远程NFS目录挂载到本地目录

```shell
sudo mount <NFS服务器IP>:/mnt/nfs-root /mnt/nfs-root
```
