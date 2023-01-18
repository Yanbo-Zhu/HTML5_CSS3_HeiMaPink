# 1 CSS 三角图形

## 1.1 例子1
```css
.box1 {
  width: 0;
  height: 0;
  border: 10px solid transparent;
  border-left-color: black;
  /* 照顾兼容性 */
  line-height: 0;
  font-size: 0;
}
```

## 1.2 例子2

![图片](https://mmbiz.qpic.cn/mmbiz_png/y7EkeCWAzmqtcdL7HZYccBic0jicaWzR8bMZvtNQGxxYDG6SvNX35cbQ6TaDfdMYoBxHVLwNHujC7dg4WzBD5TVQ/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

1.  我们用css 边框可以模拟三角效果
2.  宽度高度为0
3.  我们4个边框都要写， 只保留需要的边框颜色，其余的不能省略，都改为 transparent 透明就好了
4.  为了照顾兼容性 低版本的浏览器，加上 font-size: 0;  line-height: 0;
```css
div {  
  
    width: 0;   
  
    height: 0;  
    line-height:0；  
    font-size: 0;  
   border-top: 10px solid red;  
  
   border-right: 10px solid green;  
  
   border-bottom: 10px solid blue;  
  
   border-left: 10px solid #000;   
  
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



## 2.1 CSS3 calc函数

此 CSS 函数让你在声明CSS属性值时执行一些计算。

```
width: calc(100%-30px);
/* 子盒子永远比父盒子小30px */
```

括号里面可以使用 `+ - * /` 来进行计算。

```html
<head> 
   <style>
        .father {
            width: 300px;
            height: 200px;
            background-color: pink;
        }

        .son {
            /* width: 150px; */
            /* son盒子和父亲一样宽，都是100%，son盒子-30px */
            width: calc(100%-30px);
            height: 30px;
            background-color: skyblue;
        }
    </style>
</head>

<body>
    <!-- 需求：我们的子盒子宽度永远比父盒子小30像素 -->
    <div class="father">
        <div class="son"></div>
    </div>
</body>
```
