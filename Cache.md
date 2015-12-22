# 缓存


## 文件缓存

```
arComp('cache.file')->set('a1', 'abc', 60); // 缓存a1的值为abc 60秒过期

arComp('cache.file')->get('a1');   // abc

arComp('cache.file')->del('a1');   // 删除a1的值

arComp('cache.file')->flush();   // 清除当前项目所有缓存

arComp('cache.file')->flushAll();   // 清除所有项目缓存 后台常用



```


## redis缓存

redis组件类已实现自动断开重连机制

### 配置

``` 
'cache' => array(
    'redis' => array(
        // 懒惰加载
        'lazy' => true,
                'config' => array(
                    // redis主机
                    'host' => '127.0.0.1',
                    // 端口
                    'port' => '6379',
                    // 链接密码
                    'password' => 'pwd',
                    // 是否持久连接
                    // 'pconnect' => true,
                    // 默认数据库
                    // 'db' =>
                ),
            ),
        ),
    ),  
        ```


获取redis操作句柄

```$redis = arComp('cache.redis');```


### redis锁

获得锁

```
$redis->lock('key', 1, 6);  // 获取锁 失败时等待1秒重试，最大6秒后超时返回false
$redis->lock('key', 0);     // 默认获取不到锁直接返回false

```
成功返回true

释放锁

```$redis->unLock('key'); ```


其他操作 类似于 file





