# 开发流程


## 获取



git : https://github.com/assnr/ArPHP.git

觉得还可以的话请mark加下星



## 选择开发模式

选择适合的开发模式可以达到事半功倍的效果，相信arphp五种开发模式足以满足你的所有需求。


## start


只要在入口文件里包含ArPHP初始化文件 


index.php  入口代码

整体框框

```include_once 'ArPHP/init.php';```


单文件框架

```include_once 'arphp.php';```

访问index.php即可件 hello ArPHP!

## 配置

配置有全局配置和应用配置之分，项目配置存在于每个应用对应的目录Conf/app.config.php

全局配置在项目目录Conf/public.config.php 

注：应用配置覆盖全局配置，配置可用ini格式配置，public.config.ini,app.config.ini，同时存在不冲突


配置文件格式例：
```
return array(
    // 常规配置
    'ar' => 'arphp',```

    // 应用配置(系统)
    'moduleLists' => array(
        'main'
    ),

    // 是否开启trace信息
    'DEBUG_SHOW_TRACE' => false,


    // 组件配置
    'components' => array(
        // 远程调用
        'rpc' => array(
            // 惰性加载
            'lazy' => true,
            // 对应Compnent目录类
            'service' => array(
                // 组件配置
                'config' => array(
                    'wsFile' => 'http://192.168.1.67/arphp/arws.php',
                ),
            ),
            // 对应Compnent目录类
            'source' => array(
                // 组件配置
                'config' => array(
                    'remotePrefix' => 'http://api.test.cn/Handler/',
                    'method' => 'post',
                    // 自定义配置
                    'authOptions' => array(
                        'key' => '5c54df2b9t6621510fb3y1d44jyt2014',
                        'opt' => 'wxspcl',
                        'curlOptions' => array(
                            CURLOPT_REFERER => 'http://api.test.cn/test.do',
                            ),
                        ),
                    ),

                ),
            ),
        ), 
    ),

);


### 常规(用户)配置
```
arCfg('ar'); // arphp
// 改变配置
Ar::setConfig('ar', 'hello');
arCfg('ar'); // hello```
```
arCfg('aa'); // null
arCfg('aa', 123); // 123```


### 组件配置


### 系统配置








