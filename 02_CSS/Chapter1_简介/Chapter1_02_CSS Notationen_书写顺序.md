
# 1 Zweck von Notationen

Beim Schreiben einer CSS-Datei sammeln sich oft mehrere hundert Zeilen, die ungeordnet aufgeschrieben sind. Eine Regel wird erdacht, sequentiell unter die bereits bestehenden geschrieben und auf Grund der Spezifitätsregeln greift sie vielleicht nicht. Das Ergebnis ist oft eine ungeordnete, schlecht wartbare Datei.

Einheitliche Notationen dienen folgenden Zwecken:
1.  Wartbarkeit der Dateien
2.  Ausschalten einiger Spezifitätsregeln
3.  Einhaltung einheitlicher Namenskonventionen
4.  Modularisierung und Wiederverwendung einzelner Bestandteile.


# 2 同一个selector的中不同的 属性书写顺序

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

```
.div{
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


# 3 selectors 在 Stylesheet 文件中的书写顺序
- Selektoren mit niedriger Spezifität kommen an den Anfang des Stylesheets und solche mit höchster Spezifität werden am Ende notiert 
    - niedriger Spezifität 写在最上面
- Allgemeine Regeln und vererbbare Proerties werden zu Beginn des Stylesheets vereinbart , so daß sie teils an späterer Stelle durch spezifischere Regeln überschrieben werden können. 
    - Allgemeine Regeln und vererbbare Proerties 写在最前面
    - 越往下写的是 spezifischere Regeln， 这样下面的能覆盖掉最上面的呢

## 3.1 BEM

Mehr zu Informationen zu [BEM](http://getbem.com/introduction/).

BEM steht für .block_ _ element - - modifier

BEM basiert auf einem reinen Klassenmodell.

Die Klassen werden den Elementen im HTML-Dokument zugefügt. Alle Selektoren haben dann im Stylesheet dieselbe Spezifität und das Stylesheet wird einfach sequentiell abgearbeitet. Auf der anderen Seite wird das HTML-Dokument um zusätzliche Klassen aufgebläht.

BEM ist komponentenbasiert und die einzelnen Komponenten sind projektübergreifend wiederverwendbar.

### 3.1.1 Anwendung

**.block** ist die oberste Abstraktionsebene und steht für eine eigenständige Komponente, z.B. .header oder .button

**_ _ element** ist immer Kind eines .block, z.B. .header_ _ title oder .header_ _ logo

**- - modifier** sind style-Ausprägungen eines _ _element z.B. .header _ _ title - - position oder .header_ _ title - - color   **Regeln**:

1.  alle Selektoren bestehen aus nur einer Klasse
2.  andere Selektoren, wie Typ oder id werden nicht verwendet
3.  Verschachtelungen und Nachfahren sind nicht erlaubt
4.  !important wird nicht verwendet

⇒ alle Selektoren haben dieselbe Spezifität und die Regeln können in jedem Projekt verwendet werden.



## 3.2 OOCSS

Mehr Informationen zu [OOCSS in der Praxis](http://oocss.org/) und [OOCSS](https://benmarshall.me/oocss-object-oriented-css/)

OOCSS steht für Object Oriented CSS und ist ein generelles Konzept, das gut mit BEM oder SMACCS kombiniert werden kann. OOCCS ist klassenbasiert, aber nicht auschließlich, wie es der Fall in BEM ist.

Ein Objekt ist jeder wiederverwendbare CSS-Code. **Prinzipien**:
1.  Separation of structure from skin

Zu structure (layout) gehören
1.  height, width
2.  margin, padding
3.  overflow

Zu skin (design) gehören
1.  colors
2.  fonts
3.  shadows
4.  gradients

Separation of Containers and Contents
- z.B. werden alle folgenden Selektoren zu h2
- header>h2
- footer>h2
- main>h2

Damit sind sie unabhänging vom umgebenden Container.

Der Content wird als Klasse angelegt. Sich wiederholende Designs werden als Klasse zusammengefasst, z.B. .center oder .globalColors

**Regeln**:
1.  id-Selektoren werden vermieden
2.  Nachfahren-Selektoren werden vermieden
3.  Klassen werden nicht an Elemente gebunden
4.  !important wird nur in Ausnahmen verwendet
5.  Selektoren minimieren
6.  Multiple Klassen für Elemente sind erlaubt und erwünscht (Selektoren minimieren)
7.  Reset verwenden

**Möglichkeiten**: Eigene Komponenten entwickeln und eine Bibliothek anlegen, z.B. mit .header, .footer, .button, .list




## 3.3 SMACSS

Informationen zu [SMACSS](http://smacss.com/)

SMACSS steht für Scalable and Modular Architekture for CSS und basiert auf Kategorizierung.

**Prinzipien**:
1.  base
2.  layout
3.  module
4.  state
5.  theme

**base** Hier werden die grundlegenden Regeln für die Struktur vereinbart und ein reset.
1.  Element-Selektoren, Pseudo-Elemente und –Klassen
2.  Attribut-Selektoren
3.  Keine id- und class-Selektoren
4.  Keine Nachfahren-Selektoren
Beispiele: body, main, input, button; a:hover, a

**layout** Hier werden die Regeln für die Struktur vereinbart.
1.  class (reusable elements)
2.  id (single-use-elements)
layout ist i.d.R. mit einem präfix ausgezeichnet, z.B. .l-article oder .l-footer

**module** Dies sind einzelne Komponenten mit bestimmter Funktionalität, die jeweils Bestandteil von base oder layout sind. Alle modules sind wiederverwendbar
1.  class

**state** Hier werden spezifische Designs für module, layout oder base vereinbart. Diese Regeln werden am Ende des stylesheets positioniniert. Auch hier wird i.d.R. ein Präfix verwendet, z.B. is-
1.  class
2.  !important (am Ende des stylesheets, um module zu überschreiben)

**theme** Hier werden Farben und Media-Einbindungen deklariert
1.  class



