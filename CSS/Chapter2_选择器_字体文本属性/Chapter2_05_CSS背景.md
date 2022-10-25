# CSS 的背景

CSS 背景属性可以给元素添加背景样式。
背景属性可以设置背景颜色、背景图片、背景平铺、背景图片位置、背景图像固定等。

# 背景总结

背景图片:实际开发常见于 logo 或者一些装饰性的小图片或者是超大的背景图片, 优点是非常便于控制位置.

| 属性                    | 作用       | 值                                                            |
| --------------------- | -------- | ------------------------------------------------------------ |
| background-color      | 背景颜色     | 预定义的颜色值/十六进制/RGB代码                                           |
| background-image      | 背景图片     | url(图片路径)                                                    |
| background-repeat     | 是否平铺     | repeat/no-repeat/repeat-x/repeat-y                           |
| background-position   | 背景位置     | length/position    分别是x  和 y坐标， 切记 如果有 精确数值单位，则必须按照先X 后Y 的写法 |
| background-attachment | 背景固定还是滚动 | scroll/fixed                                                 |
| 背景简写                  | 更简单      | 背景颜色 背景图片地址 背景平铺 背景滚动 背景位置;  他们没有顺序                          |
| 背景透明                  | 让盒子半透明   | background: rgba(0,0,0,0.3);   后面必须是 4个值                     |

# 背景颜色

`background-color` 定义了元素的背景颜色。

默认的值是 transparent  透明的

```css
background-color: 颜色值;
```

一般而言，颜色默认值是 `transparent`（透明），我们也可以指定背景颜色为透明色或其他色。

# 背景图片

`background-image` 属性描述了元素的背景图像，实际开发用于 logo 或者一些装饰性开发的小图片或者是超大的背景图片，优点是便于控制位置。（也用于精灵图）

```css
background-image: none|url(图片url);

例如:
background-image: url(images/1.png);
```

# 背景平铺

若需要在 HTML 页面上对背景图进行平铺，可以使用 `background-repeat` 属性。

```css
background-repeat: repeat(默认) | no-repeat | repeat-x | repeat-y;
```

页面元素·既可以添加背景图片，也可以添加背景颜色，图片会覆盖颜色。

| 参数值       | 作用                 |
| --------- | ------------------ |
| repeat    | 背景图像在纵向和横向上平铺(默认的) |
| no-repeat | 背景图像不平铺            |
| repeat-x  | 背景图像在横向上平铺         |
| repeat-y  | 背景图像在纵向平铺          |

# 背景图片位置

`background-position` 可以改变图片在背景中的位置。

```css
background-position: x y;
```

参数 x 和 y 指 x 左边和 y 坐标，可以使用方位名词或者精确定位。

| 参数值      | 说明                                                 |
| -------- | -------------------------------------------------- |
| length   | 百分数 / 由浮点数字和单位字符组成的长度值                             |
| position | top / center / bottom / left / center / right 方位名词 |

**1.参数是方位名词**

- 若两个值都是方位名词，则两个值前后顺序无关，比如`left top`和`top left` 效果一致。

- 若只指定了一个方位名词，另一个值省略，则第二个值默认居中对齐。

**2.参数是精确单位**

- 第一个必定是 x 坐标。第二个是 y 坐标
- 若只指定一个数值，则另一个必定是 y 轴居中

**3.参数是混合单位**

- 若是混合单位，则第一个值是 x 坐标，第二个值是 y 坐标。

# 背景图像固定

`background-attachment` 属性设置背景图像是否随着页面其余部分滚动。

`background-attachment` 后期可以制作视差滚动效果。

```css
background-attachment: scroll | fixed;
```

| 参数     | 作用           |
| ------ | ------------ |
| scroll | 背景图像随着对象内容滚动 |
| fixed  | 背景图像固定       |

# 背景属性复合写法

background：属性的值的书写顺序官方没有强制的标准. 

简化代码，将属性写在同一个属性 `background` 下。 

一般按照约定顺序编写: background 背景颜色 背景图片地址 背景平铺 背景图像滚动 背景图片位置

```css
/* 有背景图片背景颜色可以不用写*/
background: transparent url(image.jpg) repeat-y fixed top;
```

# 背景颜色半透明

CSS3 提供 `background: rgba(r,g,b,a)` 属性设置图片透明度。

```css
background: rgba(0, 0, 0, 0.3);
background: rgba(0, 0, 0, .3);
```

- CSS3 新增属性，IE9+支持. 低于IE 9的版本不支持

- 最后一个参数是`alpha` 透明度 ，取值范围在0~1之间

- 我们习惯把0.3的 0省略掉，写为`background(0,0,0,.3)`;

- 注意：**背景半透明是指盒子背景半透明，盒子里面的内容不受影响**

## 盒子半透明 opacity

设置opacity元素的所有后代元素会随着一起具有透明性，一般用于调整图片或者模块的整体不透明度

`opacity: .2;`
