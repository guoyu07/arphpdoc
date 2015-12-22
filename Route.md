# 路由

路由组件支撑了Ap的路由规则，项目生成，url生成规则，ArU这些常用函数都是基于此。


## 常用的方法
以arphp默认初始地址url http://localhost/arphp/index.php 为例

arComp('url.route')->serverName();
arComp('url.route')->host();
arComp('url.route')->serverPath();
arComp('url.route')->pathToDir();