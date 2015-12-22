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
arCfg('URL_MODE');   // URL路由模式 默认PATH
arCfg('URL_GREEDY');    // URL贪婪模式 arU 函数会使用 影响生成的链接参数
arCfg('DEBUG_SHOW_TRACE');    // 开启trace跟踪信息
arCfg('DEBUG_SHOW_ERROR');    // 片段目录地址
arCfg('DEBUG_SHOW_EXCEPTION');    // 片段目录地址
arCfg('DEBUG_SHOW_EXCEPTION');    // 异常信息
arCfg('DIR.SEG');    // 片段目录地址
arCfg('DIR.SEG');    // 片段目录地址
    // url
    'URL_MODE' => 'PATH',
    // 全局url 贪婪模式
    'URL_GREEDY' => false,

    // debug
    'DEBUG_SHOW_TRACE' => true,
    'DEBUG_SHOW_ERROR' => true,
    'DEBUG_SHOW_EXCEPTION' => true,

    // 是否调试信息到日志文件
    'DEBUG_LOG' => false,

    // 默认的模板后缀
    'TPL_SUFFIX' => 'php',

    // 路由规则
    'URL_ROUTE_RULES' => array(
        // 'index/index' => array(
        //     'mode' => 'testindex:a:/:b:', // url will be localhost/testindex123/456   a will be 123 b 456
        // ),
    ),