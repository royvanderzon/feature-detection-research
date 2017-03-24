# Feature Detection & Accessibility
## HTML - Source

With the img tag `srcset=""` it is possible to render a specific image.

### Can I use?
http://caniuse.com/#search=srcset
**Global 86.03%**

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

### Can I use?
http://caniuse.com/#search=Datalist
**Global 79.67%**

### Fallback
You can use vanilla JS solutions to give the user an autocomplete experiance. Example: https://goodies.pixabay.com/javascript/auto-complete/demo.html 

## CSS - GRID

CCS Grid is a new CSS feature for GRID LAYOUT.

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

With CSS variables you can define colors once.

### Can I use?
http://caniuse.com/#search=Variables
**Global 69.62%**

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

With the native Navigator function you can get the current coordinates of the users device.

### Can I use?
http://caniuse.com/#search=navigator
**Global 50.08%**


### Fallback
By checkking of the `navigator.geolocation` object exists you can verify if the function works. If the functions doesn't work, you can ask the user for his/her location!

Example:
```
var supports_navigator = function(){
    return navigator.geolocation;
}
supports_navigator() //returns true in Chrome +55
```