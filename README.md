#html&css终极教程

本系列教程持续更新中，欢迎各位同行补充完善。

##[MDN CSS reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)

这是一份很健全的css参考指南，话不多说，五颗星强烈推荐。

##[Mastering CSS Principles: A Comprehensive Guide](http://www.smashingmagazine.com/mastering-css-principles-comprehensive-reference-guide/)
涵盖一份[smashing magazine](http://www.smashingmagazine.com/)的css知识点列表，里面内容的丰富性就不必细说了，光smashing magazine这个大名就可以代表其分量了。

##基础汇集

###CSS选择器

* [选择器测试](http://www.css3.info/selectors-test/)
（提供了一份浏览器支持css1-3选择器的测试，更高级的选择器可参考[CSS Selectors from CSS4 till CSS1](http://css4-selectors.com/selectors/)）
* [CSS选择器的优化](http://www.w3cplus.com/css/css-selector-performance)

###重置
说起html&css，不得不说的是重置，之所以需要重置，是因为各个浏览器对于常用的标签元素可能带有一些基础的样式，而这些基础样式你不需要，所以就出现了重置。一般来说重置分为两种类型的重置，一种是归零式的，一种是修复式的。归零式的就是打倒再重建，比较有名的就是最简单的`*{margin:0;padding:0;}`和Eric [reset css](http://meyerweb.com/eric/tools/css/reset/)的；而修复式的目标则在比较各个浏览器样式的异同，对解析不太良好或和其他多数浏览器不一样的进行修复，以使各个浏览器表现一致，比较出名的就是[normalize](http://necolas.github.io/normalize.css/)。目前来说normalize的占有率越来越大，它主要分为两个版本，一个是包括ie6的，一个是从ie8开始，抛弃了ie6/7。

* [部分浏览器默认样式](http://www.iecss.com/)
* [Eric reset css](http://meyerweb.com/eric/tools/css/reset/)
* [normalize](http://necolas.github.io/normalize.css/)

###盒子模型
这个问题也经常烦死一帮新人，实际的情况就是设置的width到底包不包括border和padding，拿目前的浏览器来说，ie6+和主流浏览器表现其实都一个样，那就是设置的width不包括border和padding，也即是实际元素的宽度=width+border（左右）+padding（左右），高度也如此（ie正确表现的前提就是你得有个正确的文档申明，不要激活了ie的怪异模式，不然那就对不起了）。当然其实折腾的不是上面那些，而是部分表单元素，它们依然沿用了从前的盒子模型，即设置的width包括了border和padding。而从ie8+开始，出现了一个新属性box-sizing(border-box/padding-box/content-box)，让你明确的定义你需要的盒子模型。火狐和谷歌浏览器请添加各自的前缀-moz和-webkit。既然涉及宽度高度什么的计算，顺便推荐一个css3新属性calc

* [CSS3 Box-sizing ](http://www.w3cplus.com/content/css3-box-sizing)
* [CSS 盒模型](http://www.qianduan.net/css-box-model.html)
* [CSS3的calc()使用 ](http://www.w3cplus.com/css3/how-to-use-css3-calc-function.html)

###布局
布局从页面的可变化性来说可分为固定宽度布局，流体布局，弹性布局，响应式布局；从使用技术上来说可分为position，float，em，负margin，media queries，flex，columns，grids(目前只有ie10支持)等。当然我们的页面千变万化，但是万变不离其宗，你掌握了核心技术，应付那些都是小case了。（弱弱的说下，其实em，columns和grids我也没用过。）

* [固定宽度布局](http://www.w3cplus.com/blog/tags/181.html)
* [固定宽度布局解决方案](http://www.w3cplus.com/solution/layout/layout.html)
* [CSS中强大的EM](http://www.w3cplus.com/css/px-to-em)
* [负margin用法权威指南](http://www.w3cplus.com/css/the-definitive-guide-to-using-negative-margins.html)
* [layoutgala-负margin布局](http://blog.html.it/layoutgala/)
* [CSS布局——960gs](http://www.w3cplus.com/css/css-layout-with-960-grids)
* [Bootstrap研究1-精巧的网格布局系统](http://www.cnblogs.com/xieran/archive/2012/03/28/2421301.html)
* [CSS3 Multi-columns 之跨列 ](http://www.w3cplus.com/node/72)
* [深入了解 Flexbox 伸缩盒模型 ](http://www.w3cplus.com/blog/666.html)
* [flexbox ](http://www.w3cplus.com/blog/tags/157.html)
* [Giving Content Priority with CSS3 Grid Layout](http://24ways.org/2012/css3-grid-layout/)

###清除浮动
目前我们所说的清除浮动，大多数说的实际是清除子元素的浮动，所以严格来说应该是闭合浮动。在这里我们把两者分开，清除浮动指清除上级元素的浮动，对应的使用技术是clear:both/left/right/none。而闭合子元素的浮动技术就比较多了，目前比较流行的是clearfix和overflow技术，另外还有inline-block技术和添加空标签技术等。

* [那些年我们一起清除过的浮动](http://www.iyunlu.com/view/css-xhtml/55.html)
* [闭合浮动解决方案](http://www.w3cplus.com/solution/clearfloat/clearfloat.html)

###inline-block
不得不承认它是天使与魔鬼同体，介于inline和block之间，更像是他们两个合作的产物。它带来的最大问题就是间隙，很头疼的问题，以至于你想使用的时候还得考虑考虑是否值得。当然它的另一个问题就是该死的ie6/7问题，当块级元素设置为`inline-block`会有bug，但这不是什么问题，一个万能的`display:inline-block; *display:inline; *zoom:1;`就解决了。

* [inline-block 前世今生](http://www.iyunlu.com/view/css-xhtml/64.html)

##关于table
table还没死，很多时候你还需要它

* [A Complete Guide to the Table Element](http://css-tricks.com/complete-guide-table-element/)

###通过切换class来改变显示
上面的[固定宽度布局解决方案](http://www.w3cplus.com/solution/layout/layout.html)就运用了这种思路，不同的class,#main的宽度不同。用class来控制布局或显示是一种优秀的思想，可能我们更常见的就是jquery中的toggleClass了，这里我们一般用的还是属于初级的，如果思维再扩散点，你就会发现它可以应用的场景越多。

* [Adaptable view – how do they do it?](http://www.jankoatwarpspeed.com/adaptable-view-how-do-they-do-it/)

###图片替换文字
在还没有出现css3的时代，图片替换文字那绝对的必备技巧之一，其实哪怕css3横行的现在，这个技术也仍然不会过时。这个技术最流行的莫过于`text-indent:-9999px;`,当然随着技术的更新，又出现了新的方法，如css3版的`:before`方法。

* [可用性更好的CSS隐藏文字技术(CSS图片替换文字)](http://www.iyunlu.com/view/css-xhtml/62.html)
* [十种图片替换文本CSS方法](http://www.w3cplus.com/css/ten-image-replace-text-with-css)
* [My thoughts about the latest Image Replacement techniques](http://www.css-101.org/articles/image-replacement/the_new_new_image-replacement_techniques.php)
* [CSS image replacement with pseudo-elements (NIR)](http://nicolasgallagher.com/css-image-replacement-with-pseudo-elements/)

###滑动门
这个技术在css3没有出现前，常用来切各种按钮。它的技术关键在于两个标签的背景叠加，那样就刚好是我们需要的效果。其中的背景图我们可以根据实际情况切成两张图甚至是一张图。

* [滑动门那些事](http://www.aiubug.com/?p=326)

###等高设计
我这里说的等高把布局的等高和我们平常要处理多列的等高放在一起。等高分为模拟等高，实际等高和动态计算三种情况。模拟等高适用于布局，使用背景色或背景图片平铺，来达到视觉上的等高；实际等高最简单的就是一种设置统一的高度的了，当然这个对于动态的内容来说是不适合的，但对于一些小高度的列表，你如果知道了其中的最大高度还是很合适的，而另一种就是inline-block技术了；至于动态计算那就非js莫属了。多列等高见下一个项目列表设计

* [八种创建等高列布局 ](http://www.w3cplus.com/css/creaet-equal-height-columns)

###项目列表设计
项目列表设计总的来说包括四种，第一种是左右边缘没有间隔，第二种是上下左右间隔相等，第三种是各个item等高，第四种是以某种规律特殊化某个，如谷歌的插件列表

* [项目列表解决方案](http://www.w3cplus.com/solution/itemlist/itemlist.html)

###图文混排
图文混排的技术之多和图片替换文字的有得一拼了。总的来说图文混排包括最简单的给img设置一个float就ok的；也包括最常见的图片在左文字在右互不干扰的；当然还有复杂点的可以嵌套的如评论模块；最后就是现在不常见的奇偶行图文互换。

* [图文混排解决方案](http://www.w3cplus.com/solution/imagetextmix/imagetextmix.html)
* [CSS制作Facebook的媒体对象](http://www.w3cplus.com/css/facebook-status-message-design-with-css)

###ul/ol
关于ul/ol的重要性不言而喻，看看各大网站的源码就知道了。它最常见的地方就是导航，信息列表了。鉴于各个浏览器默认样式或margin或padding，我们一般在重置的时候都是重置为0；然后对于标题类的信息列表我们一般会加个小的icon作为背景以修饰，而作为非主导航的情况下可能还会加上不同icon标识，以有一个加强可辨别认识，也使网站增色不少；至于滚动图片那又是ul的一大经典应用；当然一些项目列表什么的就属于另一方面的更复杂点的应用了。

* [8 different ways to beautifully style your lists](http://www.marcofolio.net/css/8_different_ways_to_beautifully_style_your_lists.html)
* [纯css3有序列表](http://www.w3cplus.com/demo/387.html)
* [滚动图片结构分析](http://www.w3cplus.com/framework/imgslide/index.php)


###水平垂直居中
关于这个问题我只说一点，你就知道它是多么的闹心了：它经常出现在各大前端招聘的试题上啊。首先说下水平居中，这个比较好办，目前常用的有`text-align:center;`,`margin-left:auto;margin-right:auto;`还有相对/绝对元素的`left:50%;margin-left:-width`，除了text-align没有宽度限制，其余的对不起，都需要明确自己的宽度。再说下垂直居中，这个分为单行文字和其他，单行文字设置line-height等于父元素的height就垂直居中了，当然对于知道自己高度的还是比较好搞定的，用相对/绝对元素的`top:50%;margin-top:-height`，对于未知高度的那就比较复杂了。所有这些归到最后就是知道自己宽度高度的水平垂直居中都是纸老虎，真正要考的一般就是最变态的未知宽高的水平垂直居中啊。这要是css3没有出现，那这些未知宽度可得纠结死了，而现在[flex](http://www.w3cplus.com/blog/666.html)这个为布局而生的属性，一句margin:auto就可以轻松解决了；当然[tranform](http://www.w3cplus.com/content/css3-transform)中的translate的50%也是很好用的，它的50%是自己的一半，而left，top之类的50%是它的父元素的一半。总之涉及到的技术有Position, Negative Margins, Transforms, Table-Cell, Inline-Block, Flexbox等

* [Centering in CSS: A Complete Guide](http://css-tricks.com/centering-css-complete-guide/)
* [CSS制作图片水平垂直居中](http://www.w3cplus.com/css%2520/img-vertically-center-content-with-css)
* [CSS制作水平垂直居中对齐](http://www.w3cplus.com/css/vertically-center-content-with-css)
* [关于元素水平居中](http://www.aiubug.com/?p=427)
* [flex](http://www.w3cplus.com/blog/666.html)
*  [Absolute Horizontal And Vertical Centering In CSS](http://coding.smashingmagazine.com/2013/08/09/absolute-horizontal-vertical-centering-css/)

###tabs选项卡设计
我们这里把选项卡大体分为两类，一种是有border-bottom的，我们称为线条边框类型，一种是纯颜色色块类的，我们称为颜色块类型。一般来说线条边框的比颜色块的要复杂点，因为要考虑到下面的那个border-bottom。然后当为线条框架的时候，有些tabs是紧凑的，并且所有的tabs标题宽度加起来刚好与下面的内容的宽度一致，那么这个时候的border-bottom还是很简单的，直接就是tabs标题的border-bottom就可以了，但是当总的标题宽度小于下面内容的宽度，又或者标题之间有间隔，那么这个时候的border-bottom要处理就得用点手段了

* [css tab标题解决方案](http://www.w3cplus.com/solution/tabs/tabs.html)
* [选项卡标题设计](http://www.w3cplus.com/framework/tabs/index.php)

###透明度使用
透明度分为opacity和rgba/,他们的区别在于：Opacity的透明属于全层透明，子元素中无法覆写；而Rgba透明用于color或background-color的透明，不影响到子元素

* [一个关于透明度继承的问题](http://www.css88.com/archives/746)
* [CSS3 RGBA ](http://www.w3cplus.com/content/css3-rgba)

###大背景设计
大背景一般需要考虑的是如何兼容到超大屏幕。所以一般切大背景的时候得考虑在背景不够的地方应该使用一个渐变的背景或纯色来填充，以达到柔和过度的效果，而不是愣生生的感觉。

* [如何用CSS实现大背景样式](http://www.w3cplus.com/css/how-to-css-large-background)

###整块可点击设计
本来这个不是什么问题，把所有的标签放在a里面就可以点击了。但是正是因为如此，a里面嵌套了p，div等块级元素而变得不合理。所以如果是简单的文字信息，可以a里面嵌套strong,span等，如果是复杂点的，请不要把所有的元素用a包裹起来，而是使用js代码来变相解决这个问题:当整个区块点击时，找到里面a元素的href值，然后设置window.location等于这个href值。（对于html5来说a标签是可以嵌套块级元素的。）

* [Web设计师值得收藏的10个jQuery特效(1)](http://developer.51cto.com/art/201011/235489.htm) 第6个

###border变身
border能做什么，也许超乎了你的想象。用border制作三角时，如果要兼容ie6，注意设置透明部分的border的style为dashed，然后加上`overflow:hidden;`。

* [border解决方案](http://www.w3cplus.com/solution/border/border.html)
* [纯CSS制作的图形效果](http://www.w3cplus.com/css/create-shapes-with-css)

###面包屑设计
关于面包屑比较有意思的就是可以简单得不可思议，也可以复杂的让你吐血。其实这正是设计的魅力。至于简单的直接标签都不用加什么修饰的就不用说了，下面给了三个教程说下那些箭头设计的魅力。

* [http://veerle-v2.duoh.com/blog/comments/simple_scalable_css_based_breadcrumbs](http://veerle-v2.duoh.com/blog/comments/simple_scalable_css_based_breadcrumbs)
* [CSS制作面包屑 ](http://www.w3cplus.com/demo/css-create-breadcrumb.html)
* [藤藤每日一练——CSS3 Animation Breadcrumbs ](http://www.w3cplus.com/demo/CSS3-Animation-Breadcrumbs.html)

###星级评论设计
简单来说星级评论包括三种，一种是用来展示点评结果的，你不能参与点评；第二种是用来点评的，你可以投票，且只有你自己的投票结果；最后一种就是前两者结合起来，既展示前人点评的结果，而你又能参与点评的。第一种的最好解决，直接两层元素就可以搞定，一层负责灰色的背景图，一层负责显示红色的结果，结果的宽度用百分比表示；第二种的就需要好几个标签了，一颗星一个元素，因为需要做鼠标滑过的效果，滑过第几颗星，它前面所有的元素也得改变状态，所以得js配合添加class；至于第三种就更复杂了，如果展示的时候加入了半颗星那就更复杂了，目前想到的是里面分为上面的两个部分，通过定位的方式默认显示的是点评结果，鼠标滑过显示可以点评的部分。
这方面的教程搜索了半天就找了一个第二种的。

* [星级评分系统](http://js.fgm.cc/learn/lesson4/09.html)

###sticky footer
之所以叫sticky footer而不叫fixed footer，是因为这个不是一般的用fixed来固定在视窗底部的，而是当页面不够一屏的时候，footer在视窗的底部，而当其超过一屏，那么就在页面的底部而不是视窗的底部。当然要做这个效果对于整体的html结构是有要求的，里面必须用到的技术就是min-height:100%。

说到sticky，不得不说一个新的属性：`position:sticky;`。它的表现类似`position:relative`和`position:fixed`的合体，在目标区域在屏幕中可见时，它的行为就像`position:relative`; 而当页面滚动超出目标区域时，它的表现就像`position:fixed`，它会固定在目标位置。(跟sticky footer没有任何关系，只是有一个sticky这个单词而已。)

* [sticky footer](http://www.w3cplus.com/css/css-sticky-foot-at-bottom-of-the-page)
* [position:sticky介绍](http://www.qianduan.net/position-sticky-introduction.html)

###z-index层级
这个问题之所以被提到这里，还是因为ie6/7，如果你直接从ie8+开始做兼容那就飘过吧。说到底ie6/7的z-index是基于它的父元素来的，关于这个新手碰到最典型的问题就是二级菜单被下面的滚动图片给遮挡住了，而另一个就是select的层级问题。而抛出z-index可以改变层级外，其实opacity也可以改变层级，详见第二个链接。

* [CSS教程：彻底掌握Z-index属性](http://www.cnblogs.com/gisdream/archive/2010/06/10/1755891.html)
* [What No One Told You About Z-Index](http://philipwalton.com/articles/what-no-one-told-you-about-z-index/)

###生成内容(::before,::after,content)
主要是应用伪元素`::before`,`::after`的content生成内容。看起来很简单，却强大到令人发指，只能感叹想不到，万万想不到，包括下面的@font-face制作图标也是其强大的一面。

* [How To Benefit From CSS Generated Content And Counters](http://coding.smashingmagazine.com/2013/04/12/css-generated-content-counters/)
* [One Div](http://one-div.com/)

###文字效果
关于文字的设计当然和阴影离不开，这个主要就是对text-shadow的应用了；其次应该是一些比较简单的渐变文字了，这个关键就在于使用蒙版遮罩，蒙版由半透明到纯透明，盖在文字的上面就是渐变文字了。在css3强大的今天图片的方法肯定是有历史的了，先进的谷歌浏览器就可以使用mask来搞定文字的渐变；最后不得不说的就是强大的@font-face，话说这个创立之初是用来解决自定义字体的问题，可是现在被强悍的应用在icon了，多么美丽的神话。

* [30 Useful and Cutting Edge CSS3 Text Effect and Web Typography Tutorials](http://www.1stwebdesigner.com/css/css3-text-effects-typography/)
* [CSS Gradient Text Effect](http://webdesignerwall.com/tutorials/css-gradient-text-effect)
* [Pure CSS text gradient (no PNGs)](http://nicewebtype.com/notes/2009/07/24/pure-css-text-gradient-no-pngs/)
* [CSS3 @font-face](http://www.w3cplus.com/content/css3-font-face)
* [IcoMoon](http://icomoon.io/app/)

###图片美化
图片美化包括添加边框，圆角([border-radius](http://www.w3cplus.com/node/48))，阴影([box-shadow](http://www.w3cplus.com/content/css3-box-shadow))，滤镜效果等。这里说下对于ie6-8不支持图片的圆角怎么去搞，主要的思路就是制作一个中间透明，四角为纯色的图片，然后遮盖在图片上，透明的部分就会显示出我们的图片。

* [CSS3 Filter的十种特效](http://www.w3cplus.com/css3/ten-effects-with-css3-filter)
* [AlloyImage 步入web图像处理时代](http://alloyteam.github.io/AlloyPhoto/)

###图片优化
图片的优化包括裁减，压缩，合并等。裁减可以使用css的clip来搞，压缩那当然得使用工具了，至于合并那就得考虑sprite了，当然合并应该有原则，这样在后期维护的时候才不会使人疯狂。

* [纯CSS制作缩略图片](http://www.w3cplus.com/css/pure-css-create-faux-image-cropping)
* [hhhhold-在线图片，可定义大小](http://hhhhold.com/)
* 在线图片压缩：[jpegmini](http://jpegmini.com/)，[tinyPNG](http://tinypng.org/)，[Smush.it](http://www.smushit.com/ysmush.it/)
* [Encode Data URL](http://www.pjhome.net/web/html5/encodeDataUrl.htm)
* [CSS Sprites: CSS图片合并技术详解 - 中文版](http://paranimage.com/css-sprites-guidelines/)，[The Mystery Of CSS Sprites: Techniques, Tools And Tutorials - 英文版	](http://coding.smashingmagazine.com/2009/04/27/the-mystery-of-css-sprites-techniques-tools-and-tutorials/)

###form表单设计
form表单一说起来一肚子苦水，不想说了。

* [form解决方案](http://www.w3cplus.com/solution/form/form.html)，这是初版的，分析及设计思路说得还算明白，凑合着先看下，道理是一样的。下面两个是关于html5 form的知识
* [IE10开发手册之form](http://msdn.microsoft.com/en-us/library/ie/hh673544%28v=vs.85%29.aspx)
* [A Form of Madness](http://diveintohtml5.info/forms.html)

##css3

###[css3 files](http://www.css3files.com/)
这是一套非常棒的css3学习教程，包括了animateion，background，border，color，font，gradient，shadow，text，transform，transition等。

###transform, transition
- [Advanced CSS3 2D and 3D Transform Techniques](http://www.sitepoint.com/advanced-css3-2d-and-3d-transform-techniques/)
- [Intro to CSS 3D transforms](http://desandro.github.io/3dtransforms/)
- [All you need to know about CSS Transitions](http://blog.alexmaccaw.com/css-transitions)
- [好吧，CSS3 3D transform变换，不过如此！](http://www.zhangxinxu.com/wordpress/2012/09/css3-3d-transform-perspective-animate-transition/)

###flex
- flex标准版详解：英文版 - [Dive into Flexbox](http://weblog.bocoup.com/dive-into-flexbox/)，中文版 - [深入了解 Flexbox 伸缩盒模型](http://www.w3cplus.com/blog/666.html)
- flex三大版本对比：英文版 - [Designing CSS Layouts With Flexbox Is As Easy As Pie](http://coding.smashingmagazine.com/2013/05/22/centering-elements-with-flexbox/)，中文版 - [Flexbox制作CSS布局易如反掌](http://www.w3cplus.com/css3/designing-css-layout-with-flexbox.html) 
- [Using CSS flexible boxes](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Flexible_boxes)

###[Animatable](http://leaverou.github.io/animatable/)
一份动画属性参考

###[List of Pseudo-Elements to Style Form Controls](http://tjvantoll.com/2013/04/15/list-of-pseudo-elements-to-style-form-controls/)
一份详细的表单伪元素说明

###w3cplus css3教程

####css3选择器

* [基本选择器](http://www.w3cplus.com/css3/basic-selectors)
* [属性选择器](http://www.w3cplus.com/css3/basic-selectors)
* [伪类选择器 ](http://www.w3cplus.com/css3/pseudo-class-selector)

####css3属性详解

* [box-sizing](http://www.w3cplus.com/content/css3-box-sizing)
* [border-radius](http://www.w3cplus.com/node/48)
* [border-image](http://www.w3cplus.com/content/css3-border-image)
* [border-color](http://www.w3cplus.com/content/css3-border-color)
* [box-shadow](http://www.w3cplus.com/content/css3-box-shadow)
* [text-shadow](http://www.w3cplus.com/node/52)
* [text-overflow](http://www.w3cplus.com/content/css3-text-overflow)
* [word-wrap](http://www.w3cplus.com/content/css3-word-wrap)
* [@font-face](http://www.w3cplus.com/content/css3-font-face)
* [rgba](http://www.w3cplus.com/node/45)
* [gradient](http://www.w3cplus.com/content/css3-gradient)
* [background-size](http://www.w3cplus.com/content/css3-background-size)
* [background-clip](http://www.w3cplus.com/content/css3-background-clip)
* [background-origin](http://www.w3cplus.com/content/css-background-origin)
* [Multiple Backgrounds](http://www.w3cplus.com/content/css3-multiple-backgrounds)
* [transform](http://www.w3cplus.com/content/css3-transform)
* [transition](http://www.w3cplus.com/content/css3-transition)
* [animation](http://www.w3cplus.com/content/css3-animation)
* [calc](http://www.w3cplus.com/css3/how-to-use-css3-calc-function.html)
* [appearance](http://www.w3cplus.com/css3/changing-appearance-of-element-with-css3.html)
* [::selection](http://www.w3cplus.com/content/css-selection)
* [rem](http://www.w3cplus.com/css3/define-font-size-with-css3-rem)
* [filter](http://www.w3cplus.com/css3/ten-effects-with-css3-filter)
* [@supports](http://www.w3cplus.com/css3/css3-supports.html)
* [flex](http://www.w3cplus.com/blog/666.html)
* [columns](http://www.w3cplus.com/node/72)
* [grids](http://24ways.org/2012/css3-grid-layout/)

##响应式
响应式涉及的知识点比较多，总的来说可以分为布局设计，图片视频设计，尺寸断点判断，导航设计，table设计，图标应用，表单元素设计，js交互设计，分辨率像素等。在输出内容方面，最简单的是全部输出然后通过css来控制是否显示，比较科学合理的是通过后端程序判断平台，来决定是否输出该区块内容。对于一些比较复杂大型的站点，建议pc和tablet可以公用一套html代码，而针对mobile则另外设计一套；对于一些比较简单的站点可以pc，tablet，mobile三者合一。

- [响应式设计资源总汇](http://bradfrost.github.io/this-is-responsive/resources.html)
- [Responsive设计的关键三步](http://www.w3cplus.com/css3/responsive-design-in-3-steps)
- [Responsive设计的十个基本技巧 ](http://www.w3cplus.com/css3/10-basic-tips-about-responsive-design.html)
- [响应式导航菜单在移动端的制作方法与解决方案](http://www.w3cplus.com/css3/responsive-mobile-navigation-menumethods-and-solutions.html)
- [CSS3 Media Queries 片段](http://www.w3cplus.com/blog/715.html)
- [响应式图片设计](http://www.w3cplus.com/css/flexible-images.html)
- [Clown Car Technique: Solving Adaptive Images In Responsive Web Design](http://coding.smashingmagazine.com/2013/06/02/clown-car-technique-solving-for-adaptive-images-in-responsive-web-design/)
- [响应式网页字体图标](http://www.w3cplus.com/css3/responsive-webfont-icons.html)
- [Responsive Data Table Roundup](http://css-tricks.com/responsive-data-table-roundup/)
- [各种设备尺寸](http://screensiz.es/)
- [viewport双城记](http://99jty.com/?p=1299)
- [Respond.js](https://github.com/scottjehl/Respond)

##bug
###IE haslayout
说实话真是不愿提及这个东西，但只要该死的ie6/7不消亡（ie8+没有了这个东西），这个东西你还不得不提。最常用的莫过于`*zoom:1;`,这可是解决ie6 bug的杀手级方案。这东西一两句话也说不明白，具体请看下面链接的文章吧。

* [IE hasLayout的问题总结 - 中文版](http://www.cnblogs.com/yupeng/archive/2011/04/11/2012996.html)，[IE hasLayout - 英文版](http://haslayout.net/haslayout)

###IE bug
知道怎么去打ie的bug，也是一位合格的csser必备的。但是总有人把bug运用的“淋漓尽致”，于是乎ie6/7 bug满天飞，超乎想象，但是不服不信，人家切出来的图跟设计图是相当的符合，所以照样过关。在他们眼中没有标准，他们的方法是见招拆招。对此，这篇教程只想说，bug是有限的，而且如果你对技术了解更多的话，bug就越少，甚至于直接绕过部分bug。当然在修炼好自己的同时，我们也希望ie6/7加速退亡，那样我们会轻松很多。

* [IE BUG相关文章集合](http://www.qianduan.net/ie-bug-resources.html)

###主流浏览器的Hack写法 
虽然浏览器越来越牛，bug越来越少，但是没办法，没有哪个浏览器是完美的，跟人一样，所以学会给各个浏览器打bug还是很有必要的。

* [主流浏览器的Hack写法](http://www.w3cplus.com/css/browser-hacks.html)

##css性能

##经验技巧
所谓经验技巧都是些前人总结的一些小东西，他们把踩过的坑，弯过的路，曾经的不成熟代码纠正改过，以方便后人乘凉。里面实用的东西多多，稍微一句简单的代码，加以修饰，废话连篇起来就是一篇文章。

* [11个让你代码整洁的原则](http://www.w3cplus.com/html/11-principles-for-keeping-your-code-clean)
* [十个CSS小技巧](http://www.w3cplus.com/css/ten-css-tips)
* [15个CSS技巧和窍门](http://www.w3cplus.com/css/15-css-tips-and-tricks)
* [20个CSS实战技巧](http://www.w3cplus.com/css/20-css-code-snippets-to-make-you-a-better-coder)
* [13个CSS技巧](http://www.w3cplus.com/css/13-premium-one-line-css-tips)
* [7个不能遗忘的CSS样式](http://www.w3cplus.com/css/7-css-tips-from-html5-boilerplate-websites)
* [20个实用的CSS技巧代码](http://www.w3cplus.com/css/20-incredibly-useful-CSS-snippets-for-developers)
