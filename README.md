# 前端面试知识点整理
##HTML
1.viewport meta
```javascript
    <meta name ="viewport" content ="width=device-width, initial-scale=1, maximum-scale=1, minimum-scale=1, user-scalable=no"> 
    width  　　　　 viewport 宽度(数值/device-width)   
    height         viewport 高度(数值/device-height)   
    initial-scale  初始缩放比例   
    maximum-scale  最大缩放比例   
    minimum-scale  最小缩放比例   
    user-scalable  是否允许用户缩放(yes/no)  
```
2.语义

>web语义化是指通过HTML标记表示页面包含的信息，包含了HTML标签的语义化和css命名的语义化。 
HTML标签的语义化是指：通过使用包含语义的标签（如h1-h6）恰当地表示文档结构 
css命名的语义化是指：为html标签添加有意义的class，id补充未表达的语义，如Microformat通过添加符合规则的class描述信息 为什么需要语义化：

- 去掉样式后页面呈现清晰的结构
- 盲人使用读屏器更好地阅读
- 搜索引擎更好地理解页面，有利于收录
- 便团队项目的可持续运作及维护

HTML5新增语义化标签：header、footer、nav、article、aside、section等。

##CSS

 1.排版
 
 - position
 
```
    static 默认
    relative 相对定位
    absolute 绝对定位 飘出文档流
    如果一个元素绝对定位后，其参照物是以离自身最近元素是否设置了相对定位，如果有设置将以离自己最近元素定位，如果没有将往其祖先元素寻找相对定位元素，     一直找到html为止。
    fixed 固定 属于绝对定位
    inherit 规定应该从父元素继承 position 属性的值
```

- display

