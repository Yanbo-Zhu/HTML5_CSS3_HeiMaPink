伪类选择器和伪元素选择器为 css3的新特性

# 1 伪类选择器 Pseudo-class

| 选择器          | 作用        | 特征    | 使用情况 | 隔开符号及用法                             |
| ------------ | --------- | ----- | ---- | ----------------------------------- |
| 链接 伪类选择器     | 选择不同状态的链接 | 跟链接相关 | 较多   | 重点记住`a{}`和`a:hover{}`， 因为这是实际开发中的写法 |
| :focus 伪类选择器 | 选择获得光标的表单 | 跟表单相关 | 较少   | 记住`input:focus`用法                   |

# 2 简介

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

# 3 Syntax

Like regular classes, you can chain together as many pseudo-classes as you want in a selector.

```css
selector:pseudo-class {
  property: value;
}
```

# 4 伪类的种类

## 4.1 Element display state pseudo-classes

These pseudo-classes enable the selection of elements based on their display states.

`:fullscreen`： Matches an element that is currently in fullscreen mode.

`:modal`： Matches an element that is in a state in which it excludes all interaction with elements outside it until the interaction has been dismissed.

`:picture-in-picture`： Matches an element that is currently in picture-in-picture mode.

## 4.2 Input pseudo-classes

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

## 4.3 Linguistic pseudo-classes

These pseudo-classes reflect the document language and enable the selection of elements based on language or script direction.

[`:dir()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:dir)

The directionality pseudo-class selects an element based on its directionality as determined by the document language.

[`:lang()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:lang)

Select an element based on its content language.

## 4.4 Location pseudo-classes

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

## 4.5 Resource state pseudo-classes

These pseudo-classes apply to media that is capable of being in a state where it would be described as playing, such as a video.

[`:playing`](https://developer.mozilla.org/en-US/docs/Web/CSS/:playing)

Represents a media element that is capable of playing when that element is playing.

[`:paused`](https://developer.mozilla.org/en-US/docs/Web/CSS/:paused)

Represents a media element that is capable of playing when that element is paused.

## 4.6 Time-dimensional pseudo-classes

These pseudo-classes apply when viewing something which has timing, such as a [WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API) caption track.

[`:current`](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)

Represents the element or ancestor of the element that is being displayed.

[`:past`](https://developer.mozilla.org/en-US/docs/Web/CSS/:past)

Represents an element that occurs entirely before the [`:current`](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API) element.

[`:future`](https://developer.mozilla.org/en-US/docs/Web/CSS/:future)

Represents an element that occurs entirely after the [`:current`](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API) element.

## 4.7 Tree-structural pseudo-classes

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

## 4.8 User action pseudo-classes

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

## 4.9 Functional pseudo-classes

These pseudo-classes accept a [forgiving selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list#forgiving_selector_list) as a parameter.

[`:is()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:is)

The matches-any pseudo-class matches any element that matches any of the selectors in the list provided.

[`:not()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:not)

The negation, or matches-none, pseudo-class represents any element that is not represented by its argument.

[`:where()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:where)

The specificity-adjustment pseudo-class matches any element that matches any of the selectors in the list provided without adding any specificity weight.

[`:has()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:has)

The relational pseudo-class represents an element if any of the relative selectors match when anchored against the attached element.


