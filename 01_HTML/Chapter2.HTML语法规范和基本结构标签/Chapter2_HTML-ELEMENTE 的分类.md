

# 1 BLOCK-ELEMENTE, INLINE-ELEMENTE, leer-element

## 1.1 Block-Elemente

Block-Elemente nehmen die volle Breite des Elternelements ein (sofern die Breite nicht
mittels CSS verändert wird) und die erforderliche Höhe zur Darstellung des Inhalts
Mit jedem neuen Block-Element wird ein neuer Absatz erzeugt
Nachfolgende Elemente rutschen unter das Block-Element
Gängige Bock-Elemente: `<header>, <footer>, <article>, <section>, <aside>, <nav>, <h1> bis <h6>, <p>, <ul>, <ol>, <li>, <div>`

![](image/Pasted%20image%2020241123114545.png)


## 1.2 INLINE-ELEMENTE

Inline-Elemente nehmen sowohl in der Breite als auch in der Höhe nur soviel Platz ein wie erforderlich
Mehrere Inline-Elemente werden wie Wörter hintereinander aufgereiht
Ist die verfügbare Breite durch mehrere Inline-Elemente erreicht, brechen sie in die nächste Zeile um
Gängige Inline-Elemente: `<em>, <strong>, <a>, <img> und <span>`


![](image/Pasted%20image%2020241123114607.png)



## 1.3 Leere Element 

Void Elements sind HTML-Elemente ohne End Tag
Void Elements dürfen keinen End Tag besitzen

![](image/Pasted%20image%2020241123114637.png)


# 2 Seitenstrukturierung

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

```html

<Dokumenttyp> 	  <!DOCTYPE html>
<Wurzelelement>	  <html>
<Header>	    <head>
(Kopfdaten)	     (…)
</Header>	    </head>
<Body>		    <body>
(…)		     (…)
</Body>		    </body>
</Wurzelelement>  </html>
```

| 标签名             | 定义     | 说明                            |
| --------------- | ------ | ----------------------------- |
| `<html></html>`   | HTML标签 | 页面中的最大的标签，我们称为根标签             |
|x|Dokumenttyp-Deklaration|macht Angaben zur verwendeten HTML-Version|
| `<head><head> `   | 文档的头部  | 注意在head标签中我们必须要设置的标签是title  . Das Wurzelelement ist in einer HTML-Datei immer das `<html>`-Element. enthält die Kopfdaten wie z.B. Angaben zum Titel oder Angaben für Suchmaschinen |
| `<title></title>` | 文档的标题  |  在 head标签里面  让页面拥有一个属于自己的网页标题              |
| `<body></body> `  | 文档的主体  | 元素包含文档的所有内容，页面内容基本都是放到body里面的. enthält den anzuzeigenden Inhalt (Text, Grafiken etc.) |



![](image/Pasted%20image%2020241029182949.png)



# 3 Textstrukurierung

![](image/Pasted%20image%2020241029183059.png)


# 4 Textzeichnung




![](image/Pasted%20image%2020241029183114.png)



![](image/Pasted%20image%2020241029183121.png)

# 5 Formulardarstellung

![](image/Pasted%20image%2020241029183231.png)



![](image/Pasted%20image%2020241029183258.png)


# 6 EINBETTUNG VON MEDIEN UND INHALTEN

![](image/Pasted%20image%2020241030081407.png)


# 7 DARSTELLUNG VON TABELLEN


![](image/Pasted%20image%2020241030081429.png)






