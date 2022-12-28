# 1 复合选择器简介

复合选择器是由两个或多个基础选择器，通过不同的方式组合而成的

- 后代选择器
- 子元素选择器
- 并集选择器

这样的话复合选择器可以更准确更高效的选择目标元素（标签）

# 2 复合选择器总结

## 2.1 Grouping selectors and Combinators

| 选择器   |                             | 作用          | 特征                                           | 使用情况 | 隔开符号及用法                  |
| ----- | --------------------------- | ----------- | -------------------------------------------- | ---- | ------------------------ |
| 后代选择器 | Descendant combinator       | 用来选择后代元素    | 可以是子孙后代, 只要后代他本身的他的标签名 是与之前得定义的样式的 标签名字的是一样的 | 较多   | 符号是空格 `.nav a`           |
| 子代选择器 | Child combinator            | 选择最近一级元素    | 只能选亲儿子                                       | 较少   | 符号是大于 `.nav>p`           |
|       | General sibling combinator  |             |                                              |      | A ~ B                    |
|       | Adjacent sibling combinator |             |                                              |      | A + B                    |
|       | Column combinator           |             |                                              |      | A \|\| B                 |
| 并集选择器 | Grouping selectors          | 选择某些相同样式的元素 | 可以用于集体声明                                     | 较多   | 符号是逗号，`.nav, a， .header` |

## 2.2 Pseudo-classes and pseudo-elements

| 选择器          | 作用        | 特征    | 使用情况 | 隔开符号及用法                             |
| ------------ | --------- | ----- | ---- | ----------------------------------- |
| 链接 伪类选择器     | 选择不同状态的链接 | 跟链接相关 | 较多   | 重点记住`a{}`和`a:hover{}`， 因为这是实际开发中的写法 |
| :focus 伪类选择器 | 选择获得光标的表单 | 跟表单相关 | 较少   | 记住`input:focus`用法                   |

# 3 Grouping selectors and Combinators

## 3.1 后代选择器 （Descendant combinator： A B）

后代选择器又称为包含选择器，可以选择父元素里的子元素。

写法是将外层标签写在前面，内层标签写在后面，中间空格分开。当标签发生嵌套的时候，内层标签就成为外层标签的后代。

 **语法**

```css
元素1 元素2 { 样式声明; } 上述语法表示选择元素1里面的元素2
元素1 元素2 元素3{ 样式声明; } 上述语法表示选择元素1里面的元素2里面的与元素3

父级 子级{属性:属性值;属性:属性值;}
.class h3 {color:red;font-size:16px;}   
```

- 上述语法表示选择元素 1 里面所有的元素 2

- 元素1必须是父亲， 元素2必须是孩子

- 元素1 元素2 { 样式声明; } 上述语法表示选择元素1里面的元素2， 最终改变的是元素2的样式， 元素1的样式没有被改变
  
  - 如果有元素2 in 元素8 in 元素1， 就是 元素1-> 元素8 -> 元素2，<mark> 则在此时 这个元素2的样式也会被改变</mark>
  
  - 如果有元素3 in 元素2， 则在此时 元素3的样式也没有被改变
    
    - 在这样声明后， 元素3里面的样式才会被改变： 元素1 元素2 元素3{ 样式声明; } 

- 有时候可以省略一部分， 在定义样式的时候
  
  - ```css
    .nav ul li a {
        color: red; 
    }
    
    上面写成这样，也生效 
    .nav ul a {
        color: red; 
    }
    
    这样也生效 
    .nav a {
        color: red; 
    }
    ```

- 可以连续嵌套，比如可以是孙子等

- 元素 1、2 可以是 任意的基础标签
  
  - ![](.\image\Chapter_css_复杂选择器_后代选择器_001.png)
  - 例子 ： 这样第一组 的 ol>li 不受影响 
    - ![](.\image\Chapter_css_复杂选择器_后代选择器_002_例子2.png)
    - ![](.\image\Chapter_css_复杂选择器_后代选择器_003_例子3.png)

