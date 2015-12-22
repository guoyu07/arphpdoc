# 控制器


## 实现继承




### 使用实例 ：

```

class IndexController extends ArController 
{
    // 第一个执行方法
    public function init()
    {
        // echo 'Action预先执行';

    }

    /**

     * just the example of get contents.

     *

     * @return void

     */
    public function indexAction()

    {
        // 渲染模版
        $this->display();

    }
   
}

```

Action
使用实例：

    public function indexAction()

    {

        $this->display();



    }

