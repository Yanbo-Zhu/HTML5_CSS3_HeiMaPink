
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



| Element                                                                | Funktion                                                                                                                                                                                                                                    |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **`<body>`**                                                           | Umschließt den sichtbaren Inhalt einer Webseite                                                                                                                                                                                             |
| `**<section**>`                                                        | Definiert einen allgemeinen Bereich einer Seite, in dem zusammengehöriger Inhalt gebündelt wird                                                                                                                                             |
| **`<nav>`**                                                            | Definiert Navigationsbereiche                                                                                                                                                                                                               |
| **`<article>`**                                                        | Definiert einen Artikel mit zusammengehörigen Informationen, der grundsätzlich auch allein stehen könnte und von dem umgebenden Kontext unabhängig ist                                                                                      |
| **`<aside>`**                                                          | Definiert Bereiche, die verwandte Themen zum Hauptinhalt zeigen, grundsätzlich aber auch ohne Bezug auf den Inhalt eine eigenständige Information liefern                                                                                   |
| **`<h1>`**, **`<h2>`**, **`<h3>`**, **`<h4>`**, **`<h5>`**, **`<h6>`** | Überschriften (auf verschiedenen Ebenen) für einen Seitenbereich                                                                                                                                                                            |
| `**<main>**`                                                           | Repräsentiert den Hauptinhalt eines `**<body>**`-Elements und darf nicht in `**<section>**` oder `**<article>**` enthalten sein                                                                                                             |
| `**<header>**`                                                         | Definiert einen Bereich als Kopf eines Seitenbereichs. Kann als eigentlicher Kopf einer Website eingesetzt werden, aber auch als Kopf beispielsweise einer `**<section>**`                                                                  |
| **`<footer>`**                                                         | Definiert eine Fußzeile zu einem Bereich und umfasst Angaben zum Autor, Copyright, weiterführende Links usw. Kann als eigentlicher Seitenfuß einer Website eingesetzt werden, aber auch als Element in `**<section>**` oder `**<article>**` |
| **`<address>`**                                                        | Dient zur Auszeichnung eines Abschnitts mit Kontaktmöglichkeiten, z.B. Link zur Kontaktseite oder Email-Link. Telefonnummern und postalische Adressen sind laut Standard im **`<address`>**-Element nicht erlaubt                           |


# 3 Textstrukurierung

![](image/Pasted%20image%2020241029183059.png)




| Element            | Funktion                                                                                                                                                                                                                                                                                        |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `**<p>**`          | Definiert einen Textblock (Paragraf)                                                                                                                                                                                                                                                            |
| `**<hr>**`         | Definiert eine Trennlinie, die Inhalte in logische Abschnitte unterteilt                                                                                                                                                                                                                        |
| `**<pre>**`        | Stellt Textblöcke mit Zeilenumbrüchen, Einrückungen und Leerzeichen dar, wie sie im Quelltext erfasst sind. Ist ausschließlich eine visuelle Darstellung, die beispielsweise in Sprachausgaben verloren geht                                                                                    |
| `**<blockquote>**` | Definiert einen Abschnitt als Zitat. Wird wie das `**<q>**`-Tag nicht mit Anführungszeichen, aber eingerückt dargestellt                                                                                                                                                                        |
| `**<ol>**`         | Definiert eine geordnete Liste, die automatisch nummeriert wird, entweder mit Zahlen oder Buchstaben (über CSS steuerbar). Merkmal ist, dass die Reihenfolge der einzelnen Einträge nicht frei vertauscht werden kann, ohne dass die Sinnhaftigkeit verloren geht (z.B. bei einer Bauanleitung) |
| `**<ul>**`         | Definiert eine ungeordnete Liste. Merkmal ist, dass die Reihenfolge der Listeneinträge frei vertauscht werden kann, die Liste aber trotzdem sinnvollen Inhalt liefert (z.B. die Zutatenliste eines Rezepts)                                                                                     |
| `**<li>**`         | Definiert einen Listeneintrag sowohl in einer `**<ol>**` als auch in einer `**<ul>**`                                                                                                                                                                                                           |
| `**<figure>**`     | Definiert eine in sich abgeschlossene Einheit, beispielsweise ein Bild, Video oder Audio mit der dazugehörigen Beschriftung oder ein Gedicht mit den dazugehörigen Angaben zu Titel, Autor und Erscheinungsdatum.                                                                               |
| `**<figcaption>**` | Definiert die Beschriftung einer `**<figure>**`                                                                                                                                                                                                                                                 |
| `**<div>**`        | Blockelement ohne jegliche strukturelle Bedeutung. Sollte nur eingesetzt werden, wenn keine anderen Strukturelemente für die Auszeichnung eines Abschnitts sinnvoll erscheinen                                                                                                                  |
|                    |                                                                                                                                                                                                                                                                                                 |







