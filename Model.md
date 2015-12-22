# 模型

模型主要是数据库的模型，基本是一个表一个模型的解耦


## 新建数据库Model



目录：Model/MyTableModel.class.php

```

class MyTableModel extends ArModel {

    // 表名
    public $tableName = 'YOUR_TABLE_NAME';

    // 固定写法 主要是兼容php低版本
    static public function model($class = __CLASS__) {

        return parent::model($class);

    }   


}

```


## 获取数据库Model实例



```
方法1: $model = MyTableModel::model()

方法2: $model = ArModel::model('MyTableModel')


```



## 获取数据库连接



```
方法1 ： MyTabelModel::model()->getDb();


方法2 ： 

ArPHP的的数据库实现了主从分离分布式控制，非常的实用且强大。详细见组件》数据库

默认读库 arComp('db.mysql')->read('default') 简写 arComp('db.mysql')

写库 arComp('db.mysql')->wirte('default') 
```
