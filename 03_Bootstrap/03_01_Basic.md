
# 1 **Was ist Bootstrap?**

Bootstrap ist ein ein extrem beliebtes **CSS-Framework**, das zur Gestaltung von Websites und Webanwendungen verwendet wird. Es wurde ursprünglich von Twitter entwickelt und vereinfacht die Erstellung responsiver und ansprechender Oberflächen, ohne dass man das Design von Grund auf neu erstellen muss. Bootstrap bietet vorgefertigte CSS- und JavaScript-Komponenten, die dabei helfen, schnell und einheitlich moderne, responsive und benutzerfreundliche Layouts zu gestalten.

1. Das Grid-System von Bootstrap
2. 

1. Das Grid-System von Bootstrap
    1. Grid-Struktur: Bootstrap basiert auf einem 12-Spalten-Grid-System, das die Layout-Gestaltung vereinfacht. Die Breite eines Elements lässt Sich durch die Anzahl der Spalten steuern, die es einnimmt.
    2. Flexibilität Das Grid passt Sich je nach Bildschirmgröße dynamisch an. Bootstrap nutzt vier Standard-Breakpoints für verschiedene Bildschirmgrößen (Extra Small, Small, Medium, Large und Extra Large).
    3. Responsives Design: Mit Klassen wie . col- (xx)-6 (nimmt 6 von 12 Spalten ein auf großen Bildschirmen) und . col- (xx)-12 (nimmt die gesamte Breite auf mittleren Bildschirmen) lässt Sich das Layout schnell an verschiedene Endgeräte anpassen. 
2. Vorgefertigte CSS-Komponenten: Bootstrap bietet eine große Auswahl an fertigen CSS-Komponenten, die man direkt verwenden und anpassen kann. Einige der wichtigsten Komponenten Sind:
    1. Buttons: Mit Klassen wie .btn, .btn-primary .btn-secondary lassen Sich Buttons in verschiedenen Farben und Stilen erstellen.
    2. Formulare: Bootstrap stellt Layouts und Stile für Formulare bereit, einschließlich Labels, Eingabefelder, Checkboxen und Radiobuttons.
    3. Navbar: Die Navigation lässt Sich mithilfe der navbar Komponente schnell und einfach gestalten. Die Navigation Wird auch automatisch responsiv und wechselt auf kleineren Bildschirmen zu einem Burger-Menü.
    4. Karten: Mit der card Komponente lassen Sich Informationskarten erstellen, die oft zur Darstellung von Inhalten, wie z B. Blogposts Oder Produkten, verwendet werden.
3. JavaScript-Komponenten: Zusätzlich zu den CSS-Stilen bietet Bootstrap auch JavaScript-Plugins, die es Entwicklern ermöglichen, interaktive Elemente hinzuzufügen, ohne tiefes JavaScript-Wissen:
    2. Modals: Diese erscheinen als Popup-Boxen und eignen Sich für Benachrichtigungen Oder zur Anzeige von Formularen.
    3. Dropdowns: Diese lassen Sich einfach zu Menüs Oder Buttons hinzufügen, um eine Auswahl an Optionen anzuzeigen.
    4. Tooltips und Popovers: Kleine Infoboxen, die Sich öffnen, wenn ein Element (z. B. ein Symbol) angeklickt Oder darüber geschwebt wird.
    5. Carousels: Ein Karussell, das Bilder Oder Inhalte durchschaltet und Sich besonders für Galerien eignet
4. Flexbox und Utility-Klassen
    1. Flexbox: Bootstrap verwendet Flexbox für viele Layouts und bietet Flexbox-Utilities, die Entwicklern helfen, die Anordnung und Ausrichtung von Elementen leicht anzupassen.
    2. Utility-Klassen: Bootstrap bietet Utility-Klassen wie .m-3 (Margin), .p-2 (Padding) und . text-center (zentrierter Text), die es Entwicklern ermöglichen, kleine Stileinstellungen schnell anzuwenden, ohne zusätzlichen CSS-Code schreiben zu müssen.
5. Community und Support 
    1. Bootstrap hat eine große Entwickler-Community und eine umfangreiche Dokumentation. Dadurch gibt es viele Ressourcen, Tutorials, und Diskussionsforen, in denen Entwickler Unterstützung finden können.
6. Vorteile von Bootstrap im Vergleich zu reinem CSS
    1. Schnelligkeit und Effizienz: Da viele Stilelemente und Layouts bereits vordefiniert Sind, sparen Entwickler Zeit beim Erstellen einer responsiven Website.
    2. Standardisierte Designs: Webseiten, die mit Bootstrap erstellt wurden, haben ein einheitliches und professionelles Aussehener was besonders in der Zusammenarbeit zwischen mehreren Entwicklern hilfreich ist.
    3. Cross-Browser-Kompatibilität: Bootstrap ist für eine breite Palette von Browsern optimiert und funktioniert in den meisten modernen Webbrowsem einwandfrei.


