# 5 背景颜色渐变 (-webkit-linear-gradient)

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            width: 600px;
            height: 200px;
            /* 背景渐变必须添加浏览器私有前缀 */
            /* background: -webkit-linear-gradient(left, red, blue); */
            /* background: -webkit-linear-gradient(red, blue); */
            background: -webkit-linear-gradient(top left, red, blue);
        }
    </style>
</head>

<body>
    <div></div>
</body>
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/974fa15e13cb47f0bc7a265d59f2b33c.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA55Sf5ZG95piv5pyJ5YWJ55qE,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)


# 6 rem适配布局

我们来看几个问题：

1. 页面布局文字能否随着屏幕大小变化而变化？
2. 流式布局和flex布局主要针对于宽度布局，那高度如何设置？
3. 怎么样让屏幕发生变化的时候元素高度和宽度等比例缩放？

## 6.1 rem基础

- rem (root em)是一个相对单位，类似于em，em是父元素字体大小。
- 不同的是rem的基准是相对于html元素的字体大小。
  - 比如，根元素（html）设置font-size=12px; 非根元素设置width:2rem; 则换成px表示就是24px
  - rem的优势：父元素文字大小可能不一致， 但是整个页面只有一个html，可以很好来控制整个页面的元素大小

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        html {
            font-size: 12px;
        }

        div {
            font-size: 12px;
            width: 15rem;
            height: 15rem;
            background-color: purple;
        }

        p {
            /* 1. em相对于父元素 的字体大小来说的 */
            /* width: 10em;
            height: 10em; */
            /* 2. rem 相对于 html元素 字体大小来说的 */
            width: 10rem;
            height: 10rem;
            background-color: pink;
            /* 3.rem的优点就是可以通过修改html里面的文字大小来改变页面中元素的大小可以整体控制 */
        }
    </style>
</head>

<body>
    <div>
        <p></p>
    </div>

</body>
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/f6708feda7904832b76d87995ad02bd3.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA55Sf5ZG95piv5pyJ5YWJ55qE,size_18,color_FFFFFF,t_70,g_se,x_16#pic_center)



## 6.2 媒体查询+rem实现元素动态大小变化
-   rem单位是跟着html来走的，有了rem页面元素可以设置不同大小尺寸
-   媒体查询可以根据不同设备宽度来修改样式
-   媒体查询+rem 就可以实现不同设备宽度，实现页面元素大小的动态变化

下面代码的意思是：屏幕尺寸小于320px， div 大小为 0.5*50 = 25px，屏幕尺寸大于 320px 小于 640px， div 大小为 0.5 * 100 = 50px
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        /* html {
            font-size: 100px;
        } */
        /* 从小到大的顺序 */
        
        @media screen and (min-width: 320px) {
            html {
                font-size: 50px;
            }
        }
        
        @media screen and (min-width: 640px) {
            html {
                font-size: 100px;
            }
        }
        
        .top {
            height: 1rem;
            font-size: .5rem;
            background-color: green;
            color: #fff;
            text-align: center;
            line-height: 1rem;
        }
    </style>
</head>
<body>
    <div class="top">购物车</div>
</body>

```

## 6.3 引入资源

-   当样式比较繁多的时候，我们可以针对不同的媒体使用不同 stylesheets（样式表）。
-   原理，就是直接在link中判断设备的尺寸，然后引用不同的css文件。

语法：
`<link rel="stylesheet" media="mediatype and|not|only (media feature)" href="mystylesheet.css">`

示例：
`<link rel="stylesheet" href="styleA.css" media="screen and (min-width: 400px)">`



## 6.4 rem适配方案
1. 让一些不能等比自适应的元素，达到当设备尺寸发生改变的时候，等比例适配当前设备。
2. 使用媒体查询根据不同设备按比例设置html的字体大小，然后页面元素使用rem做尺寸单位，当html字体大小变化元素尺寸也会发生变化，从而达到等比缩放的适配。


实际开发中适配方案：
1. 按照设计稿与设备宽度的比例，动态计算并设置 html 根标签的 font-size 大小；（媒体查询）
2. CSS 中，设计稿元素的宽、高、相对位置等取值，按照同等比例换算为 rem 为单位的值；

rem 适配方案技术使用
![在这里插入图片描述](https://img-blog.csdnimg.cn/a0b6ea5dab89442096a4d3595c121dc7.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA55Sf5ZG95piv5pyJ5YWJ55qE,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)

### 6.4.1 rem实际开发适配方案一

rem + 媒体查询 + less 技术
![在这里插入图片描述](https://img-blog.csdnimg.cn/2f0494ce7c554a6985ac4f0d0db421e4.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA55Sf5ZG95piv5pyJ5YWJ55qE,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)
一般情况下，我们以一套或两套效果图适应大部分的屏幕，放弃极端屏或对其优雅降级，牺牲一些效果。现在基本以750为准。

#### 6.4.1.1 动态设置 html 标签 font-size 大小
1. 假设设计稿是750px
2. 假设我们把整个屏幕划分为15等份（划分标准不一可以是20份也可以是10等份）
3. 每一份作为html字体大小，这里就是50px
4. 那么在320px设备的时候，字体大小为320/15 就是 21.33px
5. 用我们页面元素的大小 除以不同的 html 字体大小会发现他们比例还是相同的
6. 比如我们以 750为标准设计稿
7. 一个100*100像素的页面元素 在 750屏幕下， 就是 100 / 50 转换为rem 是 2rem * 2 rem 比例是 1比1
8. 320屏幕下， html 字体大小为 21.33 则 2rem = 42.66px 此时宽和高都是 42.66 但是 宽和高的比例还是 1比1
9. 但是已经能实现不同屏幕下 页面元素盒子等比例缩放的效果

#### 6.4.1.2 元素大小取值方法
- 最后的公式： 页面元素的rem值 = 页面元素值（px） / （屏幕宽度 / 划分的份数）
- 屏幕宽度/划分的份数 就是 html font-size 的大小
- 或者： 页面元素的rem值 = 页面元素值（px） / html font-size 字体大小

