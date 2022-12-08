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

````css
Something
  else
  you
  might
  like
  to
  try
  is
  styling
  a
  paragraph
  when
  it
  comes
  directly
  after
  a
  heading
  at
  the
  same
  hierarchy
  level
  in
  the
  HTML.
  To
  do
  so,
place
  a
  `
  + `
  (an *adjacent sibling combinator*)
  between
  the
  selectors.
  ```css
  h1
  + p {
  font-size: 200%;
}
````

In some circumstances, internal stylesheets can be useful. For example, perhaps you're working with a content management system where you are blocked from modifying external CSS files.

`width: calc(90% - 30px)` the values define the width of this box to be 90% of the containing block width, minus 30 pixels.

CSS @rules (pronounced "at-rules") provide instruction for what CSS should perform or how it should behave. Some @rules are simple with just a keyword and a value.

Some properties like `font`, `background`, `padding`, `border`, and `margin` are called shorthand properties. This is because shorthand properties set several values in a single line.

CSS comments begin with `/*` and end with `*/`.

Inheritance also needs to be understood in this context — some CSS property values set on parent elements are inherited by their child elements, and some aren't.

Properties like `width` (as mentioned earlier), `margin`, `padding`, and `border` are not inherited properties.

CSS provides five special universal property values for controlling inheritance. Every CSS property accepts these values.

`inherit` : Sets the property value applied to a selected element to be the same as that of its parent element. Effectively, this "turns on inheritance".

`initial` : Sets the property value applied to a selected element to the initial value of that property.

`revert` : Resets the property value applied to a selected element to the browser's default styling rather than the defaults applied to that property. This value acts like unset in many cases.

`revert-layer` : Resets the property value applied to a selected element to the value established in a previous cascade layer.

`unset` : Resets the property to its natural value, which means that if the property is naturally inherited it acts like inherit, otherwise it acts like initial.

Inline styles take precedence over all author styles, no matter the layer.

If a box has an outer display type of `inline`, then:

- The `width` and `height` properties will not apply.

- _Vertical_ `padding`, `margins`, and `borders` will apply but will not cause other inline boxes to move away from the box.

- _Horizontal_ `padding`, `margins`, and `borders` will apply and will cause other inline boxes to move away from the box.

inline-size is a logical property that defines the width of an element when the writing-mode is horizontal, or the height of the element when the writing-mode is vertical.As a design choice, you might want to display vertical text on an element, say a header:

> CSS Logical Properties (search this topic later)

To use the alternative box model for all of your elements (which is a common choice among developers), set the `box-sizing` property on the `<html> `element and set all other elements to inherit that value:

```css
html {
  box-sizing: border-box;
}
*,
*::before,
*::after {
  box-sizing: inherit;
}
```

In the example below, we have two paragraphs. The topparagraph has a `margin-bottom` of 50 pixels, the other hasa `margin-top` of 30 pixels. The margins have collapsedtogether so the actual margin between the boxes is 50pixels and not the total of the two margins.

Unlike margins, you cannot have a negative padding.

Any background applied to your element will display behind the padding.

`display: inline-block` is a special value of `display`, which provides a middle ground between `inline` and `block`. Use it if you do not want an item to break onto a new line, but do want it to respect `width` and `height` and avoid the overlapping.

Where this can be useful is when you want to give a link a larger hit area by adding padding. `<a>` is an inline element like `<span>`; you can use `display: inline-block` to allow padding to be set on it, making it easier for a user to click the link.

If you specify a background color in addition to a background image then the image displays on top of the color.

`background-repeat: no-repeat` stop the background from repeating altogether.

`background-size: cover` the browser will make the image just large enough so that it completely covers the box area while still retaining its aspect ratio. In this case, part of the image is likely to end up outside the box.

`background-size: contain` the browser will make the image the right size to fit inside the box. In this case, you may end up with gaps on either side or on the top and bottom of the image, if the aspect ratio of the image is different from that of the box.

**Note**: The default background-position value is (0,0).

**Note**: background-position is a shorthand for background-position-x and background-position-y, which allow you to set the different axis position values individually.  
`background-position: top 20px right 10px;`

`background-image: linear-gradient(105deg, rgba(0,249,255,1) 39%, rgba(51,56,57,1) 96%);`

It is also possible to have multiple background images — you specify multiple `background-image` values in a single property value, separating each one with a comma.The backgrounds will layer with the last listed background image at the bottom of the stack, and each previous image stacking on top of the one that follows it in the code.

**Note**: Gradients can be mixed with regular background images.

Another option we have available for backgrounds is specifying how they scroll when the content scrolls. This is controlled using the `background-attachment` property, which can take the following values:

- `scroll`: causes the element's background to scroll when the page is scrolled. If the element content is scrolled, the background does not move. In effect, the background is fixed to the same position on the page, so it scrolls as the page scrolls.

`fixed`: causes an element's background to be fixed to the viewport so that it doesn't scroll when the page or element content is scrolled. It will always remain in the same position on the screen.

`local`: fixes the background to the element it is set on, so when you scroll the element, the background scrolls with it.

The `background-attachment` property only has an effect when there is content to scroll, so we've made a demo to demonstrate the differences between the three values — have a look at [background-attachment.html](https://mdn.github.io/learning-area/css/styling-boxes/backgrounds/background-attachment.html) (also see the [source code](https://github.com/mdn/learning-area/tree/main/css/styling-boxes/backgrounds)).

to make the top right corner have a horizontal radius of 1em, and a vertical radius of 10%:

```css
.box {
  border-top-right-radius: 1em 10%;
}
```

The `writing-mode` property lets us switch from one writing mode to another.

The three possible values for the `writing-mode` property are:

- `horizontal-tb`: Top-to-bottom block flow direction. Sentences run horizontally.
- `vertical-rl`: Right-to-left block flow direction. Sentences run vertically.
- `vertical-lr`: Left-to-right block flow direction. Sentences run vertically.

The property mapped to `width` when in a horizontal writing mode is called `inline-size` — it refers to the size in the inline dimension. The property for `height` is named `block-size` and is the size in the block dimension.

Exm:

```html
<div class="wrapper">
  <div class="box logical">
    <img src="big-star.png" alt="star" />
    <p>
      This box uses logical properties. The star image has been floated
      inline-start, it also has a margin on the inline-end and block-end.
    </p>
  </div>
