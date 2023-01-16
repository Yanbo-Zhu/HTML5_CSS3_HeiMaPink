# 1 Universalattribute (class, id, lang, style, title)
Universalattribute sind solche Attribute, die in allen HTML-Tags erlaubt sind. Sie beschreiben z.B. eine individuelle Bezeichnung eines HTML-Elements. Die universalen Attribute werden wie andere Attribute im HTML-Tag definiert.

- class – dient der Gruppierung von HTML-Elementen. Es wird über CSS oder JavaScript angesprochen.
- id – eine eindeutige Bezeichnung für Elemente (nur einmal im Dokument vorhanden)
- lang – gibt die im HTML-Element verwendete hauptsächliche Landessprache an, es dürfen mehrere lang-Attribute verwendet werden.
- style – erlaubt individuelle CSS-Formatierungen (mehr dazu im Kapitel „CSS – Cascading Stylesheets“), sollte aber vermieden werden.
- title – stellt den eingegebenen Text als Tooltip dar

## 1.1 id的命名规则
规定元素的唯一 id。

命名规则：
- 必须以字母 A-Z 或 a-z 开头
- 其后的字符：字母(A-Za-z)、数字(0-9)、连字符("-")、下划线("_")、冒号(":") 以及点号(".")
- 值对大小写敏感
- 不能含有空格