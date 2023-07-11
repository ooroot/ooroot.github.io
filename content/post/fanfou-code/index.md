---
title: "饭否Flash插件"
categories:
  - Code
tags:
  - Flash
  - code
  - QQ空间
date: 2008-09-20
---

嘿嘿，做了个饭否Flash插件，放在博客上

　　饭否是什么？

注册饭否：http://fanfou.com
饭否是一个迷你博客。你可以通过手机、网页、MSN/GTalk/QQ随时随地发消息，时时刻刻看朋友。

## 饭否Flash插件

功能:以引用的方式把饭否即时信息发布到其他博客上面

### 使用说明：
页面中插入以下HTML代码：

```html
<embed flashvars="id=饭否ID" bgcolor="#001342" allowscriptaccess="sameDomain" wmode="Transparent" height="130" loop="false" menu="false" name="FanShow" pluginspage="http://www.macromedia.com/go/getflashplayer" quality="high" src="http://www.1314520o.com/ling/FanShow.swf" mce_src="http://www.1314520o.com/ling/FanShow.swf" type="application/x-shockwave-flash" width="335"/>
```

### 定制的部分：

flashvars：“饭否ID”
wmode：”Transparent”，则Flash背景为透明色。
bgcolor：”#001342” Flash的背景颜色，如果需要显示背景颜色，记得把wmode属性去掉。


需要使用swf（如qq空间）调用的Flash地址代码：

W335 X H130

http://www.1314520o.com/ling/FanShow.swf?id=你的饭否ID

例如我的ID

http://www.1314520o.com/ling/FanShow.swf?id=wulinfo