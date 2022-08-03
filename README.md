# CSS-Multiple-Background-Colors
A CSS hack which enables *CSS Multiple Background Colors* in the same way that we already have *CSS Multiple Background Images*.

CSS backgrounds allow for both:

 - Background Colors via the CSS property `background-color`
 - Background Images via the CSS property `background-image`

## Multiple Background Images
The property `background-image` is not constrained to a single value. **CSS Multiple Background Images** are long established feature of CSS:

```
.myclass {
  background-image:
    url('my-bg-image-1.png'), 
    url('my-bg-image-2.png'), 
    url('my-bg-image-3.png'),
    /* ... */
    url('my-bg-image-n.png');
}
```

**Source:** [Using Multiple Backgrounds in CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Backgrounds_and_Borders/Using_multiple_backgrounds)

## Multiple Background Colors
But, when it comes to `background-color`, **CSS Multiple Background Colors** isn't an option. Conventionally, background colors may not be combined.

There is, however, a hack we can take advantage of, based on... *SVG Data URIs*.

Normally, we declare `background-color` values using the following syntax:

 - Translucent red: `background-color:rgba(255, 0, 0, 0.5);`
 - Translucent orange: `background-color:rgba(255, 127, 0, 0.5);`
 - Translucent yellow: `background-color:rgba(255, 255, 0, 0.5);`
 - Translucent green: `background-color:rgba(0, 127, 0, 0.5);`
 - Translucent blue: `background-color:rgba(0, 0, 191, 0.5);`

These background colors may not be combined.

However, using *SVG Data URI* syntax, we can reproduce the same background colors like this:

 - Translucent red: `data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" style="background-color:rgba(255, 0, 0, 0.5);"%2F%3E`
 - Translucent orange: `data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" style="background-color:rgba(255, 127, 0, 0.5);"%2F%3E`
 - Translucent yellow: `data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" style="background-color:rgba(255, 255, 0, 0.5);"%2F%3E`
 - Translucent green: `data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" style="background-color:rgba(0, 127, 0, 0.5);"%2F%3E`
 - Translucent blue: `data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" style="background-color:rgba(0, 0, 191, 0.5);"%2F%3E`



And we *can* combine these colors, using the same **multiple background image** syntax above:

```
.myclass {
  background-image:
    url('data:image/svg+xml,%3Csvg%20xmlns="http://www.w3.org/2000/svg"%20style="background-color:rgba(255,0,0,0.5);"%2F%3E'), 
    url('data:image/svg+xml,%3Csvg%20xmlns="http://www.w3.org/2000/svg"%20style="background-color:rgba(255,127,0,0.5);"%2F%3E'), 
    url('data:image/svg+xml,%3Csvg%20xmlns="http://www.w3.org/2000/svg"%20style="background-color:rgba(255,255,0,0.5);"%2F%3E'),
    url('data:image/svg+xml,%3Csvg%20xmlns="http://www.w3.org/2000/svg"%20style="background-color:rgba(0,127,0,0.5);"%2F%3E'),
    url('data:image/svg+xml,%3Csvg%20xmlns="http://www.w3.org/2000/svg"%20style="background-color:rgba(0,0,191,0.5);"%2F%3E');
}
```
