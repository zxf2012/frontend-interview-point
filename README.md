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
    如果一个元素绝对定位后，其参照物是以离自身最近元素是否设置了相对定位，如果有设置将以离自己最近元素定位，如果没有将往其祖先元素寻找相对定位元素，一直     找到html为止。
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
 
 
 
 2.绘制
 
 3.动画
 
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
