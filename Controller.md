# 控制器


## 实现继承



### 使用实例 ：

```
// Index控制器
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
    public function testAction()

    {
        // 渲染模版 View/Index/test.php 模版
        $this->display();

    }
   
}

```
访问  localhost/arphp/Index/test 即可 访问到 testAction 方法


