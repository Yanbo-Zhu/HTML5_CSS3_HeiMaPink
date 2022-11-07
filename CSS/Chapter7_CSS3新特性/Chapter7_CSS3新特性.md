# 1 新特性 总结

![](image/Chapter7_CSS3新特性_总结_001.png)
![](image/Chapter7_CSS3新特性_总结_002.png)

# 2 CSS3 的其他特性

## 2.1 CSS3 滤镜 filter

filter CSS属性将模糊或颜色偏移等图形效果应用于元素。

```
filter: 函数();
```

例如： 
`filter： blur(5px);` blur 模糊处理数值越大越模糊

```html
<head>
   <style>
        img {
            /* blur 是一个函数，小括号里面的数值越大，图片越模糊，注意数值要加px单位 */
            filter: blur(5px);
        }
    </style>
</head>

<body>
    <img src="images/pink.jpg" alt="">
</body>
```

## 2.2 CSS3 calc函数

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

# 3 浏览器私有属性

浏览器私有前缀是为了兼容老版本的写法，比较新版本的浏览器无须添加。

1. 私有前缀
   
   - `-moz-`: 代表firefox浏览器私有属性
   - `-ms-`: 代表ie浏览器私有属性
   - `-webkit-`: 代表safari、chrome私有属性-o-∶代表Opera私有属性

2. 提倡的写法
   
   ```
   -moz-border-radius: 10px;
   -webkit-border-radius: 10px;
   -o-border-radius: 10px;
   border-radius: 10px;
   ```

# 4 属性的过渡 (transition)

过渡（transition）是CSS3中具有颠覆性的特征之一，我们可以在不使用Flash动画或JavaScript的情况下，当元素从一种样式变换为另一种样式时为元素添加效果。
过渡动画：是从一个状态渐渐的过渡到另外一个状态 可以让我们页面更好看，更动感十足，虽然低版本浏览器不支持（ie9以下版本）但是不会影响页面布局。

我们现在经常和 :hover 一起搭配使用。

## 4.1 transition 的属性
「定义」过渡transition是一个复合属性，包括transition-property、transition-duration、transition-timing-function、transition-delay这四个子属性。通过这四个子属性的配合来完成一个完整的过渡效果。

```css
transition: 要过渡的属性 花费时间 运动曲线 何时开始;

或者
transition-property: 过渡属性(默认值为all)
transition-duration: 过渡持续时间(默认值为0s)
transiton-timing-function: 过渡函数(默认值为ease函数)
transition-delay: 过渡延迟时间(默认值为0s)

```

过渡的口诀：谁做过渡给谁加
1. 属性：想要变化的css属性，宽度高度背景颜色内外边距都可以。如果想要所有的属性都变化过渡，写一个all就可以。
2. 花费时间：单位是秒（必须写单位）比如 0.5s
3. 运动曲线：默认是ease （可以省略）
   1. ![](image/Chapter7_CSS3新特性_属性的过渡_001.png)
4. 何时开始：单位是秒（必须写单位）可以设置延迟触发时间默认是Os （可以省略）

```css
.test{
    height: 100px;
    width: 100px;
    background-color: pink;
    transition-duration: 3s;
/*     以下三值为默认值，稍后会详细介绍 */
    transition-property: all;
    transition-timing-function: ease;
    transition-delay: 0s;
}    
.test:hover{
    width: 500px;
}
~~~html
<div class="test"></div>
```
### 4.1.1 过渡属性 transition-property
-   值: none | all | `<transition-property>[,<transition-property>]`
    -   none: 没有指定任何样式
    -  all: 默认值，表示指定元素所有支持transition-property属性的样式
    -  width: https://mp.weixin.qq.com/s?__biz=MzU0Mjg0MzI1Nw==&mid=2247484170&idx=1&sn=7e524ed872a5242e3cd5c9595afb7ff1&chksm=fb15cb1ccc62420a5ee1ed5735e069a63fe04512e6d219effc28d794c8a7a323cfc44e9bc325&scene=178&cur_album_id=1517142067985088512#rd
    - background: 见上面
    - width, background: 见上面 
-   初始值: all
-   应用于: 所有元素
-   继承性: 无
-   `<transition-property>`: 可过渡的样式，可用逗号分开写多个样式


