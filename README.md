# CSS-Multiple-Background-Colors
A CSS hack which enables *CSS Multiple Background Colors* in the same way that we already have *CSS Multiple Background Images*.

CSS backgrounds allow for both:

 - Background Colors via the CSS property `background-color`
 - Background Images via the CSS property `background-image`

## Multiple Background Images
The property `background-image` is not constrained to a single value. **CSS Multiple Background Images** are long established feature of CSS:

```
.myclass {
  background: background1, background2, /* … ,*/ backgroundN;
}
```

**Source:** [Using Multiple Backgrounds in CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Backgrounds_and_Borders/Using_multiple_backgrounds)

## Multiple Background Colors
But, when it comes to `background-color`, **CSS Multiple Background Colors** are not conventionally achievable.

There is, however, a hack we can take advantage of, based on... *SVG Data URIs* such as:

 - 
