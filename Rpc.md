# 远程调用


## 远程请求

已经封装curl

```
arComp('rpc.source')->remoteCall($url, $params = array(), $method = '');
```
$url 请求的url 

$params 参数

$method post  或者  get

使用场景：第三方短信验证码，获取远程接口数据等

## 代理



```
arComp('rpc.proxy')->callApi($url, $show = true);
```


$url 请求的url 


$show 为true直接显示(如图片)， false会下载当前资源



## Json

```
arComp('rpc.json')->callApi('api/testJson', $params);

```

直接请求本地项目json数据解析



