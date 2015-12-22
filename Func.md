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

```$module = arModule($ModuleName);``
`



### 用户参数

arGet() 是更安全的$_GET全局数组超集，里面的所有元素都经过转义，可以反正sql注入

同理arPost(), arRequest();
```
$_GET['a']; // 123
arGet('a'); // 123

```


### 加载其他路径模块


```
// $path 可以为路径 也可以 . 号分隔的path
arLm($path)

arModule('Test')->test(); // 调用当前项目Module/Test

// 引入admin/Moduel  把admin/Module纳入include_path，类似加入环境变量
arLm('admin.Module');     

// 如果admin下存在TestModule 则调用admin项目Module/Test,不存在依然调用当前项目Moduel, 场景就是可以定义一个公共的Moduel源
arModule('Test')->test(); 
```


### 模版输出



echo 的升级版本，只是加入了默认参数
```
arEcho($echo = '', $default = '', $key = '')


$echo 为空则输出$default 值

arEcho($a, 123); // 123
arEcho(1, array('a','b','c')); // b
arEcho(1, array(array('a','b','c'),array('d','e','f')), 1); // e
$a = 666;
arEcho($a, 123); // 666
```


### 片段
这功能太强大了，可以模块化的开发任何一块完整的html功能，用在模版里


新建文件Conf/Seg/Html/select.php
```
<select name="<?php echo $name; ?>" <?php echo $oPram; ?>>
    <?php
        foreach ($map as $k => $v) :
    ?>

    <option
    <?php
        if (isset($selected) && $selected == $k) :
    ?>
    selected = "selected"
    <?php
        endif;
    ?>value="<?php echo $k; ?>"><?php echo $v; ?></option>

    <?php
        endforeach;
    ?>
</select>
```
模版里面调用


      // 调用用html seg 直接输出 select标签
      arSeg(
         array(
            // seg文件
            'segKey' => 'Html/select',
            // <select name="name">
            'name' => 'sex',
            // 适配器数据 数组
            'map' => array('男', '女'),
            // 选中的value selected = selected
            'selected' => 0
         )
      );

将生成如下HTML代码

```
<select name="sex">
    <option value="0" selected="selected">男</option>
    <option value="1" >女</option>
</select>
```
真的快速开发，特别是复杂的公用数据的时候

