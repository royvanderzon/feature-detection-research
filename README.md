# Feature Detection & Accessibility
## HTML - Source

With the img tag `srcset=""` it is possible to render a specific image. The `media=""` attribute takes a query. `min` and `max` width are both allowed. The fallback is the last `img` tag. This way the user gets images based on his client width. If a bigger image is rendered and the user changes the client width the bigger image will stay. The small image won't be renderd.

The pageload will be much smaller for mobile devices.

### Demo
https://royvanderzon.github.io/feature-detection-research/html-responsiveimages.html

### Can I use?
http://caniuse.com/#search=srcset
**Global 86.03%**

Only `IE` and `opera mini` doens't support this attribute. But you should always use this because the fallback on the image works 100% everywhere.

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

With the datalist tag it is possible to autocomplete an input field with the usabillity of an selectbox. There are many frameworks like Angular or React. They provide live searches. In some cases this is important, but in some cases there is no need for an API call after every keypress. With the HTML datalist you can still get an nice live search! Made with pure html.

### Demo
https://royvanderzon.github.io/feature-detection-research/html-datalist.html

### Can I use?
http://caniuse.com/#search=Datalist
**Global 79.67%**

You could use this datalist, the only unsupported browsers are `Safari`, `Opera mini` and `IOS Safari`. It will work like an regular input field here. So a callback is not needed. With feature detection you can add this functionality.

### Fallback
You can use vanilla JS solutions to give the user an autocomplete experiance. Example: https://goodies.pixabay.com/javascript/auto-complete/demo.html 

## CSS - GRID

CCS Grid is a new CSS feature for GRID layout. With this grid you can position your components on a whole new way. The support is pretty bad, but it will we implemented in production soon. It is nice to build your website with grid css and when the browser of the user updates with the grid css it will work directly. It is important to build the website with css grid first and then rebuild it without. The fallback explains how.

### Demo
https://royvanderzon.github.io/feature-detection-research/css-grid.html

### Can I use?
http://caniuse.com/#search=grid
**Global 6.28%**

If you use this css property it is very important to keep in mind that this isn't supported very good. You have to rebuild it with normal css after the grid css works. Flexbox is recommended.

### Fallback
Before the GRID property define another grid property like flexbox. In this way if GRID is not supported, the fallback is on flexbox.
Example:
```
.wrapper{
    display: flex;
    display: grid;
}
```

## CSS - Variables

With CSS variables you can define colors once. Task runners like `gulp` and `grunt` have this option to. The only thing is that this variables are not reachable with `javascript`. This native variables are the way to go! It is supported but not very well. With `@import(./theme_colors.css)` you could divide your css files like in the task runners. It will give more structured css files.

### Demo
https://royvanderzon.github.io/feature-detection-research/css-variables.html

### Can I use?
http://caniuse.com/#search=Variables
**Global 69.62%**

You should use it if you manipulate the css very often. It will make you code cleaner, more readable and faster. Keep in mind that you always have to define a callback.

### Fallback
If u use CSS variables define the color before the actual use of it. When the variable is not supported, the fallback will be the color before the used property.
Example:
```
.red {
    color: red;
    color: var(--theme-red);
}
```

## JS - Navigator

With the native `Navigator` function you can get the current coordinates of the users device. This `navigator.geolocation` function is often used to get the coordinates of the user. The coordinates are based on the GPS or the network where the user is browsing. This function is supported everywhere exept in `opera mini`. This is why you need a fallback. Why not __ask__ the user his location? It is nice to have this automated but the only thing it does is get the current location.

### Demo
https://royvanderzon.github.io/feature-detection-research/js-navigator.html

### Can I use?
http://caniuse.com/#search=geolocation
**Global 94.49%**

You should use this defenitely, but keep in mind that travelers (that use opera mini) cannot get their current location. So always have this fallback.

### Fallback
By checkking of the `navigator.geolocation` object exists you can verify if the function works. If the functions doesn't work, you can ask the user for his/her location!

Example:
```
var supports_navigator = function(){
    return navigator.geolocation;
}
supports_navigator() //returns true in Chrome +55
```

## JS - Api

With an library you can add extra content to your website. It is important that when Javascript is disabled or doesn't work the browser can still contains content. If there is content in the HTML tag it will be overwritten by JS. So in many cases there are empty div's on a page. This is perfect for if JS doesn't work! So place usefull content in div's. Or you could always say: `<p>Please try again, something went wrong..</p>`.

The maps library uses many different native functions like `navigator`, touchevents and more. You never know what's in an library.

### Demo
https://royvanderzon.github.io/feature-detection-research/js-map.html

### Fallback
By overwriting a DOM element with content there is always something.
Example:

```
<div id="map">
    <img src="img.png" alt="">
</div>

<script>
    function initMap() {
        mapEl.innerHTML = ''
        renderMap(mapEl)
    }
</script>
```
