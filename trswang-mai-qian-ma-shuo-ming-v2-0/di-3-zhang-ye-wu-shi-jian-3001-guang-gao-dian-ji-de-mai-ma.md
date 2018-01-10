# 第3章 业务事件、广告点击的埋码

为了精准地统计某些重点业务事件的点击情况，可对该事件的按钮（或点击链接）进行埋码，要增加五个自定义的HTML属性，如下（注意：添加自定义HTML属性的元素需要是&lt;a&gt;、&lt;input&gt;或&lt;button&gt;；属性名的字母均为小写）：

data-trs-ta-event-key：事件名称，必填；值从下表

data-trs-ta-event-type：事件类别，必填；

data-trs-ta-event-item：对象标识（比如：广告ID、产品型号等这种标识信息），非必填；

data-trs-ta-event-itemname：对象名称（便于业务人员看数据，比如广告的名称、产品的名称等），非必填；

data-trs-ta-event-itemtype：对象所属类别（比如：广告位、产品类别），非必填；

data-trs-ta-event-itemnum：对象数量，类型为整数；非必填；

data-trs-ta-event-itemprice：对象价格，类型为小数，保留两位小数；非必填；

其中，事件名称和事件类别不能随意填写；支持的事件名称及类别见下面的表格：

| data-trs-ta-event-key （事件名称） | 事件说明 | data-trs-ta-event-type（事件类别） | 类别说明 |
| :--- | :--- | :--- | :--- |
| addCart | 添加购物车 | buy | 购买类 |
| jd | 引导去京东（第三方）购买 | leadToEx | 引导类 |
| suning | 引导去苏宁（第三方）购买 | leadToEx | 引导类 |
| tmall | 引导去天猫（第三方）购买 | leadToEx | 引导类 |
| ehaier | 引导去海尔商城购买 | leadToEx | 引导类 |
| diy | 引导去diy | leadToEx | 引导类 |
| gome | 引导去国美（第三方）购买 | leadToEx | 引导类 |
| aditem | 广告 | adshow | adshow |

示例如下：

```
<p><input type="button" value="添加购物车" data-trs-ta-event-key="addCart" data-trs-ta-event-type="buy" data-trs-ta-event-itemtype="冰箱" data-trs-ta-event-item="BC-130A" ></input></p>
<p><a href="http://jd.com/" data-trs-ta-event-key="jd" data-trs-ta-event-type="leadToEx" data-trs-ta-event-itemtype="冰箱" data-trs-ta-event-item="BC-130A" >去京东</a></p>
```

广告的示例：

```
<a href="http://jd.com/someAd.html" data-trs-ta-event-key="aditem" data-trs-ta-event-type="adshow" data-trs-ta-event-itemtype="广告位名称" data-trs-ta-event-item="广告ID" data-trs-ta-event-itemname="广告名称" ><img src="../ad1.jpg" alt="广告1图片"/></a>
```



