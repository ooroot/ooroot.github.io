---
title: 给图片添加效果
description: 给你的图片加上动态图形（PNG或GIF），包括：圆钉、透明胶、回形针、黄胶纸、花纹等等。
date: 2008-10-21
categories:
    - Code
tags: 
    - css
    - web
---


首先注意这个CSS只针对有CSS基础的朋友，至于应用我就不详加解释了，可以参考本文的源码。大致原理是通过CSS相对定位将PNG或GIF图形附加到图片上，使其重叠而产生效果。

给你的图片加上动态图形（PNG或GIF），包括：圆钉、透明胶、回形针、黄胶纸、花纹等等。

圆钉
image
透明胶
image
回形针
image
黄胶纸
image
花纹
image
下面是小图边框
image

写图志一直是我比较喜欢的方式，可是用表格排版还是不爽的，今天选择了这个CSS相对定位，这个CSS不止可以便捷的写图纸还能加上华丽的相框，比较遗憾的是图片尺寸大小受限于PNG图片。

 

下面是一些演示…

image
圆角无边

image
切角

image
圆角边

image
邮票

image
墨刷

image
梦幻

image
艺术线切

image
透明高光

不过使用绝对定位，这点不好，很难控制，不过看起来效果还很漂亮的

下面CSS加入主题样式
```css
div.post-body .gallery {
margin: 10px 0 0 0;
position: relative;
float: none;/*一个一行 left值则为自动换行*/
}
div.post-body .gallery img {
background: #fff;
border: solid 1px #ccc;
padding: 4px;
}
div.post-body .gallery-s {
margin: 2px 5px 2px 2px;
position: relative;
float: left;
text-align:justify;
}
div.post-body .gallery-s img {
background: #fff;
border: solid 1px #ccc;
padding: 4px;
}
div.post div.post-body .gallery1 span {
width: 28px;
height: 21px;
display: block;
position: absolute;
top: -12px;
left: 48%;
background: url(images/pin.png) no-repeat;
}
div.post div.post-body .gallery2 span{
width: 77px;
height: 27px;
display: block;
position: absolute;
top: -12px;
left: 43%;
background: url(images/tape.png) no-repeat;
}
div.post-body .gallery3 span {
width: 30px;
height: 60px;
display: block;
position: absolute;
top: -5px;
left: -2px;
background: url(images/paper-clip.png) no-repeat;
}
div.post-body .gallery4 span {
width: 115px;
height: 32px;
display: block;
position: absolute;
top: -13px;
left: 40%;
background: url(images/tape2.png) no-repeat;
}
div.post-body .gallery5 span {
width: 122px;
height: 72px;
display: block;
position: absolute;
top: -22px;
left: -15px;
background: url(images/floral-corner.png) no-repeat;
}
div.post-body .gallery6 span {
width: 189px;
height: 137px;
display: block;
position: absolute;
top: -5px;
left: -5px;
background: url(images/cut-corner.png) no-repeat;
}
div.post-body .gallery7 span {
width: 170px;
height: 120px;
display: block;
position: absolute;
top: 0;
left: 0;
background: url(images/round-corner.png) no-repeat;
}
div.post-body .gallery7 img {
border: none;
padding: 0;
}
div.post-body .gallery8 span {
width: 170px;
height: 120px;
display: block;
position: absolute;
top: 5px;
left: 6px;
background: url(images/round-corner.png) no-repeat;
}
div.post-body .gallery8 img {
border: none;
padding: 5px 6px 6px;
background: url(images/round-bg.gif) no-repeat;
}
div.post-body .gallery9 span {
width: 170px;
height: 120px;
display: block;
position: absolute;
top: 6px;
left: 7px;
background: url(images/stamp-pattern.png) no-repeat;
}
div.post-body .gallery9 img {
border: none;
padding: 6px 7px 7px;
background: url(images/stamp-bg.gif) no-repeat;
}
div.post-body .gallery10 span {
width: 181px;
height: 134px;
display: block;
position: absolute;
top: -6px;
left: -6px;
background: url(images/brush-border.png) no-repeat;
}
div.post-body .gallery10 img {
border: none;
padding: 0;
}
div.post-body .gallery11 span {
width: 216px;
height: 166px;
display: block;
position: absolute;
top: -17px;
left: -18px;
background: url(images/gold-frame.png) no-repeat;
}
div.post-body .gallery12 span {
width: 186px;
height: 137px;
display: block;
position: absolute;
top: 2px;
left: 2px;
background: url(images/watercolor-top.png) no-repeat;
}
div.post-body .gallery12 img {
border: none;
padding: 9px 12px 12px 11px;
background: url(images/watercolor-bg.png) no-repeat;
}
div.post-body .gallery13 span {
width: 170px;
height: 120px;
display: block;
position: absolute;
top: 0;
left: 0;
background: url(images/mask.png) no-repeat;
}
div.post-body .gallery13 img {
border: none;
padding: 0;
}
div.post-body .gallery14 span {
width: 170px;
height: 84px;
display: block;
position: absolute;
top: 5px;
left: 5px;
background: url(images/glossy-gradient.png);
}
```

下面是应用代码（图志）
```html
<div class="gallery-s">
 <ul>
  <li><span> </span><img alt="image" src="图片地址" /></li>
 </ul>
</div>
```
其中gallery-s表示小图

下面是大图附件图形的应用代码
```html
<div class="gallery gallery1">
 <ul>
  <li style="text-align: center;"><span> </span><img src="图片地址" alt="image" /></li>
 </ul>
</div>
```
其中gallery gallery1 为PNG图形序列1-6

至于其他应用请参考本文源码或CSS

源码下载：失效