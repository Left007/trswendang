## 2 间接嵌码方式

间接嵌码，指的是通过Ajax或其他方式获取嵌码的字符串形式，然后通过jquery或zepto的append\(\)方法添加到页面上。

如果使用jquery插件的append\\(\\)方法，可以使用上面（[1.直接嵌码](/wang-mai-qian-ma-ff08-han-jian-jie-qian-ma-fang-shi-ff09/1-tong-yong-xin-xi-cai-ji-qian-ma/11zhi-jie-qian-ma-fang-shi.md)）获取的嵌码。

由于zepto插件的问题，在使用append\(\)方法添加script标签时，不会请求src属性值所指向的文件，如果使用上面获取的嵌码，会导致ta.js不加载；而append\(\)添加script标签中的js代码可以执行，所以提供了下面的嵌码格式：

```
   <script>
    (function() {
        var ta = document.createElement("script");
        ta.id = "_trs_ta_js";
        ta.src = "//ta.8531.cn/c/js/ta.js?mpid=200";
        ta.setAttribute('async','async');
        ta.setAttribute('defer','defer');

        var s = document.getElementsByTagName("script")[0];
        s.parentNode.insertBefore(ta, s);
    })();
    </script>
```

只需要调整的ta.src的值，根据是否为Ajax页面\([1.2](/wang-mai-qian-ma-ff08-han-jian-jie-qian-ma-fang-shi-ff09/1-tong-yong-xin-xi-cai-ji-qian-ma/11zhi-jie-qian-ma-fang-shi/112-ajaxye-mian.md)\)、是否为单页面应用\([1.3](/wang-mai-qian-ma-ff08-han-jian-jie-qian-ma-fang-shi-ff09/1-tong-yong-xin-xi-cai-ji-qian-ma/11zhi-jie-qian-ma-fang-shi/113-dan-ye-mian-web-ying-yong.md)\)添加对应的标记。

由于代码比较多，所以应该仅在使用zepto进行间接嵌码时使用这种方式。

嵌码是非常关键的一步，影响到用户行为数据采集的准确性和完整性，特此提醒：

* **不同网站要嵌的代码是不同的**，不能张冠李戴，否则会影响采集数据的准确性；
* **一个页面只嵌一次这段代码**，不要多嵌，否则会影响采集数据的准确性；
* 为了不影响用户正常浏览网页，建议在网页**结尾的&lt;/body&gt;前**嵌入这段代码，而不是页面一开始处。另外，这段代码是异步加载的，即使出现不能访问等问题，也不会影响网页本身，可以放心嵌入；
* **如果网站还嵌入了谷歌统计、百度统计等代码，请将以上代码放在它们之前；**
* **不能使用innerHTML**将获取的嵌码添加到页面上，此时添加的script标签无效

（[https://www.w3.org/TR/2008/WD-html5-20080610/dom.html\#innerhtml0](https://www.w3.org/TR/2008/WD-html5-20080610/dom.html#innerhtml0)）