# 2 EINBINDUNG VON BOOTSTRAP

Nutzung von Bootstrap erfordert das Einbinden von Bootstrap-CSS- und JS-Bibliotheken
Bibliotheken werden von einem Content Delivery Network (CDN) oder von einem Verzeichnis des Webservers geladen


`“Place the <link> tag in the <head> for our CSS, and the <script> tag for our JavaScript bundle (including Popper for positioning dropdowns, poppers, and tooltips) before the closing </body>.“`

```html
<html>
  <head>
  
  	<!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
    
  </head>
  <body>
  
    <!-- Tatsächlicher Inhalt der Seite -->
    <!-- bla bla bla -->
    <!-- bla bla bla -->
    <!-- bla bla bla -->
    
    <!-- von Bootstrap benötigtes JS -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz" crossorigin="anonymous"></script>
  </body>
</html>
```


## 2.1 CDN 

![](image/Pasted%20image%2020241129210418.png)


## 2.2 VOM WEBSERVER DER HTML-SEITE


![](image/Pasted%20image%2020241129210440.png)

## 2.3 BOOTSTRAP ABHÄNGIGKEITEN

![](image/Pasted%20image%2020241129210512.png)

# 3 EINFACHE BEISPIELE

![](image/Pasted%20image%2020241129210553.png)


![](image/Pasted%20image%2020241129210615.png)


# 4 Container 


- Container bilden Grundlage für das Rastersystem
    - Können mehrfach auf einer Webseite verwendet werden, dürfen aber nicht ineinander verschachtelt werden
- Flexible Container liefern ein festes Raster, welches die Breite in Sprüngen an bestimmten Umbruchstellen (Breakpoints) anpasst und zwischen den Umbruchstellen stabil bleibt 
    - Definition eines flexiblen Container mit der Klasse `.container`
    - 随着  fenster 的宽度变大, `.container` 不是连续变大的, 而是 隔一段距离 跳变一次 
- Flüssige Container liefern ein Raster, welches sich kontinuierlich an die Breite des Bildschirms anpasst
    - Definition eines flüssigen Containers mit der Klasse `.container-fluid`
    - 随着  fenster 的宽度变大, `.container` 是连续变大的,  不是 隔一段距离 跳变一次 
- Breakpoint-Container sind bis zu einer Umbruchstelle flüssig und behalten darüber hinaus die Breite der definierten Umbruchstelle 
    - Definition mit .container-{sm|md|lg|xl|xxl}
    -  ==.container-lg:  bis zu dem Umbruchstelle immer  按照`.fluid-container`.的规律变化.  Dann 按照 `.container`的规律变化==


![](image/Pasted%20image%2020241129211137.png)


## 4.1 Rastersystem (Grid System) (class in div Element)

ein contianer ins 12 span gezergt 

- Innerhalb eines Containers kann ein **_Rastersystem_** (**_Grid System_**) aus einer oder mehreren Zeilen (**_Rows_**) mit jeweils bis zu zwölf Spalten (**_Columns_**) eingerichtet werden
- Inhalte müssen in Zellen integriert sein, die direkte Kinder von Rows sein müssen
- Neue Zeilen werden mit der Klasse `**.row**` in `**div**`-Elementen eines Containers eingerichtet
- Neue Zellen werden innerhalb einer Zeile mit den Klassen `**.col-a-b**` eingerichtet, wobei
    - `**a**` die Geräteklasse angibt
        - a的值 col order offset 
    - `**b**` die Zellenbreite als Anzahl zusammenhängender Spalten angibt
- Anzahl der verwendeten Spalten innerhalb einer Zeile darf die Maximalanzahl von zwölf nicht überschreiten, sonst wird die Zeile umgebrochen


- 可以直接写成 `.col`  , 则 width 会随机分配 
- 只写成 `.col-6`, 没有 umbruchstelle, 则随机或看上下文决定 啥时候变化 
- 写成 `.col-lg-6`, 则有 concrete Umbruchstelle

a的值 
- `col-sm-...`, `col-lg-...`, etc., define responsive breakpoints. Each size class takes effect at its defined minimum width.
- Offsets (`offset-...`) are used to create spacing by skipping columns in the grid. They shift the column to the right by the specified number of columns.
    - offset-7  , 往左 有7个 span 是空的  


![](image/Pasted%20image%2020241129211159.png)



