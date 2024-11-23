# 1 基本语法规范

HTML 标签是由尖括号包围的关键词，例如`<html>`。

![](image/Pasted%20image%2020241029163550.png)


Ein HTML-Tag ist eine Auszeichnung, z.B. `<h1>`.
Ein HTML-Element besteht aus dem Start-Tag, dem Inhalt und dem End-Tag `<h1>hallo</h1>`
Ein HTML-Attribut ist eine Ergänzung des Tags um eine weitergehende Anweisung vorzunehmen z.B. `<h1 class=“MeineBezeichnung“>`  Zu jedem Attribut gehört eine Bezeichnung und ein oder mehrere Werte. Die Reihenfolge der Attribute innerhalb eines Tags ist unwichtig für die Ausführung. Alle Attribute gehören in das öffnende Tag.




## 1.1 闭合便签和非闭合便签

- 闭合标签， 双标签， container tags 
    - 前半部部分称为 opening tags, 后半部分称为 closing tags
    - 常见的为双标签： HTML 标签通常是成对出现的，例如`<html>和<html/>`，称为双标签。第一个是开始标签，第二个是结束标签。比如 `<标签名> 内容 </标签名>`  比如`<body>我是文字</body>`
- 单标签，闭合标签， non-container tags , Standalone-Tags
    - 不常见的为单标签：有些特殊标签必须是单个标签（极少情况），例如`<br/>或<br>` (Zeilenumbruch)，我们称之为单标签。

## 1.2 标签关系

标签关系可以分为两类：包含关系和并列关系
嵌套关系父子级包含关系
并列关系兄弟级并列关系
如果两个标签之间的关系是嵌套关系，子元素最好缩进一个tab键的身位（一个tab是4个空格）。如果是并列关系，最好上下对齐。


# 2 Attirbute

![](image/Pasted%20image%2020241123114912.png)