### 4.1.2 过渡持续时间 transition-duration
Demo 见 https://mp.weixin.qq.com/s?__biz=MzU0Mjg0MzI1Nw==&mid=2247484170&idx=1&sn=7e524ed872a5242e3cd5c9595afb7ff1&chksm=fb15cb1ccc62420a5ee1ed5735e069a63fe04512e6d219effc28d794c8a7a323cfc44e9bc325&scene=178&cur_album_id=1517142067985088512#rd

-   值: `<time>[,<time>]*`
-   初始值: 0s
-   应用于: 所有元素
-   继承性: 无
-   [注意]该属性不能为负值
-   [注意]若该属性为0s则为默认值，若为0则为无效值。所以必须带单位
-   [注意]该值为单值时，即所有过渡属性都对应同样时间；该值为多值时，过渡属性按照顺序对应持续时间

### 4.1.3 过渡时间函数 timing-function
过渡时间函数用于定义元素过渡属性随时间变化的过渡速度变化效果

-   值: `<timing-function>[,<timing-function>]*`
-   初始值: ease
-   应用于: 所有元素
-   继承性: 无

**「取值」**:  过渡时间函数共三种取值，分别是关键字、steps函数和bezier函数
**「关键字」**: 
其实是bezier函数或steps函数的特殊值
- `ease: 开始和结束慢，中间快。  
- linear: 匀速。   
- ease-in: 开始慢。   
- ease-out: 结束慢。   
- ease-in-out: 和ease类似，但比ease幅度大。`



## 4.2 复合写法
```css
transition: 要过渡的属性 花费时间 运动曲线 何时开始;
```

- transition的这四个子属性之间不能用逗号隔开，只能用空格隔开。因为逗号隔开的代表不同的属性(transition属性支持多值，多值部分稍后介绍)；而空格隔开的代表不同属性的四个关于过渡的子属性。
- 过渡transition的这四个子属性只有transition-duration是必需且不能为0。
- transition-duration和transition-delay都是时间
    - 当两个时间同时出现时，第一个是transition-duration，第二个是transition-delay；
    - 当只有一个时间时，它是transition-duration，而transition-delay为默认值0s

### 4.2.1 例子


```css
div {
    width: 200px;
    height: 100px;
    background-color: pink;
    /* transition: width .5s, height .5s; */
    transition: all .5s;
    /*代表持续时间为2s，延迟时间为默认值0s*/  
    transition；2s;
    /*代表持续时间为1s，延迟时间为2s*/  
    transition: 1s 2s;
}
div:hover {
    width: 400px;
    height: 200px;
    background-color: skyblue;
}


=================
<div class="test"></div>

```

```css
<head>
   <style>
        div {
            width: 200px;
            height: 100px;
            background-color: pink;
            /* transition: 变化的属性 花费时间 运动曲线 何时开始; */
            /* 如果想要写多个属性，利用逗号进行分割 */
            transition: width 0.5s, height 0.5s;
            /* 如果想要多个属性都变化，属性写all就可以了 */
            transition: all 0.5s;
        }

        div:hover {
            width: 400px;
            height: 200px;
            background-color: red;
        }
    </style>
</head>

<body>
    <div></div>
</body>
```

# 5 2D 转换 transform

转换（`transform`）是 CSS3 中具有颠覆性的特征之一，可以实现元素的位移、旋转、缩放等效果。

2D转换是改变标签在二维平面上的位置和形状, 转换可以理解为变形。
- 移动：`translate`
- 旋转：`rotate`
- 缩放：`scale`

## 5.1 总结

1. 转换transform 我们简单理解就是变形 有2D 和 3D 之分
2. 我们暂且学了三个 分别是 位移 旋转 和 缩放
3. 2D 移动 translate(x, y) 最大的优势是不影响其他盒子， 里面参数用%，是相对于自身宽度和高度来计算的
4. 可以分开写比如 translateX(x) 和 translateY(y)
5. 2D 旋转 rotate(度数) 可以实现旋转元素 度数的单位是deg
6. 2D 缩放 sacle(x,y) 里面参数是数字 不跟单位 可以是小数 最大的优势 不影响其他盒子
7. 设置转换中心点 transform-origin : x y; 参数可以百分比、像素或者是方位名词
8. l当我们进行综合写法，同时有位移和其他属性的时候，记得要将位移放到最前

