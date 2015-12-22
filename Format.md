# 格式化

fromat组件实现了一些常规的数据替换，字符编码，过滤等，旨在简化代码的循环程度，现有的已能满足大部分需要

### 调用方式


arComp('format.format')->

```
timeToDate($obj, $key = '', $forMat = 'm-d')  // 时间日期转换

replace($key, $value, $obj)  // 批量替换

stripslashes($obj) // 批量去转义符号\

trim($obj) // 批量去两边空字符

encrypt($obj, $key = '') // 批量编码

urldecode($obj, $key = '') // 批量url反转义

urlencode($obj, $key = '') // 批量url转义

convertCharset($obj, $key = '', $in = 'gbk', $to = 'utf-8') // 批量字符串转码

addslashes() // 转义特殊字符

filterKey(array $gar, array $data) // $data中去掉$gar中没有的键的元素

arrayMergeRecursiveDistinct(array $arrayFirst, array $arraySecond) // 深入合并数组
```