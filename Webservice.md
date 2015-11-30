# WebService

webservice 可以实现主从数据，主从业务机分离模型。有效减小代码耦合程度。
ArPHP在webservice 对这块做了独到的解释,不同于基于PHP soap扩展的 webservice 内存占用高 不稳定 不稳定 不稳定重要的事情说三遍，曾经检修一项目的apache莫名挂掉的问题就是出在此。

ArPHP提供客户端数据包装功能，解析服务端返回的数据，相对于传统webservice调试困难的问题, ArPHP服务端代码调试也是相当容易，echo输出的信息可以直接显示在debug制面板。ArPHP容错程度高，内存占用低，绝对的轻量级，上手容易。可以无缝与ARPHP其他的几种模式融合。RPC调用很华丽。

ArPHP提供的服务端入口文件arws.php 定义 

```define('AR_DEBUG', true);```// 开启调试模式 默认开启 开启将显示DEBUG信息
```define('AR_DEFAULT_APP_NAME', 'ws');```// 默认的项目目录    
```define('AR_RUN_AS_SERVICE_HTTP', true);```// 以http方式服务开启webservice  
```require_once  'ArPHP/init.php';```// 引入ArPHP初始化文件



## 创建服务端服务Test



项目目录创建文件夹Service(service存放目录)

具体Service代码

```TestService.class.php

class TestService extends ArService

{
    // 测试WORKER
    public function t1Worker($a, $b)

    {

        $this->response(123);

    }

}```


## 客服端调用


```arComp('rpc.service')->WsTest('t1', array('p1', 'p2'))  // 123```
