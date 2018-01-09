### 1.1.2 Ajax页面

这里所说的“Ajax页面”是指，页面的文章内容是由Ajax获取并填充的，而非直接写入到HTML文档中。对这类页面的要求：**网页标题（即HTML的&lt;title&gt;元素）的值为空（即空字符串），然后在Ajax成功请求到文章内容后，再设置HTML的&lt;title&gt;的值（即通过js代码document.title来设置），并且必须有值，不能为空。**

需要在上面获取的代码中mpid后面增加标记“&waitTitle=true”（形式如下）。

`<script id="_trs_ta_js" src="//ta.8531.cn/c/js/ta.js?mpid=204&waitTitle=true" async="async" defer="defer"></script>`

