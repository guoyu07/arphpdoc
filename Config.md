# 系统配置变量


## PATH路径

```
arCfg('PATH.APP_SERVER_PATH');  // 项目地址
arCfg('PATH.PUBLIC');           // 项目Public目录地址
arCfg('PATH.GPUBLIC');          // 全局公共Public目录地址
arCfg('PATH.APP_SERVER_PATH');  // 项目服地址
```
## DIR 绝对路径

```
arCfg('DIR.CACHE');  // 项目Cache目录地址

arCfg('DIR.LOG');    // 日志目录地址
arCfg('DIR.UPLOAD'); // 上传目录

arCfg('DIR.VIEW');   // 视图模版地址

arCfg('DIR.EXT');    // 用户自定义扩展类目录
arCfg('DIR.SEG');    // 片段目录地址

```
## 其他配置
```
arCfg('URL_MODE');                // URL路由模式 默认PATH
arCfg('URL_GREEDY');              // URL贪婪模式 arU 函数会使用 影响生成的链接参数
arCfg('DEBUG_SHOW_TRACE');        // 开启trace跟踪信息
arCfg('DEBUG_SHOW_ERROR');        // 片段目录地址
arCfg('DEBUG_SHOW_EXCEPTION');    // 片段目录地址
arCfg('DEBUG_SHOW_EXCEPTION');    // 异常信息
arCfg('DEBUG_LOG');               // 错误信息是否记录到日志，如果开启，将不显示错误信息，而是记录到文件
arCfg('TPL_SUFFIX');              // 模版文件后缀名 默认php


arCfg('URL_ROUTE_RULES');         // 路由规则 可以生成更优雅的URL 适合seo优化
    // 路由规则
    'URL_ROUTE_RULES' => array(
        'index/index' => array(
            'mode' => 'testindex:a:/:b:', 
            // url: http://localhost/testindex123/456   a will be 123 b 456
        ),
    ),
```
    