# 远程调用


## 远程请求

已经封装curl

```
arComp('rpc.source')->remoteCall($url, $params = array(), $method = '');
```
$url 请求的url 

$params 参数

$method post  或者  get


## 代理



```
arComp('rpc.proxy')->callApi($url, $show = true);
```


$url 请求的url 


$show 为true直接显示(如图片)， false会下载当前资源
