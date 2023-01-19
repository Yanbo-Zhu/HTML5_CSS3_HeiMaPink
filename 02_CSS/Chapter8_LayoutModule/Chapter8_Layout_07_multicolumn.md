# 1 Multiple Columns (column-count)

Die Eigenschaft column-count setzt die Anzahl der Spalten auf die als Parameter eingesetzte positive Ganzzahl.

Ein Beispiel:

```css
<div style="    
  -webkit-column-count: 2; /* Chrome, Safari, Opera */
  -moz-column-count: 2; /* Firefox */
  column-count: 2; width: 300px;">
    Eine Besonderheit in CSS3 ist das Verwenden mehrerer Spalten, 
    wie bei einer Zeitung. Hierdurch können z. B. Blogs 
    oder Web Shops profitieren.
</div>
```
Der aus alten HTML-Versionen bekannte Workaround mittels der Verwendung von Tabellen oder mehreren Div-Elementen entfällt dadurch. Noch ist das Feature teilweise proprietär, d.h. auch hier muss ggfs. -webkit- bzw. -moz- vorangestellt werden.
