# 列表


## Session




同于

```
arComp('list.session')->set('a', 123);
arComp('list.session')->get('a'); // 123
arComp('list.session')->flush(); // 清空sesion
$_SESSION['a']  // 123

```

之所以把SESSION 全局数组扩展成List, 是因为List本来就是 ArrayList的超集。有共性的写出优雅的代码， 相比于JAVA，C#，总感觉直接数组出来的元素很素 ，这也是为什么函数式的编写风格代码看上去不够高大上的原因。