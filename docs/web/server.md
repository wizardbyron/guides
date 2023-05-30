# Web 服务器

## Nginx

## Caddy

参考配置

```caddyfile
:80
encode gzip zstd #启动编码、压缩、
root * /srv # 根目录访问点
try_files {path} /index.html # 单页 App 访问（例如 vue）
file_server # 启用静态文件服务
reverse_proxy /api/* api:3000 # 反向代理，访问 ./api/* 的转发给 api:3000
```

`encode gzip zstd` 是一个指令，用于**启用 HTTP 压缩**。这有助于减少传输到客户端的数据大小，从而提高页面加载速度和响应时间。这个指令包含两个参数，`gzip` 和 `zstd`，分别代表不同的压缩算法：

`gzip`: 表示使用 Gzip 压缩算法。Gzip 是一种广泛使用的文件压缩工具，经常用于减小文件大小以便于传输。大多数现代 Web 浏览器都支持 Gzip 压缩。

`zstd`: Zstandard（Zstd） 是一种实时压缩算法，相比 Gzip 有着更好的压缩率和速度。虽然它还不如 Gzip 流行，但许多新的 Web 浏览器已经开始支持它。

当你在 Caddyfile 中使用 `encode gzip zstd` 指令时，服务器将根据客户端的请求头（Accept-Encoding）来选择一种合适的压缩算法。