## 5.2 二维坐标系

![](image/Chapter7_CSS3新特性_2d转换_001_二维坐标系.png)

## 5.3 移动 translate

2D移动是2D转换里面的一种功能，可以改变元素在页面中的位置，**类似**定位。

语法

```css
transform: translate(x, y);
transform: translateX(x);
transform: translateY(y);

transform:translate(100px,100px); /* 如果只移动X轴 */ 
transform:translate(100px,0); 
translateX(100px);
```

- 参数 `x, y` 可以是百分数，为盒子自身的宽度或高度。

重点
- 定义 2D 转换中的移动，沿着X和Y轴移动元素
- translate 最大的优点：不会影响到其他元素的位置
- translate 中的百分比单位是相对于 本身元素 的宽度和高度来计算的:  `trainslate:(50%，50%)`
- 对行内标签没有效果

```css
div {
  background-color: lightseagreen;
  width: 200px;
  height: 100px;
  /* 平移 */
  /* 水平垂直移动 100px */
  /* transform: translate(100px, 100px); */

  /* 水平移动 100px */
  /* transform: translate(100px, 0) */

  /* 垂直移动 100px */
  /* transform: translate(0, 100px) */

  /* 水平移动 100px */
  /* transform: translateX(100px); */

  /* 垂直移动 100px */
  transform: translateY(100px);
  /*百分比用法*/
  transform: translateY(100%);   
}
```

### 5.3.1 让盒子实现水平和垂直居中

```css
/*子绝父相*/
position: absolute;
top: 50%;
left: 50%;
transform: translate(-50%, -50%);


========================
div {  
    position: relative;  
    width: 500px;  
    height: 500px;  
    background-color: pink;  
    /* 1. 我们tranlate里面的参数是可以用 % */  
    /* 2. 如果里面的参数是 % 移动的距离是 盒子自身的宽度或者高度来对比的 */  
    /* 这里的 50% 就是 50px 因为盒子的宽度是 100px */  
    /* transform: translateX(50%); */  
    }  
          
p {  
    position: absolute;  
    top: 50%;  
    left: 50%;  
    width: 200px;  
    height: 200px;  
    background-color: purple;  
    /1.* margin-top: -100px;  
    margin-left: -100px; */  
    
    /2.* translate(-50%, -50%)    
      盒子往上走自己高度的一半   */  
    transform: translate(-50%, -50%);  
  }  
          
span {  
    /* translate 对于行内元素是无效的 */  
    transform: translate(300px, 300px);  
     }

```




## 5.4 旋转 rotate

值为正数则顺时针旋转，为负数则逆时针旋转。

1. rotate 里面跟度数，单位是 deg 比如 rotate(45deg)
2. **角度为正时，顺时针，负时，为逆时针**
3. 默认旋转的中心点是元素的中心点

语法：

```css
transform: rotate(45deg);

/* 单位是：deg */
img:hover {
  transform: rotate(360deg)
}

```

例子：

```html
<head>
   <style>
        img {
            width: 150px;
            border-radius: 50%;
            border: 5px solid pink;
            /* 过渡写到本身，谁做动画给谁加 */
            transition: all 0.3s;
        }

        img:hover {
            transform: rotate(360deg);
        }
    </style>
</head>

<body>
    <img src="#" alt="">
</body>
```

### 5.4.1 2D转换中心点 transform-origin

我们可以通过设置 `transform-origin` 设置元素转换的中心点。

语法

```css
transform-origin: x y;
```

 重点

- 注意后面的参数 x 和 y 用空格隔开
- x y 默认转换的中心点是元素的中心点（50% 50%）
- 还可以给 x y 设置像素或者方位名词（top bottom left right center）

例子

```css
<head>
   <style>
        div {
            width: 200px;
            height: 200px;
            background-color: pink;
            margin: 100px auto;
            transition: all 1s;
            /* 1.可以跟方位名词 ,以左下角为轴进行旋转*/
            transform-origin: left bottom;
        }

        div:hover {
            transform: rotate(360deg);
        }
    </style>
</head>

<body>
    <div></div>
</body>
```

## 5.5 缩放 scale

