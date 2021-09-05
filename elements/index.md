---
title: Elements
layout: page
permalink: /elements.html
markdown: prose
---

The formatting elements specified by Markdown come in two basic types: there are block elements and inline elements.

**Block elements** include such things as paragraphs of text, code blocks, block quotes, lists, and tables. Headings and theme breaks (horizontal rules) are also thought of as block elements

**Inline elements** includes things like emphasis (italics) and strong emphasis (bold), links (URLs), images (image links), and code spans (inline code).

One way to keep this straight is that block elements may contain inline elements, but not the other way around.

## Block Elements

### Headers

```
## This is a Heading h2 
###### This is a Heading h6
```

## This is a Heading h2 
###### This is a Heading h6

## Lists

### Unordered

```
* Item 1
* Item 2
```

* Item 1
* Item 2

### Ordered

```
1. Item 1
  1. Item 1a
  1. Item 1b
```

1. Item 1
  1. Item 1a
  2. Item 1b

## Blockquotes

```md
> Markdown is a lightweight markup language with plain-text-formatting syntax, created in 2004 by John Gruber with Aaron Swartz.
```

> Markdown is a lightweight markup language with plain-text-formatting syntax, created in 2004 by John Gruber with Aaron Swartz.

## Tables

```md
| Left columns  | Right columns |
| ------------- |:-------------:|
| left foo      | right foo     |
| left bar      | right bar     |
```

| Left columns  | Right columns |
| ------------- |:-------------:|
| left foo      | right foo     |
| left bar      | right bar     |

## Blocks of code

``````
```js
let message = 'Hello world';
alert(message);
```
``````
 covert to markdown

`````js
let message = 'Hello world';
alert(message);
`````

## Inline Examples

|Markdown                       |Output                       |
|-------------------------------|-----------------------------|
|\*Emphasis\*                   |*Emphasis*                   |
|\*\*Strong\*\* emphasis        |**Strong** emphasis          |
|\`Code\`span                   |`Code`span                   |
|\~\~Strikethrough\~\~          |~~Strikethrough~~            |
|\*\*Strong\*\* emphasis        |**Strong** emphasis          |
|`[URL](https://shenlu89.github.io/)`|[URL](https://shenlu89.github.io)                      |
|`Autolinks <https://shenlu89.github.io>`|Autolinks <https://shenlu89.github.io>|
|`![logo]({{ site.github.url }}/assets/icon/logo.svg)` | ![logo]({{ site.github.url }}/assets/icon/logo.svg) |
|`$$y=x_1+x_2$$`                  |$$y=x_1+x_2$$             |