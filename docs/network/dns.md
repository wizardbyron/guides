# DNS

DNS （Domain Name Service） 域名服务

端口：53

## DNS 原理

<https://computingforgeeks.com/bind-vs-dnsmasq-vs-powerdns-vs-unbound/>

## Linux 添加DNS服务器地址

<https://blog.csdn.net/lcr_happy/article/details/54867510>

`/etc/resolv.conf`是DNS客户机配置文件，用于设置DNS服务器的IP地址及DNS域名，还包含了主机的域名搜索顺序。

## nslookup

### nslookup 安装

centos:

``` shell
sudo yum install -y bind-utils
```

## 通过 BIND 设置本地 DNS 服务

<https://www.digitalocean.com/community/tutorials/how-to-configure-bind-as-a-private-network-dns-server-on-ubuntu-14-04>

## 通过 DNSmasq 设置本地 DNS 服务

URL: <https://thekelleys.org.uk/dnsmasq/doc.html>

### DNSmasq安装

- Docker 方式

``` shell
docker run -d  --name dnsmasq     --restart always -p 53:53/udp -p 8080:8080  -v /data/dns/dnsmasq.conf:/etc/dnsmasq.conf --log-opt "max-size=100m" -e "HTTP_USER=admin" -e "HTTP_PASS=123456" jpillora/dnsmasq
```

### DNSmasq配置

<https://cloud.tencent.com/developer/article/1174717>

### 基于docker搭建DNSmasq

<https://cloud.tencent.com/developer/article/1692705>
