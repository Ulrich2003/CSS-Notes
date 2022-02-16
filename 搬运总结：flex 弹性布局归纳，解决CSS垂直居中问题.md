# 搬运总结：flex 弹性布局归纳，解决CSS垂直居中问题

本文参考：

- https://juejin.cn/post/6844903474774147086#heading-1

- http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html?utm_source=tuicool

两篇文章整理而成

推荐一个非常不错的布局课程：

- https://www.bilibili.com/video/BV1ov411k7sm?p=7&spm_id_from=pageDriver

@[toc]
### 前言

一些常见，较为普通的布局模式主要依赖**display属性+position属性+float属性**，但倘若要实现一些特殊的布局，这种传统的布局方式实现起来就不是很方便。比如开发中常遇到的垂直居中布局。但flex布局具有很强的灵活性，任何一个容器都可以指定flex布局，连行内元素也可以使用flex布局。

> 采用 Flex 布局的元素，称为 Flex 容器（flex container），简称"容器"。它的所有子元素自动成为容器成员，称为 Flex 项目（flex item），简称"项目"。
>
> ![image-20220124163021648](https://img-blog.csdnimg.cn/img_convert/209d36cd6b3334c5475196af8291f683.png)
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

![img](https://img-blog.csdnimg.cn/img_convert/71245457dc0bd43a867b901a00b06b1e.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/3aaec32a1b7d47958466946eecd22697.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ2h1YW5ZYW5nIENoZW4=,size_20,color_FFFFFF,t_70,g_se,x_16)

常用属性：

#### **flex-start**：起始端对齐

![img](https://img-blog.csdnimg.cn/img_convert/4e3ef2b022ff8cf19c88e55b44702368.png)

#### **flex-end**：末尾段对齐

![img](https://img-blog.csdnimg.cn/img_convert/f48e25978ee900af114f65531ca14d05.png)

#### **center**：居中对齐

![img](https://img-blog.csdnimg.cn/img_convert/e28a4104d61dfc072ecfbe3be601841a.png)

#### **space-around**：

子容器沿主轴均匀分布，位于首尾两端的子容器到父容器的距离是子容器间距的一半。

![img](https://img-blog.csdnimg.cn/img_convert/aafac2201935e2ceb317f38c9b7f8998.png)

#### **space-between**：

子容器沿主轴均匀分布，位于首尾两端的子容器与父容器贴合。

![img](https://img-blog.csdnimg.cn/img_convert/86162dc6375ceb27bb69890b2f3883f8.png)

### **align-items**：设置子容器如何沿交叉轴（Y轴）排列
![在这里插入图片描述](https://img-blog.csdnimg.cn/fa30918b803f45ec8a3c48393073d347.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ2h1YW5ZYW5nIENoZW4=,size_20,color_FFFFFF,t_70,g_se,x_16)
#### **flex-start**：起始端对齐

![img](https://img-blog.csdnimg.cn/img_convert/87dadd6fe95d9228c4aee29f2c1bb42d.png)

#### **flex-end**：末尾段对齐

![img](https://img-blog.csdnimg.cn/img_convert/0bad9024f86234914bec973e167c18a9.png)

#### **center**：居中对齐

![img](https://img-blog.csdnimg.cn/img_convert/6aae2c04d3c9ec5fd5ad442f08e21826.png)

#### **baseline**：基线对齐

![image-20220124172936451](https://img-blog.csdnimg.cn/img_convert/73d9093e00d83c2467e3acecb94c65b8.png)

![img](https://img-blog.csdnimg.cn/img_convert/a5bad63a806257815309046e1d46dde9.png)

#### **stretch**：拉伸对齐

![img](https://img-blog.csdnimg.cn/img_convert/5056e04cc1688ebe4258285385a4df41.png)

### **align-content**：多行沿交叉轴对齐
align-items是将每一行视为一个整体来处理的，相对于align-items，align-content是将多行视为一个整体来进行对齐的。
![在这里插入图片描述](https://img-blog.csdnimg.cn/c01465cbb9ca481ba87d2079736cd3d3.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ2h1YW5ZYW5nIENoZW4=,size_20,color_FFFFFF,t_70,g_se,x_16)


#### **flex-start**：起始端对齐

![img](https://img-blog.csdnimg.cn/img_convert/c2b780556343d5ca3e8cb70a48470f60.png)

#### **flex-end**：末尾段对齐

![img](https://img-blog.csdnimg.cn/img_convert/719066674e1b804082b120cdda554fc3.png)

#### **center**：居中对齐

![img](https://img-blog.csdnimg.cn/img_convert/2c0fe0701ff76dfbbba445d2e8759577.png)

#### **space-around**：等边距均匀分布

![img](https://img-blog.csdnimg.cn/img_convert/48d762917a0e88fc9a5d0900bbf1eca8.png)

#### **space-between**：等间距均匀分布（顶、底贴合父容器）

![img](https://img-blog.csdnimg.cn/img_convert/c8fd2875bf2e36d6a0cc0b0bbd060cb3.png)

#### **stretch**：拉伸对齐

![img](https://img-blog.csdnimg.cn/img_convert/a781912eee6aea80e1f46f801a85d722.png)

### 如何定义盒子中主轴和交叉轴的方向？
![在这里插入图片描述](https://img-blog.csdnimg.cn/0c9a13e0385941ff9dbf6192739cbd6d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ2h1YW5ZYW5nIENoZW4=,size_20,color_FFFFFF,t_70,g_se,x_16)

#### 向右：`flex-direction: row` （默认值）

![image-20220124173428294](https://img-blog.csdnimg.cn/img_convert/761616a23a7ca9d0cb923cfcff49215e.png)

#### 向左：`flex-direction: row-reverse`

![image-20220124173451404](https://img-blog.csdnimg.cn/img_convert/bd2f6a486171856ae21697b4ac33b261.png)

#### 向下：`flex-direction: column` （默认值）

![image-20220124173620266](https://img-blog.csdnimg.cn/img_convert/77eb8336f2639eaaae28b5e9dedb00f6.png)

#### 向上：`flex-direction: column-reverse`

![image-20220124173650648](https://img-blog.csdnimg.cn/img_convert/a232d610705770922b12c54468b0ab03.png)

### 如何定义父容器中的换行方式 **flex-wrap**

flex-wrap有3个值，分别是`nowrap`，`wrap`，`wrap-reverse`

#### **nowrap**：不换行

![img](https://img-blog.csdnimg.cn/img_convert/f0157c8c6080d48789c098630a90201e.png)

#### **wrap**：换行

![img](https://img-blog.csdnimg.cn/img_convert/955fda61df08c4936f0cdb98209cffde.png)

#### **wrap-reverse**：逆序换行

![img](https://img-blog.csdnimg.cn/img_convert/be89da8b08f002d21ce2c8f42c3468f5.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/b5c938c5dc7c4079a0c07cf1204f4da9.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ2h1YW5ZYW5nIENoZW4=,size_20,color_FFFFFF,t_70,g_se,x_16)

### 设置子容器的基准大小：**flex-basis**

flex-basis为容器设置不伸缩（压缩）情况下的默认尺寸。当主轴为横向时代表宽度，主轴为纵向时代表高度。
⚠️ 在主轴为横向时，设置了`flex-basis`后，`width`将会失效

![image-20220124211445287](https://img-blog.csdnimg.cn/img_convert/078e3a9b7b5531f4916b83a14484059b.png)

### 设置子容器弹性伸展的比例：**flex-grow**

如图，在子容器基准大小为300px的情况下，将剩余空间划分为6份，1份分给第一个盒子，2份分给第二个盒子，3份分给第三个盒子

![image-20220124212156295](https://img-blog.csdnimg.cn/img_convert/ca4d21b2d9ba543f6df5010083c331d3.png)

### 设置子容器弹性收缩的比例：**flex-shrink**

![img](https://img-blog.csdnimg.cn/img_convert/47475fbff0eb308934dea6b8bc9c2901.png)

![img](https://img-blog.csdnimg.cn/img_convert/4f7d9d1afa1d65bc4d702d47d7736903.png)

### 设置排列顺序：**order**

改变子容器的排列顺序，覆盖 HTML 代码中的顺序，默认值为 0，可以为负值，数值越小排列越靠前。

![img](https://img-blog.csdnimg.cn/img_convert/d9bc28ebedfcb87a5811ef074b9e7cae.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/76a7f77e0a3b4300920b7d11646c0ddb.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ2h1YW5ZYW5nIENoZW4=,size_20,color_FFFFFF,t_70,g_se,x_16)

