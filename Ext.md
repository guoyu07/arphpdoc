# 扩展


## 上传文件

```
arComp('ext.upload')->upload('filefield', $path, $extension);

```

$path 为上传目录 默认为项目目录/Upload

$extension  允许的扩展名

### 返回值

String 的文件名称



## 自定义扩展

继承ArComponnent类


实现init方法

调用

```arComp('ext.yourextensionname')->func();```