### 3.1.1 例子

```css
/*选择ul 里面的所有 li 标签元素*/
ul li {
    样式声明
}  
```

![](.\image\Chapter_css_复杂选择器_后代选择器_004_例子4.png)

## 3.2 亲儿子元素选择器 (Child combinator： A>B)

子元素选择器（子选择器）只能选择作为元素作为元素的最近一级子元素。简单理解就是选亲儿子。 跟孙子没有关系, 虽然孙子也用同名的标签

**语法**

```css
元素1 > 元素2 { 样式声明; }  上述语法表示选择元素1 里面的所有直接后代(子元素)元素2，例如

.class>h3 {color:red;font-size:14px;}

/*选择div里面所有最近一级 P 标签元素*/ 
div > p{
    样式声明
}
```

- 元素之间用大于号 `>` 隔开
- 1 为父级。二为子级，最终选择的是元素 2
- 元素 2 必须是亲儿子。这里的子,指的是亲儿子。不包含孙子 重孙子之类。
  - 比如有 元素1-> 元素2： 则现在这里的元素2的样式会被改变
  - 也有 元素1-> 元素8 -> 元素2， <mark>则现在这里的元素2的样式不会被改变</mark>

## 3.3 General sibling combinator （A ~ B）

The general sibling combinator (~) separates two selectors and matches all iterations of the second element, that are following the first element (though not necessarily immediately), and are children of the same parent element.

```css
/* Paragraphs that are siblings of and
   subsequent to any image */
img ~ p {
  color: red;
}
```

Syntax 

```
former_element ~ target_element { style properties }`
```

### 3.3.1 例子

[General sibling combinator - CSS&colon; Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/General_sibling_combinator)

```css
p ~ span {
  color: red;
}
```

```html
<span>This is not red.</span>
<p>Here is a paragraph.</p>
<code>Here is some code.</code>
<span>And here is a red span!</span>
<span>And this is a red span!</span>
<code>More code…</code>
<div>How are you?</div>
<p>Whatever it may be, keep smiling.</p>
<h1>Dream big</h1>
<span>And yet again this is a red span!</span>
```

## 3.4 并集选择器 (Grouping selectors: A，B)

如果某些选择器定义的相同样式，就可以利用并集选择器，可以让代码更简洁。

并集选择器（CSS选择器分组）是各个选择器通过,连接而成的，通常用于集体声明。

并集选择器可以选择多组标签，同时为他们定义相同的样式。通常用于集体声明。

- 任何形式的选择器（包括标签选择器、class类选择器 id选择器等），都可以作为并集选择器的一部分。

- 并集选择器通常用于集体声明  ，<mark>逗号</mark>隔开的，所有选择器都会执行后面样式，逗号可以理解为和的意思。<mark>最后一个选择器不需要加逗号</mark>

**语法**

```css
元素1, 元素2 { 样式声明; }
```

### 3.4.1 例子

```css
1 
表示   .one 和 p  和 #test 和 .pig li 这四个选择器都会执行颜色为红色。 通常用于集体声明。 

.one, 
p , 
#test 
.pig li {
    color: #F00;
}  


2 
/*选择  ul  和  div 标签元素 */
ul,div {
    样式声明
} 
```

![](.\image\Chapter_css_复杂选择器_并集选择器_001.png)

## 3.5 交集选择器

![](.\image\Chapter_css_复杂选择器_交集选择器_001.png)

其中第一个为标签选择器，第二个为class选择器，两个选择器之间不能有空格，如h3.special。
交集选择器是并且的意思,即...又...的意思  

交集选择器,相交的部分就是要设置属性值的标签
1,格式:
选择器1选择器2...{
    属性:值;
}
2,注意点:
(1),选择器之间没有任何的连接符号
(2),选择器可以是标签名称,也可以是id、class名称
(3),交集选择器仅仅是了解


比如：   
p.one   选择的是： 类名为 .one 的段落标签。   
div#yzh_animation  选择的是： id为 yzh_animation 的div标签。   
