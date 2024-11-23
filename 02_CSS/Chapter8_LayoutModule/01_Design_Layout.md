
![](image/Pasted%20image%2020241123134524.png)

# 1 FESTES LAYOUT

Bei einem festen Layout sind die Dimensionen in der Einheit Pixel angegeben
Dynamische Anpassung des Layouts für unterschiedliche Geräte ist nicht möglich


# 2 FLÜSSIGES/ELASTISCHES LAYOUT

Ein fl uides oder fl üssiges Layout wird in Prozenten des Viewport defi niert

Ändert sich die Größe des Viewport, ändern sich auch die Dimensionen des Layouts

Inhalte wie Texte oder Bilder bleiben jedoch in ihrer Größe erhalten

Bei einem elastischen Layout werden die Breitenangaben in der Einheit em angegeben, die sich auf die Schriftgröße bezieht

Das Layout skaliert mit der Schriftgröße, nicht bei Änderungen der Bildschirmbreite

# 3 ADAPTIVES LAYOUT

Das adaptive Layout ist ein festes Layout, welches in mehreren Versionen existiert und sich bei Änderung des Viewport anpasst

Bei Änderungen des Viewport wird an vordefi nierten Bildschirmbreiten (Breakpoints, Umbruchstellen)

zwischen den verschiedenen Versionen gewechselt Zwischen den Umbruchstellen verhält es sich wie ein festes Layout



# 4 RESPONSIVES LAYOUT

Das responsive Layout vereint die Eigenschaften des adaptiven und des fl üssigen Layouts
Es verfügt ebenfalls über Umbruchstellen, an denen zwischen verschiedenen Versionen des Layouts gewechselt wird
Zwischen den Umbruchstellen verhält sich das responsive Layout wie das fl üssige Layout


# 5 例子 

## 5.1 FESTES LAYOUT FLÜSSIGES LAYOUT

![](image/Pasted%20image%2020241123135123.png)

![](image/Pasted%20image%2020241123135138.png)

Layouts basieren auf Rastersystemen (Grid Systems), welche in der Horizontalen die Breite einer Webseite in eine Anzahl von Spalten unterteilen

Bei einem festen Layout erfolgt die Fixierung der Spaltenbreite üblicherweise in der Einheit Pixel

Bei einem fl üssigen Layout erfolgt die Festlegung der Spaltenbreite üblicherweise in der Einheit Prozent, wobei die Summe der Spalten einer Zeile 100% beträgt

Die zur Verfügung stehende Breite wird durch das Elternelement vorgegeben und kann zum Beispiel durch die CSS-Eigenschaften min-width oder max-width angegeben werden


## 5.2 RESPONSIVE DESIGN?

Positionierung von HTML-Elementen kann durch ein generisches Koordinatensystem mit den Klassen .col und .row erheblich vereinfacht werden
.row verursacht einen Zeilenumbruch mittels clear: both
Jede Zeile wird in zwölf Spalten unterteilt
Mehrere Spalten können durch col-x zu einer Zelle verbunden werden, wobei x die Anzahl der Spalten darstellt, die die Zelle umfasst

![](image/Pasted%20image%2020241123135608.png)

---

![](image/Pasted%20image%2020241123135633.png)

![](image/Pasted%20image%2020241123135645.png)


Adaptives Layout: mit Media Queries können Umbruchstellen (Breakpoints) defi niert werden, an denen zwischen verschiedenen Layouts gewechselt wird
In Kombination mit Prozentangaben für die Breite von Spalten ergibt sich so ein vollwertiges Responsive Design

