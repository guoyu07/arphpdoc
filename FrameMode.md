# 外部框架

如果你想在其他的框架中添加新的功能和模块，而对原来的架构又不熟悉，这时你就可以考虑ArPHP作为外部框架来支持你的选择。



```defined('AR_AS_OUTER_FRAME') or define('AR_AS_OUTER_FRAME', true); ```// 定义为外部框架

```require_once  'ArPHP/init.php';```



在其他的框架入口文件中首先引入ArPHP即可。