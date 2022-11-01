
# 1 selectors 在Stylesheet 文件中的书写顺序
- Selektoren mit niedriger Spezifität kommen an den Anfang des Stylesheets und solche mit höchster Spezifität werden am Ende notiert 
    - niedriger Spezifität 写在最上面
- Allgemeine Regeln und vererbbare Proerties werden zu Beginn des Stylesheets vereinbart , so daß sie teils an späterer Stelle durch spezifischere Regeln überschrieben werden können. 
    - Allgemeine Regeln und vererbbare Proerties 写在最前面
    - 越往下写的是 spezifischere Regeln， 这样下面的能覆盖掉最上面的呢

# 2 同一个selector的不同CSS 属性书写顺序（重点）

2. 布局定位属性/ 位置属性 (最开始写, 最上面的位置写)：
    1. display / position / float / clear / visibility / overflow
    2. （建议 display 第一个写，毕竟关系到模式）    
3.  自身属性/大小属性：
    1. width / height / margin / padding / 
4. 背景(background, border等)
5.  文本属性：
    1. color / font / text-decoration / text-align / vertical-align / white- space / break-word
6.  其他属性（CSS3）
    1. content / cursor / border-radius / box-shadow / text-shadow / background:linear-gradient …
    2. animation, transition等css3属性

```css
.div2{
       z-index: 2;
       position: absolute;
       right: 20px;
       bottom:40px ;
       width: 350px;
       height: 260px;
       margin-left: 20px;
       padding: 20px 30px;
       background: #e2f4fc;
       border: 20px solid #E6CAFF;
       line-height: 20px;
       text-align: center;
       font-weight: bold;
       font-size: 16px;
       color: #464646;
       /* css3属性 */
       box-sizing: border-box;
}
```

```css
.jdc {  
    display: block;  
    position: relative;  
    float: left;  
    width: 100px;  
    height: 100px;  
    margin: 0 10px;  
    padding: 20px 0;  
    font-family: Arial, 'Helvetica Neue', Helvetica, sans-serif;  
    color: #333;  
    background: rgba(0,0,0,.5);  
    -webkit-border-radius: 10px;  
    -moz-border-radius: 10px;  
    -o-border-radius: 10px;  
    -ms-border-radius: 10px;  
    border-radius: 10px;  
}
```

