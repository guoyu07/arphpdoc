# 工具

工具封装了常用的方法供使用

```
// 获取客户端ip 以web模式运行有效
arComp('tools.util')->getClientIp();

```
```
// $cli 为true 命令行模式下使用 false 直接web容器下获取服务端ip
arComp('tools.util')->getServerIp($os = 'linux', $cli = true)
```