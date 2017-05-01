# CSS在移动端实现三角的几种方式

现在移动端盛行，PC基本也在淘汰IE6、7、8、9（呵呵 说大话了）。
现在好多手机端的样式该怎么写了，还是按照以前写PC的那种写法呢还是怎么样，比如这个尖角怎么写？而且有多少种写法呢？
此处放图片
嗯那就来试试吧，
第一种按照以前的写法肯定是切个图片上去了，简单了事兼容也一级棒，不但好控制，那点小东西也增加不了多少图片的大小，反正现在流量多而且到处都有WIFI。
第二种做法打个小于号‘&lt;’最好是实体‘&lt;’上去,它的大小是由 font-size 决定的，然后在上色color可以加粗font-width，就这么简单。
<pre>
&lt;div class=”header”&gt;&lt;i&gt;&lt;&lt;/i&gt;www.w3cbest.com&lt;/div&gt;
.header{background-color: #999;height: 40px;line-height: 20px;width: 320px;position: relative;padding: 10px;}
.header i{color:#fff;font-size: 26px;font-family: simsun;font-style: normal;}
</pre>
第三种用字体icon &lt;a href=”http://fontawesome.io” target=”_blank”&gt;fontawesome&lt;/a&gt;这是一个字体icon库，类似这样的字体icon有很多，中国代表性的是阿里巴巴的&lt;a href=”http://www.iconfont.cn/” target=”_blank”&gt;iconfont&lt;/a&gt;这个怎么用就不说了，你们大家应该都知道怎么用。
<pre>
&lt;div class=”header”&gt;&lt;i class=”fa fa-angle-left”&gt;&lt;/i&gt;www.w3cbest.com&lt;/div&gt;
.header{background-color: #999;height: 40px;line-height: 20px;width: 320px;position: relative;padding: 10px;}
.header i{color:#fff;font-size: 26px;}
</pre>
第四种用伪类来做::befor和::after通过设置宽高填充背景和css3旋转就可以做到如此效果。
<pre>
&lt;div class=”header”&gt;www.w3cbest.com &lt;/div&gt;
.header{position: relative;}
.header:before,.header::after{content: ”;position: absolute;left: 10px;height: 2px;width: 15px;background-color: #fff;}
.header:before{transform: rotate(-45deg);top: 15px;}
.header:after{transform: rotate(45deg);top:25px;}
</pre>
第五种也是用伪类来做::befor通过设置宽高和描相邻的两条边和css3旋转就可以做到如此效果。
<pre>
&lt;div class=”header”&gt;www.w3cbest.com&lt;/div&gt;
.header{position: relative;}
.header:before{content: ”;position: absolute;left: 10px;height: 15px;width: 15px;border-width:1px; border-style: solid; border-color: transparent transparent #fff #fff;}
.header:before{transform: rotate(45deg);top: 15px;}
</pre>
以上就是我整理的五种实现方法，有不好的地方大家就来喷我，如果你们还有更好的实现方法也可以提供出来，大家共同学习。
