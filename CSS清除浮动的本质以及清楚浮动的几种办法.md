# CSS清除浮动的本质以及清楚浮动的几种办法
## 清除浮动的本质
清除浮动的本质是清除浮动元素脱离标准流造成的影响
清除浮动的策略是闭合浮动，只让浮动在父盒子内部影响，**不影响父盒子外面的其他盒子**
## 清除浮动的几种方法
#### 额外标签法「隔墙法」
额外标签法🏷️会在浮动元素末尾添加一个🈳️的标签
- 优点：通俗易懂，书写方便✍️
- 缺点：添加许多无意义标签，结构性比较差
- 注意 ⚠️：新的空标签必须是一个块级元素
```html
<style>
    .child{
        width: 50px;
        height: 50px;
        border: blue 1px solid;
        float: left;
    }
    .box{
        border: black 1px solid;
    }
    .clear{
        clear: both;
    }
</style>
<body>
    <div class="box">
        <div class="child"></div>
        <div class="child"></div>
        <div class="clear"></div>
    </div>
</body>
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/9d19bbc59d5b4678a147587325a6f42e.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAQ2h1YW5ZYW5nIENoZW4=,size_20,color_FFFFFF,t_70,g_se,x_16)
#### 父级添加Overflow
可以给父级元素添加`Overflow`属性，将属性值设置为`hidden`，`auto`或`scroll`

- 优点：代码简介
- 缺点：无法显示溢出部分

```html
<style>
    .child{
        width: 50px;
        height: 50px;
        border: blue 1px solid;
        float: left;
    }
    .box{
        border: black 1px solid;
        overflow: hidden;
    }
</style>
<body>
    <div class="box">
        <div class="child"></div>
        <div class="child"></div>
    </div>
</body>
```
#### :after伪元素清除浮动
额外标签法的升级版，**很多大厂都在用这种清除浮动的方式**，但对IE不是很友好（基于现在IE已经淘汰了，所以不再做IE适配的讨论）
`:after`伪元素清除浮动相对于额外标签法的优点是没有多余的标签🏷️

```html
<style>
    .child{
        width: 50px;
        height: 50px;
        border: blue 1px solid;
        float: left;
    }
    .box{
        border: black 1px solid;
        overflow: hidden;
    }
    .clearfix::after{
        content: "";
        display: block;
        height: 0;
        clear: both;
        visibility: hidden;
    }
</style>
<body>
    <div class="box clearfix">
        <div class="child"></div>
        <div class="child"></div>
    </div>
</body>
```
#### 双伪元素
同样是作用在父元素上面的👆
是:after伪元素清除浮动的升级版，同时也是大厂常用的方式，同样有IE兼容问题，但IE已死不做讨论。

```html
<style>
    .child{
        width: 50px;
        height: 50px;
        border: blue 1px solid;
        float: left;
    }
    .box{
        border: black 1px solid;
        overflow: hidden;
    }
    .clearfix::after,.clearfix::before{
        display: table;
        content: "";

    }
    .clearfix::after{
        clear: both;
    }
</style>
<body>
    <div class="box clearfix">
        <div class="child"></div>
        <div class="child"></div>
    </div>
</body>
```

