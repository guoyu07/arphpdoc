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
                        'local' => array(
                            // 链接字符串
                            'dsn' =>'mysql:host=localhost;dbname=arphp1;port=3306',

                            'user' => 'arphp',

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
                            ),
                        'default' => array(
                            'dsn' => 'mysql:host=localhost;dbname=arphp3;port=3306',

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
                    )

                ),
            ),



