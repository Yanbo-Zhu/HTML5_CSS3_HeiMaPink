# 

# 选择器分类

https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors?retiredLocale=de#combinators

CSS selectors can be grouped into the following categories based on the type of elements they can select.

## Basic selectors

### Universal selector ( *{color: red; } )

Selects all elements. Optionally, it may be restricted to a specific namespace or to all namespaces.

**Syntax:** `*` `ns|*` `*|*`

**Example:** `*` will match all the elements of the document.

### Type selector ( elementname {color: red; })

Selects all elements that have the given node name.

**Syntax:** `elementname`

**Example:** `input` will match any [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element.

### Class selector (.classname {color: red; } )

Selects all elements that have the given `class` attribute.

**Syntax:** `.classname`

**Example:** `.index` will match any element that has `class="index"`.

### ID selector ( #nav {color: red;} )

Selects an element based on the value of its `id` attribute. There should be only one element with a given ID in a document.

**Syntax:** `#idname`

**Example:** `#toc` will match the element that has `id="toc"`.

### Attribute selector ( [title] {color: red; } )

Selects all elements that have the given attribute.

**Syntax:** `[attr]` `[attr=value]` `[attr~=value]` `[attr|=value]` `[attr^=value]` `[attr$=value]` `[attr*=value]`

**Example:** `[autoplay]` will match all elements that have the `autoplay` attribute set (to any value).

## Grouping selectors

### Selector list ( SelectorA, SelectorB )

The `,` selector is a grouping method that selects all the matching nodes.

**Syntax:** `A, B`

**Example:** `div, span` will match both [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) and [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) elements.

## Combinators

### Descendant combinator  ( SelectorA SelectorB )

The " " (space) combinator selects nodes that are descendants of the first element.

**Syntax:** `A B`

**Example:** `div span` will match all [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) elements that are inside a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) element.

### Child combinator ( SelectorA > SelectorB )

The `>` combinator selects nodes that are direct children of the first element.

**Syntax:** `A > B`

**Example:** `ul > li` will match all [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li) elements that are nested directly inside a [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) element.

### General sibling combinator ( SelectorA ~ SelectorB )

The `~` combinator selects siblings. This means that the second element follows the first (though not necessarily immediately), and both share the same parent.

**Syntax:** `A ~ B`

**Example:** `p ~ span` will match all [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) elements that follow a [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p), immediately or not.

### Adjacent sibling combinator ( SelectorA + SelectorB )

The `+` combinator matches the second element only if it *immediately* follows the first element.

**Syntax:** `A + B`

**Example:** `h2 + p` will match the first [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) element that *immediately* follow an [`<h2>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) element.

### Column combinator ( SelectorA || SelectorB )

The `||` combinator selects nodes which belong to a column.

**Syntax:** `A || B`

**Example:** `col || td` will match all [`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td) elements that belong to the scope of the [`<col>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col).

## Pseudo-classes and pseudo-elements

### Pseudo classes (a:visited)

The `:` pseudo allow the selection of elements based on state information that is not contained in the document tree.

**Example:** `a:visited` will match all [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) elements that have been visited by the user.

### Pseudo elements (`p::first-line)

The `::` pseudo represent entities that are not included in HTML.

**Example:** `p::first-line` will match the first line of all [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) elements.

# Structure of a selector

https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors?retiredLocale=de#combinators

## Simple selector

A selector with a single component, such as a single id selector or type selector, that's not used in combination with or contains any other selector component or combinator. A given element is said to match a simple selector when that simple selector accurately describes the element. All [basic selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors?retiredLocale=de#basic_selectors), attributes, and single [pseudo-classes and pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors?retiredLocale=de#pseudo-classes_and_pseudo-elements) are simple selectors.

## Compound selector

A sequence of [simple selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors?retiredLocale=de#simple_selector) that are not separated by a [combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors?retiredLocale=de#combinators). A compound selector represents a set of simultaneous conditions on a single element. A given element is said to match a compound selector when the element matches all the simple selectors in the compound selector.

In a compound selector, the [type selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Type_selectors) or a [universal selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors) in a compound selector must come first in the sequence of selectors. Only one type selector or universal selector is allowed in the sequence. Since whitespace represents the [descendant combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Descendant_combinator), no whitespace is allowed between the simple selectors in a compound selector.

**Example:** `a#selected {...}`

## Complex selector

A sequence of one or more simple and/or [compound selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors?retiredLocale=de#compound_selector) that are separated by [combinators](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors?retiredLocale=de#combinators). A complex selector represents a set of simultaneous conditions on a set of elements. These conditions apply in the context of relationships described by the combinators. A given element is said to match a complex selector when the element matches compound selectors and the combinators between the compound selectors.

**Examples:** `a#selected > .icon {...}`, `.box h2 + p {...}`, `a .icon {...}`

## Relative selector

A selector that represents an element relative to one or more [anchor elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) preceded by a combinator. Relative selectors that don't begin with an explicit [combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors?retiredLocale=de#combinators) have an implied [descendant combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Descendant_combinator).

**Examples:** `+ div#topic > #reference {...}`, `> .icon {...}`

## Selector list

A comma-separated list of [simple](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors?retiredLocale=de#simple_selector), [compound](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors?retiredLocale=de#compound_selector), or [complex](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors?retiredLocale=de#complex_selector) selectors. If the constituent selector type of a selector list is important but unspecified, it is called a *complex selector list*. A given element is said to match a selector list when the element matches any (at least one) of the selectors in that selector list. Read more about when a selector list is deemed [invalid](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list#invalid_selector_list) and how to construct a [forgiving selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list#forgiving_selector_list).

**Example:** `#main, article.heading {...}`
