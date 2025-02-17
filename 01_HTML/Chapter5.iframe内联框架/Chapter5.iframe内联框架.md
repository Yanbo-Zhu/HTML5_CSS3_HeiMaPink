# 1 视频资源

https://www.bilibili.com/video/BV1x4411V75C?p=11&vd_source=55e5cc2f534c16c73bbeb684e98c4195https://www.bilibili.com/video/BV1x4411V75C?p=11&vd_source=55e5cc2f534c16c73bbeb684e98c4195

[HTML页面引入另一个HTML页面，比如各个页面引入通用的网站头部、尾部、导航栏_原来的1024的博客-CSDN博客_html 引入头部](https://blog.csdn.net/yldmkx/article/details/115313765)



# 2 iframe内联框架的基本原理

就是在一个网页里嵌套另一个网页

可以引入其他的html, 或者视频， 等等

```html
<iframe src="https://html.spec.whatwg.org/dev/tables.html" height="400" width="600"></iframe>
<iframe src="https://eloquentjavascript.net/01_values.html" height="400" width="600"></iframe>
```

|Attribut|Funktion|
|---|---|
|allowFullscreen|Erlaubt dem iFrame die Aktivierung des Vollbildmodus.|
|height|Höhe des iFrame in Pixeln. Standardwert ist 150 Pixels.|
|loading|Legt fest ob iFrame unmittelbar oder basierend auf bestimmten Bedingungen geladen wird.|
|referrerPolicy|Legt fest, welche Informationen beim Laden der Seite an den Drittanbieter gesendet werden.|
|src|Quelle (URL) des Drittanbieterinhalts|
|width|Breite des iFrame in Pixeln. Standardwert ist 300 Pixels.|
|name|Name des iFrame|


- Einbindung von Drittanbieterinhalten in einem _**Inline Frame**_ (_**iFrame**_)
- Eingebundene Webseite muss via HTTPS geladen werden
- Drittanbieter kann Einbindung durch spezielle HTTP-Header-Attribute unterbinden
- Same Origin Policy hindern iFrames daran, Änderungen an der Seite vorzunehmen


# 3 语法
```html
<iframe src="path" name="mainFrame"></iframe>
```


- src： 地址
- name 
- frameborder
- width 宽度高度
- height


![](Image/Chapter5_002_iframe框架语法.png)




# 4 例子

## 4.1 例子0

添加一个bilibili的视频： 

![](Image/Chapter5_001_iframe框架例子.png)

## 4.2 例子1

`<iframe src="https://www.baidu.com" frameborder="0"></frame>`

![](Image/Chapter5_004_iframe框架_例子1_1.png)

## 4.3 例子2

![](Image/Chapter5_003_iframe框架_例子2_1.png)

点击 “点击跳转”后， 左边会加载iframe 框架内的东西

![](Image/Chapter5_004_iframe框架_例子2_2.png) 

## 4.4 例子3 引入一个自建的html

```html
<!DOCTYPE html>
<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8"/>
    <title>首页</title>
</head>
<body>
    <iframe src="centerHeader.html" height="100%" width="100%" scrolling="no" frameborder="0">
    </iframe>
</body>
```



## 4.5 引入video 

```html
<video controls preload poster="img/universal.jpg">
  <source src="media/jurassicpark.mp4" type="video/mp4">
  <source src="media/jurassicpark.mp4" type=video/ogg">
  <p>
    Ihr Browser unterstützt die direkte Anzeige von Videos nicht.<br>
    Das Video zum Download: <a href="media/jurassicpark.mp4">Jurassic Park</a>
  </p>                                                    
</video>
```


- HTML5 ermöglicht Einbindung von Audio- und Videoinhalten ohne Plug-Ins mittels `**<audio>**`- und `**<video>**`-Elementen
- Einbindung von Videos unterschiedlicher Kodierungen mit vielen Konfigurationsmöglichkeiten 
- Browser wählt eine kompatible Kodierung
- Wenn Browser Kodierungen nicht unterstützt, erfolgt ein Hinweis zusammen mit einem Link zum Download

| Attribut             | Funktion                                                                                                                                                         |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `controls`           | Ergänzt Video um eine Bedienleiste, deren Layout über CSS und JavaScript angepasst werden kann angepasst                                                         |
| `autoplay`           | Startet das Video automatisch beim Laden der Seite                                                                                                               |
| `loop`               | Spielt das Video in einer Endlosschleife                                                                                                                         |
| `poster`             | Referenziert eine Grafik die gezeigt wird wenn das Video nicht abgespielt wird                                                                                   |
| `width` und `height` | Breiten- und Höhenangaben für das Video                                                                                                                          |
| `preload`            | Steuert ob die Videodatei beim Laden der Seite vorgeladen wird oder nicht, beziehungsweise ob nur Metadaten geladen werden (möglich Werte: auto, metadata, none) |