</div>
```

```css
.box {
  inline-size: 200px;
  writing-mode: horizontal-tb;
}

img {
  float: inline-end;
  margin-inline-end: px;
  margin-block-end: 10px;
}
```

**Note**: Currently, only Firefox supports flow relative values for float. If you are using Google Chrome or Microsoft Edge, you may find that the image did not float.

If you are not using multiple writing modes, then for now you might prefer to use the physical versions. However, ultimately we expect that people will transition to the logical versions for most things, as they make a lot of sense once you also start dealing with layout methods such as flexbox and grid.

`overflow: visible` default
`overflow: hidden`  
`overflow: scroll`

> To just scroll on the y axis, you could use the overflow-y property, setting `overflow-y: scroll`.

`overflow: scroll hidden`

If you only want scrollbars to appear when there is more content than can fit in the box, use `overflow: auto`.

When developing a site, always keep overflow in mind.

**em** : size of the parent.  
**rem** : Font size of the root element.  
**rlh** : Line height of the root element. When used on the `font-size` or `line-height` properties of the root element, it refers to the properties' initial value.  
**vw** : 1% of the viewport's width.  
**vh** : 1% of the viewport's height.

To start with, we set 16px as the font size on the `<html>` element.

Note: Setting an alpha channel on a color has one key difference to using the opacity property we looked at earlier. When you use opacity you make the element and everything inside it opaque, whereas using RGBA colors only makes the color you are specifying opaque.

**Note**: Setting an alpha channel on a color has one key difference to using the `opacity` property we looked at earlier. When you use opacity you make the element and everything inside it opaque, whereas using RGBA colors only makes the color you are specifying opaque.

When you use margin and padding set in percentages, the value is calculated from the **inline size** of the containing block — therefore the width when working in a horizontal language.

A common use of `max-width` is to cause images to scale down if there is not enough space to display them at their intrinsic width while making sure they don't become larger than that width.

1vw = 1% of viewport width
1vh = 1% of viewport height
1vmin = 1vw or 1vh, whichever is smaller
1vmax = 1vw or 1vh, whichever is larger


