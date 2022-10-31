# 1 Pseudo-classes and pseudo-elements

1. 结构伪类选择器和伪元素选择器为 css3的新特性

| 选择器          | 作用        | 特征    | 使用情况 | 隔开符号及用法                             |
| ------------ | --------- | ----- | ---- | ----------------------------------- |
| 链接 伪类选择器     | 选择不同状态的链接 | 跟链接相关 | 较多   | 重点记住`a{}`和`a:hover{}`， 因为这是实际开发中的写法 |
| :focus 伪类选择器 | 选择获得光标的表单 | 跟表单相关 | 较少   | 记住`input:focus`用法                   |

# 2 伪类选择器 Pseudo-classes

## 2.1 简介

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

## 2.2 Syntax

Like regular classes, you can chain together as many pseudo-classes as you want in a selector.

```css
selector:pseudo-class {
  property: value;
}
```

## 2.3 链接伪类

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

## 2.4 focus 伪类

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

## 2.5 结构伪类选择器

见 [Pseudo-classes - CSS&colon; Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes?retiredLocale=de) 

### 2.5.1 总结

结构伪类选择器主要根据文档结构来选择器元素，常用于根据父级选择器里面的子元素。

| 选择符                 | 简介                  |
| ------------------- | ------------------- |
| `E: first-child`    | 匹配父元素中的第一个子元素E      |
| `E: last-child`     | 匹配父元素中最后一个E元素       |
| `E: nth-child(n)`   | 匹配父元素中的第n个子元素E (重点) |
| `E: first-of-type`  | 指定类型E的第一个           |
| `E: last-of-type`   | 指定类型E的最后一个          |
| `E: nth-of-type(n)` | 指定类型E的第n个           |

```css
ul li:first-child {
    background-color: pink;
}
ul li:last-child {
    background-color: pink;
}
ul li:nth-child(5) {
    background-color: skyblue;
}
```

1. 结构伪类选择器一般用于选择父级里面的第几个孩子

2. nth-child 对父元素里面所有孩子排序选择（序号是固定的），先找到第n个孩子，然后看看是否和E匹配

3. nth-of-type 对父元素里面指定子元素进行排序选择，先去匹配E，然后再根据E找第n个孩子

4. 关于nth-child(n)， 我们要知道n是从0开始计算的，要记住常用的公式

5. 如果是无序列表，我们肯定用 nth-child 更多

6. 类选择器，属性选择器，伪类选择器，权重为10

### 2.5.2 :first-child 和E:last-child

`:first-child` 是 CSS 伪类，表示父元素的第一个子元素。

```css
<head>
    <style>
        /* 1.选择ul里面的第一个孩子 小li */

        ul li:first-child {
            background-color: pink;
        }
        /* 2.选择ul里面的最后一个孩子 小li */

        ul li:last-child {
            background-color: pink;
        }
    </style>
</head>


<body>
    <ul>
        <li>我是第1个孩子</li>
        <li>我是第2个孩子</li>
        <li>我是第3个孩子</li>
        <li>我是第4个孩子</li>
        <li>我是第5个孩子</li>
        <li>我是第6个孩子</li>
        <li>我是第7个孩子</li>
        <li>我是第8个孩子</li>
    </ul>
```

### 2.5.3 :last-child

`:last-child` CSS 伪类 代表父元素的最后一个子元素。

### 2.5.4 E:first-of-type和E:last-of-type

| E:first-of-type | 指定类型E的第一个  |
| --------------- | ---------- |
| E:last-of-type  | 指定类型E的最后一个 |

```html
<head>
    <style>
        ul li:first-of-type {
            background-color: pink;
        }

        ul li:last-of-type {
            background-color: pink;
        }

        ul li:nth-last-child(2) {
            background-color: pink;
        }
    </style>
</head>


<body>
    <ul>
        <li>我是第1个孩子</li>
        <li>我是第2个孩子</li>
        <li>我是第3个孩子</li>
        <li>我是第4个孩子</li>
        <li>我是第5个孩子</li>
        <li>我是第6个孩子</li>
        <li>我是第7个孩子</li>
        <li>我是第8个孩子</li>
    </ul>
</body>
```

### 2.5.5 :nth-child(n)

nth-child(n)选择某个父级元素的一个或多个特定的子元素（重点）

`:nth-child(an+b)` 这个 CSS 伪类首先找到所有当前元素的兄弟元素，然后按照位置先后顺序从 1 开始排序，选择的结果为 CSS 伪类 `:nth-child`括号中表达式 `(an+b)` 匹配到的元素集合 `(n=0，1，2，3...)`

