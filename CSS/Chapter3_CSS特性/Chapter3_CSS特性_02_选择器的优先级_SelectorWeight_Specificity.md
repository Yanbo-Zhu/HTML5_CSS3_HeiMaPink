# 1 介绍

(x,x,x)

| 第一位 | Id selektor                                               |
| --- | --------------------------------------------------------- |
| 第二位 | class selektor， attribute<br> selectors，  pseudo-classes, |
| 第三位 | Type selektor                                             |

- 谁的值越大， 谁的样式就被采用
- 第一位i最重要， 只有当第一位 的值， 相等时， 才会比较第二位的值

# 2 Selector weight categories

[Specificity - CSS&colon; Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)

The selector weight categories are listed here in the order of decreasing specificity:

## 2.1 ID column

Includes only ID selectors, such as #example. 
For each ID in a matching selector, add 1-0-0 to the weight value.

## 2.2 CLASS column

Includes

-  [class selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors), such as .myClass,
- attribute selectors like [type="radio"] and [lang|="fr"],
- pseudo-classes, such as :hover, :nth-of-type(3n), and :required.

For each class, attribute selector, or pseudo-class in a matching selector, add 0-1-0 to the weight value.

## 2.3 TYPE column

Includes 

- type selectors, such as p, h1, and td, and 
- pseudo-elements like ::before, ::placeholder, and 
- all other selectors with double-colon notation. 

For each type or pseudo-element in a matching selector, add 0-0-1 to the weight value.

## 2.4 No value

Includes

- The universal selector (*) and 
- the pseudo-class :where() and its parameters 
  aren't counted when calculating the weight so their value is 0-0-0, but they do match elements. 

These selectors do not impact the specificity weight value.

Combinators, such as +, >, ~, " ", and ||, may make a selector more specific in what is selected but they don't add any value to the specificity weight.

The negation pseudo-class, [`:not()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:not), itself has no weight. Neither do the [`:is()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:is) or the [`:has()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:has) pseudo-classes. The parameters in these selectors, however, do. The values of both come from the parameter in the list of parameters that has the highest specificity. The [`:not()`, `:is()` and `:has()` exceptions](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity?retiredLocale=de#the-is-not-and-has-exceptions) are discussed below.
