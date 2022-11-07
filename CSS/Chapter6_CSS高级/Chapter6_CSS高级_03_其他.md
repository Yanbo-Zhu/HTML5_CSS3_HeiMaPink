# 1 CSS 三角图形

## 1.1 例子1
```css
.box1 {
  width: 0;
  height: 0;
  border: 10px solid transparent;
  border-left-color: black;
  /* 照顾兼容性 */
  line-height: 0;
  font-size: 0;
}
```

## 1.2 例子2

![图片](https://mmbiz.qpic.cn/mmbiz_png/y7EkeCWAzmqtcdL7HZYccBic0jicaWzR8bMZvtNQGxxYDG6SvNX35cbQ6TaDfdMYoBxHVLwNHujC7dg4WzBD5TVQ/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

1.  我们用css 边框可以模拟三角效果
2.  宽度高度为0
3.  我们4个边框都要写， 只保留需要的边框颜色，其余的不能省略，都改为 transparent 透明就好了
4.  为了照顾兼容性 低版本的浏览器，加上 font-size: 0;  line-height: 0;
```css
div {  
  
    width: 0;   
  
    height: 0;  
    line-height:0；  
    font-size: 0;  
   border-top: 10px solid red;  
  
   border-right: 10px solid green;  
  
   border-bottom: 10px solid blue;  
  
   border-left: 10px solid #000;   
  
     }
```


# 2 CSS 初始化
不同浏览器对有些标签的默认值是不同的，为了消除不同浏览器对 HTML 文本呈现的差异，照顾浏览器的兼容，我们需要对 CSS 初始化
简单理解： CSS 初始化是指重设浏览器的样式。（也称为 CSS reset ）每个网页都必须首先进行 CSS 初始化。 这里我们以京东 css 初始化代码为例。
Unicode 编码字体： 把中文字体的名称用相应的 Unicode 编码来代替，这样就可以有效的避免浏览器解释 CSS 代码时候出现乱码的问题。