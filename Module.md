# 中间件

Module就是中间件对你没有看错，它在控制器和Model之间穿梭，完成公共迭代功能。

可以构建Module把整个公用性强的模块实现，


目录 : Module/MyModule.class.php

```
class MyModule

{

    public function test()

    {

        echo 'test';

    }

}

```

Controller调用：

arModule('My')->test();