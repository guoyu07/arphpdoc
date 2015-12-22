# 系统函数


## 系统别名函数


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
```

Ar::setConfig('a', 123);
arCfg('a')   // 123

// .多级属性

Ar::setConfig('a.b', 456);
arCfg('a.b') // 456```







