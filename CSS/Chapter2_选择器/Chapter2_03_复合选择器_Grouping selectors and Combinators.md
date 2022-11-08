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
比如：   p.one   选择的是： 类名为 .one 的段落标签。   
/*用的相对来说比较少，不建议使用。*/

# 4 伪类选择器 Pseudo-classes

## 4.1 简介

- **伪类选择器**用于向某些选择器添加特殊的效果
  - 比如给链接添加特殊效果，
  - 或选择第1个，第n个元素
  - 或者鼠标放在某个上面， 这个文字会变换颜色
- 伪类选择器书写最大的特点是**用冒号(😃**表示，比如 `:hover`、`:first-child`
- 伪类选择器很多，比如有链接伪类、结构伪类，这里先记录常用的链接伪类选择器

A CSS pseudo-class is a keyword added to a selector that specifies a special state of the selected element(s). 

For example, the pseudo-class :hover can be used to select a button when a user's pointer hovers over the button and this selected button can then be styled.

```css
/* Any button over which the user's pointer is hovering */
button:hover {
  color: blue;
}
```

A pseudo-class consists of a colon (:) followed by the pseudo-class name (e.g., :hover). <mark>A functional pseudo-class also contains a pair of parenthesis to define the arguments </mark>(e.g., :dir()). The element that a pseudo-class is attached to is defined as an anchor element (e.g., button in case button:hover).

Pseudo-classes let you apply a style to an element not only in relation to the content of the document tree, but also in relation to external factors like the history of the navigator (:visited, for example), the status of its content (like :checked on certain form elements), or the position of the mouse (like :hover, which lets you know if the mouse is over an element or not).

## 4.2 Syntax

Like regular classes, you can chain together as many pseudo-classes as you want in a selector.

```css
selector:pseudo-class {
  property: value;
}
```

## 4.3 链接伪类

用于向某些选择器添加特殊的效果。写的时候，他们的顺序尽量不要颠倒,按照lvha的顺序。否则可能引起错误。

链接伪类，是利用交集选择器.

```css
a:link /*选择所有未被访问的链接， 这类链接具有什么样的样式 */
a:visited /*选择所有已被访问的链接, 就是说这个链接曾经被访问后， 变成另外一种颜色*/   
a:hover /*选择鼠标指针位于其上的链接， 鼠标放在上面后， 变成另外一种颜色*/
a:active /*选择活动链接（鼠标按下未弹起的链接的时候， 这个 链接具有什么样的样式）*/
```

**注意事项**

1. 确保样式生效，要按照 LVHA 的顺序声明：link,visited,hover, active。不按照这个顺序， 样式 则就没有效果了 
   1. 短语： love hate 或者 lv 抱抱 hao 
2. a 链接在浏览器中有默认样式，所以实际开发都需要给链接单独指定样式。
   - 只给body 定义样式， 不会影响到 a 的样式， 需要单独给 a 定义样式 
   1. ![](.\image\Chapter_css_复杂选择器_链接伪类选择器_002.png)

**开发中实际写法**

实际工作中，很少写全四个状态，一般写法如下：

```css
1 
a {
  color: gray;
  text-decoration: none;
}
a:hover {
  color: #369;
  text-decoration: underline;
}
========
2 

a {   /* a是标签选择器  所有的链接 */
   font-weight: 700;
   font-size: 16px;
   color: gray;
      text-decoration: none; /* 清除链接默认的下划线*/
}
a:hover {   /* :hover 是链接伪类选择器 鼠标经过 */
   color: red; /*  鼠标经过的时候，由原来的 灰色 变成了红色 */
}

====
3 


/* a是标签选择器 */
a {
    color:gray;
}

/* :hover 是链接伪类选择器，鼠标经过 */
a :hover {
    /*鼠标经过的时候，由原来的灰色  变成了红色*/
   color:red; 
}
```

例子

![](.\image\Chapter_css_复杂选择器_链接伪类选择器_001.png)

## 4.4 focus 伪类

`:focus` 伪类选择器用于获取焦点的表单元素。 

焦点就是光标，一般情况 `<input>` 类表单元素才能获取，因此这个选择器也主要针对表单元素来说。

点击第三个表单， 这个表单上面就有光标了，并且被框起来  这就是 这个选择起的效果 . 

谁获得了贯标， 会就是更改他本身的样式 

![](.\image\Chapter_css_复杂选择器_focus伪类选择器_001.png)

语法： 

```
input:focus {
  background-color: yellow;
}
```

例子

![](.\image\Chapter_css_复杂选择器_focus伪类选择器_002.png)

## 4.5 重要的伪类

见 [Pseudo-classes - CSS&colon; Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes?retiredLocale=de) 

### 4.5.1 :first-child

`:first-child` 是 CSS 伪类，表示父元素的第一个子元素。

### 4.5.2 :last-child

`:last-child` CSS 伪类 代表父元素的最后一个子元素。

### 4.5.3 :nth-child(n)

`:nth-child(an+b)` 这个 CSS 伪类首先找到所有当前元素的兄弟元素，然后按照位置先后顺序从 1 开始排序，选择的结果为 CSS 伪类 `:nth-child`括号中表达式 `(an+b)` 匹配到的元素集合 `(n=0，1，2，3...)`

### 4.5.4 :not(p)

`:not()` 用来匹配不符合一组选择器的元素。由于它的作用是防止特定的元素被选中，它也被称为反选伪类（negation pseudo-class）

## 4.6 伪类的种类

### 4.6.1 Element display state pseudo-classes

These pseudo-classes enable the selection of elements based on their display states.

`:fullscreen`： Matches an element that is currently in fullscreen mode.

`:modal`： Matches an element that is in a state in which it excludes all interaction with elements outside it until the interaction has been dismissed.

`:picture-in-picture`： Matches an element that is currently in picture-in-picture mode.

### 4.6.2 Input pseudo-classes

These pseudo-classes relate to form elements, and enable selecting elements based on HTML attributes and the state that the field is in before and after interaction.

`:autofill`: Matches when an `<input>` has been autofilled by the browser.

`:enabled`: Represents a user interface element that is in an enabled state.

`:disabled`: Represents a user interface element that is in a disabled state.

`:read-only`: Represents any element that cannot be changed by the user.

`:read-write`: Represents any element that is user-editable.

`:placeholder-shown`: Matches an input element that is displaying placeholder text. For example, it will match the `placeholder` attribute in the `<input>` and `<textarea>` elements.

`:default`: Matches one or more UI elements that are the default among a set of elements.

[`:checked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:checked)

Matches when elements such as checkboxes and radio buttons are toggled on.

[`:indeterminate`](https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate)

Matches UI elements when they are in an indeterminate state.

[`:blank`](https://developer.mozilla.org/en-US/docs/Web/CSS/:blank)

Matches a user-input element which is empty, containing an empty string or other null input.

[`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid)

Matches an element with valid contents. For example, an input element with the type 'email' that contains a validly formed email address or an empty value if the control is not required.

[`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)

Matches an element with invalid contents. For example, an input element with type 'email' with a name entered.

[`:in-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:in-range)

Applies to elements with range limitations. For example, a slider control when the selected value is in the allowed range.

[`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)

Applies to elements with range limitations. For example, a slider control when the selected value is outside the allowed range.

[`:required`](https://developer.mozilla.org/en-US/docs/Web/CSS/:required)

Matches when a form element is required.

[`:optional`](https://developer.mozilla.org/en-US/docs/Web/CSS/:optional)

Matches when a form element is optional.

[`:user-invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:user-invalid)

Represents an element with incorrect input, but only when the user has interacted with it.

### 4.6.3 Linguistic pseudo-classes

These pseudo-classes reflect the document language and enable the selection of elements based on language or script direction.

[`:dir()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:dir)

The directionality pseudo-class selects an element based on its directionality as determined by the document language.

[`:lang()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:lang)

Select an element based on its content language.

### 4.6.4 Location pseudo-classes

These pseudo-classes relate to links, and to targeted elements within the current document.

[`:any-link`](https://developer.mozilla.org/en-US/docs/Web/CSS/:any-link)

Matches an element if the element would match either [`:link`](https://developer.mozilla.org/en-US/docs/Web/CSS/:link) or [`:visited`](https://developer.mozilla.org/en-US/docs/Web/CSS/:visited).

[`:link`](https://developer.mozilla.org/en-US/docs/Web/CSS/:link)

Matches links that have not yet been visited.

[`:visited`](https://developer.mozilla.org/en-US/docs/Web/CSS/:visited)

Matches links that have been visited.

[`:local-link`](https://developer.mozilla.org/en-US/docs/Web/CSS/:local-link)

Matches links whose absolute URL is the same as the target URL. For example, anchor links to the same page.

[`:target`](https://developer.mozilla.org/en-US/docs/Web/CSS/:target)

Matches the element which is the target of the document URL.

[`:target-within`](https://developer.mozilla.org/en-US/docs/Web/CSS/:target-within)

Matches elements which are the target of the document URL, but also elements which have a descendant which is the target of the document URL.

[`:scope`](https://developer.mozilla.org/en-US/docs/Web/CSS/:scope)

Represents elements that are a reference point for selectors to match against.

### 4.6.5 Resource state pseudo-classes

These pseudo-classes apply to media that is capable of being in a state where it would be described as playing, such as a video.

[`:playing`](https://developer.mozilla.org/en-US/docs/Web/CSS/:playing)

Represents a media element that is capable of playing when that element is playing.

[`:paused`](https://developer.mozilla.org/en-US/docs/Web/CSS/:paused)

Represents a media element that is capable of playing when that element is paused.

### 4.6.6 Time-dimensional pseudo-classes

These pseudo-classes apply when viewing something which has timing, such as a [WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API) caption track.

[`:current`](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)

Represents the element or ancestor of the element that is being displayed.

[`:past`](https://developer.mozilla.org/en-US/docs/Web/CSS/:past)

Represents an element that occurs entirely before the [`:current`](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API) element.

[`:future`](https://developer.mozilla.org/en-US/docs/Web/CSS/:future)

Represents an element that occurs entirely after the [`:current`](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API) element.

### 4.6.7 Tree-structural pseudo-classes

These pseudo-classes relate to the location of an element within the document tree.

[`:root`](https://developer.mozilla.org/en-US/docs/Web/CSS/:root)

Represents an element that is the root of the document. In HTML this is usually the `<html>` element.

[`:empty`](https://developer.mozilla.org/en-US/docs/Web/CSS/:empty)

Represents an element with no children other than white-space characters.

[`:nth-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child)

Uses `An+B` notation to select elements from a list of sibling elements.

[`:nth-last-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-last-child)

Uses `An+B` notation to select elements from a list of sibling elements, counting backwards from the end of the list.

[`:first-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:first-child)

Matches an element that is the first of its siblings.

[`:last-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:last-child)

Matches an element that is the last of its siblings.

[`:only-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:only-child)

Matches an element that has no siblings. For example, a list item with no other list items in that list.

[`:nth-of-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-of-type)

Uses `An+B` notation to select elements from a list of sibling elements that match a certain type from a list of sibling elements.

[`:nth-last-of-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-last-of-type)

Uses `An+B` notation to select elements from a list of sibling elements that match a certain type from a list of sibling elements counting backwards from the end of the list.

[`:first-of-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/:first-of-type)

Matches an element that is the first of its siblings, and also matches a certain type selector.

[`:last-of-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/:last-of-type)

Matches an element that is the last of its siblings, and also matches a certain type selector.

[`:only-of-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/:only-of-type)

Matches an element that has no siblings of the chosen type selector.

### 4.6.8 User action pseudo-classes

These pseudo-classes require some interaction by the user in order for them to apply, such as holding a mouse pointer over an element.

[`:hover`](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover)

Matches when a user designates an item with a pointing device, such as holding the mouse pointer over the item.

[`:active`](https://developer.mozilla.org/en-US/docs/Web/CSS/:active)

Matches when an item is being activated by the user. For example, when the item is clicked on.

[`:focus`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus)

Matches when an element has focus.

[`:focus-visible`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-visible)

Matches when an element has focus and the user agent identifies that the element should be visibly focused.

[`:focus-within`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-within)

Matches an element to which [`:focus`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus) applies, plus any element that has a descendant to which [`:focus`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus) applies.

### 4.6.9 Functional pseudo-classes

These pseudo-classes accept a [forgiving selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list#forgiving_selector_list) as a parameter.

[`:is()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:is)

The matches-any pseudo-class matches any element that matches any of the selectors in the list provided.

[`:not()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:not)

The negation, or matches-none, pseudo-class represents any element that is not represented by its argument.

[`:where()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:where)

The specificity-adjustment pseudo-class matches any element that matches any of the selectors in the list provided without adding any specificity weight.

[`:has()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:has)

The relational pseudo-class represents an element if any of the relative selectors match when anchored against the attached element.

# 5 伪元素 Pseudo-elements ( selector::pseudo-element )

[Pseudo-elements - CSS&colon; Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements?retiredLocale=de)

A CSS pseudo-element is a keyword added to a selector that lets you style a specific part of the selected element(s). 

## 5.1 注意事项

You can use<mark> only one</mark> pseudo-element in a selector. 

It must appear <mark>after the simple selectors</mark> in the statement.

## 5.2 syntax

```css
selector::pseudo-element {
  property: value;
}
```

For example, ::first-line can be used to change the font of the first line of a paragraph.

```css
/* The first line of every <p> element. */
p::first-line {
  color: blue;
  text-transform: uppercase;
}
```

## 5.3 有哪些伪元素

### 5.3.1 总览

A

- [`::after`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after)

B

- [`::backdrop`](https://developer.mozilla.org/en-US/docs/Web/CSS/::backdrop)
- [`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before)

C

- [`::cue`](https://developer.mozilla.org/en-US/docs/Web/CSS/::cue)
- [`::cue-region`](https://developer.mozilla.org/en-US/docs/Web/CSS/::cue-region)

F

- [`::first-letter`](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-letter)
- [`::first-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-line)
- [`::file-selector-button`](https://developer.mozilla.org/en-US/docs/Web/CSS/::file-selector-button)

G

- [`::grammar-error`](https://developer.mozilla.org/en-US/docs/Web/CSS/::grammar-error) Experimental

M

- [`::marker`](https://developer.mozilla.org/en-US/docs/Web/CSS/::marker)

P

- [`::part()`](https://developer.mozilla.org/en-US/docs/Web/CSS/::part)
- [`::placeholder`](https://developer.mozilla.org/en-US/docs/Web/CSS/::placeholder)

S

- [`::selection`](https://developer.mozilla.org/en-US/docs/Web/CSS/::selection)
- [`::slotted()`](https://developer.mozilla.org/en-US/docs/Web/CSS/::slotted)
- [`::spelling-error`](https://developer.mozilla.org/en-US/docs/Web/CSS/::spelling-error) Experimental

T

- [`::target-text`](https://developer.mozilla.org/en-US/docs/Web/CSS/::target-text) Experimental

### 5.3.2 ::after (:after)

CSS 伪元素 `::after` 用来创建一个伪元素，作为已选中元素的最后一个子元素。通常会配合 `content` 属性来为该元素添加装饰内容。这个虚拟元素默认是行内元素。

```
.exciting-text::after {
  content: "<- 让人兴兴兴奋!";
  color: green;
}
```

我们几乎可以用想要的任何方法给 `content` 属性里的文字和图片的加上样式.

### 5.3.3 ::before (:before)

CSS 中，`::before` 创建一个伪元素，其将成为匹配选中的元素的第一个子元素。常通过 `content` 属性来为一个元素添加修饰性的内容。此元素默认为行内元素。 使用 `::before` 伪元素的一个简单示例就是用于加入引号。

HTML

```html
<q>一些引用</q>, 他说, <q>比没有好。</q>.
```

CSS

```css
q::before {
  content: "«";
  color: blue;
}
q::after {
  content: "»";
  color: red;
}
```
