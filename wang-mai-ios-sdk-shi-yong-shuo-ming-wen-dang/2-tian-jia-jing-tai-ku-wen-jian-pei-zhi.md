# 2 添加静态库文件配置

**1、将trs\_ta\_sdk.framework文件拖入到工程中。**

进入Capabilities打开Keychain Sharing状态为ON，工程中会出现一个后缀为.entitlements的文件,是为了存储唯一标识用的。这里一定一定要打开，否则会影响统计的准确性。

**2、添加以下2个Framework到工程中**

添加CoreTelephony.framework为了获取用户运营商信息。

如果需要统计经纬度则要添加CoreLocation.framework获取用户的经纬度信息。如果应用没有统计经纬度的需求，就不要有任何有关定位的设置，否则提交APPStore会被拒绝。

**3、ATS问题**

iOS SDK支持HTTPS网络请求。  


  