# 4 Textzeichnung


| Element        | Funktion                                                                                                                                                                                                                                              |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `**<a>**`      | Definiert einen Hyperlink zu einer anderen Seite                                                                                                                                                                                                      |
| `**<em>**`     | Betont ein Wort, hebt es durch Akzentuierung hervor. Die visuelle Darstellung ist kursiv                                                                                                                                                              |
| `**<strong>**` | Verleiht einem Wort Wichtigkeit und hebt es dadurch vom restlichen Text ab. Die visuelle Darstellung ist fett                                                                                                                                         |
| `**<cite>**`   | Definiert den Titel einer Quelle, z.B. `**<cite>**`Die Bibel`**</cite>**`. Ist abzugrenzen von eigentlichen Zitaten, die über `**<blockquote>**` oder einen `**<q>**`-Tag ausgezeichnet werden sollen                                                 |
| `**<q>**`      | Definiert ein Zitat. Wird visuell durch Anführungszeichen dargestellt                                                                                                                                                                                 |
| `**<abbr>**`   | Definiert eine Abkürzung oder ein Akronym. Im `**title**`-Attribut sollte die Bedeutung des Akronyms beziehungsweise die Abkürzung ausgeschrieben werden                                                                                              |
| `**<time>**`   | Zeichnet eine Zeitangabe aus                                                                                                                                                                                                                          |
| `**<code>**`   | Zeichnet einen Text als Quellcode oder Computerbefehl aus. Visuell wird ein `**<code>**`-Abschnitt über einen Monospace-Schrifttyp dargestellt. Um Zeilenumbrüche von Befehlen zu erhalten, ist zusätzlich der Einsatz des `**<pre>**`-Tags notwendig |
| `**<kbd>**`    | Zeichnet einen Text aus, der auf eine Benutzereingabe über die Tastatur hinweist. Beispielsweise: Zum Neuladen der Seite drücken Sie die Taste `**<kbd>**`F5`**</kbd>**`                                                                              |
| `**<sub>**`    | Stellt einen Text tief. Sollte nur eingesetzt werden, wenn es den Konventionen einer Sprache entspricht, zum Beispiel bei der Auszeichnung chemischer Zeichen: H`**<sub>**`2`**</sub>**` für H2O                                                      |
| `**<sup>**`    | Stellt einen Text hoch. Sollte ebenfalls nur eingesetzt werden, wenn es den Konventionen einer Sprache entspricht, beispielsweise bei einer Quadratmeterangabe: 45m`**<sup>**`2`**</sup>**` für 45m2                                                  |

