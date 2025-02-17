
![](image/Pasted%20image%2020241123134524.png)

# 1 FESTES LAYOUT

- Bei einem **_festen Layout_** sind die Dimensionen in der Einheit Pixel angegeben
- Dynamische Anpassung des Layouts für unterschiedliche Geräte ist nicht möglich


# 2 FLÜSSIGES/ELASTISCHES LAYOUT

- Ein **_fluides_** oder **_flüssiges Layout_** wird in Prozenten des Viewport definiert
- Ändert sich die Größe des Viewport, ändern sich auch die Dimensionen des Layouts
- Inhalte wie Texte oder Bilder bleiben jedoch in ihrer Größe erhalten
- Bei einem _**elastischen** Layout_ werden die Breitenangaben in der Einheit em angegeben, die sich auf die Schriftgröße bezieht
- Das Layout skaliert mit der Schriftgröße, nicht bei Änderungen der Bildschirmbreite

# 3 ADAPTIVES LAYOUT

- Das **_adaptive Layout_** ist ein festes Layout, welches in mehreren Versionen existiert und sich bei Änderung des Viewport anpasst
- Bei Änderungen des Viewport wird an vordefinierten Bildschirmbreiten (**_Breakpoints_**, **_Umbruchstellen_**) zwischen den verschiedenen Versionen gewechselt
- Zwischen den Umbruchstellen verhält es sich wie ein festes Layout



# 4 RESPONSIVES LAYOUT

- Das _**responsive Layout**_ vereint die Eigenschaften des adaptiven und des flüssigen Layouts
- Es verfügt ebenfalls über Umbruchstellen, an denen zwischen verschiedenen Versionen des Layouts gewechselt wird
- Zwischen den Umbruchstellen verhält sich das responsive Layout wie das flüssige Layout


# 5 例子 

## 5.1 FESTES LAYOUT FLÜSSIGES LAYOUT


Festes Layout

```css
body {
  width: 1000px;
}
header {
  width: 1000px;
}
nav {
  width: 250px;
  float: left;
  ...
}
main {
  width: 500px;
  float: left;
  ...
}
aside {
  width: 250px;
  float: left;
  ...
}
fotter {
  clear: both;
  width: 1000px;
  ...
}

```



Flüssiges Layout
```css
body {
  width: 1000px;
}
header {
  width: 100%;
}
nav {
  width: 25%;
  float: left;
  ...
}
main {
  width: 50%;
  float: left;
  ...
}
aside {
  width: 25%;
  float: left;
  ...
}
fotter {
  clear: both;
  width: 100%;
  ...
}
```



![](image/Pasted%20image%2020241123135138.png)

- Layouts basieren auf **_Rastersystemen_** (**_Grid Systems_**), welche in der Horizontalen die Breite einer Webseite in eine Anzahl von Spalten unterteilen
- Bei einem festen Layout erfolgt die Fixierung der Spaltenbreite üblicherweise in der Einheit Pixel
- Bei einem flüssigen Layout erfolgt die Festlegung der Spaltenbreite üblicherweise in der Einheit Prozent, wobei die Summe der Spalten einer Zeile 100% beträgt
- Die zur Verfügung stehende Breite wird durch das Elternelement vorgegeben und kann zum Beispiel durch die CSS-Eigenschaften `**min-width**` oder `**max-width**` angegeben werden


## 5.2 RESPONSIVE DESIGN?

- Positionierung von HTML-Elementen kann durch ein generisches Koordinatensystem mit den Klassen **`.col`** und `**.row**` erheblich vereinfacht werden
- `**.row**` verursacht einen Zeilenumbruch mittels `**clear: both**`
- Jede Zeile wird in zwölf Spalten unterteilt
- Mehrere Spalten können durch `**col-x**` zu einer Zelle verbunden werden, wobei `**x**` die Anzahl der Spalten darstellt, die die Zelle umfasst

---

1
```css
<div class="row">
  <header class="col-12">
    <h1>YASN - Responsives Layout I</h1>
  </header>
</div>

<div class="row">
  <nav class="col-3">
    <ul>
      <li>Dashboard</li>
      <li>Profil</li>
      <li>Netzwerk</li>
      <li>Timeline</li>
    </ul>
  </nav>

  <main class="col-6">
    <h1>Blog von Trapattoni</h1>
    <p>Es gibt im Moment.... </p>
  </main>
  
  <aside class="col-3">
    <h1>Zitate</h1>
    <h2>George</h2>
    <p>"Ich denke wir sind uns...</p>
    <h2>Helmut</h2>
    <p>"Die Schwierigkeit ist das Problem."</p>
    <h2>Konrad</h2>
    <p>"Ich bin wie ich bin....</p>
  </aside>
</div>

<div class="row">
  <footer class="col-12">
    <p>Ändere die Fenstergröße,...</p>
  </footer>
</div>
```

