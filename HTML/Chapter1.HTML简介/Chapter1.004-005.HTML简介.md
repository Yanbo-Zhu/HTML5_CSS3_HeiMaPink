# 1 HTML, CSS, JS
1 HTML dient dem grundlegenden Aufbau (Inhalt) von Webseiten.
2 Durch CSS wird das Design einer Webseite definiert. CSS  hat sehr oft auch starke Auswirkungen auf Funktionalität und Sicherheit. 
Ist z.B. die Änderung der Schriftart notwendig, wäre viel mehr Aufwand nötig, in jeder HTML-Datei die Schriftart zu ändern, als nur eine einzige CSS-Datei zu editieren. Fehler im Design können einfacher gefunden werden, da es nur das Stylesheet sein kann, das den Fehler beinhaltet, nicht aber ein Befehl innerhalb irgendeines HTML-Tags.
3 JavaScript ermöglicht die interaktive Manipulation von Inhalten (HTML) und Design (CSS).

CSS verändert keinesfalls nur das Design einer Webseite, sondern hat sehr oft auch starke Auswirkungen auf Funktionalität und Sicherheit. 
Gerade wenn JavaScript eingesetzt wird und man sich dabei an CSS orientiert. 

# 2 HTML

Hyper Text Markup Language 超文本标记语言 

# 3 常用浏览器及其内核

浏览器是网页显示、运行的平台。

五大浏览器有 IE、Firefox、Chrome、Safari 和 Opera。

四大内核：Trident, Gecko, Webkit, Blink

</br>

浏览器内核（渲染引擎）：负责读取网页内容，整理讯息，计算网页的显示方式并显示页面。

| 浏览器          | 内核             | 备注                                                                                                   |
| ------------ | -------------- | ---------------------------------------------------------------------------------------------------- |
| IE           | Trident        | IE、猎豹安全、360、百度浏览器                                                                                    |
| firefox      | Gecko          | 火狐浏览器内核                                                                                              |
| Safari       | Webkit         | 苹果浏览器内核                                                                                              |
| Chrome       | Chromium/Blink | 在 Chromium 项目中研发 Blink 渲染引擎（即浏览器核心），内置于 Chrome 浏览器之中。Blink 其实是 WebKit 的分支。大部分国产浏览器最新版都采用Blink内核。二次开发 |
| Chrome/Opera | Blink          | chrome/opera 浏览器内核                                                                                   |

# 4 Web标准的构成

| 标准  | 说明                               |
| --- | -------------------------------- |
| 结构  | 结构对网页元素进行整理和分类，现阶段主要是HTML  . die semantische Beschreibung eines Textes.      |
| 表现  | 表现用于设置网页元素的版式、颜色、大小等外观样式，主要是指CSS |
| 行为  | 行为是指网页模型的定义以及交互的编写，现阶段主要是JS      |

Web标准提出的最佳体验方案：结构、表现、行为相分离。

# 5 Web标准的优点

易于维护：只需更改CSS文件，就可以改变整站的样式
页面响应快：HTML文档体积变小，响应时间短
可访问性：语义化的HTML（结构和表现相分离的HTML）编写的网页文件，更容易被屏幕阅读器识别
设备兼容性：不同的样式表可以让网页在不同的设备上呈现不同的样式
搜索引擎：语义化的HTML能更容易被搜索引擎解析，提升排名

# 6 W3C标准

html5, css3, javascript 之间的关系

结构化标准语言： html, xml

表现标准语言 css

行为标准 dom, javascript 
