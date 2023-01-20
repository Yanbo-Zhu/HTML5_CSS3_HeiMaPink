

# 1 其他类型的居中
-   有宽度的块级元素居中对齐，是margin: 0 auto;
-   让文字居中对齐，是 text-align: center;
- 
# 2 horizontal-align 水平方向
不存在  horizontal-align 这eigenschaft  

## 2.1 text-align (Horizontale Ausrichtung )

`text-align` 属性用于设置元素文本内容的对齐方式。相当于html中的align对齐属性。
Die horizontale Ausrichtung kennen Sie bereits aus Textverarbeitungsprogrammen, wobei sich text-align nicht nur auf wirkliche Texte bezieht sondern auf alle Elemente innerhalb eines Block-Elementes.


注意：是让盒子里面的文本内容水平居中， 而不是让盒子居中对齐

```
div {
  text-align: center;
}
```

| 属性值    | 解释      |
| ------ | ------- |
| left   | 左对齐（默认） |
| right  | 右对齐     |
| center | 居中对齐    |
|justify| Ausrichtung als Blocksatz|

例子： 

![](image/Chapter2_css_文字属性_003_文字对齐_例子.png)
[![4 3 textalign.jpg](https://vfhwebp.eduloop.de/mediawiki/images/vfhwebp.eduloop.de/a/a3/4_3_textalign.jpg)](https://vfhwebp.eduloop.de/mediawiki/images/vfhwebp.eduloop.de/a/a3/4_3_textalign.jpg)

# 3 vertical-align

`vertical-align` 指定行内/行内块元素的元素的垂直对齐方式。 (property sets vertical alignment of an inline, inline-block or table-cell box.)
这个属性 对 块元素无效, 比如对 div 元素就无效 

- 使用场景：经常用于设置**图片**或者**表单（行内块元素）**和**文字垂直对齐**。
- 官方解释：用于设置一个元素的垂直对齐方式，<mark>但是它只针对于**行内元素**或者**行内块元素**或者 表格单元 有效</mark>
    - Das property vertical-align ist nur auf Tabellenzellen und inline-Elemente anwendbar.
    - 特别是行内块元素， 通常用来控制图片/表单与文字的对齐。

## 3.1 属性值

vertical-align: baseline | top | middle | bottom

| 值        | 描述                        |
| -------- | ------------------------- |
| baseline | 默认，元素放置在父元素的基线上           |
| top      | 把元素的顶端与行中最高元素的顶端对齐（顶线对齐）  |
| middle   | 把此元素放置在父元素的中部（中线对齐）       |
| bottom   | 把元素的顶端与行中最低的元素的顶端对齐（底线对齐） |

![在这里插入图片描述](https://img-blog.csdnimg.cn/2f7832a64527405181bd3edbcd3a736a.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

![图片](https://mmbiz.qpic.cn/mmbiz_png/y7EkeCWAzmqtcdL7HZYccBic0jicaWzR8bX32nStNY16aY9odqroA3Mpia6nia2fuh9DYmYCszG7V1to2VsNwibY8Sg/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

## 3.2 位置 

Zusätzlich gibt es Werte, die vor allem bei Textpassagen Sinn ergeben, oder wenn Sie Elemente (z.B. Bilder) innerhalb von Texten platzieren möchten:

baseline – an der Basislinie ausgerichtet (gibt es keine, wird es nach unten bündig ausgerichtet)
sub – tiefergestellte Ausrichtung (ohne Veränderung der Schriftgröße)
super – höhergestellte Ausrichtung (ohne Veränderung der Schriftgröße)
text-top – Ausrichtung am oberen Textrand
text-bottom – Ausrichtung am unteren Textrand


## 3.3 图片、表单和文字居中对齐 vertical-align: middle


vertical-align：middle的作用机制就是对齐基线，这里之所以要设置line-height（最关键的）就是要让首行匿名元素（空白节点）处于父容器基线左右的位置，然后内联元素设置了vertical-align:middle才会对齐这个节点，否则是无效的！！！！


图片、表单都属于行内块元素，默认的 vertical-align 是基线对齐。
此时可以给图片、表单这些行内块元素的 vertical-align 属性设置为 middle 就可以让文字和图片垂直居中对齐了。

```css
img {
  vertical-align: middle;
}
li {
  disaplay: inline-block;
  vertical-align: middle;
}
```

### 3.3.1 重点

vertical-align：middle的作用机制就是对齐基线，这里之所以<mark>要设置line-height（最关键的）就是要让首行匿名元素（空白节点）处于父容器基线左右的位置</mark>，然后内联元素设置了vertical-align:middle才会对齐这个节点，否则是无效的！！！！

![在这里插入图片描述](https://img-blog.csdnimg.cn/159dbd0d98f941f5b17eb713341d3c64.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

您可以狠狠地点击这里：[CSS3 width:fill-available下的垂直居中demo](https://www.zhangxinxu.com/study/201605/width-fill-available.html)

![块状元素尺寸表现内联元素垂直居中行为](https://image.zhangxinxu.com/image/blog/201605/2016-05-20_004332.png)

完整关键CSS代码如下：

```css
.box {
    height: 200px; 
    /* 行高控制垂直居中 */
    line-height: 200px;
}
.fill-available {
    /* 元素内联，响应行高和vertical-align控制 */
    display: inline-block;
    vertical-align: middle;

    /* 宽度如块状元素般表现 */
    width: -webkit-fill-available;
    width: -moz-fill-available;
    width: -moz-available;    /* FireFox目前这个生效 */
    width: fill-available;
}
```


## 3.4 解决图片底部默认空白缝隙问题

bug ：图片底侧会有一个空白缝隙，原因是行内块元素会和文字的基线对齐。给图片加边框就可以看见
![在这里插入图片描述](https://img-blog.csdnimg.cn/6ab28389075f4478a70a11cae3e5a58e.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)
![图片](https://mmbiz.qpic.cn/mmbiz_png/y7EkeCWAzmqtcdL7HZYccBic0jicaWzR8boGWdjhQUvkicibGiaRYd0KDL2Y1kmqWLl75piaeMlRTMVh4go056Pj1OLA/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)


主要解决方法有两种：

1. 给图片添加 `vertical—align: middle top bottom;` 等。（提倡使用的）
    1. ![图片](https://mmbiz.qpic.cn/mmbiz_png/y7EkeCWAzmqtcdL7HZYccBic0jicaWzR8bNO8sogwyKtqHT6Bg0iaDeAkWqlbbSWqKJIGqtt8As1oFz17wBkQYb4g/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)
2. 把图片转换为块级元素 `display: block；`, 给img 添加 display：block; 转换为块级元素就不会存在问题了。