- `n` 可以是整数、关键字（`even/odd`）、公式（`n/2n/2n+1`）
- n如果是数字，就是选择第n个子元素，里面数字从1开始
- n可以是关键字：**even** 偶数，**odd**奇数
- n可以是公式：常见的公式如下（如果n是公式，则从0开始计算，但是第0个元素或者超出了元素的个数会被忽略）

| 公式   | 取值          |
| ---- | ----------- |
| 2n   | 偶数          |
| 2n-1 | 奇数          |
| 5n   | 5 10 15 ... |
| n+   | 5 6 7 8 ... |
| -n+5 | 前五个         |

#### 2.5.5.1 例子

```html
<head>
    <style>
        /* 选择ul里面的第2个孩子 小li */
        ul li:nth-child(2) {
            background-color: pink;
        }
    </style>
</head>


<body>
    <ul>
        <li>我是第1个孩子</li>
        <li>我是第2个孩子</li>
        <li>我是第3个孩子</li>
        <li>我是第4个孩子</li>
        <li>我是第5个孩子</li>
        <li>我是第6个孩子</li>
        <li>我是第7个孩子</li>
        <li>我是第8个孩子</li>
    </ul>
</body>
```

```html
<style>
        /* 1.把所有的偶数 even的孩子选出来 */
        ul li:nth-child(even) {
            background-color: #ccc;
        }

        /* 2.把所有的奇数 odd的孩子选出来 */
        ul li:nth-child(odd) {
            background-color: gray;
        }
        /* 3.nth-child(n) 从0开始 每次加1 往后面计算  这里面必须是n 不能是其他的字母 选择了所有的孩子*/
        /* ol li:nth-child(n) {
            background-color: pink;
        } */
        /* 4.nth-child(2n)母选择了所有的偶数孩子 等价于 even*/
        /* ol li:nth-child(2n) {
            background-color: pink;
        }
        ol li:nth-child(2n+1) {
            background-color: skyblue;
        } */
        /* ol li:nth-child(n+3) {
            background-color: pink;
        } */
        ol li:nth-child(-n+3) {
            background-color: pink;
        }
    </style>
</head>

<body>
    <ul>
        <li>我是第1个孩子</li>
        <li>我是第2个孩子</li>
        <li>我是第3个孩子</li>
        <li>我是第4个孩子</li>
        <li>我是第5个孩子</li>
        <li>我是第6个孩子</li>
        <li>我是第7个孩子</li>
        <li>我是第8个孩子</li>
    </ul>
    <ol>
        <li>我是第1个孩子</li>
        <li>我是第2个孩子</li>
        <li>我是第3个孩子</li>
        <li>我是第4个孩子</li>
        <li>我是第5个孩子</li>
        <li>我是第6个孩子</li>
        <li>我是第7个孩子</li>
        <li>我是第8个孩子</li>
    </ol>
</body>
```

### 2.5.6 关于 `nth-of-type` 与 `nth-of-child`

1. `div: nth-child` 会把所有的盒子都排列序号 执行的时候首先看 `:nth-child(1)` 之后回去看 前面 `div`
2. `div: nth-of-type` 会把指定元素的盒子排列序号 执行的时候首先看 div指定的元素 之后回去看 `:nth-of-type(1)` 第几个孩子

区别：

1. nth-child对父元素里面所有孩子排序选择（序号是固定的）先找到第n个孩子，然后看看是否和E匹配
2. nth-of-type对父元素里面指定子元素进行排序选择。先去匹配E ，然后再根据E找第n个孩子

## 2.6 其他的伪类

### 2.6.1 :not(p)

`:not()` 用来匹配不符合一组选择器的元素。由于它的作用是防止特定的元素被选中，它也被称为反选伪类（negation pseudo-class）

## 2.7 伪类的种类

### 2.7.1 Element display state pseudo-classes

These pseudo-classes enable the selection of elements based on their display states.

`:fullscreen`： Matches an element that is currently in fullscreen mode.

`:modal`： Matches an element that is in a state in which it excludes all interaction with elements outside it until the interaction has been dismissed.

`:picture-in-picture`： Matches an element that is currently in picture-in-picture mode.

### 2.7.2 Input pseudo-classes

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

### 2.7.3 Linguistic pseudo-classes

These pseudo-classes reflect the document language and enable the selection of elements based on language or script direction.

[`:dir()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:dir)

The directionality pseudo-class selects an element based on its directionality as determined by the document language.

[`:lang()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:lang)

Select an element based on its content language.

### 2.7.4 Location pseudo-classes

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

### 2.7.5 Resource state pseudo-classes

These pseudo-classes apply to media that is capable of being in a state where it would be described as playing, such as a video.

