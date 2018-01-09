### 3.2.2 用户信息采集原理

嵌入了ta.js的页面需要实现方法：window.TA17Callbacks\_getAndSendLoginUser \(callback\)，通过该方法可以获取当前登录用户信息的字符串表示--UID。当ta.js加载完成后，就会调用window. TA17Callbacks\_getAndSendLoginUser \(callback\)方法，并传入一个回调函数--callback；当嵌码页面获取到用户信息后，调用callback\(UID\)即可\(如果没有登录用户，可以将null或空字符串传入callback方法\)。

	ta.js在获得用户信息后，就会将其存储在cookie中，这样当用户跳转到其他未提供window. TA17Callbacks\_getAndSendLoginUser \(callback\)方法的页面，也同样可以在PV信息中携带用户信息。但该cookie为会话级别，在用户关闭浏览器后就会失效。

	在用户退出登录成功后，需要调用方法window.TA17Obj.clearLoginUser\(\)，该方法由ta.js定义，用于清除当前登录用户cookie。



