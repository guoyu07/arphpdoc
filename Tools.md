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
```
// 截取字符串 包括中文一样的OK
arComp('tools.util')->substr_cut($str, $len, $charset="utf-8")

```

```
// 截取字符串 包括中文一样的OK $format  有CHAR,NUMBER,ALL 三种
arComp('tools.util')->randpw($len = 8, $format = 'ALL')

```