# 缓存


## 文件缓存

```
arComp('cache.file')->set('a1', 'abc', 60); // 缓存a1的值为abc 60秒过期

arComp('cache.file')->get('a1');   // abc

arComp('cache.file')->flush();   // 清除当前项目所有缓存

arComp('cache.file')->flushAll();   // 清除所有项目缓存 后台常用






```