## 4.2 {sm|md|lg|xl|xxl} 的解释 

- Bootstrap verfügt über sechs vorgefertigte Media Queries für sechs verschiedene Geräteklassen
- Raster können für jede Geräteklasse aufgebaut werden 
- Innerhalb einer Geräteklasse werden Zellen in die nächste Zeile umgebrochen, wenn der Viewport die untere Grenze der für diese Geräteklasse festgelegten Bildschirmbreite unterschreitet
- Ist der Viewport größer als die für eine Geräteklasse festgelegte Bildschirmbreite, wird in flexiblen Containern die Breite des Rasters schrittweise an die Breite der jeweiligen Geräteklasse angepasst und in flüssigen Containern an die Breite des Viewport angepasst 
- Umbruchbreite (Container-Breite) basiert auf Minimum-MediaQueries, d.h. **sie beziehen sich auf den definierten Umbruchpunkt und alle darüber**

![](image/Pasted%20image%2020241129211152.png)



## 4.3 例子

用 `<div class="row"> ` 去确定一组关系 

1 
```html
<!-- try it yourself -->

<!DOCTYPE html>
<html>
<head>
    <title>Grid 1</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
</head>
<body>
    <div class="container-fluid">
        <h3>Resize the browser window to see the effect!</h3>
        <br>
        
        <div class="row">
            <div class="col-12 col-sm-4" style="background-color:tomato;">.col-12 .col-sm-4</div> // sm 的作用就是 当 > 576px 的时候, .col-sm-4 被优先使用, 会优于.col-12
            <div class="col-6 col-sm-6" style="background-color:rgb(88, 136, 179);">.col-6 .col-sm-6</div>
            <div class="col-6 col-sm-2" style="background-color:lightgreen;">.col-6 .col-sm-2</div>
        </div>
    </div>
</body>
</html>

```

2 
```html
<!-- try it yourself -->

<!DOCTYPE html>
<html>
<head>
    <title>Grid 2</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
</head>
<body>
    <div class="container-fluid">
        <h3>Resize the browser window to see the effect!</h3>
        <br>
        
        <div class="row">
            <div class="col-12 col-md-4" style="background-color:rgb(255, 105, 97);">.col-12 .col-md-4</div>
            <div class="col-12 col-md-4" style="background-color:rgb(135, 206, 250);">.col-12 .col-md-4</div>
            <div class="col-12 col-md-4" style="background-color:rgb(240, 128, 128);">.col-12 .col-md-4</div>
        </div>
        <div class="row">
            <div class="col-6 col-md-3" style="background-color:rgb(221, 160, 221);">.col-6 .col-md-3</div>
            <div class="col-6 col-md-9" style="background-color:rgb(144, 238, 144);">.col-6 .col-md-9</div>
        </div>
    </div>
</body>
</html>
```


3 
```html
<!-- try it yourself -->

<!DOCTYPE html>
<html>
<head>
    <title>Grid 3</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
</head>
<body>
    <div class="container-fluid">
        <h3>Resize the browser window to see the effect!</h3>
        <br>
        
        <div class="row">
            <div class="col-6 col-sm-8 col-md-10" style="background-color:rgb(191, 130, 150);">.col-6 .col-sm-8 .col-md-10</div>
            <div class="col-6 col-sm-4 col-md-2" style="background-color:rgb(18, 216, 196);">.col-6 .col-sm-4 .col-md-2</div>
        </div>
        <div class="row">
            <div class="col-6" style="background-color:rgb(178, 103, 208);">.col-6</div>
            <div class="col-6" style="background-color:rgb(233, 98, 125)">.col-6</div>
        </div>
        <div class="row">
            <div class="col-10 col-sm-8 col-lg-3" style="background-color:rgb(100, 216, 43);">.col-10 .col-sm-8 .col-lg-3</div>
            <div class="col-2 col-sm-4 col-lg-9" style="background-color:rgb(220, 159, 48)">.col-2 .col-sm-4 .col-lg-9</div>
        </div>
        <div class="row">
            <div class="col-7 col-sm-6 col-md-8" style="background-color:rgb(177, 179, 81);">.col-7 .col-sm-6 .col-md-8</div>
            <div class="col-5 col-sm-6 col-md-4" style="background-color:rgb(140, 140, 208);">.col-5 .col-sm-6 .col-md-4</div>
        </div>
    </div>
</body>
</html>
```


4 
![](image/Pasted%20image%2020241204215716.png)

