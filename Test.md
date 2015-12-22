# 性能测试

针对ArPHP学习了一些国内外优秀框架。将对框架进行压力测试对比！



测试工具 siege

测试命令 siege -c 300 -t 30S Url

测试环境 各框架代码均在同一台虚拟机centos服务器上测试

测试参考 内存 cpu

注:Url 为实现各框架的地址，不考虑业务层代码，只实现输出 hello world!

测试结果（取三次最优测试结果记录）：




## 原生PHP


```


Transactions:              17863 hits

Availability:             100.00 %

Elapsed time:              29.95 secs

Data transferred:           0.22 MB

Response time:              0.01 secs

Transaction rate:         596.43 trans/sec

Throughput:             0.01 MB/sec

Concurrency:                3.03

Successful transactions:       17863

Failed transactions:               0

Longest transaction:            1.00

Shortest transaction:           0.00
```





其实php的高并发能力还是非常强大的



--------------------------------------------


## ThinkPHP


```


Transactions:               6449 hits

Availability:             100.00 %

Elapsed time:              29.75 secs

Data transferred:           0.08 MB

Response time:              0.83 secs

Transaction rate:         216.77 trans/sec

Throughput:             0.00 MB/sec

Concurrency:              180.77

Successful transactions:        6449

Failed transactions:               0

Longest transaction:            1.91

Shortest transaction:           0.00


```




--------------------------------------------


## Yii



```

Transactions:               5392 hits

Availability:             100.00 %

Elapsed time:              29.67 secs

Data transferred:           0.07 MB

Response time:              1.08 secs

Transaction rate:         181.73 trans/sec

Throughput:             0.00 MB/sec

Concurrency:              196.43

Successful transactions:        5392

Failed transactions:               0

Longest transaction:            1.89

Shortest transaction:           0.02
```


--------------------------------------------


## ArPHP


```


Transactions:              17158 hits

Availability:             100.00 %

Elapsed time:              29.99 secs

Data transferred:           0.21 MB

Response time:              0.02 secs

Transaction rate:         572.12 trans/sec

Throughput:             0.01 MB/sec

Concurrency:               11.21

Successful transactions:       17158

Failed transactions:               0

Longest transaction:            1.26

Shortest transaction:           0.00

```



测试结果：ArPHP的每秒请求数，请求总数已经和原生的PHP相当接近。性能损失非常小。

说明：结果值仅供参考，选择一个自己喜欢的最好。

