### 3.2.3 具体实现

下面两种方式选择一种操作。

**方式一：**

需要在可以获取登录用户信息的页面，实现方法window.TA17Callbacks\_getAndSendLoginUser \(callback\)。该方法可以使用同步或异步方式获取用户信息，在获取成功后将回调函数callback\(\)放到try…catch语句中执行，并将用户标识uId信息作为callback\(\)的参数。