[`:playing`](https://developer.mozilla.org/en-US/docs/Web/CSS/:playing)

Represents a media element that is capable of playing when that element is playing.

[`:paused`](https://developer.mozilla.org/en-US/docs/Web/CSS/:paused)

Represents a media element that is capable of playing when that element is paused.

### 2.7.6 Time-dimensional pseudo-classes

These pseudo-classes apply when viewing something which has timing, such as a [WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API) caption track.

[`:current`](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)

Represents the element or ancestor of the element that is being displayed.

[`:past`](https://developer.mozilla.org/en-US/docs/Web/CSS/:past)

Represents an element that occurs entirely before the [`:current`](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API) element.

[`:future`](https://developer.mozilla.org/en-US/docs/Web/CSS/:future)

Represents an element that occurs entirely after the [`:current`](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API) element.

### 2.7.7 Tree-structural pseudo-classes

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

### 2.7.8 User action pseudo-classes

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

### 2.7.9 Functional pseudo-classes

These pseudo-classes accept a [forgiving selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list#forgiving_selector_list) as a parameter.

[`:is()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:is)

The matches-any pseudo-class matches any element that matches any of the selectors in the list provided.

[`:not()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:not)

The negation, or matches-none, pseudo-class represents any element that is not represented by its argument.

[`:where()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:where)

The specificity-adjustment pseudo-class matches any element that matches any of the selectors in the list provided without adding any specificity weight.

[`:has()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:has)

The relational pseudo-class represents an element if any of the relative selectors match when anchored against the attached element.

# 3 伪元素 Pseudo-elements ( selector::pseudo-element )

[Pseudo-elements - CSS&colon; Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements?retiredLocale=de)

A CSS pseudo-element is a keyword added to a selector that lets you style a specific part of the selected element(s). 

伪元素选择器可以帮助我们利用CSS创建新标签元素，而不需要HTML标签，从而简化HTML结构。

## 3.1 注意事项

You can use<mark> only one</mark> pseudo-element in a selector. 

It must appear <mark>after the simple selectors</mark> in the statement.

## 3.2 syntax

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

## 3.3 有哪些伪元素

### 3.3.1 总览

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

### 3.3.2 `::before` 和 `::after`

| 选择符        | 简介           |
| ---------- | ------------ |
| `::before` | 在元素内部的前面插入内容 |
| `::after`  | 在元素内部的后面插入内容 |

注意：

- before 和 after 创建一个元素，但是属于行内元素
  
  - before和after 都是一个盒子，都作为父元素的孩子

- 新创建的这个元素在文档树中是找不到的，所以我们称为伪元素

- 语法：`element：before{}`

- before 和 after 必须有 content 属性

- 伪元素选择器和标签选择器一样，权重为 1

- before是放在内容的前面，after是放在了内容的后面

- before 在父元素内容的前面创建元素， after 在父元素内容的后面插入元素
  
  - ```html
    <head>
        <style>
            div {
                width: 200px;
                height: 200px;
                background-color: pink;
            }
            /* div::before 权重是2 */
            div::before {
                /* 这个content是必须要写的 */
                content: '我';
            }
    
            div::after {
                content: '小猪佩奇';
            }
        </style>
    </head>
    
    <body>
        <div>
            是
        </div>
    ```

#### 3.3.2.1 ::after (:after)

CSS 伪元素 `::after` 用来创建一个伪元素，作为已选中元素的最后一个子元素。通常会配合 `content` 属性来为该元素添加装饰内容。这个虚拟元素默认是行内元素。

```
.exciting-text::after {
  content: "<- 让人兴兴兴奋!";
  color: green;
}
```

我们几乎可以用想要的任何方法给 `content` 属性里的文字和图片的加上样式.

#### 3.3.2.2 ::before (:before)

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

### 3.3.3 例子

#### 3.3.3.1 案例一：伪元素字体图标

```
 div::after {
    position: absolute;
    top: 10px;
    right: 10px;
    font-family: 'icomoon';
    content: '\e91b';
    color: red;
    font-size: 18px;
}
```

#### 3.3.3.2 案例二：伪元素遮罩层

```
.tudou::before {
    content: '';
    display: none;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, .3) url(images/arr.png) no-repeat center;
}
```

#### 3.3.3.3 案例三：伪元素清除浮动

单伪元素清除浮动

```
.clearfix::after {
    content: '';
    display: block; 
    height: 0;
    clear: both;
    visibility: hidden;
}
```

双伪元素清除浮动

```
.clearfix::before,.clearfix::after {
    content: '';
    display: block;
}
.clearfix::after {
    clear: both;
}
```