缩放：`scale`,只要给元素添加上了这个属性就能控制它放大还是缩小

```css
 transform: scale(x, y);
```

- 注意其中的x和y用逗号分割
- sacle缩放最大的优势：
    - 不占空间. 
    - 可以设置转换中心点缩放，默认以中心点缩放的，而且不影响其他盒子
    - 可以配合 `transform-origin` 使用，改变缩放中心。

## 5.6 使用
transform: scale(1, 1): 宽高都放大一倍，相当于没有放大
transform: scale(2, 2): 宽和高都放大了二倍
transform: scale(2): 如果只写了一个参数，第二个参数就和第一个参数一致
transform:scale(0.5, 0.5): 缩小

- 参数大于 `1` 则放大，小于 `1` 则缩小。
- `x, y` 不跟单位的话，是指缩放的倍数。

  ```css
  transform: scale(2,1);

   div:hover {  
    /* 注意，数字是倍数的含义，所以不需要加单位 */  
    /* transform: scale(2, 2) */  
     
    /* 实现等比缩放，同时修改宽与高 */  
    /* transform: scale(2) */  
     
    /* 小于 1 就等于缩放*/  
    transform: scale(0.5, 0.5)  
   }

  ```


```css
<head>
   <style>
        div {
            width: 200px;
            height: 200px;
            background-color: pink;
            margin: 100px auto;
        }

        div:hover {
            /* 1.里面写的数字不跟单位 就是倍数的意思 1就是1倍，2就是2倍 */
            transform: scale(2, 2);
        }
    </style>
</head>

<body>
    <div></div>
</body>
```

## 5.7 2D 转换综合写法

注意：

1. 同时使用多个转换，其格式为： `transform: translate(), rotate() scale()`
2. 其顺序会影转换的效果。（先旋转会改变坐标轴方向）
3. 当我们同时有位移和其他属性的时候，记得要将位移放到最前.

```css
<head>   
   <style>
        div {
            width: 200px;
            height: 200px;
            background-color: pink;
            transition: all .5s;
        }

        div:hover {
            /* 我们同时有位移和其他属性，我们需要把位移放到最前面 位移，旋转，缩放*/
            transform: translate(150px, 50px) rotate(180deg) scale(1.2);
        }
    </style>
</head>

<body>
    <div></div>
</body>
```

# 6 动画 animation

动画( animation ) 是 CSS3 中具有颠覆性的特征之一，可通过设置多个节点来精确控制一个或一组动画，常用来实现复杂的动画效果。
相比较过渡，动画可以实现更多变化，更多控制，连续自动播放等效果。

## 6.1 动画的基本使用

分为两步：

1. 定义动画 (动画序列 `%α`)
2. 使用/调用动画

### 6.1.1 用keyframs定义动画

```css
 /* 1. 定义动画 */
@keyframes move {
    /*开始状态*/
    0% {
        transform: translateX(0px);
    }
    /*结束状态*/
    100% {
        transform: translateX(1000px);
    }
}
```

### 6.1.2 调用动画

```css
div {
    width: 200px;
    height: 200px;
    background-color: pink;
    /* 2. 调用动画 */
    /* 动画名称 */
    animation-name: move;
    /* 持续时间 */
    animation-duration: 5s;
}
```

### 6.1.3 动画序列

- 0% 是动画的开始，100% 是动画的完成。这样的规则就是动画序列。
- 在 @keyframes 中规定某项 CSS 样式，就能创建由当前样式逐渐改为新样式的动画效果。
- 动画是使元素从一种样式逐渐变化为另一种样式的效果。您可以改变任意多的样式任意多的次数。
- 请用百分比来规定变化发生的时间，或用关键词"from"和“to”，等同于0%和100%。

注意:

1. 可以做多个状态的变化 `keyframes` 关键帧
2. 百分比必须是整数
3. 百分比是总时间 `animation-duration` 的划分

```css
<style>  
    div {  
      width: 100px;  
      height: 100px;  
      background-color: aquamarine;  
      animation-name: move;  
      animation-duration: 0.5s;  
    }  
  
    @keyframes move{  
      0% {  
        transform: translate(0px)  
      }  
      100% {  
        transform: translate(500px, 0)  
      }  
    }  
  </style>
```

### 6.1.4 整体示例

