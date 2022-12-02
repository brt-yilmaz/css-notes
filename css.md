CSS from [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS?retiredLocale=de)  

To link styles.css to index.html, add the following line somewhere inside the <head> of the HTML document: 

`<link rel="stylesheet" href="styles.css" />`  

You can target multiple selectors at the same time by separating the selectors with a comma. If you want all paragraphs and all list items to be green, your rule would look like this: 

```css
p,
li {
  color: green;
}
```  

You can apply the class of special to any element on your page that you want to have the same look as this list item.  

```css
li.special,
span.special {
  color: orange;
  font-weight: bold;
}
```  
you can use a selector called the `descendant combinator`, which takes the form of a space between two other selectors.  

```css
li em {
  color: rebeccapurple;
}
```

```css
Something else you might like to try is styling a paragraph when it comes directly after a heading at the same hierarchy level in the HTML. To do so, place a `+` (an *adjacent sibling combinator*) between the selectors.

```css
h1 + p {
  font-size: 200%;
}
```  

In some circumstances, internal stylesheets can be useful. For example, perhaps you're working with a content management system where you are blocked from modifying external CSS files.  

`width: calc(90% - 30px)` the values define the width of this box to be 90% of the containing block width, minus 30 pixels.  

CSS @rules (pronounced "at-rules") provide instruction for what CSS should perform or how it should behave. Some @rules are simple with just a keyword and a value.  