```html
<!-- try it yourself -->

<!DOCTYPE html>
<html>
<head>
    <title>Grid 4</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
</head>
<body>
    <div class="container-fluid">
        <h3>Resize the browser window to see the effect!</h3>
        <br>

        <div class="row">
            <div class="col-8" style="background-color:rgb(173, 216, 230);">.col-8
                <div class="row">
                    <div class="col-6" style="background-color:rgb(255, 182, 193);">Verschachtelt .col-6</div>
                    <div class="col-6" style="background-color:rgb(255, 228, 181);">Verschachtelt .col-6</div>
                </div>
            </div>
            <div class="col-4" style="background-color:rgb(196, 176, 0);">.col-4</div>
        </div>
    </div>
</body>
</html>
```


5 

```html
<!-- try it yourself -->

<!DOCTYPE html>
<html>
<head>
    <title>Grid 5</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
</head>
<body>
    <div class="container-fluid">
        <h3>Resize the browser window to see the effect!</h3>
        <br>

        <div class="row">
            <div class="col-sm-4" style="background-color: yellow;">col-sm-4</div>
            <div class="col-sm-4 offset-4 col-lg-8" style="background-color: bisque;">col-sm-4 offset-4 col-lg-8</div>
            <div class="col-sm-4 offset-xl-4 col-lg-8 offset-lg-2" style="background-color: yellowgreen;">col-sm-4 offset-xl-4 col-lg-8 offset-lg-2</div>
            <div class="col-1 offset-7" style="background-color: aqua;">col-1 offset-7</div>
        </div>
    </div>
</body>
</html>
```



- **First Column (`col-sm-4`)**:
    - Takes **4/12 of the width** on `sm` screens (≥576px) and above.
    - Has a yellow background.
    - No offsets, so it starts from the left.
- **Second Column (`col-sm-4 offset-4 col-lg-8`)**:
    - Takes **4/12 of the width** on `sm` screens and above, with an **offset of 4/12**, meaning it skips 4 columns and starts at the 5th column.
    - On `lg` screens (≥992px), it switches to **8/12 of the width**, without any offset.
    - Has a bisque background.
- **Third Column (`col-sm-4 offset-xl-4 col-lg-8 offset-lg-2`)**:
    - Takes **4/12 of the width** on `sm` screens and above.
    - On `lg` screens, it switches to **8/12 of the width** with an **offset of 2/12**.
    - On `xl` screens (≥1200px), it has an **offset of 4/12** but retains its `col-sm-4` width.
    - Has a yellow-green background.
- **Fourth Column (`col-1 offset-7`)**:
    - Takes **1/12 of the width** on all screen sizes.
    - Has an **offset of 7/12**, meaning it skips 7 columns and starts at the 8th column.
    - Has an aqua background.



Visualization of Layout Behavior:
- tiny Screens (screen width <sm)
    - ![](image/Pasted%20image%2020241204220647.png)
- **Small Screens (`sm`)**:
    - All columns behave according to their `col-sm-...` classes.
    - The second and third columns will be offset.
    - ![](image/Pasted%20image%2020241204220700.png)
- **Large Screens (`lg`)**:
    - The second column becomes wider (`col-lg-8`), and its offset is removed.
    - The third column also becomes wider and is centered with an offset of 2.
    - ![](image/Pasted%20image%2020241204220712.png)
- **Extra Large Screens (`xl`)**:
    - The third column adjusts its offset to 4.
    - ![](image/Pasted%20image%2020241204220754.png)

# 5 BILDER IN BOOTSTRAP


- Ohne `**width**`- und `**height**`-Attribute im `**img**`-Element werden Bilder in der Originalgröße dargestellt
- Bilder werden durch Hinzufügen der Klasse  
    `**.img-fluid**` im `**img**`-Element "responsive"
- `**.img-fluid**` wendet auf das `**img**`-Element die CSS-Eigenschaften `**max-width: 100%**`, `**height: auto**` und `**display:block**` an. 实际效果是 image 随着窗口的大小 自动化resize image 的大小, 一直保持 全图展示
- `image-fluid rounded`
- `image-fluid img-thumbnail`
- `image-fluid rounded-circle`
- 


![](image/Pasted%20image%2020241129212033.png)



----

![](image/Pasted%20image%2020241129212104.png)


----

- Bootstrap ermöglich die einfache Erstellung von Slide Shows durch die Klasse `**.carousel**`
- `**.carousel**` kennzeichnet die Slide Show
- `**.slide**` fügt den Animationseffekt hinzu
- `**.carousel-indicators**` zusammen mit einer Liste fügen die klickbaren Punkte im unteren Bereich hinzu
- .`**carousel-inner**` fügt dem Karussell Bilder hinzu 
- .`**carousel-control-***` fügen Vor- und Zurück-Buttons hinzu


![](image/Pasted%20image%2020241129212122.png)