```css
.row::after {
  content: '';  # 加入一个content
  clear: both;  // right-floating,  left-floating 
  display: block;
}

[class*='col-'] {
  width: 100%;
  float: left;
  padding: 15px;
  border: 1px solid red;
}

.col-1 {width: 8.33%;}
.col-2 {width: 16.66%;}
.col-3 {width: 25%;}
.col-4 {width: 33.33%;}
.col-5 {width: 41.66%;}
.col-6 {width: 50%;}
.col-7 {width: 58.33%;}
.col-8 {width: 66.66%;}
.col-9 {width: 75%;}
.col-10 {width: 83.33%;}
.col-11 {width: 91.66%;}
.col-12 {width: 100%;}
```


---

2
![](image/Pasted%20image%2020241123135633.png)


```css
.row::after {
  content: '';
  clear: both;
  display: block;
}

[class*='col-'] {
  width: 100%;
  float: left;
  padding: 15px;
  border: 1px solid red;
      }

@media only screen and (min-width: 768px) {
  .col-1 {width: 8.33%;}
  .col-2 {width: 16.66%;}
  .col-3 {width: 25%;}
  .col-4 {width: 33.33%;}
  .col-5 {width: 41.66%;}
  .col-6 {width: 50%;}
  .col-7 {width: 58.33%;}
  .col-8 {width: 66.66%;}
  .col-9 {width: 75%;}
  .col-10 {width: 83.33%;}
  .col-11 {width: 91.66%;}
  .col-12 {width: 100%;}
}
```

- _**Adaptives Layout**_: mit Media Queries können Umbruchstellen (Breakpoints) definiert werden, an denen zwischen verschiedenen Layouts gewechselt wird
- In Kombination mit Prozentangaben für die Breite von Spalten ergibt sich so ein vollwertiges **_Responsive Design_**


---

3  Responsive Design mit mehreren Breakpoints



![](image/Pasted%20image%2020250217205604.png)

```css
<div class="row">
  <header class="col-12 col-m-12">
    <h1>YASN - Responsives Layout I</h1>
  </header>
</div>

<div class="row">
  <nav class="col-3 col-m-3">
    <ul>
      <li>Dashboard</li>
      <li>Profil</li>
      <li>Netzwerk</li>
      <li>Timeline</li>
    </ul>
  </nav>

  <main class="col-6 col-m-9">
    <h1>Blog von Trapattoni</h1>
    <p>Es gibt im Moment.... </p>
  </main>
  
  <aside class="col-3 col-m-12">
    <h1>Zitate</h1>
    <h2>George</h2>
    <p>"Ich denke wir sind uns...</p>
    <h2>Helmut</h2>
    <p>"Die Schwierigkeit ist das Problem."</p>
    <h2>Konrad</h2>
    <p>"Ich bin wie ich bin....</p>
  </aside>
</div>

<div class="row">
  <footer class="col-12 col-m-12">
    <p>Ändere die Fenstergröße,...</p>
  </footer>
</div>
```


```css
.row::after {
  content: '';
  clear: both;
  display: block;
}

[class*='col-'] {
  width: 100%;
  float: left;
}

@media only screen and (min-width: 600px) {
  .col-m-1 {width: 8.33%;}
  .col-m-2 {width: 16.66%;}
  .col-m-3 {width: 25%;}
  .col-m-4 {width: 33.33%;}
  .col-m-5 {width: 41.66%;}
  .col-m-6 {width: 50%;}
  .col-m-7 {width: 58.33%;}
  .col-m-8 {width: 66.66%;}
  .col-m-9 {width: 75%;}
  .col-m-10 {width: 83.33%;}
  .col-m-11 {width: 91.66%;}
  .col-m-12 {width: 100%;}
}

@media only screen and (min-width: 768px) {
  .col-1 {width: 8.33%;}
  .col-2 {width: 16.66%;}
  .col-3 {width: 25%;}
  .col-4 {width: 33.33%;}
  .col-5 {width: 41.66%;}
  .col-6 {width: 50%;}
  .col-7 {width: 58.33%;}
  .col-8 {width: 66.66%;}
  .col-9 {width: 75%;}
  .col-10 {width: 83.33%;}
  .col-11 {width: 91.66%;}
  .col-12 {width: 100%;}
}
```


Adaptives Layout: mit Media Queries können Umbruchstellen (Breakpoints) defi niert werden, an denen zwischen verschiedenen Layouts gewechselt wird
In Kombination mit Prozentangaben für die Breite von Spalten ergibt sich so ein vollwertiges Responsive Design

