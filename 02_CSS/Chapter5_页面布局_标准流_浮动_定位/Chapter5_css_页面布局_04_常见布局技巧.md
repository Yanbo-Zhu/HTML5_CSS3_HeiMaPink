# 2 常见布局技巧

## 2.1 margin负值的运用

1. 解决并排盒子之间的边框宽度加倍问题。 原理：让每个盒子压住前面的盒子，边框叠加。
2. 鼠标移动边框颜色变化效果。

### 2.1.1 有两个盒子

- 两个盒子加边框1px，浮动，贴紧会出现 1 + 1 = 2px
- 给右边盒子添加`margin-left: -1px`
- 正数向右边走，负数向左边走
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/49161c07333346c990eab8dca70b4425.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

### 2.1.2 有多个盒子

https://blog.csdn.net/Augenstern_QXL/article/details/119172527

![在这里插入图片描述](https://img-blog.csdnimg.cn/8bf8e78f78bf4dfa89950aa8dd76bfd6.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)
当我们有多个盒子时的解决办法：

1. 让每个盒子 margin 往左侧移动 -1px 正好压住相邻盒子边框
2. 鼠标经过某个盒子的时候，提高当前盒子的层级即可
   - 如果没有定位，则加相对定位(保留位置)
   - 如果有定位，则加 z-index

```csss
/*如果盒子没有定位，则鼠标经过添加相对定位即可*/
ul li:hover {
  position: relative;
  border: 1px solid orange;
}
/*若li都有定位，则使用 z-index 提高层级*/
ul li {
  z-index: 1;
  border: 1px solid orange;
}
```

```html
<head>
<style>
    ul li {
        float: left;
        list-style: none;
        width: 150px;
        height: 200px;
        border: 1px solid red;
        margin-left: -11px
    }

    ul li:hover {
        position: relative;
        border: 1px solid blue;
    }

</style>
</head>
<body>
    <ul>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
    </ul>
</body>
```

## 2.2 文字围绕浮动元素巧妙运用

原理：浮动元素不会遮住文字。

```
div {
  float: left;
}
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/71377b1f43f34ff1aaf153cf1dceb0b6.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

## 2.3 行内块元素巧妙运用

![在这里插入图片描述](https://img-blog.csdnimg.cn/7d1aaaf6a6d549e7b1a90c25447fb370.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

行内块元素布局当前页码和 pre，next盒子，使用 text-align: center 居中。
页码在页面中间显示：

1. 把这些链接盒子转换为行内块，之后给父级指定 `text-align: center`
2. 利用行内块元素中间有缝隙，并且给父级添加 `text-align: center` ，行内块元素会水平居中
