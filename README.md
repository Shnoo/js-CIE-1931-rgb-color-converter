# JavaScript CIE-1931-rgb-color-converter
A simple JS  lib for converting rgb to cie1931 (Which Philips HUE Color lights use) and vice versa.

- NO dependency
- Automatically adjusts Colors based on light capability
- Color correction supports a range of Philips lights
- ECMAScript 6
- Easy to use

This lib was made with the help of the Hue Docs.

Note: *Color accuracy can differ depening on light capabilites.*

# Installation

Download the script [here](https://github.com/Shnoo/Philips-Hue-Color-Converter/blob/master/ColorConverter.js) and include it (unless you are packaging scripts somehow else)
```html
<script src="path/to/ColorConverter.js</script>
```

Do not include the script directly from GitHub (http://raw.github.com/...). The file is being served as text/plain and as such being blocked in Internet Explorer on Windows 7 for instance (because of the wrong MIME type). Bottom line: GitHub is not a CDN.

# Usage

### Convert RGB to XY for Philips Hue lights
```js
let xy = ColorConverter.rgbToXy(red, green, blue, light.modelid);
// xy = {x: xValue, y: yValue};
```

### Convert RGB to XY for non Philips lights
```js
let xy = ColorConverter.rgbToXy(red, green, blue);
// xy = {x: xValue, y: yValue};
```
*Note: Colors may be off due to gamut capabilities of the Light. This setting uses a default gamut range provided by Philips Hue Docs. This may exceed the lights capabilities, resulting in wrong colors depending on lights behaviour.*

### Convert XY + bightness to RGB
```js
let rgb = ColorConverter.xyBriToRgb(x ,y , brightness);
// rgb =  {r: redValue, g: greenValue, b: blueValue}
```