| Element      | Funktion                                                                                                                                                                                                                                                                                                                                                          |
| ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `**<mark>**` | Definiert einen markierten oder hervorgehobenen Text, ist jedoch mit keiner Betonung wie durch `**<em>**` oder `**<strong>**` verbunden. Sinnvoller Einsatz kann das Hervorheben eines Suchbegriffs in einer Suchergebnisliste sein. Die Standarddarstellung ist ein gelb hinterlegter Text                                                                       |
| `**<span>**` | Definiert einen Bereich als Inline-Element ohne jegliche Bedeutung. Eine semantische Auszeichnung durch ein anderes Element ist immer zu bevorzugen. Sinnvoller Einsatz ist die Sprachauszeichnung eines sonst geläufigen Begriffs wie beispielsweise `**<span lang="en">**`Meeting`**</span>**`, damit Screenreader diesen mit der richtigen Aussprache vorlesen |
| `**<br>**`   | Definiert einen Zeilenumbruch innerhalb eines `**<p>**`- oder `**<address>**`-Elements. Sollte auf keinen Fall eingesetzt werden, um Abstände zwischen HTML-Elementen zu erzeugen. Werden mehrere `**<br>**` nacheinander in einem `**<p>**`-Element verwendet, ist zu prüfen, ob der relevante Text in zwei `**<p>**`-Blöcke aufgeteilt werden kann              |
| `**<wbr>**`  | Definiert optionale Zeilenumbrüche, damit lange Wörter an der richtigen Stelle getrennt werden. Beispielsweise Do`**<wbr**`>nau`**<wbr>**`dampf`**<wbr>**`schiff`**<wbr>**`fahrts`**<wbr>**`ge`**<wbr>**`sell`**<wbr>**`schafts`**<wbr>**`ka`**<wbr>**`pi`**<wbr>**`täns`**<wbr>**`müt`**<wbr>**`ze                                                               |




![](image/Pasted%20image%2020241029183114.png)



![](image/Pasted%20image%2020241029183121.png)

# 5 Formulardarstellung


|Element|Funktion|
|---|---|
|`**<form>**`|Definiert ein Formular und muss alle Formularelemente umschließen. Im **`<form>`**-Tag wird die URL angegeben, an die ein Formular gesendet wird, sowie der Übertragungsmodus (get, post) festgelegt. Ebenfalls wird über den enctype der Übertragungsmodus festgelegt, der im Falle eines Dateiuploads den Wert multipart/form-data haben muss|
|`**<fieldset>**`|Gliedert ein Formular und fasst inhaltlich zusammengehörige Formularfelder zusammen|
|`**<legend>**`|Definiert eine übergeordnete Beschriftung von zusammengehörigen Formularfeldern, die über `**<fieldset>**` zu einer Einheit zusammengefasst werden|
|`**<label>**`|Definiert eine eindeutige Beschriftung für jedes einzelne Eingabefeld. Jedem `**<label>**` kann nur ein Formularelement (`**<input>**`, `**<select>**`, `**<textarea>**`) zugeordnet werden. Die Verknüpfung wird über das for-Attribut des `**<label>**` und das `**id**`-Attribut des Eingabefeldes hergestellt|
|`**<input>**`|HTML-Tag für verschiedene Typen von Eingabefeldern. Einzeiliges Eingabefeld zur Eingabe von Daten durch den Benutzer, Radio- und Checkboxen zur Auswahl, Upload-Button-Feld, Absende- und Reset-Button. Mit HTML5 hat sich der Umfang der `**<input>**`-Typen und damit die Datenarten, die damit erfasst werden können, wesentlich erhöht.|
|`**<datalist>**`|Definiert Werte die als Vorauswahl für ein einzeiliges Eingabefeld ausgewählt werden können|
|`**<select>**`|Definiert eine Auswahlliste, auch Auswahlmenü oder Dropdown genannt, mit einer Liste fest definierter Werte|
|`**<option>**`|Definiert eine einzelne Auswahlmöglichkeit innerhalb einer `**<select>**`-Box|
|`**<optgroup>**`|Gruppiert mehrere `**<option>**`-Tags innerhalb einer `**<select>**`-Box zu einer Einheit von Auswahlmöglichkeiten|

![](image/Pasted%20image%2020241029183231.png)





|Element|Funktion|
|---|---|
|`**<textarea>**`|Mehrzeiliges Eingabefeld|
|`**<keygen>**`|Generiert ein Schlüssel-Paar für eine sichere Datenübertragung|
|`**<output>**`|Definiert ein Feld, in dem das Ergebnis einer Rechenoperation angezeigt wird|
|`**<progress>**`|Definiert einen Fortschrittsbalken der den Status einer Aufgabe darstellt. Zur Dynamisierung kann der Wert des Balkens über JavaScript verändert werden|
|`**<meter>**`|Definiert eine Art Pegelanzeige, welche die Leere oder Fülle darstellt, zum Beispiel die genutzte Kapazität einer Festplatte oder die Relevanz eines Suchergebnisses für einen Suchbegriff|
|`**<button>**`|Definiert einen Button, der je nach Typ als Submit- oder Reset-Button eingesetzt werden kann. Ohne type wird beim Klicken des Button ein Formular nicht abgesendet. `**<button>**` kann auch außerhalb  von Formularen eingesetzt werden, um beispielsweise JavaScript-Aktionen anzustoßen.|