Attribute bestimmen die Eigenschaften eines HTML-Elements
Case insensitive 
Sind ausschliesslich im Start Tag enthalten
Bestehen aus Attributnamen und Attributwert (letzterer in ' oder ")
Verfügbare Attribute hängen vom HTML-Element ab
Universalattribute können in allen HTML-Elementen gesetzt werden
Einige HTML-Elemente verfügen über Pfl ichtattribute deren Werte gesetzt werden müssen
Default-Werte für den Fall, dass Pfl ichtattribute nicht gesetzt werden 
Freie Attributwerte oder vordefi nierte Attributwerte





## 2.1 Universalattribute (class, id, lang, style, title)
Universalattribute sind solche Attribute, die in allen HTML-Tags erlaubt sind. Sie beschreiben z.B. eine individuelle Bezeichnung eines HTML-Elements. Die universalen Attribute werden wie andere Attribute im HTML-Tag definiert.

- class – dient der Gruppierung von HTML-Elementen. Es wird über CSS oder JavaScript angesprochen.
- id – eine eindeutige Bezeichnung für Elemente (nur einmal im Dokument vorhanden)
- lang – gibt die im HTML-Element verwendete hauptsächliche Landessprache an, es dürfen mehrere lang-Attribute verwendet werden.
- style – erlaubt individuelle CSS-Formatierungen (mehr dazu im Kapitel „CSS – Cascading Stylesheets“), sollte aber vermieden werden.
- title – stellt den eingegebenen Text als Tooltip dar

## 2.2 id的命名规则
规定元素的唯一 id。

命名规则：
- 必须以字母 A-Z 或 a-z 开头
- 其后的字符：字母(A-Za-z)、数字(0-9)、连字符("-")、下划线("_")、冒号(":") 以及点号(".")
- 值对大小写敏感
- 不能含有空格

# 3 Zeichencodierung 



![](image/Pasted%20image%2020241123115112.png)

- Zeichencodierung ordnet Zeichen eines Zeichensatzes einer Codierung zu, z.B. einer 8-Bit-Ganzzahl
- ASCII (American Standard Code for Information Interchange): Alte amerikanische Zeichencodierung basierend auf 7 Bits
- UTF-8 (8-Bit Universal Coded Character Set (UCS) Tranfsformation Format): Deckungsgleich mit ASCII in den ersten 128 Zeichen
- 98,8% der Top-1000-Webseiten verwenden UTF-8
- Bei Verwendung von UTF-8 können nebenstehende Zeichen in Plain Text angegeben werden
- Bei Verwendung von anderen Zeichencodierungen (z.B. ISO 8859-1) muss der HTML Entity Name verwendet werden

HTML-Syntax benötigt einige Zeichen als Steuerzeichen (<, >, ', ", &)
Sollen Steuerzeichen als Inhalt dargestellt werden, müssen sie als HTML Entity Name oder Unicode Entity Number geschrieben werden







# 4 Barrierefreiheit

Die Stand 2021/2022 überarbeiteten Web Accessibility Guidelines (WCAG) geben Empfehlungen zur korrekten Realisierung barrierefreier Webseiten. Das umfasst:
https://www.w3.org/TR/wcag-3.0/

- Nutzen einer klaren Sprache
- Nutzen geeigneter Textgrößen und Kontraste (betrifft eher CSS)
- Ca. 10% der männlichen Bevölkerung sind Rot-Grün-blind oder Rot-Grün-schwach
- Beachten alternativer Darstellungsformen und z. B. auch Vorlesehilfen
- <ins>Hinterlegen von Tastaturkürzeln auf Links und Buttons mit dem Attribut <em> accesskey </em> (leider uneinheitlich zwischen Browsern, da nicht alle Access Keys verfügbar sind und es nicht standardisiert wurde) </ins>
    - https://www.runoob.com/tags/att-global-accesskey.html
- <ins>Beachten der Sprungreihenfolge mit der Tabulatortaste mit dem Attribut <em> tabindex </em> </ins>
    - tabindex 全局属性 指示其元素是否可以聚焦，以及它是否/在何处参与顺序键盘导航（通常使用Tab键，因此得名）。 https://developer.mozilla.org/zh-CN/docs/Web/HTML/Global_attributes/tabindex
- <ins>Hinterlegen von alternativen Texten und Tooltips auf Grafiken mit den Attributen  <em> alt </em>und  <em> title </em> </ins>
- Nutzen von validiertem HTML und CSS (vgl. validator.w3.org)
- Verzicht auf komplexe Handlungsfolgen, je nach Zielgruppe, z. B. verschachtelte (nested) Menüs oder Drag&Drop, da motorische (运动机能) Einschränkungen vorliegen könnten

# 5 XHTML

XHTML 指「可扩展超文本标签语言」（EXtensible HyperText Markup Language）。
XHTML 的目标是取代 HTML。
XHTML 与 HTML 4.01 几乎是相同的。
XHTML 是更严格更纯净的 HTML 版本。
XHTML 是作为一种 XML 应用被重新定义的 HTML,是严格版本的HTML。例如它要求标签必须小写，标签必须被正确关闭，标签顺序必须正确排列，对于属性都必须使用双引号等。
XHTML 是一个 W3C 标准。

# 6 写HTML代码时应注意什么？

- 尽可能少的使用无语义的标签div和span；

- 在语义不明显时，既可以使用div或者p时，尽量用p, 因为p在默认情况下有上下间距，对兼容特殊终端有利；

- 不要使用纯样式标签，如：b、font、u等，改用css设置。

- 需要强调的文本，可以包含在strong或者em标签中（浏览器预设样式，能用CSS指定就不用他们），strong默认样式是加粗（不要用b），em是斜体（不用i）；

- 使用表格时，标题要用caption，表头用thead，主体部分用tbody包围，尾部用tfoot包围。表头和一般单元格要区分开，表头用th，单元格用td；

- 表单域要用fieldset标签包起来，并用legend标签说明表单的用途；

- 每个input标签对应的说明文本都需要使用label标签，并且通过为input设置id属性，在lable标签中设置for来让说明文本和相对应的input关联起来。 了