需求：我们想页面一打开，一个盒子就从左边走到右边

```css
<head> 
   <style>
        /* 需求：我们想页面一打开，一个盒子就从左边走到右边 */
        /* 1.定义动画 */

        @keyframes move {
            /* 开始状态 */
            0% {
                transform: translateX(0px);
            }
            /* 结束状态 */
            100% {
                transform: translateX(1000px);
            }
        }

        div {
            width: 200px;
            height: 200px;
            background-color: pink;
            /* 使用动画 */
            animation-name: move;
            /* 持续时间 */
            animation-duration: 2s;
        }
    </style>
</head>

<body>
    <div></div>
</body>
```

from to 语法

```html
<head>  
   <style>
        /* 需求：我们想页面一打开，一个盒子就从左边走到右边 */
        /* 1.定义动画 */

        @keyframes move {
            from {
                transform: translate(0, 0);
            }
            to {
                transform: translate(1000px, 0);
            }
        }

        div {
            width: 200px;
            height: 200px;
            background-color: pink;
            /* 使用动画 */
            animation-name: move;
            /* 持续时间 */
            animation-duration: 2s;
        }
    </style>
</head>

<body>
    <div></div>
</body>
```

## 6.2 动画常用属性

| 属性                          | 描述                                        |
| --------------------------- | ----------------------------------------- |
| `keyframes`                 | 规定动画。                                     |
| `animation`                 | 所有动画属性的简写属性,除了animation-play-state属性。     |
| `animation-name`            | 规定@keyframes动画的名称。(必须的)                   |
| `animation-duration`        | 规定动画完成一个周期所花费的秒或毫秒，默认是0。（必须的)             |
| `animation-timing-function` | 规定动画的速度曲线，默认是“ease” .                     |
| `animation-delay`           | 规定动画何时开始，默认是0.                            |
| `animation-iteration-count` | 规定动画被播放的次数，默认是1，还有infinite                |
| `animation-direction`       | 规定动画是否在下一周期逆向播放，默认是 "normal",alternate逆播放 |
| `animation-play-state`      | 规定动画是否正在运行或暂停。默认是"running",还有"paused".    |
| `animation-fill-mode`       | 规定动画结束后状态,保持forwards回到起始backwards         |

```css
div {  
  width: 100px;  
  height: 100px;  
  background-color: aquamarine;  
  /* 动画名称 */  
  animation-name: move;  
  /* 动画花费时长 */  
  animation-duration: 2s;  
  /* 动画速度曲线 */  
  animation-timing-function: ease-in-out;  
  /* 动画等待多长时间执行 */  
  animation-delay: 2s;  
  /* 规定动画播放次数 infinite: 无限循环 */  
  animation-iteration-count: infinite;  
  /* 是否逆行播放 */  
  animation-direction: alternate;  
  /* 动画结束之后的状态 */  
  animation-fill-mode: forwards;  
}  
  
div:hover {  
  /* 规定动画是否暂停或者播放 */  
  animation-play-state: paused;  
}
```

### 6.2.1 动画简写属性

```css
animation: 动画名称 持续时间 运动曲线 何时开始 播放次数 是否反方向 动画起始或者结束的状态;
animation: myfirst 5s linear 2s infinite alternate;
```

知识要点
- 简写属性里面不包含 `animation-play-state`
- 暂停动画: `animation-play-state: puased;`
- 经常和鼠标经过等其他配合使用想要动画走回来，而不是直接跳回来: `animation-direction: alternate`
- 盒子动画结束后，停在结束位置:  `animation-fill-mode: forwards`

### 6.2.2 速度曲线细节 animation-timing-function

`animation-timing-function`：规定动画的速度曲线，默认是“ease”

| **值**       | **描述**                  |
| ----------- | ----------------------- |
| linear      | 动画从头到尾的速度是相同的。匀速        |
| ease        | 默认。动画以低速开始，然后加快，在结束前变慢。 |
| ease-in     | 动画以低速开始。                |
| ease-out    | 动画以低速结束。                |
| ease-in-out | 动画以低速开始和结束。             |
| steps()     | 指定了时间函数中的间隔数量（步长）       |