```
    inline 默认。此元素会被显示为内联元素，元素前后没有换行符。
    block 此元素将显示为块级元素，此元素前后会带有换行符。
    inline-block 行内块元素。
    flex（早期版本叫box） 将对象作为弹性伸缩盒显示。（http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html）
```
    
 - float、clear
 
 ```
    HTML页面的标准文档流(默认布局)是：从上到下，从左到右，遇块(块级元素)换行。
    浮动层：给元素的float属性赋值后，就是脱离文档流，进行左右浮动，紧贴着父元素(默认为body文本区域)的左右边框。
    而此浮动元素在文档流空出的位置，由后续的(非浮动)元素填充上去：块级元素直接填充上去，若跟浮动元素的范围发生重叠，浮动元素覆盖块级元素。
    内联元素：有空隙就插入。
    
    <div style="clear:both"></div>
    .clearfix:after {
        content: ".";
        display: block;
        height: 0;
        clear: both;
        visibility: hidden;
    }
 ```
 - 盒子模型
 
 ```
    内容(content)、填充(padding)、边框(border)、边界(margin)
    内容（content（with/height））、内边距（padding）、边框（border）、外边距（margin）
    box-sizing
        box-sizing属性可以为三个值之一：content-box（default），border-box，padding-box。

        content-box，border和padding不计算入width之内

        padding-box，padding计算入width内

        border-box，border和padding计算入width之内，其实就是怪异模式了~
 ```
 
 - 行
 
 ```
    line-height（http://www.studyofnet.com/news/273.html）:
        “行高“指一行文字的高度，具体来说是指两行文字间基线间的距离。在CSS，line-height被用来控制行与行之间的垂直距离。line-height 属性会影响行框的     布局。在应用到一个块级元素时，它定义了该元素中基线之间的最小距离而不是最大距离。
        从上到下四条线分别是顶线、中线、基线、底线，很像才学英语字母时的四线三格，我们知道vertical-align属性中有top、middle、baseline、bottom，就     是和这四条线相关。
        行高是指上下文本行的基线间的垂直距离，即图中两条红线间垂直距离。
    行距是指一行底线到下一行顶线的垂直距离，即第一行粉线和第二行绿线间的垂直距离。
    半行距是行距的一半，即区域3垂直距离/2，区域1，2，3，4的距离之和为行高，而区域1，2，4距离之和为字体size，所以半行距也可以这么算：（行高-字体         size）/2
    vertical-align（http://www.zhangxinxu.com/wordpress/2010/05/%E6%88%91%E5%AF%B9css-vertical-align%E7%9A%84%E4%B8%80%E4%BA%9B%E7%90%86%E8%A7%A3%E4%B8%8E%E8%AE%A4%E8%AF%86%EF%BC%88%E4%B8%80%EF%BC%89/）
        定义和用法
        vertical-align 属性设置元素的垂直对齐方式。
        说明
        该属性定义行内元素的基线相对于该元素所在行的基线的垂直对齐。允许指定负长度值和百分比值。这会使元素降低而不是升高。在表单元格中，这个属性会设         置单元格框中的单元格内容的对齐方式。
        值	描述
        长度	通过距离升高（正值）或降低（负值）元素。'0cm'等同于'baseline'
        百分值 – %	通过距离（相对于1line-height1值的百分大小）升高（正值）或降低（负值）元素。'0%'等同于'baseline'
        baseline	默认。元素的基线与父元素的基线对齐。
        sub	降低元素的基线到父元素合适的下标位置。
        super	升高元素的基线到父元素合适的上标位置。
        top	把对齐的子元素的顶端与line box顶端对齐。
        text-top	把元素的顶端与父元素内容区域的顶端对齐。
        middle	元素的中垂点与 父元素的基线加1/2父元素中字母x的高度 对齐。
        bottom	把对齐的子元素的底端与line box底端对齐。
        text-bottom	把元素的底端与父元素内容区域的底端对齐。
        inherit	采用父元素相关属性的相同的指定值。
 ```
 
 - 文本
 
 ```
    whitespace
        定义和用法
        white-space 属性设置如何处理元素内的空白。
        值	描述
        normal	默认。空白会被浏览器忽略。
        pre	空白会被浏览器保留。其行为方式类似 HTML 中的 <pre> 标签。
        nowrap	文本不会换行，文本会在在同一行上继续，直到遇到 <br> 标签为止。
        pre-wrap	保留空白符序列，但是正常地进行换行。
        pre-line	合并空白符序列，但是保留换行符。
        inherit	规定应该从父元素继承 white-space 属性的值。
    wordbreak
        定义和用法
        word-break 属性规定自动换行的处理方法。
        值	描述
        normal	使用浏览器默认的换行规则。
        break-all	允许在单词内换行。
        keep-all	只能在半角空格或连字符处换行。
    word-wrap    
        定义和用法
        word-wrap 属性允许长单词或 URL 地址换行到下一行。
        值	描述
        normal	只在允许的断字点换行（浏览器保持默认处理）。
        break-word	在长单词或 URL 地址内部进行换行。
    区别
        word-wrap:break-word与word-break:break-all共同点是都能把长单词强行断句，不同点是word-wrap:break-word会首先起一个新行来放置长单词，新的         行还是放不下这个长单词则会对长单词进行强制断句；而word-break:break-all则不会把长单词放在一个新行里，当这一行放不下的时候就直接强制断句了。
 ```
 
 2.绘制
    
 - background
 
 ```
    值	描述	
    background-color	规定要使用的背景颜色。	
    background-position	规定背景图像的位置。	
    background-size	规定背景图片的尺寸。	
    background-repeat	规定如何重复背景图像。	
    background-origin	规定背景图片的定位区域。	
    background-clip	规定背景的绘制区域。	
    background-attachment	规定背景图像是否固定或者随着页面的其余部分滚动。	
    background-image	规定要使用的背景图像。	
    inherit	规定应该从父元素继承 background 属性的设置。
    如何定位背景图像：
    body
    { 
        background-image:url('bgimage.gif');
        background-repeat:no-repeat;
        background-attachment:fixed;
        background-position:center;
    }
    CSS3 新属性（http://www.daqianduan.com/3302.html）
        Background Size属性用来重设你的背景图片。有几个属性值：
            (1)background-size: contain;
            缩小背景图片使其适应标签元素（主要是像素方面的比率）
            (2)background-size: cover;
            让背景图片放大延伸到整个标签元素大小（主要是像素方面的比率）
            (3)background-size: 100px 100px;
            标明背景图片缩放的尺寸大小
            (4)background-size: 50% 100%;
            百分比是根据内容标签元素大小，来缩放图片的尺寸大小
 ```
 - transform（转换）
 
 ```
    定义和用法
    transform 属性向元素应用 2D 或 3D 转换。该属性允许我们对元素进行旋转、缩放、移动或倾斜。
    语法
    transform: none|transform-functions;
    值	描述	
    none	定义不进行转换。	
    matrix(n,n,n,n,n,n)	定义 2D 转换，使用六个值的矩阵。	
    matrix3d(n,n,n,n,n,n,n,n,n,n,n,n,n,n,n,n)	定义 3D 转换，使用 16 个值的 4x4 矩阵。	
    translate(x,y)	定义 2D 转换。	
    translate3d(x,y,z)	定义 3D 转换。	
    translateX(x)	定义转换，只是用 X 轴的值。	
    translateY(y)	定义转换，只是用 Y 轴的值。	
    translateZ(z)	定义 3D 转换，只是用 Z 轴的值。	
    scale(x,y)	定义 2D 缩放转换。	
    scale3d(x,y,z)	定义 3D 缩放转换。	
    scaleX(x)	通过设置 X 轴的值来定义缩放转换。	
    scaleY(y)	通过设置 Y 轴的值来定义缩放转换。	
    scaleZ(z)	通过设置 Z 轴的值来定义 3D 缩放转换。	
    rotate(angle)	定义 2D 旋转，在参数中规定角度。	
    rotate3d(x,y,z,angle)	定义 3D 旋转。	
    rotateX(angle)	定义沿着 X 轴的 3D 旋转。	
    rotateY(angle)	定义沿着 Y 轴的 3D 旋转。	
    rotateZ(angle)	定义沿着 Z 轴的 3D 旋转。	
    skew(x-angle,y-angle)	定义沿着 X 和 Y 轴的 2D 倾斜转换。	
    skewX(angle)	定义沿着 X 轴的 2D 倾斜转换。	
    skewY(angle)	定义沿着 Y 轴的 2D 倾斜转换。	
    perspective(n)	为 3D 转换元素定义透视视图。
    例子
        div
        {
        transform:rotate(7deg);
        -ms-transform:rotate(7deg); 	/* IE 9 */
        -moz-transform:rotate(7deg); 	/* Firefox */
        -webkit-transform:rotate(7deg); /* Safari 和 Chrome */
        -o-transform:rotate(7deg); 	/* Opera */
        }
 ```
 
 3.动画
 
 - transition（过渡）
 
 ```
    语法
    transition: property duration timing-function delay;
    值	描述
    transition-property	规定设置过渡效果的 CSS 属性的名称。
    transition-duration	规定完成过渡效果需要多少秒或毫秒。
    transition-timing-function	规定速度效果的速度曲线。
        语法
        transition-timing-function: linear|ease|ease-in|ease-out|ease-in-out|cubic-
        bezier(n,n,n,n);
        值	描述
        linear	规定以相同速度开始至结束的过渡效果（等于 cubic-bezier(0,0,1,1)）。
        ease	规定慢速开始，然后变快，然后慢速结束的过渡效果（cubic-bezier(0.25,0.1,0.25,1)）。
        ease-in	规定以慢速开始的过渡效果（等于 cubic-bezier(0.42,0,1,1)）。
        ease-out	规定以慢速结束的过渡效果（等于 cubic-bezier(0,0,0.58,1)）。
        ease-in-out	规定以慢速开始和结束的过渡效果（等于 cubic-bezier(0.42,0,0.58,1)）。
        cubic-bezier(n,n,n,n)	在 cubic-bezier 函数中定义自己的值。可能的值是 0 至 1 之间的数值。
    transition-delay	定义过渡效果何时开始。
    例子
        <style> 
        div
        {
        width:100px;
        height:100px;
        background:blue;
        transition:width 2s;
        -moz-transition:width 2s; /* Firefox 4 */
        -webkit-transition:width 2s; /* Safari and Chrome */
        -o-transition:width 2s; /* Opera */
        }

        div:hover
        {
        width:300px;
        }
        </style>
 ```
 
 - animation(动画)
 
 ```
    语法
    animation: name duration timing-function delay iteration-count direction;
    值	描述
    animation-name	规定需要绑定到选择器的 keyframe 名称。。
    animation-duration	规定完成动画所花费的时间，以秒或毫秒计。
    animation-timing-function	规定动画的速度曲线。
    animation-delay	规定在动画开始之前的延迟。
    animation-iteration-count	规定动画应该播放的次数。
    animation-direction	规定是否应该轮流反向播放动画。
    例子
        <style> 
        div
        {
        width:100px;
        height:100px;
        background:red;
        position:relative;
        animation:mymove 5s infinite;
        -webkit-animation:mymove 5s infinite; /*Safari and Chrome*/
        }

        @keyframes mymove
        {
        from {left:0px;}
        to {left:200px;}
        }

        @-webkit-keyframes mymove /*Safari and Chrome*/
        {
        from {left:0px;}
        to {left:200px;}
        }
        </style>
 ```
 
##JS
<h3>ES6</h3>
##WEB API
##HTTP
##常见框架
##模块化开发
##构建工具
##版本控制
##优化
##算法

1.堆排序
    
##数据结构
##常见面试题
1.从浏览器地址栏输入url到显示页面的步骤(以HTTP为例)？
##坑