![](image/Pasted%20image%2020241029183258.png)


# 6 EINBETTUNG VON MEDIEN UND INHALTEN

![](image/Pasted%20image%2020241030081407.png)


|Element|Funktion|
|---|---|
|`**<img>**`|Mehrzeiliges Eingabefeld|
|`**<iframe>**`|Generiert ein Schlüssel-Paar für eine sichere Datenübertragung|
|`**<embed>**`|Definiert ein Feld, in dem das Ergebnis einer Rechenoperation angezeigt wird|
|`**<object>**`|Definiert einen Fortschrittsbalken der den Status einer Aufgabe darstellt. Zur Dynamisierung kann der Wert des Balkens über JavaScript verändert werden|
|`**<param>**`|Definiert eine Art Pegelanzeige, welche die Leere oder Fülle darstellt, zum Beispiel die genutzte Kapazität einer Festplatte oder die Relevanz eines Suchergebnisses für einen Suchbegriff|
|`**<video>**`|Definiert einen Button, der je nach Typ als Submit- oder Reset-Button eingesetzt werden kann. Ohne type wird beim Klicken des Button ein Formular nicht abgesendet. `**<button>**` kann auch außerhalb  von Formularen eingesetzt werden, um beispielsweise JavaScript-Aktionen anzustoßen|
|`**<audio>**`|Bindet Audiodateien oder Audiostreams ein|
|`**<source>**`|Definiert eine oder mehrere Quelldateien innerhalb des `**<video>**`- oder `**<audio>**`-Elements. Browser suchen sich eine Quelle aus, die sie unterstützen|
|`**<track>**`|Definiert die Quelle für eine Untertitelung innerhalb des `**<audio>**`- oder `**<video>**`-Elements|
|`**<canvas>**`|Definiert einen Bereich, in dem dynamische Grafiken, Diagramme oder Bilder skriptgesteuert dargestellt oder verändert werden können|



# 7 DARSTELLUNG VON TABELLEN


|Element|Funktion|
|---|---|
|`**<table>**`|Definiert eine Tabelle zur Gliederung von tabellarischen Daten, umschließt alle benötigten Elemente (unter anderem `**<tr>**`, `**<tth>**` und `**<td>**`) zur Aufbereitung der Daten|
|`**<caption>**`|Definiert den Titel einer Tabelle|
|`**<tbody>**`|Definiert den eigentlichen Inhalt einer Tabelle. Ohne eine Auszeichnung durch `**<thead>**`, `**<tfoot>**` und `**<tbody>**` entsprechen alle Zeilen automatisch dem `**<tbody>**`|
|`**<thead>**`|Definiert eine oder mehrere Kopfzeilen einer Tabelle. Im Ausdruck wird der Tabellenkopf auf jedem weiteren Blatt erneut ausgedruckt|
|`**<tfoot>**`|Definiert eine oder mehrere Fußzeilen einer Tabelle und ist für Summierungen bzw. Zusammenfassungen vorgesehen. Falls eine Tabelle über `**<tbody>**`, `**<thead>**` und `**<tfoot>**` gegliedert ist, muss `**<tfoot>**` hinter dem `**<thead>**`-Tag und vor dem `**<tbody>**`-Tag angegeben werden. Bei der Druckausgabe wird der Wert von `**<tfoot>**` auf jedem einzelnen Blatt ausgegeben|
|`**<tr>**`|Definiert eine Zeile innerhalb einer Tabelle|
|`**<th>**`|Definiert eine einzelne Kopfzeile innerhalb einer Tabelle, welche eine Spalte oder Zeile betitelt|
|`**<td>**`|Definiert eine normale Datenzelle innerhalb einer Tabelle|


![](image/Pasted%20image%2020241030081429.png)