```css
/*打字机效果*/  
div {  
  width: 0px;  
  height: 50px;  
  line-height: 50px;  
  white-space: nowrap;  
  overflow: hidden;  
  background-color: aquamarine;  
  animation: move 4s steps(24) forwards;  
}  
  
@keyframes move {  
  0% {  
    width: 0px;  
  }  
  
  100% {  
    width: 480px;  
  }  
}
```

# 7 3D 转换

我们生活的环境是3D的，照片就是3D物体在2D平面呈现的例子.

3D转换的特点：

- 近大远小。
- 物体后面遮挡不可见

当我们在网页上构建3D效果的时候参考这些特点就能产出3D效果。

## 7.1 三维坐标系

三维坐标系其实就是指立体空间，立体空间是由3个轴共同组成的。
![](image/Chapter7_CSS3新特性_3d转换_001_三位坐标系.png)

- x轴：水平向右 **注意： x 右边是正值，左边是负值**
- y轴：垂直向下 **注意： y 下面是正值，上面是负值**
- z轴：垂直屏幕 **注意： 往外面是正值，往里面是负值**

## 7.2 3D 转换知识要点
3D 转换我们主要学习工作中最常用的 3D 位移 和 3D 旋转
-   `3D` 位移：`translate3d(x, y, z)`
    
-   `3D` 旋转：`rotate3d(x, y, z)`
    
-   `透视` ：`perspctive`
    
-   `3D`呈现 `transfrom-style`

## 7.3 3D位移translate3d
```css
  transform: translate3d(100px, 100px, 100px)  
  /* 注意：x, y, z 对应的值不能省略，不需要填写用 0 进行填充 */  
  transform: translate3d(100px, 100px, 0)
```

3D移动在2D移动的基础上多加了一个可以移动的方向，就是z轴方向

- translform:translateX(100px)：仅仅是在x轴上移动

- translform:translateY(100px)：仅仅是在Y轴上移动

- translform:translateZ(100px)：仅仅是在Z轴上移动（注意：translateZ一般用px单位）

- transform:translate3d(x,y,z)：其中 x、y、z 分别指要移动的轴的方向的距离
-  注意：x, y, z 对应的值不能省略，不需要填写用 0 进行填充

因为z轴是垂直屏幕，由里指向外面，所以默认是看不到元素在z轴的方向上移动

## 7.4 透视perspective

透视：在2D平面产生近大远小视觉立体，但是只是效果二维的. 如果想要在网页产生3D效果需要透视（理解成3D物体投影在2D平面内）
- 模拟人类的视觉位置，可认为安排一只眼睛去看
- 透视我们也称为视距：视距就是人的眼睛到屏幕的距离
- 距离视觉点越近的在电脑平面成像越大，越远成像越小
- 透视的单位是像素

透视写在被观察元素的父盒子上面的
![](image/Chapter7_CSS3新特性_3d转换_002_透视.png)

知识要点
- 透视需要写在被视察元素的父盒子上面
- d：就是视距，视距就是一个距离人的眼睛到屏幕的距离。
- z：就是 z轴，物体距离屏幕的距离，z轴越大（正值） 我们看到的物体就越大

### 7.4.1 perspective的语法
```css
body {
  /*透视需要写在被视察元素的父盒子上面 */
  perspective: 1000px;
}
```

### 7.4.2 translateZ
- perspecitve 给父级进行设置视距的，translateZ 给 子元素进行设置不同的大小  
- translform:translateZ(100px)：仅仅是在Z轴上移动。
-   有了透视，就能看到translateZ 引起的变化了
    -   translateZ：近大远小
    -   translateZ：往外是正值
    -   translateZ：往里是负值

## 7.5 3D旋转 rotate3d

### 7.5.1 语法
3D旋转：3D旋转指可以让元素在三维平面内沿着 x轴，y轴，z轴或者自定义轴进行旋转。
- transform: rotateX(45deg) ：沿着X轴正方向旋转45度
- transform: rotateY(45deg) ：沿着Y轴正方向旋转45度
- transform: rotateZ(45deg) ：沿着Z轴正方向旋转45度
- transform: rotate3d(x,y,z,deg) ：沿着自定义轴旋转 deg为角度(了解即可)

xyz是表示旋转轴的矢量，是标示你是否希望沿着该轴旋转，最后一个标示旋转的角度。

