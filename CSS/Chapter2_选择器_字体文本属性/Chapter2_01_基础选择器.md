# 选择器的作用

选择器就是根据不同需求把不同标签选择出来。

![](../Chapter1_简介/image/Chapter1_Css简介_001_css属性规则.png)

css中一共有哪些选择器:  https://www.w3school.com.cn/cssref/css_selectors.asp

# 选择器分类

选择器分为基础选择器和复合选择器两大类。

- 基础选择器由单个选择器组成
- 基础选择器包括：标签选择器、类选择器、id 选择器和通配符选择器、

# 基础选择器总结

| 基础选择器  |                    | 作用                                                  | 特点                 | 使用情况       | 用法                        |
| ------ | ------------------ | --------------------------------------------------- | ------------------ | ---------- | ------------------------- |
| 标签选择器  | Type Selector      | 选中所有相同标签                                            | 不能差异化选择            | 较多         | `p{color:red;}`           |
| 类选择器   | class Selector     | 选出一个或多个标签                                           | 可以根据需求选择           | 较多         | `.nav {color: red;}`      |
| id 选择器 | id Selector        | 一次只能选出一个标签                                          | 一个 id 属性在页面中只能出现一次 | 一般配合 js 使用 | `#nav {color: red;}`      |
| 通配符选择器 | Universal Selector | 选择所有标签元素                                            | 选择的太多，有部分不需要       | 特殊情况使用     | `* {color: red; }`        |
| 属性线则气  | Attribute Selevtor | Selects all elements that have the given attribute. |                    |            | `[title] {color: red;  }` |

- 每个选择器都有自己的使用场景，都要掌握。
- 如果是修改样式，类选择器是使用最多的。

# 团队约定

1. 尽量少用通配符选择器 `*`。

2. 尽量少用ID选择器

3. 不使用无具体语义定义的标签选择器。

```css
/* 推荐 */
.jdc {}
li {}
p{}

/* 不推荐 */
*{}
#jdc {}
div{}   因为div 没有语义，我们尽量少用
```

# 标签选择器 Type selector

直接用 HTML 标签名作为选择器，按标签名称分类，**为页面某一类标签指定统一的 CSS 样式。**

语法

```
标签名 {
    属性1： 属性值1;
    属性2： 属性值2;
    属性3： 属性值3;
}
```

优点 标签选择器可以把某一标签全部选择出来，快速为同类型标签设置统一样式。

缺点 不能设置差异化样式，只能选择全部当前标签。

例子： 

![](.\image\Chapter_css_简单选择器_001_标签选择器_例子.png)

# 类选择器 class selector

差异化选择不同标签，单独选一个或者某个标签。

## 语法

记忆口诀：样式点定义，结构类调用

使用 `.` 号 来进行定义一个新的class 。

后面， 使用 `class` 属性来调用 class 类，

```css
.类名 {
    属性1： 属性值1;
    属性2： 属性值2;
    属性3： 属性值3;
}
```

## 注意

记忆口诀：样式点定义，结构类调用

1. 类选择器用 `.` 标识，紧跟类名。

2. 性定义的类名必须小写，使用 `-` 连接单词。
   
   1. ```css
      <style>
      .red {
          color: red;
      }
      
      .star-sing{
          color: red;
      }
      </style>
      ```

3. 不要用纯数字、中文。用英文名

4. 命名有意义。

5. 类选择器在 HTML 中以 class 属性表示，在CSS中，类选择器以一个点 . 号表示

## 类选择器-单类名

```css
// 定义一个class， 这个class将所有拥有red类HTML元素均设置为红色
<style>
.red {
    color: red;
}
</style>

//使用的时候
<div class='red'>变红色</div>
<li class='red'>来生缘</li>
```

## 类选择器-多类名

- 一个标签， 在标签的 class 属性中， 写多个类名
- 多个类名中间必须用空格分开
- 这个标签就可以分别具有这些类名的样式

```
<p class="class-name1 class-name2"></p>
```

![](.\image\Chapter_css_简单选择器_003_标签选择器_一个标签多类名.png)

## 多类名开发中使用场景

1. 可以把一些标签元素相同的样式(公共的部分)放到一个类里面
2. 这些标签都可以调用这个公共的类，然后再调用自己独有的类
3. 从而节省CSS代码，统一修改也方便

例子： 

![](.\image\Chapter_css_简单选择器_002_标签选择器_例子2.png)

# id 选择器

id 选择器可以为标有特定 id 的 HTML 元素指定特定的样式。

用 `#` 来定义id， 以 id 属性来设置 id 选择器。

用id 来调用这个样式

记忆口诀：样式 **#** 定义，结构 **id** 调用。只能调用一次，别人切勿使用

```
#id名 {
    属性1: 属性值1;
    ...
}
```

注意：id 属性只能在每个 HTML 文档中出现一次。

```css
<div id="pink">woshishui</div>
<div id="pink">woshishui</div>  // 同一个id只能调用一次， 所以这里再次出现pink是不正确的
```

## 例子

![](.\image\Chapter_css_简单选择器_004_id选择器_例子.png)

## id 选择器与类选择器的区别

1. 类选择器（class）好比人的名字，一个人可以有多个名字，同时一个名字也可以被多个人使用

2. id 选择器好比人的身份证号码，全中国是唯一的，不得重复。

3. id 选择器和类选择器最大的不同在于使用次数上

4. 类选择器在修改样式中用的最多，id 选择器一般用于页面唯一性的元素上，经常和 JavaScript 搭配使用。

# 通配符选择器 Univeral Selector

- 用 `*` 定义通配符选择器，选取页面中所有标签。对所有的标签都起作用， 不管这个标签的名字叫啥
- 通配符选择器不需要调用，自动就给所有的元素使用样式
- 特殊情况使用， 一般是用于清楚元素标签的内外边距
  - ```css
    * {
        margin: 0;
        padding: 0;
    }
    ```

语法

```
* {
    属性1: 属性值1;
    ...
}
```

```

```

例子： 

  ![](.\image\Chapter_css_简单选择器_005_通配符选择器_例子.png)

# 属性选择器 Attribute Selector

Selects all elements that have the given attribute.

Syntax: [attr] [attr=value] [attr~=value] [attr|=value] [attr^=value] [attr$=value] [attr*=value]

Example: [autoplay] will match all elements that have the autoplay attribute set (to any value).

## 例子

更多例子见 [Attribute selectors - CSS&colon; Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors)

例子1

```css
a {
  color: blue;
}

/* Internal links, beginning with "#" */
a[href^="#"] {
  background-color: gold;
}

/* Links with "example" anywhere in the URL */
a[href*="example"] {
  background-color: silver;
}

/* Links with "insensitive" anywhere in the URL,
   regardless of capitalization */
a[href*="insensitive" i] {
  color: cyan;
}

/* Links with "cAsE" anywhere in the URL,
with matching capitalization */
a[href*="cAsE" s] {
  color: pink;
}

/* Links that end in ".org" */
a[href$=".org"] {
  color: red;
}

/* Links that start with "https" and end in ".org" */
a[href^="https"][href$=".org"] {
  color: green;
}
```

```html

```
