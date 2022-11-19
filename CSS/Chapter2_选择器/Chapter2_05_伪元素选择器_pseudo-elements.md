# 1 伪元素 Pseudo-elements ( selector::pseudo-element ) 总览 

[Pseudo-elements - CSS&colon; Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements?retiredLocale=de)

A CSS pseudo-element is a keyword added to a selector that lets you style a specific part of the selected element(s). 

伪元素选择器可以帮助我们利用CSS创建新标签元素，而不需要HTML标签，从而简化HTML结构。

# 2 注意事项

You can use<mark> only one</mark> pseudo-element in a selector. 

It must appear <mark>after the simple selectors</mark> in the statement.

# 3 syntax

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

# 4 有哪些伪元素

## 4.1 总览

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

## 4.2 `::before` 和 `::after`

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
  
```html
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

### 4.2.1 ::after 

CSS 伪元素 `::after` 用来创建一个伪元素，作为已选中元素的最后一个子元素。
通常会配合 `content` 属性来为该元素添加装饰内容。
这个虚拟元素默认是行内元素。

```
.exciting-text::after {
  content: " 让人兴兴兴奋!";
  color: green;
}
```

我们几乎可以用想要的任何方法给 `content` 属性里的文字和图片的加上样式.

### 4.2.2 ::before 

CSS 中，`::before` 创建一个伪元素，其将成为匹配选中的元素的第一个子元素。
常通过 `content` 属性来为一个元素添加修饰性的内容。
此元素默认为行内元素。 
使用 `::before` 伪元素的一个简单示例就是用于加入引号。

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
### 4.2.3 例子
#### 4.2.3.1 例子杂
```css
<style>  
    div {  
      width: 100px;  
      height: 100px;  
      border: 1px solid lightcoral;  
    }  
  
    div::after,  
    div::before {  
      width: 20px;  
      height: 50px;  
      text-align: center;  
      display: inline-block;  
    }  
    div::after {  
      content: '德';  
      background-color: lightskyblue;  
    }  
  
    div::before {  
      content: '道';  
      background-color: mediumaquamarine;  
    }  
  </style>
```

#### 4.2.3.2 伪元素字体图标

```css
p {  
   position: relative;  
   width: 220px;  
   height: 22px;  
   border: 1px solid lightseagreen;  
   margin: 60px;  
  
}  
p::after {  
  content: '\ea50';  
  font-family: 'icomoon';  
  position: absolute;  
  top: -1px;  
  right: 10px;  
}
```

#### 4.2.3.3 案例一：伪元素字体图标

```css
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

#### 4.2.3.4 案例二：伪元素遮罩层

```css
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

#### 4.2.4 案例三：伪元素清除浮动

单伪元素清除浮动

```css
.clearfix::after {
    content: '';
    display: block; 
    height: 0;
    clear: both;
    visibility: hidden;
}
```

双伪元素清除浮动

```css
.clearfix::before,.clearfix::after {
    content: '';
    display: block;
}
.clearfix::after {
    clear: both;
}
```