```css
/*沿着X轴旋转45deg*/
transform: rotate3d(1,0,0,45deg) 
/*沿着对角线旋转45deg*/
transform: rotate3d(1,1,0,45deg) 
```


### 7.5.2 rotateX: 左手准则

-   左手的手拇指指向 x轴的正方向
-   其余手指的弯曲方向就是该元素沿着x轴旋转的方向

![](image/Chapter7_CSS3新特性_3d转换_003_左手准则1.png)

```css
div {
  /*透视写在被视察元素的父盒子上面 */
  perspective: 300px;
}
/*被观察元素*/
img {
  display: block;
  margin: 100px auto;
  transition: all 1s;
}

img:hover {
  transform: rotateX(-45deg)
}
```

### 7.5.3 rotateY: 左手准则

-   左手的手拇指指向 y轴的正方向
-   其余手指的弯曲方向就是该元素沿着y轴旋转的方向（正值）
![](image/Chapter7_CSS3新特性_3d转换_004_左手准则2.png)

```css
div {  
  perspective: 500px;  
}  
  
img {  
  display: block;  
  margin: 100px auto;  
  transition: all 1s;  
}  
  
img:hover {  
  transform: rotateY(180deg)  
}
```

### 7.5.4 rotateZ
```css
div {  
  perspective: 500px;  
}  
  
img {  
  display: block;  
  margin: 100px auto;  
  transition: all 1s;  
}  
  
img:hover {  
  transform: rotateZ(180deg)
```

### 7.5.5 rotate3d
-   transform: rotate3d(x, y, z, deg) -- 沿着自定义轴旋转 deg 为角度
-   x, y, z 表示旋转轴的矢量，是标识你是否希望沿着该轴进行旋转，最后一个标识旋转的角度
    -   transform: rotate3d(1, 1, 0, 180deg) -- 沿着对角线旋转 45deg
    -   transform: rotate3d(1, 0, 0, 180deg) -- 沿着 x 轴旋转 45deg

```
div {
  perspective: 500px;
}

img {
  display: block;
  margin: 100px auto;
  transition: all 1s;
}

img:hover {
  transform: rotate3d(1, 1, 0, 180deg)
}

```4.1 鼠标样式 cursor
cursor: default | pointer | move | text | not-allowed;
Copy to clipboardErrorCopied
4.2 取消表单轮廓和文本域缩放
input {
  outline: none;
}
textarea {
  outline: none;
  resize: none;
}
Copy to clipboardErrorCopied
5. vertical-align 的应用
vertical-align 指定行内/行内块元素的元素的垂直对齐方式。

5.1 图片、表单和文字对齐 vertical-align
img {
  vertical-align: middle;
}
li {
  disaplay: inline-block;
  vertical-align: middle;
}
Copy to clipboardErrorCopied
5.2 解决图片底部默认空白缝隙问题
bug ：图片底侧会有一个空白缝隙，原因是行内块元素会和文字的基线对齐。主要解决方法有两种：

给图片添加 vertical—align: middle topl bottom; 等。（提倡使用的）
把图片转换为块级元素 display: block；



## 7.6 3D呈现transform-style


- 这个属性很重要, 控制子元素是否开启三维立体环境
- transform-style: flat 子元素不开启3d立体空间 默认的
- transform-style: preserve-3d 子元素开启立体空间
- 代码写给父级，但是影响的是子盒子

![](image/Chapter7_CSS3新特性_3d转换_005_transform-style.png)

```html
<body>  
    <div class="box">  
        <div></div>  
        <div></div>  
    </div>  
</body>
```

```css
<style>  
    body {  
        perspective: 500px;  
        }  
          
    .box {  
        position: relative;  
        width: 200px;  
        height: 200px;  
        margin: 100px auto;  
        transition: all 2s;  
        /* 让子元素保持3d立体空间环境 */  
        transform-style: preserve-3d;  
        }  
          
    .box:hover {  
        transform: rotateY(60deg);  
    }  
          
    .box div {  
        position: absolute;  
        top: 0;  
        left: 0;  
        width: 100%;  
        height: 100%;  
        background-color: pink;  
    }  
          
    .box div:last-child {  
        background-color: purple;  
        transform: rotateX(60deg);  
    }  
</style>
```