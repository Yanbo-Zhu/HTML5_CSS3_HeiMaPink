# 1 自定义variable/ Custom Properties
CSS Variablen heißen Custom Properties.
- Sie werden wie folgt vereinbart： `--variablen-bezeichner: wert`
- Der Aufruf erfolgt über eine Funktion.: `var(--variablen-bezeichner)`

说明
- 自定义variablet通常定义为 globale Variablen， die  im :root vereinbart werden.
- Sollen die Variablen mit anderen Dateien (z.B. js) später verändert werden, dann müssen Custom Properties verwendet werden 
- keine Sass Variablen.

例子: 
```css
:root{

    /* Deklaration*/
    --main-hue: 240;

    /* Deklaration und Aufruf.
    Verändern Sie den Wert für --main-hue und schauen Sie, was passiert.
    Der hue kann einen Wert zwischen 0 und 360, jeweils inklusive annehmen.
    Der Variablenaufruf erfolgt über die Funktion var()
    In der Parameterliste werden dann die Werte, oder
    wie folgt auch Variablen angegeben.

    */

    --main-color: hsl(var(--main-hue),100%,50%);
    --secondary-color: hsl(var(--main-hue), 100%, 20%);
    --tertiary-color: hsl(var(--main-hue), 100%, 90%);

}

  

h1,
h2,
h3{

    /* Aufruf */
    color: var(--secondary-color);
    background-color: var(--tertiary-color);

}

  
article{
    background-color: var(--secondary-color);
    color: var(--tertiary-color);
}
```