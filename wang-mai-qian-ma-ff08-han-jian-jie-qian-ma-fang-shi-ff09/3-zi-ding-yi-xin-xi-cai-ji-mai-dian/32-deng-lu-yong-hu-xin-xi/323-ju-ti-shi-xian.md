### 3.2.3 具体实现

下面两种方式选择一种操作。

**方式一：自定义函数**

需要在可以获取登录用户信息的页面，实现方法window.TA17Callbacks\_getAndSendLoginUser \(callback\)。该方法可以使用同步或异步方式获取用户信息，在获取成功后将回调函数callback\(\)放到try…catch语句中执行，并将用户标识uId信息作为callback\(\)的参数。

```
window. TA17Callbacks_getAndSendLoginUser = function(callback) {
    var uId = '';
    /**
     * 获取用户信息的操作
     * 成功获取后执行下面的回调函数
     */
    try {
        callback(uId);
} catch (err) {
    // 记录错误信息
}
}
```

在用户注销登录后，需要调用window.TA17Obj.clearLoginUser\(\)方法

```
    try{
        window.TA17Obj.clearLoginUser();//注销登录后调用
    }catch(e){
        //记录错误信息
    }
```

**方式二：添加cookie**

在需要收集登录用户的页面设置cookie值。有以下要求：

* 名称：\_trs\_user
* 值：需要使用encodeURIComponent\(\)对用户信息进行编码
* 域：设置为一级域名，如www.haier.com的页面设置cookie的域为haier.com
* 路径：设置为根，/
* 失效时间：不设置，即为会话cookie

在注销登录时，可以调用ta.js提供的方法window.TA17Obj.clearLoginUser\(\)，也可以直接删除上面设置的cookie。





