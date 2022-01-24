# 搬运总结：flex 弹性布局归纳，解决CSS垂直居中问题

本文参考：

- https://juejin.cn/post/6844903474774147086#heading-1

- http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html?utm_source=tuicool

两篇文章整理而成

[TOC]

### 前言

一些常见，较为普通的布局模式主要依赖**display属性+position属性+float属性**，但倘若要实现一些特殊的布局，这种传统的布局方式实现起来就不是很方便。比如开发中常遇到的垂直居中布局。但flex布局具有很强的灵活性，任何一个容器都可以指定flex布局，连行内元素也可以使用flex布局。

> 采用 Flex 布局的元素，称为 Flex 容器（flex container），简称"容器"。它的所有子元素自动成为容器成员，称为 Flex 项目（flex item），简称"项目"。
>
> ![image-20220124163021648](https://vichien-public.oss-cn-guangzhou.aliyuncs.com/typora/image-20220124163021648.png)
>
> 容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。主轴的开始位置（与边框的交叉点）叫做`main start`，结束位置叫做`main end`；交叉轴的开始位置叫做`cross start`，结束位置叫做`cross end`。

### ✅ 解决开发中垂直居中的问题

```css
#父元素 {
    display: flex;
    justify-content: center; // 定义如何沿着主轴方向（X轴）排列子容器
    align-items: center // 用于定义如何沿着交叉轴（Y轴）方向排列子容器
}
```

### **justify-content**：设置子容器沿主轴（X轴）方向排列

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/5f2a17efffe8f3ab78a4.png~tplv-t2oaga2asx-watermark.image)

常用属性：

#### **flex-start**：起始端对齐

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/ac1d8c5e7b4a2ba51ca7.png~tplv-t2oaga2asx-watermark.image)

#### **flex-end**：末尾段对齐

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/9ec9245881c2882a35a6.png~tplv-t2oaga2asx-watermark.image)

#### **center**：居中对齐

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/476461f1b9604a985046.png~tplv-t2oaga2asx-watermark.image)

#### **space-around**：

子容器沿主轴均匀分布，位于首尾两端的子容器到父容器的距离是子容器间距的一半。

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/63119c88aa64853107a9.png~tplv-t2oaga2asx-watermark.image)

#### **space-between**：

子容器沿主轴均匀分布，位于首尾两端的子容器与父容器贴合。

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/495f46fc9c5c0c6d1e65.png~tplv-t2oaga2asx-watermark.image)

### **align-items**：设置子容器如何沿交叉轴（Y轴）排列

#### **flex-start**：起始端对齐

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/93d138727b9dd780bdda.png~tplv-t2oaga2asx-watermark.image)

#### **flex-end**：末尾段对齐

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/112f075777fdcb6f5d6f.png~tplv-t2oaga2asx-watermark.image)

#### **center**：居中对齐

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/d7b0131447247a5228fe.png~tplv-t2oaga2asx-watermark.image)

#### **baseline**：基线对齐

![image-20220124172936451](https://vichien-public.oss-cn-guangzhou.aliyuncs.com/typora/image-20220124172936451.png)

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/26b04323df92c4b1b023.png~tplv-t2oaga2asx-watermark.image)

#### **stretch**：拉伸对齐

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/ef196e2ba84c406c9ad6.png~tplv-t2oaga2asx-watermark.image)

### **align-content**：多行沿交叉轴对齐

#### **flex-start**：起始端对齐

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/0183db03d8fedadc4cf8.png~tplv-t2oaga2asx-watermark.image)

#### **flex-end**：末尾段对齐

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/12e524438423ac7afc8c.png~tplv-t2oaga2asx-watermark.image)

#### **center**：居中对齐

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/274a5c1282b997e423db.png~tplv-t2oaga2asx-watermark.image)

#### **space-around**：等边距均匀分布

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/4a435e3fd0cab3433631.png~tplv-t2oaga2asx-watermark.image)

#### **space-between**：等间距均匀分布（顶、底贴合父容器）

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/f50d931bdfeb6c24ccae.png~tplv-t2oaga2asx-watermark.image)

#### **stretch**：拉伸对齐

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/878b39463db6bc499fbc.png~tplv-t2oaga2asx-watermark.image)

### 如何定义盒子中主轴和交叉轴的方向？

#### 向右：`flex-direction: row` （默认值）

![image-20220124173428294](https://vichien-public.oss-cn-guangzhou.aliyuncs.com/typora/image-20220124173428294.png)

#### 向左：`flex-direction: row-reverse`

![image-20220124173451404](https://vichien-public.oss-cn-guangzhou.aliyuncs.com/typora/image-20220124173451404.png)

#### 向下：`flex-direction: column` （默认值）

![image-20220124173620266](https://vichien-public.oss-cn-guangzhou.aliyuncs.com/typora/image-20220124173620266.png)

#### 向上：`flex-direction: column-reverse`

![image-20220124173650648](https://vichien-public.oss-cn-guangzhou.aliyuncs.com/typora/image-20220124173650648.png)

### 如何定义父容器中的换行方式 **flex-wrap**

flex-wrap有3个值，分别是`nowrap`，`wrap`，`wrap-reverse`

#### **nowrap**：不换行

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/a41d1342e46cd37cd09e.png~tplv-t2oaga2asx-watermark.image)

#### **wrap**：换行

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/0566bf9682ffa0890624.png~tplv-t2oaga2asx-watermark.image)

#### **wrap-reverse**：逆序换行

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/2f578fcc69919238bd3b.png~tplv-t2oaga2asx-watermark.image)

### 设置子容器的基准大小：**flex-basis**

flex-basis为容器设置不伸缩（压缩）情况下的默认尺寸。当主轴为横向时代表宽度，主轴为纵向时代表高度

![image-20220124211445287](https://vichien-public.oss-cn-guangzhou.aliyuncs.com/typora/image-20220124211445287.png)

### 设置子容器弹性伸展的比例：**flex-grow**

如图，在子容器基准大小为300px的情况下，将剩余空间划分为6份，1份分给第一个盒子，2份分给第二个盒子，3份分给第三个盒子

![image-20220124212156295](https://vichien-public.oss-cn-guangzhou.aliyuncs.com/typora/image-20220124212156295.png)

### 设置子容器弹性收缩的比例：**flex-shrink**

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/38596937d4f86beeac0b.png~tplv-t2oaga2asx-watermark.image)

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/d278e36c13b9643ff481.png~tplv-t2oaga2asx-watermark.image)

### 设置排列顺序：**order**

改变子容器的排列顺序，覆盖 HTML 代码中的顺序，默认值为 0，可以为负值，数值越小排列越靠前。

![img](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/leancloud-assets/4eb20f9bfc611e66b069.png~tplv-t2oaga2asx-watermark.image)