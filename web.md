# WEB


定义常量“AR_AS_WEB” 为ture的的模式（默认），这是Ar'PHP最基本的运行模式， 常见PHP框架就是此模式, ArPHP 系统常量都以AR开头，所有系统常量详见附录**常量说明** 

入口文件


```defined('AR_AS_WEB') or define('AR_AS_WEB', true);```// 定义为web模式 （默认为此模式）

```include 'arphp.php';```// 引入arphp框架（注意这里是单文件）