# 优雅关闭

`优雅关闭（Graceful Shutdown）`是当部署应用程序的新版本替换以前的版本时。进程管理器将首先向应用程序发送一个 SIGTERM 信号，以通知该进程将被杀死。 一旦应用程序收到这个信号，它应该：

1. 停止接受新请求。
2. 完成所有正在进行的请求。
3. 清理它应用的资源，包括数据库连接和文件锁。
4. 退出。

## 技巧

1. 设置超时时间进行强制终止以避免过长的终止等待时间。

## 案例

1. Go 语言在 1.8 版本之后的增加了 [Shutdown()方法](https://pkg.go.dev/net/http#Server.Shutdown)以支持优雅关闭。
2. Kubernetes 的 delete 操作默认都有 30 秒的优雅关闭时限。并且可以通过设置`--grace-period=<seconds>`参数来调整关闭时限的长度。

## 工具 & 平台

（待补充）

## 参考和引用

- [Wikipedia - Signal(IPC)](https://en.wikipedia.org/wiki/Signal_(IPC))
- [GNU - Termination-Signals](https://www.gnu.org/software/libc/manual/html_node/Termination-Signals.html)
- [Kubernetes.io - Pod Lifecycle](https://kubernetes.io/docs/concepts/workloads/pods/pod-lifecycle/)
- [Express.js - Health Checks and Graceful Shutdown](https://expressjs.com/en/advanced/healthcheck-graceful-shutdown.html)
