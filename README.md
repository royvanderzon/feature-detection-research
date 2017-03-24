# Feature Detection & Accessibility
## HTML - Responsive images

With the img tag `srcset=""` it is possible to render a specific image.

### Fallback
In the `picture` element has to be an `img` at the bottom. Like this:

```
<picture>
    <source srcset="1.jpg" media="(max-width: 200px)">
    <source srcset="2.jpg" media="(max-width: 500px)">
    <img src="3.jpg" alt="Responsive image"> <!-- FALLBACK -->
</picture>
```

The first mathing image will be rendered. When none images are correct, 
the `img` will be rendered.

## HTML - Datalist

With the datalist tag it is possible to autocomplete an input field with the usabillity of an selectbox.

### Fallback
You can use vanilla JS solutions to give the user an autocomplete experiance. Example: https://goodies.pixabay.com/javascript/auto-complete/demo.html 
