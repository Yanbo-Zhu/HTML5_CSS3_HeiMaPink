# 1 box-sizing

 CSS3中可以通过 box-sizing 来指定盒模型，有2个值：即可指定为 content-box，border-box ，这样我们计算盒子大小的方式就发生了改变。

可以分成两种情况：

1. `box-sizing：content-box` 盒子大小为 width + padding + border （以前默认的）
2. `box-sizing: border-box` 盒子大小为 width 如果盒子模型我们改为了 box-sizing： border-box ，那padding 和 border就不会撑大盒子了（前提 padding 和 border 不会超过 width 宽度）

## 1.1 content-box

```css
box-sizing: content-box;
```

- 第一种情况是 CSS 的盒子模型，盒子大小为 width + padding + border

- 此种情况盒子大小为 宽度 + 内边距 + 边框，这也是我们之前写盒子所默认的

## 1.2 border-box

box-sizing: border-box;

- 第二种情况是 CSS3 的盒子模型，盒子大小为 width

- 此种情况盒子大小为 宽度，不包括内边距和边框，这样 padding 和 border 就不会撑大盒子了(前提是 padding 和 border 不会超过 width 宽度)

- 我们可以在以后的 css 通配符中添加 CSS3 盒子模型

```css
* {
   margin: 0;
   padding: 0;
   box-sizing: border-box;
   /*  这样的话padding和border就不会撑大盒子了 */
}
```

# 2 圆角边框

CSS3 新增 **圆角边框** 属性，盒子可以变成圆角。

`border-radius` 属性用于设置元素的外边框圆角。

语法

```
border-radius: length;
```

原理

- `radius`半径（圆的半径） 原理:(椭）圆与边框的交集形成圆角效果
  注意
1. 参数值可以是**数值**或**百分比**的形式

2. 如果是**正方形**，想要设置为一个圆，把数值修改为**高度或者宽度的一半**即可，或者直接写为**50%**

3. 如果是一个矩形，设置为**高度**的一半就可以

4. 该属性是一个简写属性，可以跟四个值，分别代表**左上角，右上角，右下角，左下角**
   
   ```css
   border-top-left-radius:
   border-top-right-radius:
   border-bottom-right-radius:
   border-bottom-left-radius:
   ```

```
参数

- 参数值可以为数值或百分比的形式
- 若是正方形，想要设置一个圆，则将数值修改为高度或者宽度的一般即可，或者直接写为 50%
- 若是矩形，设置为 height 的一半就可以做
- 简写属性，跟四个值，分别代表左上角、右上角、右下角、左下角
- 分开来写：`border-top-left-radius`、`border-top-right-radius`、`border-bottom-right-radius`、`border-bottom-left-radius`

# 2 盒子阴影

CSS3 新增盒子阴影，使用 `box-shadow` 属性。

语法
```

bxo-shadow: h-shadow v-shadow blur spread color inset;

```
| 值        | 描述                      |
| -------- | ----------------------- |
| h-shadow | 必需，水平阴影的位置，允许负值         |
| v-shadow | 必需，垂直阴影的位置，允许负值         |
| blur     | 可选，模糊距离                 |
| spread   | 可选，阴影的尺寸                |
| color    | 可选，阴影的颜色                |
| inset    | 可选，将外部阴影改为内部阴影（默认是外部阴影） |
-   模糊距离：影子的虚实
-   阴影尺寸：影子的大小

注意：

1. 默认是外阴影，但是不可以写这个单词（outset）, 否则导致阴影无效
2. 盒子阴影不占空间，不会影响其他盒子排列

## 2.1 常用的阴影格式
原先盒子没有影子，当我们鼠标经过盒子就添加阴影效果

```css
div:hover {
      box-shadow:10px 10px 10px -4px rgba(0,0,0,.3);     

}
```

# 3 文字阴影

CSS3 中，使用 `text-shadow` 属性设置文本阴影。
`text-shadow: h-shadow v-shadow blur color`

| 值        | 描述              |
| -------- | --------------- |
| h-shadow | 必需，水平阴影位置。允许负值。 |
| v-shadow | 必须，垂直阴影。允许负值。   |
| blur     | 可选，模糊距离。        |
| color    | 可选，阴影颜色。        |
