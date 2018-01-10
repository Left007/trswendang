# 第2章 页面嵌码

给网站的所有页面嵌入标准的网脉采集代码，以实现PV、UV等用户基础访问行为的采集。

假设网站ID为【网站ID】，则在在需要统计的网页结尾的&lt;/body&gt;元素前，加入如下HTML代码：

```
<script id="_trs_ta_js" src="//ta.trs.cn/c/js/ta.js?mpid=【网站ID】" async="async" defer="defer"></script>
```

嵌码是非常关键的一步，影响到用户行为数据采集的准确性和完整性，特此提醒：

* **不同网站要嵌的代码是不同的，不能张冠李戴**，否则会影响采集数据的准确性；
* 为了不影响用户正常浏览网页，建议在**网页结尾的&lt;/body&gt;前嵌入这段代码**，而不是页面一开始处。另外，这段代码是异步加载的，即使出现不能访问等问题，也不会影响网页本身，可以放心嵌入。


