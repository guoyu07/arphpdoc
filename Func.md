# 系统函数


### 获取组件实例



```
// 加载组件 等同于 Ar::c($name); 
arComp($name = '')
```

arphp很多地方采用单例静态内存存储区放置同名对象，重复合理利用资源，效率高


### 获取配置值

```

// $name 为key, $default 为配置不存在值时的返回默认值
arCfg($name = '', $default = 'NOT_RGI')
```


### 设置配置值



配置的值是全局的 设置一次后面执行到的地方都可以获得

1. 配置文件中设置
2. 代码设置

```
Ar::setConfig('a', 123);
arCfg('a')   // 123

// .多级属性

Ar::setConfig('a.b', 456);
arCfg('a.b') // 456
```




### 生成URL
arU($name = '', $params = array(), $urlMode = 'NOT_INIT')

等于组件里的方法arComp('url.route')->createUrl($name, $params, $urlMode);

参数说明:

$name 生成的url字符串
$params 参数 数组
$urlMode PATH(路径默认),QUERY（查询）,FULL(完整查询链接)三种

```
// /arphp/url/test/a/1/b/2
arU('url/test', array('a' => 1, 'b' => 2));  


// http://localhost/arphp?a_c=url&a_a=test&a=1&b=2
arU('url/test', array('a' => 1, 'b' => 2), 'QUERY'); 


// http://localhost/arphp/index.php?a_c=url&a_a=test&a=1&b=2
arU('url/test', array('a' => 1, 'b' => 2), 'FULL'); 


```

### 获取Module实例

```$module = arModule($ModuleName);```







