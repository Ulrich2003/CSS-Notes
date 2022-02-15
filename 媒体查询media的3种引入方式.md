# 媒体查询media的3种引入方式
### 第一种：利用@media引入
在`<style>...</style>`标签里使用`@media`来实现媒体查询
```html
<!DOCTYPE html>
<html lang="en">
  <body>
    <div id="box"></div>
  </body>

  <style>
    @media (min-device-width: 300px) and (max-device-width: 500px) {
      #box {
        width: 100px;
        height: 100px;
        background-color: cadetblue;
      }
    }
    @media (min-device-width: 501px) {
      #box {
        width: 100px;
        height: 100px;
        background-color: blueviolet;
      }
    }
  </style>
</html>
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/783e6b3e35eb45e88ea2fb8f05262adc.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ2h1YW5ZYW5nIENoZW4=,size_20,color_FFFFFF,t_70,g_se,x_16)
### 第二种：
在`<style>...</style>`标签上使用`media=""`
⚠️ 注意： and左右的空格和小括号都不能少
```html
<!DOCTYPE html>
<html lang="en">
  <body>
    <div id="box"></div>
  </body>

  <style media="(min-device-width: 300px) and (max-device-width: 500px)">
    #box {
      width: 100px;
      height: 100px;
      background-color: cadetblue;
    }
  </style>
  
  <style media="(min-device-width: 501px)">
    #box {
      width: 100px;
      height: 100px;
      background-color: blueviolet;
    }
  </style>
</html>
```
### 第三种：
在`<link>...</link>`标签上使用`media=""`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <link
      rel="stylesheet" href="./style1.css"
      media="(min-device-width: 300px) and (max-device-width: 500px)"
    />
    <link
      rel="stylesheet" href="./style2.css"
      media="(min-device-width: 501px)"
    />
  </head>

  <body>
    <div id="box"></div>
  </body>

</html>
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/42dbea66cac94871b0a1fd4e0aa01beb.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ2h1YW5ZYW5nIENoZW4=,size_20,color_FFFFFF,t_70,g_se,x_16)
![在这里插入图片描述](https://img-blog.csdnimg.cn/898ad5f02f074b48ab0c3421aab5449d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ2h1YW5ZYW5nIENoZW4=,size_20,color_FFFFFF,t_70,g_se,x_16)

