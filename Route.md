# 路由

路由组件支撑了Ap的路由规则，项目生成，url生成规则，ArU这些常用函数都是基于此。


## 常用的方法
```
以arphp默认初始地址url http://localhost/arphp/index.php, E:\web为网站DocumentRoot为例

arComp('url.route')->serverName();  // http://localhost
arComp('url.route')->host();        // http://localhost/arphp
arComp('url.route')->host(true);    // http://localhost/arphp/index.php

// 绝对地址转换为web相对路径
arComp('url.route')->serverPath('E:\web\arphp\main\\');  // /arphp/main
// web路径转为绝对地址
arComp('url.route')->pathToDir('/arphp/main');   // E:\web\arphp\main

```