![](https://raw.githubusercontent.com/miemiewang/gitskills/master/images/1.png)
#一．Html+css部分
##1.html+css 
###对html的梳理： 
####（1）w3c标准：
网页主要由三部分组成：结构、表现和行为。  
对应的标准也分三方面：结构化标准语言主要包括XHTML和XML，表现标准语言主要包括CSS，行为标准主要包括对象模型（如W3C DOM）、ECMAScript等。
####（2）Doctype：
DOCTYPE标签是一种标准通用标记语言的文档类型声明，它的目的是要告诉标准通用标记语言解析器，它应该使用什么样的文档类型定义（DTD）来解析文档。
####（3）Html结构的语义化：
* 去掉或样式丢失的时候能让页面呈现清晰的结构
*  屏幕阅读器（如果访客有视障）会完全根据标记来“读”你的网页.例如,如果使用的含语 义的标记,屏幕阅读器就会“逐个拼出”单词,而不是试着去对它完整发音
*  PDA、手机等设备可能无法像普通电脑的浏览器一样来渲染网页（通常是因为这些设备对CSS的支持较弱）使用语义标记可以确保这些设备以一种有意义的方式来渲染网页.理想情况下,观看设备的任务是符合设备本身的条件来渲染网页.
*  语义标记为设备提供了所需的相关信息,就省去了你自己去考虑所有可能的显示情况。搜索引擎的爬虫也依赖于标记来确定上下文和各个关键字的权重
*  你的页面是否对爬虫容易理解非常重要,因为爬虫很大程度上会忽略用于表现的标记,而只注重语义标记。

####（4）浏览器的内核：
*  IE: trident内核
*  Firefox：gecko内核（网页浏览速度最快的内核）
*  Safari:webkit内核
*  Opera: 以前是presto内核，Opera现已改用Google Chrome的Blink内核
*  Chrome:Blink(基于webkit，Google与Opera Software共同开发)
####（5）浏览器的怪异模式和标准模式：
要想写出跨浏览器的CSS，必须知道浏览器解析CSS的两种模式：标准模式(strict mode)和怪异模式(quirks mode)。  
标准模式是指，浏览器按W3C标准解析执行代码；怪异模式则是使用浏览器自己的方式解析执行代码，因为不同浏览器解析执行的方式不一样，所以我们称之为怪异模式。浏览器解析时到底使用标准模式还是怪异模式，与网页中的DTD声明直接相关，DTD声明定义了标准文档的类型（标准模式解析）文档类型，会使浏览器使用相应的方式加载网页并显示，忽略DTD声明,将使网页进入怪异模式(quirks mode)。

####（6）盒模型： 
![](https://raw.githubusercontent.com/miemiewang/gitskills/master/images/2.png)
![](https://raw.githubusercontent.com/miemiewang/gitskills/master/images/3.png)   

*  W3C 盒子模型的范围包括 margin、border、padding、content，并且 content 部分不包含其他部分
*  IE 盒子模型的范围也包括 margin、border、padding、content，和标准 W3C 盒子模型不同的是：IE 盒子模型的 content 部分包含了 border 和 padding

####（7）行内元素与块级元素
* 块级元素：块状元素排斥其他元素与其位于同一行，可以设定元素的宽和高，块级元素一般是其他元素的容器，可容纳块级元素和行内元素。常见的块级元素有div, p ,h1~h6等
* 行内元素：行内元素不可以设置宽和高，但可以与其他行内元素位于同一行，行内元素内一般不可以包含块级元素。行内元素的高度一般由元素内部的字体大小决定，宽度由内容的长度控制。常见的行内元素有a, em ,strong等。   
<p>行内元素与块级元素可以通过设置display的属性来转换。<br/>
注：img和表单元素为替换元素，有内在尺寸，具有width和height，也可以设定。</p>

####（8）xhtml,xml和html的区别：
<p>html(超文本标记语言)——xhtml(可扩展性超文本标记语言)——xml（可扩展性标记语言）;</p>
* Xhtml:web标准(div+css)
* Xml:公共格式，不依附于特定浏览器  
* html最终会发展到xml，xhtml是html向xml发展的一个过渡，xhtml的特性也适合xml;
<p>html： 对大小写不敏感； 标签不必成对出现；<br/>
XHML:对大小写敏感，必须是小写的； 标签必须成对出现，有开始标签就必须有结束标签； 属性值必须在引号之内； 不支持属性最小化( eg：正确：`<input checked='checked'> `
错误：`<input checked> ` ); name属性不赞成使用，以后会被淘汰； 空元素也要结束标签：如：`<br/>`,`<hr/>`(水平分割线) <p>
####（9）src与href的区别： 
* src用于替换当前元素，href用于在当前文档和引用资源之间确立联系。
* src是source的缩写，指向外部资源的位置，指向的内容将会嵌入到文档中当前标签所在位置；在请求src资源时会将其指向的资源下载并应用到文档内，例如js脚本，img图片和frame等元素。`<script src =”js.js”></script>`当浏览器解析到该元素时，会暂停其他资源的下载和处理，直到将该资源加载、编译、执行完毕，图片和框架等元素也如此，类似于将所指向资源嵌入当前标签内。
* href是Hypertext Reference的缩写，指向网络资源所在位置，建立和当前元素（锚点）或当前文档（链接）之间的链接，如果我们在文档中添加<link href=”common.css” rel=”stylesheet”/>那么浏览器会识别该文档为css文件，就会并行下载资源并且不会停止对当前文档的处理。

#### （10）外边距重叠：
<p>在CSS当中，相邻的两个盒子（可能是兄弟关系也可能是祖先关系）的外边距可以结合成一个单独的外边距。</p>

* 折叠结果遵循下列计算规则：
  * 两个相邻的外边距都是正数时，折叠结果是它们两者之间较大的值。
  * 两个相邻的外边距都是负数时，折叠结果是两者绝对值的较大值。
  * 两个外边距一正一负时，折叠结果是两者的相加的和。
* 外边距重叠的例外：
  * 水平边距永远不会重合。
  * 相邻的盒模型中，如果其中的一个是浮动的（float），垂直margin不会重叠，并且浮动的盒模型和它的子元素之间也是这样。
  * 设置了overflow属性的元素和它的子元素之间的margin不被重叠（overflow取值为visible除外）。
  * 设置了绝对定位（position:absolute）的盒模型，垂直margin不会被重叠，并且和他们的子元素之间也是一样。
  * 设置了display:inline-block的元素，垂直margin不会重叠，甚至和他们的子元素之间也是一样。
  * 如果一个盒模型的上下margin相邻，这时它的margin可能重叠覆盖它。在这种情况下，元素的位置取决于它的相邻元素的margin是否重叠。
     *  如果元素的margin和它的父元素的margin-top重叠在一起，盒模型border-top的边界定义和它的父元素相同。
     *  另外，任意元素的父元素不参与margin的重叠，或者说只有父元素的margin-bottom是参与计算的。一个应用了清除操作的元素的margin-top绝不会和它的块级父元素的margin-bottom重叠。
     *  根元素的垂直margin不会被重叠
* 防止外边距重叠：
  * 外层元素padding代替
  * 内层元素透明边框 border:1px solid transparent;
  * 内层元素绝对定位 postion:absolute:
  * 外层元素 overflow:hidden;
  * 内层元素 加float:left;或display:inline-block;
  * 内层元素padding:1px;

###对css的梳理：

####（1）css选择器
* 如果样式是行内样式（通过Style=””定义），那么a=1
*  b为ID选择器的总数
*  c为Class类选择器的数量。
*  d为类型选择器的数量
*  属性选择器，伪类选择器和class类选择器优先级一样，伪元素选择器和类型选择器一样
*  !important 权重最高，比 inline style 还要高  
例如：
`#wrapper #content .focus` (0,2,1,0)
`.wrap div a`(0,0,1,2)

####（2）Display
* Block:默认宽度为父元素宽度，可设置宽高，换行显示
* Inline:默认宽度为内容宽度，不可设置宽高，同行显示
* Inline-block:默认宽度为内容宽度，可设置宽高，同行显示，整块换行

####（3）display:none和visibility:hidden
* Display:none隐藏对应元素但不挤占该元素原来的空间，宽高将丢失
* Visibility:hidden 隐藏对应元素并且挤占该元素原来的空间

####（4）z-index
* 使用条件
 * 有position属性且值不为static
* 堆栈上下文：
 * 当一个元素是文档的根元素(html)
 * 当一个元素有一个position值且不为static,有一个z-index值且不为auto
 * 当一个元素的opacity小于1

####（5）Position：
* Relative:元素仍在文档流中  参照物为元素本身
* absolute:默认宽度为内容宽度  脱离文档流（后面的元素会浮上来） 参照物为一个定位祖先元素/根元素（祖先元素定位最好为relative,因为不会脱离文档流，只当参照物使用；根元素为html）
* Fixed:默认宽度为内容宽度&nbsp;&nbsp;&nbsp;&nbsp;脱离文档流&nbsp;&nbsp;&nbsp;&nbsp;参照物为视窗

####（6）float:
* 默认宽度为内容宽度  脱离文档流  向指定方向一直移动
* Float元素在同一文档流
* Float元素半脱离文档流，对于元素，脱离文档流，对内容，在文档流

#####Float清除浮动的四种方式：
* 在父元素最后增加一个空元素，div或br（本身会多出一行，height应设为0），将其css样式设为clear:both
* 将父元素样式设为overflow:hidden,zoom:1（用于兼容ie6）
*  给父元素增添伪类:after{display:block;clear:both;content:”";visibility:hidden;height:0;}
*  将父元素设为浮动（本身会脱离文档流，并且宽度为内容宽度）；

####（7）布局解决方案：

#####居中布局
`<div class='parent'>`   
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `<div class='child'>demo</div>` <br/>
 `</div>`

* 水平居中

###### inline-block+text-align
.parent{text-align:center;}   
 .child{display:inline-block;}

######table+margin
.child{display:table;margin:0 auto;}

######absolute+transform
.parent{position:relative;}  
.child{position:absolute;left:50%;transform:translateX(-50%);}

######flex+justify-content
.parent{display:flex;justify-content:center;}

* 垂直居中
######table-cell+vertical-align
.parent{display:table-cell;vertical-align:middle;}
######absolute+transform
.parent{position:relative;}  
.child{position:absolute;transform:translateY(-50%);top:50%;}
######flex+align-items
.parent{display:flex;align-items:middle;}

* 水平垂直居中
######inline-block+vertical-align+text-align+table-cell
.parent{display:table-cell;text-align:center;vertical-align:middle;}  
.child{display:inline-block;}
######absolute+transform
.parent{position:relative;}  
.child{position:absolute;left:50%;top:50%;transform:translate(-50%,-50%)
######flex+justify-content+align-items
.parent{display:flex;justify-content:center;align-items:middle;}
####多列布局
 `<div class='parent'>`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`<div class='left'>left</div>`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`<div class='right'><p>right</p><p>right</p></div>`  
`</div>`

* 定宽与自适应
######float+margin
.left{float:left;width:100px;}  
.right{margin-right:100px;}
######float+overflow
.left{float:left;width:100px;}  
.right{overflow:hidden;}
######table+table-cell
.parent{display:table;width:100%;}   
.left,.right{display:table-cell;}  
.left{width:100x;}
######flex
.parent{display:flex}  
.left{width:100px;}  
.right{flex:1;}

* 不定宽与自适应
######float+overflow
######flex
##2.Html5+css3

####（1）Viewport
* Viewport概念：设备屏幕上用来显示网页的那块区域，一般情况下，viewport大于浏览器可视区域，所以有横向滚动条
*  Css中的1px并不等于设备的1px，早期css像素等于一个屏幕物理像素，后来移动设备分辨率提高了，但屏幕尺寸没变，所以1px代表大于1px的物理像素
*  每个移动设备浏览器都有一个理想宽度，指css宽度，可以用devide-width设置<meta name=”viewport” content=”width=device-width, user-scalable=yes, initial-scale=2.5, maximum-scale=5.0, minimun-scale=1.0”>
 *  width和height指令分别指定视区的逻辑宽度和高度
 *  user-scalable指令指定用户是否可以缩放视区，即缩放Web页面的视图。
 *  initial-scale指令用于设置Web页面的初始缩放比例。
 *  maximum-scale和minimum-scale指令用于设置用户对Web页面缩放比例的限制。

####（2）rem和em
* em  
 * 当使用em单位时，像素值是em值乘以使用em单位的元素的字体大小，例如如果一个div有18px字体大小，10em等同于180px  
 * Em的继承：
Em单位是相对于使用em单位的元素的字体大小，父元素的字体大小可以影响em值纯粹是因为继承，如果根元素字体大小为16px，一个子元素里padding为1.5em，该div将从根元素继承字体大小16px，因此padding会解析成1.5`*`16=24px 
如果多加一个`div`包裹原先的div，然后将其字体大小设为1.25em，原始的div的padding值为16`*`1.25`*`1.5=30px;
*  Rem:  
  * 像素值是由html元素里的字体大小决定的，此字体大小会被浏览器中字体大小的设置影响，除非显示重写一个具体单位
例如，根元素字体大小16Px,10rem等同于160px

####（3）css3新增选择器
* 属性选择器  
 * E[attr]  只使用属性名，但没有确定任何属性值 
 * E[type="text]        指定属性名，并指定了该属性的属性值
 * E[attr~="value"]    指定属性名，并且具有属性值，此属性值是一个词列表，并且以空格隔开
 *  E[attr^="value"]    指定了属性名，属性值是以value开头的
 *  E[attr$="value"]    指定了属性名，而且属性值是以value结束的
 *  E[attr*="value"]    指定了属性名，而且属值中包含value
 *  E[attr|="value"]    指定了属性名，并且属性值是value或者以“value-”开头的值
*   结构性伪类
  *  P:nth-child(2):找p标签父级下的第二个子元素并且这个元素还是p标签
  *  P:nth-of-type(2):找p标签父级下的第二个p元素

#### （4） box-sizing
* Content-box:标准盒模型  width/height=border+padding+content
* Border-box:怪异盒模型  width/height=content

####  （5）  background
*  Background-size:
 *  contain: 包含，整个背景图都要被包含在元素内，没有超出的部分。
 *  cover: 覆盖，背景要覆盖元素的所有区域，不能有空白出现。
*  background-origin:
 *  Border-box:从border区域开始显示背景
 *  Padding-box:从padding区域开始显示背景
 *  Content-box:从content区域开始显示背景
*   background-clip:
 *  Border-box:从border区域向外裁剪背景
 *  Padding-box:从padding区域向外裁剪背景
 *  Content-box:从content区域向外裁剪背景
 *  Text:从文本区域向外裁剪 

#### （6）Transform/transition/animation
* Transform:静态属性，用来做元素的特殊变形   eg:transform:translate3D(x,y,z)
* Transition:简单动画属性，animation简化版
*  Animation:transition的扩展  
例如：@keyframs a{  
0%{left:100px;}  
100%{left:1000px;}  
}  
.animate{left:100px;animation:a 0.5s ease-out;}

##3.sass,compass

###Sass部分：

####（1）编译风格
*  nested：嵌套缩进的css代码，它是默认值。
*  expanded：没有缩进的、扩展的css代码。
*  compact：简洁格式的css代码。
*  compressed：压缩后的css代码。

####（2）变量
SASS允许使用变量，所有变量以$开头。  
eg:$blue : #1875e7;　  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;div {  
　　　color : $blue;  
　　}

####(3)计算功能  
SASS允许在代码中使用算式：  
body {  
　　　　margin: (14px/2);  
　　　　top: 50px + 100px;  
　　　　right: $var * 10%;  
}

####（4）允许嵌套
　div {  
　　　　hi {  
　　　　　　color:red;  
　　　　}  
　　}

####（5）注释
SASS共有两种注释风格。  

  * 标准的CSS注释 `/* comment */` ，会保留到编译后的文件。  
  * 单行注释 // comment，只保留在SASS源文件中，编译后被省略。  
  * 在/*后面加一个感叹号，表示这是"重要注释"。即使是压缩模式编译，也会保留这行注释，通常可以用于声明版权信息。

####（6）代码的重用
* 继承  
 SASS允许一个选择器，继承另一个选择器。比如，现有class1：  
　　.class1 {  
　　　　border: 1px solid #ddd;  
　　}  
 class2要继承class1，就要使用@extend命令：  
　　.class2 {  
　　　　@extend .class1;  
　　　　font-size:120%;  
　　}
* Mixin  
Mixin有点像C语言的宏（macro），是可以重用的代码块。  
使用@mixin命令，定义一个代码块。  
　　@mixin left {  
　　　　float: left;  
　　　　margin-left: 10px;  
　　}  
使用@include命令，调用这个mixin。   
　　div {  
　　　　@include left;  
　　}  
mixin的强大之处，在于可以指定参数和缺省值。  
　　@mixin left($value: 10px) {  
　　　　float: left;  
　　　　margin-right: $value;  
　　}  
使用的时候，根据需要加入参数：  
　　div {  
　　　　@include left(20px);  
　　}

* 插入文件  
@import命令，用来插入外部文件。 
　　@import "path/filename.scss";  
如果插入的是.css文件，则等同于css的import命令。　@import "foo.css";

####（7）高级用法
* 条件语句  
@if可以用来判断：  
　　p {  
　　　　@if 1 + 1 == 2 { border: 1px solid; }  
　　　　@if 5 < 3 { border: 2px dotted; }  
　　}  
配套的还有@else命令：  
　　@if lightness($color) > 30% {   
　　　　background-color: #000;  
　　}     @else {    
　　　　background-color: #fff;  
　　}
* 循环语句
SASS支持for循环：  
　　@for $i from 1 to 10 {  
　　　　.border-#{$i} {  
　　　　　　border: #{$i}px solid blue;  
　　　　}  
　　}  
也支持while循环：  
　　$i: 6;  
　　@while $i > 0 {  
　　　　.item-#{$i} { width: 2em * $i; }  
　　　　$i: $i - 2;  
　　}  
each命令，作用与for类似：  
　　@each $member in a, b, c, d {  
　　　　.#{$member} {  
　　　　　　background-image: url("/image/#{$member}.jpg");  
　　　　}  
　　}
* 自定义函数  
SASS允许用户编写自己的函数。  
　　@function double($n) {  
　　　　@return $n * 2;  
　　}  
	`#sidebar` {  
　　　　width: double(5px);  
　　}

###compass部分

####（1）Compass采用模块结构，不同模块提供不同的功能。目前，它内置五个模块：
* reset
* css3
* layout
* typography
* utilities

####（2）sprite
* 合成图片：@import "logo/*.png";
* 显示图片宽高:$logo-sprite-dimensions:true;
* 显示hover,active:$disable-magic-sprite-selectors:false;
* 引入合成图片：all-logo-sprites();

####（3）清除浮动
.clearfix{
@include legacy-pie-clearfix();
}

####（4）table
* @include outer-table-borders();外边框  
* @include inner-table-borders(1px);内边框
* @include table-scaffolding();
numeric
* @include alternating-rows-and-columns(yellow,blue,#222222,green,red);  
指分别对应：偶数行，奇数行，隔行列差值，th颜色，footer颜色，前三项必填

####（5）选择器
`#{append-selector("a,p,span,div",".search")}`{
	color:#000;
}  
将后面的类名添加到前面的选择器

####(6)config.rb相关配置
* relative_assets = true图片绝对路径或相对路径
* line_comments = false输出为css文件时是否保留注释

####（7）字体
* $base-font-size
* $base-line-height基线
* @include adjust-font-size-to(48px);自动将字体大小和行距转换为em
* @include leader()  margin-top几倍于基线的高
* @include trailer()  margin-bottom几倍于基线的高

####（8）a
* @include link-colors(red,blue,yellow,green,white)  
第一个值必填，其他不填则设为继承
* @include unstyled-link()  
抹平超链接样式，与父文本样式一样

####（9）text
* @include ellipsis()  
文本超出部分显示为省略号
* @include wrap()不换行  
* @include force-wrap()强行换行
* @include hide-text()隐藏文本
* @include replace-text()图片替换文本
* @include replace-text-with-dimensions(）自动匹配图片与容器的宽高

####(10)css3
@include opacity(0.9)


#javascript
![](https://raw.githubusercontent.com/miemiewang/gitskills/master/images/20.png)
![](https://raw.githubusercontent.com/miemiewang/gitskills/master/images/21.png)
####（1）标准模式与严格模式的区别
* 不能隐式声明和定义变量  
* 对象的属性不能重名  
* Argument.callee会报错  
* 不能使用with语句
####（2）数据类型
* Undefined:
转换：string(undefined),boolean(false),number(NaN)
* Null
Null==undefined
* Boolean
* Number  
  * 浮点数值会产生误差。例如0.1+0.2=0.30000000000000004,可以使用
  * parseFloat(num).toFixed(1)将其转换为保留一位小数  
  * NaN既非数值，是一个特殊的数值，isNaN()用以确定这个参数是否不是数值  
  * Number()转换规则如下：    
   如果是boolean值，true和false分别转化为1和0  
   如果是数字值，简单的传入和返回  
   如果是undefined，返回NaN  
   字符串为空，转换为0  
   如果是对象，调用valueOf()方法，如果转化结果是NaN，调用对象的toString()方法
* String  
数值，布尔值，对象和字符串都有一个toString()方法，该方法返回一个字符串的副本   
String()能够将任何类型的值转化为字符串
* Object  
Object的每个实例都有下列属性和方法
 * Constructor:保存着用于创建当前对象的函数
 * hasOwnProperty:用于检查给定的属性是否在对象实例中
 * isPrototypeOf():用于检查传入的对象是否是传入对象的原型
 * toLocalString(),toString()，返回对象的字符串表示
 * propertyIsEnumerable()检查给定的属性是否能够使用for-in语句枚举
 valueOf()返回对象的字符串，数值或布尔值表示
####（3）类型识别
* typeOf  
 * 可以识别标准类型（null除外）typeOf null//object
 * 不能识别具体的对象类型（function除外）typeOf function//function
* object.prototype.toString
 * 可以识别标准类型及内置对象类型
 * 不能识别自定义类型  
Object.prototype.toString.call(‘a’)==’[Object String]’
* Constructor
 * 识别标准类型(null和undefined除外）
 * 识别内置对象类型
 * 识别自定义类型  
[1,2].constructor==Array
* instanceOf
 * 判别内置对象类型
 * 不能识别原始类型（null,number,string.boolean.undefined）
 * 可以判别自定义对象类型  
[1,2] instanceof Array==true;
####(4)js类型转换规则
* 显示转换
 *  转换为数值：Number()、parseInt()、parseFloat()
 * 转换为字符串：toString()、String()
 * 转换为布尔类型:Boolean()（如果是对象，调用对象的valueOf()方法，然后根据前面规则转换，如果转换结果是NaN，调用对象toString()方法）
* 隐式类型转换
 * 用于检测是否为非数值的函数：isNaN，该函数会尝试将参数值用Number()进行转换
 * 递增递减操作符，一元正负符号操作符
 * 加法、乘除、减号、取模运算符
 * 逻辑，相等、关系操作符
####（5）字符串常用方法
* 获取类方法    
  * charAt()    
     * stringObject.charAt(index)  
     * 方法可用来获取指定位置的字符串，index为字符串索引值，从0开始到string.leng – 1，若不在这个范围将返回一个空字符串。如：  
var str = 'abcde';  
console.log(str.charAt(2));     //返回c  
console.log(str.charAt(8));     //返回空字符串  
  * charCodeAt()  
      * stringObject.charCodeAt(index)  
      * charCodeAt()方法可返回指定位置的字符的Unicode编码。charCodeAt()方法与charAt()方法类似，都需要传入一个索引值作为参数，区别是前者返回指定位置的字符的编码，而后者返回的是字符子串。  
var str = 'abcde';  
console.log(str.charCodeAt(0));     //返回97  
  * fromCharCode()  
      * String.fromCharCode(numX,numX,…,numX)  
      * fromCharCode()可接受一个或多个Unicode值，然后返回一个字符串。另外该方法是String 的静态方法，字符串中的每个字符都由单独的数字Unicode编码指定。  
String.fromCharCode(97, 98, 99, 100, 101)   //返回abcde  
* 查找类方法  
  * indexOf()  
     * stringObject.indexOf(searchvalue,fromindex)  
     * indexOf()用来检索指定的字符串值在字符串中首次出现的位置。它可以接收两个参数，searchvalue表示要查找的子字符串，fromindex表示查找的开始位置，省略的话则从开始位置进行检索。  
 var str = 'abcdeabcde';  
  console.log(str.indexOf('a'));  // 返回0  
 console.log(str.indexOf('a', 3));   // 返回5  
console.log(str.indexOf('bc')); // 返回1  
  * lastIndexOf()方法  
     * stringObject.lastIndexOf(searchvalue,fromindex)
     * lastIndexOf()语法与indexOf()类似，它返回的是一个指定的子字符串值最后出现的位置，其检索顺序是从后向前。  
var str = 'abcdeabcde';  
console.log(str.lastIndexOf('a'));  // 返回5  
console.log(str.lastIndexOf('a', 3));   // 返回0 从第索引3的位置往前检索  
console.log(str.lastIndexOf('bc')); // 返回6    
  * search()方法
      * stringObject.search(substr) 
      * stringObject.search(regexp)
      * search()方法用于检索字符串中指定的子字符串，或检索与正则表达式相匹配的子字符串。它会返回第一个匹配的子字符串的起始位置，如果没有匹配的，则返回-1。  
var str = 'abcDEF';  
console.log(str.search('c'));   //返回2  
console.log(str.search('d'));   //返回-1  
console.log(str.search(/d/i));  //返回3  
  * match()方法
      * stringObject.match(substr) 
      * stringObject.match(regexp)
      * match()方法可在字符串内检索指定的值，或找到一个或多个正则表达式的匹配。
      * 如果参数中传入的是子字符串或是没有进行全局匹配的正则表达式，那么match()方法会从开始位置执行一次匹配，如果没有匹配到结果，则返回null。否则则会返回一个数组，该数组的第0个元素存放的是匹配文本，除此之外，返回的数组还含有两个对象属性index和input，分别表示匹配文本的起始字符索引和stringObject 的引用(即原字符串)。  
var str = '1a2b3c4d5e';  
console.log(str.match('h'));    //返回null  
console.log(str.match('b'));    //返回["b", index: 3, input: "1a2b3c4d5e"]  
console.log(str.match(/b/));    //返回["b", index: 3, input: "1a2b3c4d5e"]  
      * 如果参数传入的是具有全局匹配的正则表达式，那么match()从开始位置进行多次匹配，直到最后。如果没有匹配到结果，则返回null。否则则会返回一个数组，数组中存放所有符合要求的子字符串，并且没有index和input属性。  
var str = '1a2b3c4d5e';  
console.log(str.match(/h/g));   //返回null  
console.log(str.match(/\d/g));  //返回["1", "2", "3", "4", "5"]
* 截取类方法
  * subString()
     * stringObject.(start,end)
     * subString()是最常用到的字符串截取方法，它可以接收两个参数(参数不能为负值)，分别是要截取的开始位置和结束位置，它将返回一个新的字符串，其内容是从start处到end-1处的所有字符。若结束参数(end)省略，则表示从start位置一直截取到最后。  
var str = ‘abdopfg';  
console.log(str.subString(1, 4));   //返回bdo  
console.log(str.subString(1));  //返回bdopfg  
console.log(str.subString(-1)); //返回abdopfg，传入负值时会视为0
 * slice()
     * stringObject.slice(start,end)
     * slice()方法与subString()方法非常类似，它传入的两个参数也分别对应着开始位置和结束位置。而区别在于，slice()中的参数可以为负值，如果参数是负数，则该参数规定的是从字符串的尾部开始算起的位置。也就是说，-1 指字符串的最后一个字符。  
var str =’abdopfg ';  
console.log(str.slice(1, 4));   //返回bdo  
console.log(str.slice(-3, -1)); //返回pf  
console.log(str.slice(1, -1));  //返回abdopf  
console.log(str.slice(-1, -3)); //返回空字符串，若传入的参数有问题，则返回空
 * substr()
     * stringObject.substr(start,length)
     * substr()方法可在字符串中抽取从start下标开始的指定数目的字符。其返回值为一个字符串，包含从 stringObject的start（包括start所指的字符）处开始的length个字符。如果没有指定 length，那么返回的字符串包含从start到stringObject的结尾的字符。另外如果start为负数，则表示从字符串尾部开始算起。  
var str = ‘abdopfg';  
console.log(str.substr(1, 3))   //返回bdo  
console.log(str.substr(2))  //返回dopfg  
console.log(str.substr(-2, 4))  //返回fg，目标长度较大的话，以实际截取的长度为准
* 其他方法
  * replace()方法
     * stringObject.replace(regexp/substr,replacement)
     * replace()方法用来进行字符串替换操作，它可以接收两个参数，前者为被替换的子字符串（可以是正则），后者为用来替换的文本。
如果第一个参数传入的是子字符串或是没有进行全局匹配的正则表达式，那么replace()方法将只进行一次替换（即替换最前面的），返回经过一次替换后的结果字符串。  
var str = ';  
console.log(str.replace('a', 'A'));  
console.log(str.replace(/a/, 'A'));  
     * 如果第一个参数传入的全局匹配的正则表达式，那么replace()将会对符合条件的子字符串进行多次替换，最后返回经过多次替换的结果字符串。  
var str = ';  
console.log(str.replace(/a/g, 'A'));    //返回  
console.log(str.replace(/a/, '$'));   //返回$$$BCDE
  * split()方法
     * stringObject.split(separator,)
     * split()方法用于把一个字符串分割成字符串数组。第一个参数separator表示分割位置(参考符)，第二个参数howmany表示返回数组的允许最大长度(一般情况下不设置)。  
   var str = 'a|b|c|d|e';  
   console.log(str.split('|'));    //返回["a", "b", "c", "d", "e"]  
   console.log(str.split('|', 3)); //返回["a", "b", "c"]  
console.log(str.split('')); //返回["a", "|", "b", "|", "c", "|", "d", "|", "e"]  
     * 也可以用正则来进行分割  
var str = 'a1b2c3d4e';  
console.log(str.split(/\d/)); //返回["a", "b", "c", "d", "e"]
  * toLowerCase()和toUpperCase()
     * stringObject.toLowerCase() 
     * stringObject.toUpperCase()
####（6）数组常用方法
* 数组元素的添加
    * arrayObj. push([item1 [item2 [. . . [itemN ]]]]);// 将一个或多个新元素添加到数组结尾，并返回数组新长度
    * arrayObj.unshift([item1 [item2 [. . . [itemN ]]]]);// 将一个或多个新元素添加到数组开始，数组中的元素自动后移，返回数组新长度
    * arrayObj.splice(insertPos,0,[item1[, item2[, . . . [,itemN]]]]);//将一个或多个新元素插入到数组的指定位置，插入位置的元素自动后移，返回""。
* 数组元素的删除
    * arrayObj.pop(); //移除最后一个元素并返回该元素值
    * arrayObj.shift(); //移除最前一个元素并返回该元素值，数组中元素自动前移
    * arrayObj.splice(deletePos,deleteCount); //删除从指定位置deletePos开始的指定数量deleteCount的元素，数组形式返回所移除的元素
* 数组的截取和合并
    * arrayObj.slice(start, [end]); //以数组的形式返回数组的一部分，注意不包括 end 对应的元素，如果省略 end 将复制 start 之后的所有元素
    * arrayObj.concat([item1[, item2[, . . . [,itemN]]]]); //将多个数组（也可以是字符串，或者是数组和字符串的混合）连接为一个数组，返回连接好的新的数组
* 数组的拷贝
    * arrayObj.slice(0); //返回数组的拷贝数组，注意是一个新的数组，不是指向
    * arrayObj.concat(); //返回数组的拷贝数组，注意是一个新的数组，不是指向
* 数组元素的排序
    * arrayObj.reverse(); //反转元素（最前的排到最后、最后的排到最前），返回数组地址
    * arrayObj.sort(); //对数组元素排序，返回数组地址
* 数组元素的字符串化
    * arrayObj.join(separator); //返回字符串，这个字符串将数组的每一个元素值连接在一起，中间用 separator 隔开。
    * toLocaleString 、toString 、valueOf：可以看作是join的特殊用法，不常用
####（7）数组去重的四种方法
1.

		 Array.prototype.unique1 = function()  
			{  
				var n = []; //一个新的临时数组  
				for(var i = 0; i < this.length; i++) //遍历当前数组  
				{  
				//如果当前数组的第i已经保存进了临时数组，那么跳过，  
				//否则把当前项push到临时数组里面  
					if (n.indexOf(this[i]) == -1) n.push(this[i]);  
				}  
						return n;  
		}

2.

		Array.prototype.unique2 = function()  
			{  
				var n = {},r=[]; //n为hash表，r为临时数组  
				for(var i = 0; i < this.length; i++) //遍历当前数组  
				{  
					if (!n[this[i]]) //如果hash表中没有当前项  
						{  
							n[this[i]] = true; //存入hash表  
							r.push(this[i]); //把当前数组的当前项push到临时数组里面  
						}  
					}  
				return r;  
			}

3.

	 Array.prototype.unique3 = function()  
		{  
			var n = [this[0]]; //结果数组  
			for(var i = 1; i < this.length; i++) //从第二项开始遍历  
			{  
				//如果当前数组的第i项在当前数组中第一次出现的位置不是i，  
				//那么表示第i项是重复的，忽略掉。否则存入结果数组  
				if (this.indexOf(this[i]) == i) n.push(this[i]);  
			}  
		return n;  
	}

4.

	 Array.prototype.unique4 = function()  
		{  
			this.sort();  
			var re=[this[0]];  
			for(var i = 1; i < this.length; i++)  
			{  
				if( this[i] !== re[re.length-1])  
				{  
					re.push(this[i]);  
				}  
			}  
			return re;  
		}
####（8）递归算法
* 

		 function fact(num){   
			if (num<=1){   
				return 1;   
			}else{   
				return num`*`fact(num-1);   
			}   
		}   
		以下可能导致出错  
		var anotherFact = fact;   
		fact = null;   
		alert(antherFact(4)); //出错   
		用arguments.callee可解决问题，这是一个指向正在执行的函数的指针。   
		function fact(num){   
			if (num<=1){   
				return 1;   
			}else{   
				return num*arguments.callee(num-1); //此处更改了。   
			}   
		}   
		var anotherFact = fact;   
		fact = null;   
		alert(antherFact(4)); //结果为24.  
####（9）找到所有匹配字符串

		var str='my name is mimi,do you remember me?';  
		var arr=[];  
		var save=str.indexOf('m');  
		while(save>-1){   //不能用if  
			arr.push(save);  
			save=str.indexOf('m',save+1)  
		}  
		alert(arr);//0,5,11,13,25,27,32   
####（10）数组求和
reduce()和reduceRight()  

		Var value=[1,2,3,4]  
		Var sum=value.reduce(function(prev,cur,index,array){  
			Return prev+cur;  
		});  
4个参数：前一个值，当前值，项的索引和数组对象
####（11）正则表达式
* test -- RegExp的test方法用来测试字符串是否匹配给出的匹配模式，返回布尔值；  
* exec -- RegExp的exec方法返回包含第一个匹配的的数组或null；  
* match -- String的match方法返回包含所有匹配子字符串的数组；
* replace -- String的replace方法完成string的替换操作，支持正则表达式；
* search -- 与String的indexof方法类似，不同的是search支持正则表达式，而不仅仅是字符串；
* split -- 按照一定规则拆分字符串并将子字符串存储到数组中的String方法。
####（12）Math方法
* floor(x) 对一个数进行下舍入。
* max(x,y) 返回 x 和 y 中的最高值 
* min(x,y) 返回 x 和 y 中的最低值
* pow(x,y) 返回 x 的 y 次幂 
* random() 返回 0 ~ 1 之间的随机数
* round(x) 把一个数四舍五入为最接近的整数
* sin(x) 返回数的正弦
* sqrt(x) 返回数的平方根
* tan(x) 返回一个角的正切 
* ceil(x) 对一个数进行上舍入。
####（13）变量作用域
Js为静态作用域（词法作用域）：跟程序定义的位置有关，与执行顺序无关。Js没有块级作用域，只有函数作用域
####（14）函数声明与函数表达式
1. 声明总是在作用域开始时先行解析；
2. 表达式在遇到时候才运算。
####（15）闭包
* 由函数和与其相关的引用环境组合而成
* 允许函数访问其引用环境中的变量  
当内部函数 在定义它的作用域 的外部 被引用时,就创建了该内部函数的闭包 ,如果内部函数引用了位于外部函数的变量,当外部函数调用完毕后,这些变量在内存不会被 释放,因为闭包需要它们.  
在Javascript中，如果一个对象不再被引用，那么这个对象就会被GC回收。如果两个对象互相引用，而不再被第3者所引用，那么这两个互相引用的对象也会被回收。因为函数a被b引用，b又被a外的c引用，这就是为什么函数a执行后不会被回收的原因。  
例：var name = "The Window";     
　　var object = {     
　　　　name : "My Object",     
　　　　getNameFunc : function(){     
　　　　　　return function(){     
　　　　　　　　return this.name;     
　　　　　};     
　　　　}     
};     
alert(object.getNameFunc()());  //The Window
闭包中的this指向调用它的对象，直接调用就指向window，这里的object.getNameFunc()()相当于，var a=object.getNameFunc(),执行a(),也是直接调用
###2.dom
####（1）querySelector和querySelectorAll
获取的节点不是动态的，增删节点不会表现出来
####（2）js操作dom节点
* 访问节点  
document.getElementById(id);
返回对拥有指定id的第一个对象进行访问  
document.getElementsByName(name);  
返回带有指定名称的节点集合  
注意:Elements  
document.getElementsByTagName(tagname);  
返回带有指定标签名的对象集合    
注意：Elements  
document.getElementsByClassName(classname);  
返回带有指定class名称的对象集合  
注意：Elements
* 生成节点  
document.createElement(eName);  
创建一个节点  
document.createAttribute(attrName);  
对某个节点创建属性  
document.createTextNode(text);  
创建文本节点
* 添加节点  
document.insertBefore(newNode,referenceChild);  
在某个节点前插入节点  
parentNode.appendChild(newNode);  
给某个节点添加子节点
* 复制节点  
cloneNode(true | false);  
复制某个节点  
参数：是否复制原节点的所有属性
* 删除节点  
parentNode.removeChild(node)  
删除某个节点的子节点  
node是要删除的节点  
注意：IE会忽略节点间生成的空白文本节点(例如，换行符号)，而Mozilla不会这样做。在删除指定节点的时候不会出错，但是如果要删除最后一个子结点或者是第一个子结点的时候，就会出现问题。这时候，就需要用一个函数来判断首个子结点的节点类型。  
元素节点的节点类型是 1，因此如果首个子节点不是一个元素节点，它就会移至下一个节点，然后继续检查此节点是否为元素节点。整个过程会一直持续到首个元素子节点被找到为止。通过这个方法，我们就可以在 Internet Explorer 和 Mozilla 得到正确的方法。  
* 属性操作  
getAttribute(name)  
通过属性名称获取某个节点属性的值  
setAttribute(name,value);  
修改某个节点属性的值  
removeAttribute(name)  
删除某个属性
* 查找节点  
parentObj.firstChild  
如果节点为已知节点的第一个子节点就可以使用这个方法。此方法可以递归进行使用  
parentObj.firstChild.firstChild.....  
parentObj.lastChild  
获得一个节点的最后一个节点，与firstChild一样也可以进行递归使用  
parentObj.lastChild.lastChild.....  
parentObj.childNodes  
获得节点的所有子节点，然后通过循环和索引找到目标节点
* 获取相邻的节点  
neborNode.previousSibling :获取已知节点的相邻的上一个节点  
nerbourNode.nextSlbling: 获取已知节点的下一个节点
* 获取父节点  
childNode.parentNode:得到已知节点的父节点
* 替换节点方法replace(new,old)
####（3）事件流
![](https://raw.githubusercontent.com/miemiewang/gitskills/master/images/22.png)  
每当某一事件发生时，都会经过捕获阶段->处理阶段->冒泡阶段(有些浏览器不支持捕获) 
捕获阶段是由上层元素到下层元素的顺序依次。而冒泡阶段则正相反。 
####（4）事件注册
eventTarget.addEventListener(type.listener,false)||attachEvent(type.listener)  
取消：eventTarget.removeEventListener(type.listener,false)||detachEvent(type.listener) 
 
		var eventHandler={ 		
			addHandler:function(element,type,func){   　　      	
							if(element.addEventListener){  　             
								element.addEventListener(type,func,false);        
							 }else if(element.detachEvent{  　　           		
								element.attachEvent('on'+type,func);  　       
							}else{  　　        					
								element['on'+type]=func;  　　     
						  	}       					
						},
			removerHandler:function(element,type,func){  　        
								if(element.removeEventListener){  	　　          
									element.removeEventListener(type,func,false);  	　　         
								}else if(element.detachEvent){ 	 　　          
									element.detachEvent('on'+type,func);  
	 　　      					}else{  　              	 					
									element['on'+type]=null;  
								}   　　     
							}  　   
	 	}  
阻止事件冒泡  
event.stopPropagation()(w3c)    
  event.cancelBubble==true//ie6,7,8    
event.stopImmediatePropagation()(w3c)其后的事件也被阻止  
阻止默认行为  
event.returnValue=false(ie)  
event.preventDefault(w3c)  
####（5）addEventListener和attachEvent的区别
* 适应的浏览器版本不同
前者在Mozilla中使用，后者在ie中
* 执行顺序不一样  
前者依次顺序执行监听函数  
后者倒序执行
* 使用事件监听的好处：
    * 事件监听可以同时执行多个函数，而像click,mouseover等事件后一个方法会覆盖掉前一个
    * 采用事件监听可以解除相应的绑定，但解除时一定要用函数的句柄，把整个函数写上无法解除  
Function a(){alert(1)}  
btn.addEventListener(‘click’,a,false)  
btn.removeEventListener(‘click’,a)  
####(6)事件委托
利用冒泡原理，把事件加到父级上，触发执行效果

* 提高性能。例如：在有很多个li并需要为其添加事件时，依次触发很耗性能，可以利用事件委托加到ul上
* 新添加的元素还会有之前的事件，例如：点击button动态添加Li,仍然会有之前的事件
####（7）mouse事件
![](https://raw.githubusercontent.com/miemiewang/gitskills/master/images/23.png)
####（8）dom优缺点
* DOM的优势主要表现在：易用性强，使用DOM时，将把所有的XML文档信息都存于内存中，并且遍历简单，支持XPath，增强了易用性。
* DOM的缺点主要表现在：效率低，解析速度慢，内存占用量过高，对于大文件来说几乎不可能使用。另外效率低还表现在大量的消耗时间，因为使用DOM进行解析时，将为文档的每个element、attribute、processing- instrUCtion和comment都创建一个对象，这样在DOM机制中所运用的大量对象的创建和销毁无疑会影响其效率。
###3.面向对象
####(1)程序设计方法：  
面向过程：以过程为中心，自顶向下逐一细化  
面向对象：对象作为程序的基本单元，程序分解为数据和相关操作
####(2)面向对象：  
* 基本概念：  
类，对象  
属性，方法  
* 基本特性：  
继承，封装，多态  
####(3)js中的面向对象
* constructor（构造器）
* 创建构造器的三种方法：  
Function Employee(){}  
Var Employee=function(){}  
Var Employee=new function(){}
####(4)new关键字完成三个工作
* 创建一个对象
* 将该对象的_proto_指向函数的prototype
* 调用该函数
####(5) 原型模式和基于原型继承的js对象系统
原型编程范型包括以下规则：  

* 所有的数据都是对象：  
Js基本类型包括：undefined,boolean,string,number  
对象类型为：object,null  
除了undefined，boolean,string和number都可以通过“包装类”变成对象类型数据，js中有一个根对象存在，为object.prototype  
* 要得到一个对象不是通过实例化类，而是找到一个对象作为原型，并克隆他  

		function Person(name){  
			this.name=name;  
		}  
		Person.prototype.getName=function(){  
			return this.name;  
		}  
		var person1=new Person(‘wangy’);  
		alert(person1.name)//’wangy’;  
		object.getPrototypeOf(person1)===Person.prototype;  
用new运算符来创建对象的过程，实际上也只是先克隆object.prototype对象，再进行其他操作
* 对象会记住它的原型  
`Var a=new object();`  
`A._proto_===object.prototype;`  
`_proto_`就是对象跟“对象构造器”的原型联系起来的纽带
* 如果对象无法响应某个请求，它会把这个请求委托给他自己的原型  
`var a=function(){};  `  
`a.prototype={name:'seven'};  `
`var b=function(){};`  
`b.prototype=new a();`  
`var c=new b();`  
`alert(a.__proto__);//function Empty(){}`  
`alert(b.__proto__)//function Empty(){}`  
`alert(c.__proto__===b.prototype)//true  `
####(6)js面向对象中this的指向
* 作为对象的方法调用  
    * 当函数作为该对象的方法被调用时，this指向该对象  

			Obj={  
    			Name:’wangy’,  
				getName:function(){  
    				 alert(this.name)  
				}  
			}  
			obj.getName()//wangy  
			Var b=obj.getName;  
			b()//undefined
    * 作为普通函数调用（this总是指向全局对象）  

			var name='globalName';  
			var a=function(){  
				return this.name;  
			}  
			alert(a())//globalName;
    * 构造器调用（this指向返回的这个对象）  

			var a=function(){  
				this.name='miemie';  
			}  
			var b=new a();  
			alert(b.name)//miemie  
			var a=function(){  
				this.name='miemie';  
				return this.name='haha'  
			}  
			var b=new a();  
			alert(b.name)//haha  
当构造器显示的返回了一个对象时，运算结果最终会返回这个对象
    * 在call和apply中调用  

			var a={  
				name:'yami',  
 				sayName:function(){  
					alert(this.name);  
				}  
			}  
			var b={  
				name:'wuba'  
			}  
			a.sayName.call(b);//wuba  
Call或apply会改变this的指向
    * 其他：  
Var a=new Function(‘alert(this)’);  
This总指向全局对象  
Eval(‘alert(this)’);  
指向调用上下文中的this；
    * This的总结：
  
![](https://raw.githubusercontent.com/miemiewang/gitskills/master/images/6.png)
####（7）call或apply的区别和用法
* 区别：传入参数形式不同，apply接受两个参数，第一个参数指定了函数体内this的指向，apply的二个参数作为一个带下标的集合，可以为数组也可以为类数组，apply方法把这个集合中的元素作为参数传递给被调用的函数。Call传入的参数数量不固定，从第二个参数开始往后，每个参数被依次传入函数  
Func.apply(null,[1,2,3]);  
Func.call(null,1,2,3);  
如果传入的第一个参数为null,函数体内的this会指向默认的宿主对象，浏览器中就是window
* Call和apply的用途：
   * 改变this指向  

			var a={  
				name:'yami',	  	
			}  
			var b={  
				name:'wuba'  
			}  
			var sayName=function(){  
				alert(this.name);  
			}  
			sayName.call(a);//yami  
   * Function.prototype.bind  

			Function.prototype.bind=function(context){  
				var self=this;  
				return function(){  
					return self.apply(context,arguments);  
				}  
			}  
			var b={  
				name:'wuba'  
			}  
			var func=function(){  
				alert(this.name);  
			}.bind(b);  
			func();//wuba
   * 借用其他对象的方法  

			var a=function(){  
				this.name='wangy';  
			}  
			var b=function(){  
				a.apply(this);  
			}  
			b.prototype.getName=function(){  
				alert(this.name);  
			}  
			var c=new b();  
			c.getName();//wangy  
####（8）原型链
![](https://raw.githubusercontent.com/miemiewang/gitskills/master/images/26.png)

* 属性查找，删除，修改皆通过原型链
* Delete只能删除对象本身上的属性，不能删除原型上的属性
* 判断属性是否来自对象本身：hasownproperty();
* 无论属性存在于原型中还是对象中，in操作符都会在能够访问特定属性时返回true；  
同时使用hasownproperty()和in就可以确定属性到底存在于原型还是对象上

		Function hasownproperty(object,name){  
			Return !object.hasOwnProperty(name)&&(name in object);  
		}
* 要想取得对象上所有可枚举的实例属性，可以使用Object.keys()方法，该方法接受一个对象作为参数，返回一个包含所有可枚举属性的字符串数组
* 要想得到所有实例属性，无论可枚举，可以使用Object.getOwnPropertyNames(),使用方法同上
####(9)原型的动态性
* 我们对原型对象所做的任何修改都能立即从实例上反映出来，即使是先创建了实例后修改原型也照样如此

		Function Person(){}
		Var friend=new Person();
		Person.prototype.sayHi=function(){
			alert(‘hi’);
		}
		friend.sayHi()///hi
* 把原型修改为另一个对象等于切断了构造函数与最初原型之间的联系，实例中的指针仅指向原型，而不指向构造函数  

		Function Person(){}  
		Var friend=new Person();  
		Person.prototype={  
			Constructor:Person,  
			Name:'John';,  
			sayName:function(){  
				alert(this.name);  
			}  
		}  
		friend.sayName()//error  
重写原型对象切断了现有原型与任何之前已经存在的对象实例之间的联系，它们引用的仍是最初的原型
####(10)继承
* 原型链继承  

		var A=function(){  
			this.name='wangy';  
		}  
		A.prototype.getName=function(){  
			alert(this.name);  
		}  
		var B=function(){  
			this.job='workker';  
		}  
		B.prototype=new A();  
		B.prototype.getJob=function(){  
			alert(this.job);  
		}  
		var c=new B();  
		c.getName();//'wangy'  
问题：引用类型值共享的问题  

		var A=function(){  
			this.color=['red','yellow'];  
		}  
		var B=function(){}  
		B.prototype=new A();  
		var c=new B();  
		c.color.push('blue');//['red','yellow','blue'];  
		var d=new B();  
		d.color//['red','yellow','blue'];
* 借用构造函数 
 
		var A=function(){  
			this.color=['red','yellow'];  
		}  
		var B=function(){  
			A.call(this);  
		}  
		var c=new B();  
		c.color.push('blue');//['red','yellow','blue'];  
		var d=new B();  
		d.color//['red','yellow'];  
问题：方法都在构造函数中定义，函数复用无从谈起
* 组合继承
  
		var A=function(name){  
			this.name=name;  
			this.color=['red','yellow'];  
		}  
		A.prototype.sayName=function(){  
			alert(this.name);  
		}  
		var B=function(name){  
			A.call(this,name);  
		}  
		B.prototype=new A();  
		var c=new B('dingding');  
		c.color.push('blue');//['red','yellow','blue'];  
		c.sayName()//dingding  
		var d=new B('haha');  
		d.color//['red','yellow'];  
		d.sayName()//haha
* 原型式继承  

		function object(o){  
			function F(){};  
			F.prototype=o;  
			return new F();  
		}  
		var Person={  
			name:'greg',  
			friends:['hong','qian','xiang']  
		}  
		var a=Object.create(Person);  
		a.friends.push('dong');  
		var b=Object.create(Person);  
		b.friends.push('ya');  
		alert(b.friends);
* 原型模式之浅复制和深复制  
浅复制：  

		var obj={  
			'name':{  
				'num':'wangyang',  
				'num2':'wangy'  
			},  
			'age':'20'  
		}  
		function clone(obj){  
			var ret={},k;  
			for(var k in obj){  
			ret[k]=obj[k];  
			}  
			return ret;  
		}
		var b=clone(obj);  
		b.name.num='wangding';  
		Alert(obj.name.num)//wangding  
深复制：  

        function clone2(obj){  
	        var ret,k,b;  
	        if(b=(obj instanceof Array)||obj instanceof Object){ 
		        ret=b?[]:{};  
                for(var k in obj){  
			       if(obj[k] instanceof Array||obj[k] instanceof   Object){  
				       ret[k]=clone2(obj[k]);  
	               }else{  
			  	      ret[k]=obj[k];  
		       }  
		    }  
	        return ret;  
	    }  
var c=clone2(obj);  
c.name.num='wangqian';  
Alert(obj.name.num)//wangyang
###4.ajax
####（1）常见http状态码
![](https://raw.githubusercontent.com/miemiewang/gitskills/master/images/4.png)
####（2）ajax调用示例
![](https://raw.githubusercontent.com/miemiewang/gitskills/master/images/27.png)
####（3）readyState
* 0：未初始化，对象已经创建，还没有调用open方法
* 1：载入，已经调用open方法，还没发送请求
* 2：载入完成，请求已经发送完成
* 3：交互，可以接收到部分响应数据
* 4：完成，已经接收到全部数据，并且连接被关闭
####（4）兼容性  
 if (window.ActiveXObject) {      
       &nbsp;&nbsp;&nbsp;&nbsp; xmlHttp = new ActiveXObject("Microsoft.XMLHTTP");      
    }      
    else if (window.XMLHttpRequest) {      
       &nbsp;&nbsp;&nbsp;&nbsp; xmlHttp = new XMLHttpRequest();      
}    
####（5）ajax方法封装

    function ajax(method, url, data, success) { 
 
    var xhr = null;  
	try {  
		xhr = new XMLHttpRequest();  
	} catch (e) {  
		xhr = new ActiveXObject('Microsoft.XMLHTTP');  
	}  

	if (method == 'get' && data) {  
		url += '?' + data;  
	}  
	xhr.open(method,url,true);
  
	if (method == 'get') {  
		xhr.send();  
	} else {  
		xhr.setRequestHeader('content-type', 'application/x-www-form-urlencoded');  
		xhr.send(data);  
	} 
 
	xhr.onreadystatechange = function() {  		
		if ( xhr.readyState == 4 ) {  
			if ( xhr.status == 200 ) {  
				success && success(xhr.responseText);  
			} else {  
				alert('出错了,Err：' + xhr.status);  
			}  
		}  
	}  
    }
####（6）json
* JSON(JavaScript Object Notation) 是一种轻量级的数据交换格式，采用完全独立于语言的文本格式，是理想的数据交换格式。  
* 在JSON中，有两种结构：对象和数组。  
* JSON字符串转换为JSON对象
   
	 	要运用上面的str1，必须运用下面的要领先转化为JSON对象： 
	 	//由JSON字符串转换为JSON对象   		
		var obj = eval('(' + str + ')');
		或者
    	var obj = str.parseJSON(); //由JSON字符串转换为JSON对象
    	或者		
		var obj = JSON.parse(str); //由JSON字符串转换为JSON对象  		
		然后，就可以这样读取：
    	Alert(obj.name);
* 可以运用 toJSONString()或者全局要领 JSON.stringify()将JSON对象转化为JSON字符串。
    
		例如：  	
		var last=obj.toJSONString(); //将JSON对象转化为JSON字符 	
		或者
		var last=JSON.stringify(obj); //将JSON对象转化为JSON字符
####（7）Ajax优缺点
* 优点：   
  * 可以使得页面不重载全部内容的情况下加载局部内容，降低数据传输量。
  * 
  避免用户不断刷新或者跳转页面，提高用户体验

* 缺点：   
  * 对搜索引擎不友好（要实现ajax下的前后退功能成本较大)
　
  *  可能造成请求数的增加
　 
  * 跨域问题限制
####（8）ajax跨域
* Cors
* jsonP
获取百度数据

		function fn(data){
			var html='';
			if(data.s.length){
				for(var i=0;i<data.s.length;i++){
					oUl.style.display='block';
					html+='<li><a href="http://www.baidu.com/s?wd='+data.s[i]+'">'+data.s[i]+'</a></li>'
				}
				oUl.innerHTML=html;
			}else{
				oUl.style.display='none';
			}
		}
		var oUl=null;
		window.onload=function(){
		
			oUl=document.getElementsByTagName('ul')[0];
			var oBtn=document.getElementsByTagName('input')[0];
			oBtn.onkeyup=function(){
				var oScript=document.createElement('script');
				if(this.value!=''){
					oScript.src='http://suggestion.baidu.com/su?wd='+this.value+'&cb=fn';
					document.body.appendChild(oScript);
				}else{
					oUl.style.display='none';
				}
			}
		}
####（9）jquery中的ajax封装
* 快捷API  
只有返回成功才执行回调  
$.get(url,[data],[callback],[type])  
$.post(url,[data],[callback],[type])  
//type指定返回数据格式json,xml,html  
$(selector).load(url,[data],[callback])  
将页面片段载入到selector所代表的容器中  
$.getScript(url,[data],callback)  
动态加载脚本  
$.getJson(url,[data],callback)
* 底层方法$.ajax()
* 序列化  
$.param()序列化对象  
$.serialize()序列化表单  
Eg:$.serialize(‘#form’)//username=’wy’&password=’1234’  
$.serializeArray()将表单中的各个字段序列化为一个数组  
[{name:’username’,value:’wy’},{name:’password’,value:’1234’}]
####（10）使用get和post的区别
* 使用Get请求时,参数在URL中显示,而使用Post方式,则不会显示出来
* 使用Get请求发送数据量小,Post请求发送数据量大
* get请求需注意缓存问题,post请求不需担心这个问题
* post请求必须设置Content-Type值为application/x-form-www-urlencoded
* 发送请求时,因为get请求的参数都在url里,所以send函数发送的参数为null,而post请求在使用send方法时,却需赋予其参数。
####（11）解决get缓存问题
* get请求URL后加字符串，让浏览器认为不是相同请求
* 在ajax发送请求前加XMLhttpRequest.setRequestHeader(‘cache-control’,’no-cache’)
* 使用post代替get
# Jquery部分
###1.window.onload与$(document).ready()的对比
####（1）执行时机
前者必须等待网页中所有的内容加载完毕后（包括图片）才能执行，后者网页中所有dom结构绘制完毕后就执行，可能dom元素关联的东西并没有加载完
####（2）编写个数
前者不能同时编写多个，后者能
####（3）前者无简写，后者为$(function(){})
###2.$(this)和this的区别
$(this) 返回一个 jQuery 对象，你可以对它调用多个 jQuery 方法，比如用 text() 获取文本，用val() 获取值等等。而 this 代表当前元素，它是 JavaScript 关键词中的一个，表示上下文中的当前 DOM 元素。你不能对它调用 jQuery 方法，直到它被 $() 函数包裹，例如 $(this)。
###3.使用 CDN 加载 jQuery 库的主要优势是什么 ? 
除了报错节省服务器带宽以及更快的下载速度这许多的好处之外, 最重要的是，如果浏览器已经从同一个CDN下载类相同的 jQuery 版本, 那么它就不会再去下载它一次. 因此今时今日，许多公共的网站都将jQuery用于用户交互和动画, 如果浏览器已经有了下载好的jQuery库，网站就能有非常好的展示机会。
###4.删除节点的方法及区别  
Remove()该节点所包含的后代元素将同时被删除，返回值为一个指向已被删除节点的引用，也可以通过传递参数选择性删除元素  
Detach()所有绑定的事件，附加的数据会保留下来  
Empty()清空元素中的所有后代节点  
###5.attr()和prop()的区别
* 添加属性名称该属性就会生效，用prop()
* 具有true,false两个属性用prop()
* 其余用attr()
###6.窗口  
$(window).width()//窗口可视区宽度  
$(document).width()//窗口文档宽度  
$(document.body).width()//窗口文档body的宽度  
$(document.body).outerwidth()//padding+border  
$(document.body).outerwidth(true)//P+b+margin  
$(document).scrollTop()
###7.事件冒泡   
event.stopPropagation()阻止冒泡  
event.preventDefault()阻止默认行为  
Return false 以上两者一起阻止  
###8.事件对象属性  
Event.type事件类型  
Event.target获取触发事件的元素  
event.relatedTarget相关元素(存在过渡的事件的相关主体之一)  
event.pageX  event.pageY鼠标距窗口文档左边和顶部的距离  
Event.which获取鼠标左中右键  
1=左   2=中    3=右  
Event.matakey获取ctrl按键
###9.stop([clearQ],[gotoEnd])  
第一个参数代表是否要清空未执行完的动画  
第二个代表是否将正在执行的动画跳转到末状态  
直接使用stop()会立即停止当前在进行的动画，执行队列中下一个动画
###10.$.map()与$.each()  
$.map([0.1.2],function(n){  
return n>0?n+1:null;})//[2,3]    
两者方法类似，通过循环每个对象或者数组的“项”执行回调函数来实现对数组或对象的操作，不同点在于each()返回的是原来的数组，而map()会创建新数组，each()中的this指向当前数组或对象，map指向window
###11.$.each()和$().each()
前者可以遍历任何集合，后者用于jquery对象的遍历，如dom操作
###12.$.proxy()
`<input type=’button’ name=’我是按钮的name’/>`
		
			Var obj={
				Name:’我是obj的name’,
				sayName:function(){
					alert(this.name)
				}
			}
			$(‘input’).click(obj.sayName)//我是按钮的name
			$(‘input’).click($.proxy(obj.sayName,obj))
			$(‘input’).click($.proxy(obj,’sayName’))//我是obj的name
$.proxy()类似于apply,改变执行上下文  
$.proxy(a,b)  
(1)a为函数，b为该函数的对象所有  
(2)A为对象，b为该对象里的属性，把a作为对象传入b中，改变this
###13.mouseenter和mouseover  
前者不冒泡，后者冒泡  
前者只在鼠标穿过被选元素时触发事件，后者无论穿过被选元素还是子元素都触发
###14.事件处理方法  
Bind(),live(),on(),delegate()  

* 相同：均支持单元素多事件绑定，空格相隔方式或大括号替代方式  
均通过事件冒泡方式，将事件传递到document进行事件的响应
不同：
* Bind()只针对已存在的元素进行事件的设置
Live(),on(),delegate()均支持未来新添加元素的事件设置
###15.focusin,focus,focusout,blur  
Focus和blur在元素本身产生  
Focusin和focusout在元素包含的元素中产生，也就是可以在父元素上检测子元素失去焦点的情况
###16.queue()和dequeue()
用queue()把函数加入队列
用dequeue()将函数数组中的第一个函数取出，并执行