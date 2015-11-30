# 外部框架

如果你想在其他的框架中添加新的功能和模块，而对原来的架构又不熟悉，这时你就可以考虑ArPHP作为外部框架来支持你的选择。



```defined('AR_AS_OUTER_FRAME') or define('AR_AS_OUTER_FRAME', true); ```// 定义为外部框架

```require_once  'ArPHP/init.php';```



## Useage


在其他的框架入口文件中首先引入ArPHP即可，在加载过程中路由会首先解析ArPHP的路由设置，如果不存在交互控制器，在WEB模式下直接会报错，这里原理就是不处异常，自动把权限交给下级框架处理业务

