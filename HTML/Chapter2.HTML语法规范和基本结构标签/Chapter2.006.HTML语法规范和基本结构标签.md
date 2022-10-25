# 基本语法规范

HTML 标签是由尖括号包围的关键词，例如<html>。

闭合标签， 双标签， container tags ： 

- 前半部部分称为 opening tags, 后半部分称为 closing tags

- 常见的为双标签： HTML 标签通常是成对出现的，例如<html>和<html/>，称为双标签。第一个是开始标签，第二个是结束标签。比如 <标签名> 内容 </标签名>   比如<body>我是文字</body>

单标签，闭合标签， non-container tags 

- 不常见的为单标签：有些特殊标签必须是单个标签（极少情况），例如`<br/>或<br>`，我们称之为单标签。

## 标签关系

标签关系可以分为两类：包含关系和并列关系
嵌套关系父子级包含关系
并列关系兄弟级并列关系
如果两个标签之间的关系是嵌套关系，子元素最好缩进一个tab键的身位（一个tab是4个空格）。如果是并列关系，最好上下对齐。

# HTML 基本结构标签

每个网页都会有一个基本的结构标签，页面内容都是在这些基本标签上书写。 HTML 页面也叫 HTML 文档。
基本骨架:

```html
<!-- 页面中最大的标签 根标签 -->
<html>
    <!-- 头部标签 -->
    <head>     
        <!-- 标题标签 -->
        <title></title> 
    </head>
    <!-- 文档的主体 -->
    <body>
    </body>
</html>
```

| 标签名             | 定义     | 说明                            |
| --------------- | ------ | ----------------------------- |
| <html></html>   | HTML标签 | 页面中的最大的标签，我们称为根标签             |
| <head><head>    | 文档的头部  | 注意在head标签中我们必须要设置的标签是title    |
| <title></title> | 文档的标题  | 让页面拥有一个属于自己的网页标题              |
| <body></body>   | 文档的主体  | 元素包含文档的所有内容，页面内容基本都是放到body里面的 |

## 文档类型声明标签 <!DOCTYPE>

<!DOCTYPE>

文档类型声明，作用就是告诉浏览器使用哪种HTML版本来显示网页。
<!DOCTYPE html> 这句代码的意思是: 当前页面采取的是 <mark>HTML5 </mark>版本来显示网页.
注意：
<!DOCTYPE> 声明位于文档中的<mark>最前面的位置，处于 <html> 标签之前</mark>。
<!DOCTYPE> 不是一个 HTML 标签，它就是文档类型声明标签。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>

</body>
</html>
```

## lang 语言种类

```html
<html lang="en">

</html>
```

用来定义当前文档显示的语言

这样的可以，来告诉阅览器这个页面采取html5版本来显示页面

- en 定义语言为英语, 就是定义为英文网页
- zh-CN 定义语言为中文， 就是定义为 中文网页

其实对于文档显示来说， 定义成 en 的文档也可以显示中文， 定义成 zh-CN的文档也可以显示英文

**「lang的作用」**

- 根据根据lang属性来设定不同语言的css样式，或者字体

- 告诉搜索引擎做精确的识别

- 让语法检查程序做语言识别

- 帮助翻译工具做识别

- 帮助网页阅读程序做识别

## Head 标签部分

Meta 标签 为面属性标签， 它用来标书我们网站的一些信息

Meta标签一般用来作 SEO 

## title 网站标题

`title` 具有不可替代性，是我们内页的第一个重要标签，是搜索引擎了解网页的入口和对网页主题归属的最佳判断点。

## Meta 标签

#### charset 字符集

```html
<head>
    <meta charset="UTF-8">
