### 3.2.1 基本概念

* 访客Cookie：其实质就是网脉标记的浏览器ID，标识一台电脑（手机）上的一个浏览器。比如，一台设备上装了三种浏览器：IE、Firefox、Chrome，它们的访客Cookie是不同的。
*  登录用户：按某系统登录逻辑成功登录了的用户。

为了使采集到的信息含有系统登录了的用户标识，需要在登录页、退出页（不一定是页面）或其他特定页面实现指定的js回调函数，由ta.js调用，连同PV信息一同发给网脉采集服务端。
