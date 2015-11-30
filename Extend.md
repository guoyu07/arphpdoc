# 扩展函数库

如果你熟悉ArPHP的话，以后不管遇到什么框架都能够轻松应对。因为ArPHP可以运行于任何一个框架中， 而不冲突。

```define('AR_OUTER_START', true); ```// 定义为外部扩展库 

```require_once 'ArPHP/init.php';``` // 引入整体框架  同 include 'arphp.php'


即可作为扩展在其他的框架中使用，以后在也不用怕在陌生的Cms,框架中修改别人的代码了。




和WEB模式的区别就是项目目录不在是main相面， 少了项目配置

AR_MAN_NAME  项目名称  默认为 Arman
AR_MAN_PATH  项目目录  默认为入口文件path + AR_MAN_NAME，这个路径在如ECHSHOP等多入口项目文件下最好手动设置下， 不然会生成N多个项目目录。

```define('AR_OUTER_START', true);```// 设置为扩展模式

```defined('AR_MAN_NAME') or define('AR_MAN_NAME', 'Arman');``` // 项目名称

```defined('AR_MAN_PATH') or define('AR_MAN_PATH', AR_ROOT_PATH . AR_MAN_NAME . DS);``` // 项目路径







注:扩展中很多ArPHP本身的功能就没有了，比如控制器等。