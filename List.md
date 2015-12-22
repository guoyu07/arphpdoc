# 列表List


## Session




```
arComp('list.session')->set('a', 123);
arComp('list.session')->get('a'); // 123
arComp('list.session')->flush(); // 清空sesion
$_SESSION['a']  // 123

```

之所以把SESSION 全局数组扩展成List, 是因为List本来就是 ArrayList的超集。有共性的写出优雅的代码， 相比于JAVA，C#，总感觉直接数组出来的元素很素 ，这也是为什么函数式的编写风格代码看上去不够高大上的原因。



## 日志

当时不记得为什么把日志放List这里了 ,可能后面可以扩展成读取日志的功能list,日志非常有用，在调试代码不能中断的情况下游刃有余。在改垃圾代码时细细体会吧。

```arComp('list.log')->record(123, 'abc');```

会在Log/日期/abc.txt 记录123