</head>
```

字符集（character set）是多个字符的集合，以便计算机能够识别和存储各种文字。
在<head>标签内，可以通过<meta>标签的charset 属性来设置文档使用何种字符编码。
charset常用的值有：GB2312 , GBK、UTF-8，其中UTF-8被称为万国码，基本包含了全世界所有国家需要用到的字符。

#### name 属性

```html
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <meta name="description" content="来这个地方能够学习java">
</head>
```

**name属性的取值**

- keywords(关键字) 告诉搜索引擎，该网页的关键字

- description(网站内容描述) 用于告诉搜索引擎，你网站的主要内容。

- viewport(移动端的窗口)
  
  - 通常viewport是指视窗、视口。浏览器上(也可能是一个app中的webview)用来显示网页的那部分区域。在移动端和pc端视口是不同的，pc端的视口是浏览器窗口区域，而在移动端有三个不同的视口概念：布局视口、视觉视口、理想视口

- robots(定义搜索引擎爬虫的索引方式) robots用来告诉爬虫哪些页面需要索引，哪些页面不需要索引

- author(作者)

- generator(网页制作软件）

- copyright(版权)

<mark>后面的 content 中的值， 就是只 前面为 name = viewport 的时候， 这个 viewport 对应的取值</mark>

#### http-equiv属性

```html
<head>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
</head>
```

http-equiv相当于http的文件头作用，它可以向浏览器传回一些有用的信息，以帮助正确和精确地显示网页内容

- content-Type 设定网页字符集(Html4用法，不推荐)

- Expires(期限) ,可以用于设定网页的到期时间。一旦网页过期，必须到服务器上重新传输。

- Pragma(cache模式),是用于设定禁止浏览器从本地机的缓存中调阅页面内容，设定后一旦离开网页就无法从Cache中再调出

- Refresh(刷新),自动刷新并指向新页面。

- cache-control（请求和响应遵循的缓存机制）

#### keywords

- keywords 是页面关键词，是搜索引擎的关注点之一。
- keywords 最好限制为6～8 个关键词，关键词之间用英文逗号隔开，采用关键词1,关键词2 的形式。

### description 网站说明

简要说明我们网站主要是做什么的

# HTML页面结构分析

![](.\Chapter2_001_狂神_页面结构分析.png)

# HTML标签的语义化

- 方便代码的阅读和维护，样式丢失的时候能让页面呈现清晰的结构。

- 有利于SEO，搜索引擎根据标签来确定上下文和各个关键字的权重。

- 方便其他设备解析，如盲人阅读器根据语义渲染网页

-  标签：规定页面上所有链接的默认 URL 和设置整体链接的打开状态

# TDK 标签 SEO 优化

https://docs.mphy.top/#/HTML/ch04

SEO（Search Engine Optimization），即搜索引擎优化，是一种利用搜索引擎的规则提高网站在有关搜索引擎内自然排名的方式。

SEO 的目的是对网站进行深度优化，从而帮助网站获得免费流量，进而在搜索引擎上提升网站排名，提高网站知名度。

页面必须有三个标签用来进行 SEO 优化。

- `title`
- `description`
- `keyword`

```html
<!-- 网站标题 -->
<title></title>
<!-- 网站说明 -->
<meta name="description" content="">
<!-- 网站关键词 -->
<meta name="keywords" content="">
```

## title 网站标题

`title` 具有不可替代性，是我们内页的第一个重要标签，是搜索引擎了解网页的入口和对网页主题归属的最佳判断点。

建议：网站名（产品名）- 网站的介绍（尽量不要超过30个汉字）

例如：

- 京东(JD.COM) - 综合网购首选-正品低价、品质保障、配送及时、轻松购物！
- 小米商城 - 小米5s、红米Note 4、小米MIX、小米笔记本官方网站

## description 网站说明

简要说明我们网站主要是做什么的。

我们提倡，description 作为网站的总体业务和主题概括，多采用“我们是…”、“我们提供…”、“×××网作为…”、“电话：010…”之类语句。

例如：

```html
<meta name="description" content="京东JD.COM-专业的综合网上购物商城,销售家电、数码通讯、电脑、家居百货、服装服饰、母婴、图书、食品等数万个品牌优质商品.便捷、诚信的服务，为您提供愉悦的网上购物体验!" />
```

## keywords 关键字

- keywords 是页面关键词，是搜索引擎的关注点之一。
- keywords 最好限制为6～8 个关键词，关键词之间用英文逗号隔开，采用关键词1,关键词2 的形式。

例如：

```html
<meta name= " keywords" content="网上购物,网上商城,手机,笔记本,电脑,MP3,CD,VCD,DV,相机,数码,配件,手表,存储卡,京东" />
```

## LOGO SEO优化

1. logo 里面首先放一个h1 标签，目的是为了提权，告诉搜索引擎，这个地方很重要。

2. h1 里面再放一个链接，可以返回首页的，把logo 的背景图片给链接即可。

3. 为了搜索引擎收录我们，我们链接里面要放文字（网站名称），但是文字不要显示出来。
- 方法1：text-indent 移到盒子外面（text-indent: -9999px) ，然后overflow:hidden ，淘宝的做法。

- 方法2：直接给font-size: 0; 就看不到文字了，京东的做法。
4. 最后给链接一个title 属性，这样鼠标放到 logo 上就可以看到提示文字了。

# XHTML

XHTML 指「可扩展超文本标签语言」（EXtensible HyperText Markup Language）。
XHTML 的目标是取代 HTML。
XHTML 与 HTML 4.01 几乎是相同的。
XHTML 是更严格更纯净的 HTML 版本。
XHTML 是作为一种 XML 应用被重新定义的 HTML,是严格版本的HTML。例如它要求标签必须小写，标签必须被正确关闭，标签顺序必须正确排列，对于属性都必须使用双引号等。
XHTML 是一个 W3C 标准。

# 写HTML代码时应注意什么？

- 尽可能少的使用无语义的标签div和span；

- 在语义不明显时，既可以使用div或者p时，尽量用p, 因为p在默认情况下有上下间距，对兼容特殊终端有利；

- 不要使用纯样式标签，如：b、font、u等，改用css设置。

- 需要强调的文本，可以包含在strong或者em标签中（浏览器预设样式，能用CSS指定就不用他们），strong默认样式是加粗（不要用b），em是斜体（不用i）；

- 使用表格时，标题要用caption，表头用thead，主体部分用tbody包围，尾部用tfoot包围。表头和一般单元格要区分开，表头用th，单元格用td；

- 表单域要用fieldset标签包起来，并用legend标签说明表单的用途；

- 每个input标签对应的说明文本都需要使用label标签，并且通过为input设置id属性，在lable标签中设置for来让说明文本和相对应的input关联起来。 了
