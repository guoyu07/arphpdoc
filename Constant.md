# 系统常量



```
// 启动时间
AR_START_TIME

// 开启调试 默认是true
AR_DEBUG    

// 外部启动 否false 默认管理目录ArMan
AR_OUTER_START

// 自启动session 默认是 true
AR_AUTO_START_SESSION

// 作为外部框架加载 可嵌入其他框架 false
AR_AS_OUTER_FRAME

// 内部实现http webservice 多套 arphp程序互调接口 false

AR_RUN_AS_SERVICE_HTTP

// 实现 cmd socket 编程 false
AR_AS_CMD

// web application 默认方式
AR_AS_WEB

// app名 默认main
AR_DEFAULT_APP_NAME

// 默认的控制器名  默认Index
AR_DEFAULT_CONTROLLER

// 默认的Action 默认 index
AR_DEFAULT_ACTION

// 目录分割符号  DIRECTORY_SEPARATOR
DS

// ar框架目录
AR_FRAME_PATH  AR框架目录

// 项目根目录
AR_ROOT_PATH

// AR核心类库目录
AR_CORE_PATH

// Ar系统初始配置目录
AR_CONFIG_PATH

// 系统扩展目录
AR_EXT_PATH

// 系统模块目录
AR_COMP_PATH

// Web目录地址
AR_SERVER_PATH

// 默认配置文件
AR_PUBLIC_CONFIG_FILE

```


## 扩展模式
```
// 扩展库项目名 默认Arman
AR_MAN_NAME
// 扩展库项目路径
AR_MAN_PATH
```
## 命令行模式
```
// 命令行开发项目目录
AR_CMD_PATH 

 ```
覆盖请在加载arphp之前定义值