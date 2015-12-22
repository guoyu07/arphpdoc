# 数据库


# Mysql


## 配置


系统的数据库组件都是 基于PDO开发的，所以要开启Pdo_mysql扩展



组件配置代码:


         'db' => array(
            // 延迟加载
            'lazy' => true,
            // 定义组件名称mysql
            'mysql' => array(
                // 通用配置格式
                'config' => array(
                
                    // 配置写库（一般主库，这里展示读写分离配置）
                    'write' => array(
                        'writedb' => array(
                            // 链接字符串
                            'dsn' =>'mysql:host=localhost;dbname=arphp3;port=3306',
                            // 用户
                            'user' => 'arphp',
                            // 密码
                            'pass' => 'pass',
                            // 表前缀
                            'prefix' => '',

                            'option' => array(
                                PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
                                PDO::MYSQL_ATTR_USE_BUFFERED_QUERY => true,
                                PDO::MYSQL_ATTR_INIT_COMMAND => 'SET NAMES \'UTF8\'',
                                ),
                            ),
                        ),
                    // 配置读库
                    'read' => array(
                      
                        'readdb' => array(
                            'dsn' => 'mysql:host=localhost;dbname=arphp2;port=3306',

                            'user' => 'dbread',

                            'pass' => 'dbpass',

                            'prefix' => '',

                            'option' => array(
                                PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
                                PDO::MYSQL_ATTR_USE_BUFFERED_QUERY => true,
                                PDO::MYSQL_ATTR_INIT_COMMAND => 'SET NAMES \'UTF8\'',
                                ),
                        
                         )    
                    
                    
                        'default' => array(
                            'dsn' => 'mysql:host=localhost;dbname=arphp;port=3306',

                            'user' => 'root',

                            'pass' => '',

                            'prefix' => '',

                            'option' => array(
                                PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
                                PDO::MYSQL_ATTR_USE_BUFFERED_QUERY => true,
                                PDO::MYSQL_ATTR_INIT_COMMAND => 'SET NAMES \'UTF8\'',
                                ),
                            ),
                        ),
                    ),
                ),
            ),


## 获取数据库实例

### 原生写法


```$db = arComp('db.mysql')->read('default'); ```// 获取read.default配置即arphp数据库 默认请配置一个read.default配置

```$db = arComp('db.mysql')->read('readdb');``` // 获取read.readdb配置即arphp2数据库

```$db = arComp('db.mysql')->write('writedb');``` // 获取read.writedb配置即arphp3数据库



### Model模型（一个模型一个表推荐写法）

1. 在Model文件夹下建立TestModel.class.php 文件
2. 保存如下内容

class TestModel extends ArModel
{
    // 表名
    public $tableName = 'test';

    // 初始化model 固定写法
    static public function model($class = __CLASS__)
    {
        return parent::model($class);

    }


}

3. 获取实例
```$db = TestModel::model()->getDb();``` // 获取默认read.default配置数据库下的test表数据库实例



# 数据库操作


## 查询


### 查询一行

```
$result = $db->table('t1')->queryRow();

```
$result 为一维数组

### 查询所有



```
$db->table('t1')->queryAll();

```


### 条件查询

$db->table('t1')->where($dbCondition)->queryAll();

### $dbCondition 


可以为字符串 ``` "a=1 and b = 2"```
也可以为数组``` array('a' => 1, 'b > ' => 1, 'c != ' => 1); ```



### 查询limit

查询5条

```
$db->table('t1')->where($dbCondition)->limit(5)->queryAll();
```



### 排序order

```
$db->table('t1')->where($dbCondition)->limit(5)->order('id desc')->queryAll();
```

### 分组group


```
$db->table('t1')->where($dbCondition)->group('name')->queryAll();
```


### 联表查询
```
$db->table('t1')->where($dbCondition)->leftJoin('t2', 't1.id = t2.tid')->queryAll();

```


## 删除

```
$db->table('t1')->where($dbCondition)->delete();

```


## 更新

```
$db->table('t1')->where($dbCondition)->update(array('name' => 'abc'));

```


