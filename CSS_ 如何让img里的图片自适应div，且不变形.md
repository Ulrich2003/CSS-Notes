# 如何让img里的图片自适应div，且不变形

```html
<div>
    <img src="..." alt="image">
<div>
```
解决方案：使用`object-fit`属性

```css
img{
    width: 100%;
    height: 100%;
    object-fit: cover;
}
```
`object-fit`中的几个属性值：
|值| 功能 |
|--|--|
| fill | 不保持纵横比缩放图片，使图片完全适应 |
| contain|保持纵横比缩放图片，使图片的长边能完全显示出来 |
|cover|保持纵横比缩放图片，只保证图片的短边能完全显示出来|
|none|保持图片宽高不变|
|scale-down|当图片实际宽高小于所设置的图片宽高时，显示效果与none一致；否则，显示效果与contain一致|

