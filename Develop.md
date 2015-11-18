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



### 常规配置





### 组件配置


### 系统配置








