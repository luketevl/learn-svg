# learn-svg
Learn about SVG

# LINKS
- https://d3js.org/
- https://www.vecteezy.com/
- https://www.shutterstock.com/
- http://svgcuts.com/blog/category/fsvgotw/
- https://icomoon.io/
- https://iconmonstr.com/
- https://useiconic.com/
- https://github.com/willianjusten/awesome-svg/blob/master/topics/Icons.md
- https://www.npmjs.com/package/gulp-svg-sprites
- https://d3js.org/
- http://snapsvg.io/
- https://greensock.com/
- https://bonsaijs.org/


# SVG
> Vectorial image in format XML, with support to animations and interactivity
> Responsive and adaptive

## When use
- Simple icons
- Flat icons
![Image when use](https://i.imgur.com/XGF8PDk.png)

## Methods to use

### With image
- Using
```html
<img src="image.svg" alt=""/>
```
- Advantage
  - Can be cached
- Disadvantage
  - Doesnt have interation with **css**
  - Doesnt have interation with **dom**
  - Animation work in inside SVG

- Using with **data-uri**
```html
<img src="data:image/svg+xml;" alt=""/>
```
- Disadvantage
  - Can not be cached
  - Doesnt have interation with **css**
  - Doesnt have interation with **dom**
  - Size can be more what the original file with .svg

### With background-image
- Using
```css
.svg{
  background-image: url('image.svg');
}
```
- Advantage
  - Can be cached
- Disadvantage
  - Doesnt have interation with **css**
  - Doesnt have interation with **dom**
  - Animation work in inside SVG

### With iframe / object / embed 
> **bad** use
- Using `iframe`
```html
<iframe src="image.svg" frameborde="0"></iframe>
```
- Using `object`
```html
<object data="image.svg" type=""></object>
```
- Using `embed`
```html
<embed data="image.svg" type=""></embed>
```
- Disadvantage
  - Very slown
  - Different behavior in browsers
  - Small permission to edit

### SVG INLINE
> Good pratice


- Advantage
  - Have interation with **CSS**
  - Have interation with **dom**
  - Havent adiiconal request HTTP
- Disadvantage
  - Can not be cached
  - Doesnt have interation with **dom**
  - Animation work in inside SVG


## VIEWPORT and VIEWBOX

- Creating **viewport**
```html
<svg></svg>
```
![](https://i.imgur.com/nyoXPzL.png)
- Attributes of **viewport**
  - `preserveAspectRatio` | proportional size image
    - **none**
      - ![preserveAspectRatio=none](https://i.imgur.com/4AqJpxG.png)
    - xMinYMin, xMaxYMax, xMedYMed
      - **xMinYMin meet** | occupe the maximo
        - ![preserveAspectRatio=xMinYMin meet](https://i.imgur.com/EcjlUpa.png)
      - **xMinYMin slice** | occupe the all and slice
        - - ![preserveAspectRatio=xMinYMin slice*](https://i.imgur.com/BdX14zF.png)
      

```html
<svg preserveAspectRatio></svg>
```
   
> All the drawing behavior inside, space with the drawing
- Creating **viewbox**
> Equal zoom in and zoom out, more space viewbox less element size, less space viewbox more element size
```html
<svg viewBox="x y minX minY"></svg>
```

## BASIC SHAPES

- React or Square | Rectangule or Square
```html
<svg>
  <rect x="0" y="0" width="200" height=""></rect>
</svg>
```

- Circle
  - **r** | raio
  - **cx** | axis X
  - **cy** | axis Y
```html
<svg>
  <circle r="25" cx="70" cy="70" />
</svg>
```

- Ellipse
  - **rx** | raio axis X
  - **ry** | raio axis Y
  - **cx** | axis X
  - **cy** | axis Y
```html
<svg>
  <ellipse r="25" cx="70" cy="70" />
</svg>
```
- Line
```html
<svg>
  <line x1="10" y1="10" x2="100" y2="120" stroke="#000" stroke-width="2" />
</svg>
```
- Polyline
```html
<svg>
  <polyline points="0,40 40,40 40,80" fill="transparent" stroke="#000" stroke-width="2" />
</svg>
```
- Polygon
```html
<svg>
  <polygon points="0,40 40,40 40,80" fill="transparent" stroke="#000" stroke-width="2" />
</svg>
```
- Path
  - **M** | Moveto
  - **L** | Lineto
  - **A** | Arcs
  - **z** | Closepath
```html
<svg>
  <path
    stroke=#000"
    stroke-width="4"
    fill="none"
    d="M40,20 L40,80 A30,30 0 0,0 100,100z"
  />
</svg>
```
![Basic shape PATH](https://i.imgur.com/0OJ0zmr.png)

## TEXTS
- Creating texts with svg
```html
<svg>
  <text x="0" y="40" fill="#000">Text</text>
</svg>
```

## Container elements
- **Defs** | Container that contains elements for **reuse**, only visible case you **call**
```html
<svg>
  <defs>
    <circle id="my-circle" />
  </defs>
  <use xlink:href="my-circle">
  <use xlink:href="my-circle" x="80">
</svg
```
- **G** | Group elements similar
```html
<svg>
  <g fill="red">
    <circle id="my-circle" />
    <circle id="my-circle2" />
  </g>
</svg
```
- **Symbol** | Define an Object if will instance and used by **use** and have your self **viewbox**
```html
<svg>
  <symbol id="my-circle" viewBox="0 0 200 100">
    <circle/>
  </symbol>
  <use xlink:href="my-circle">
  <use xlink:href="my-circle" x="80">
</svg
```

## STYLING SVG

### Fill and Stroke
```html
<style>
  .circle{
    stroke: #000;
    stroke-width: 5;
    
  }
  .circle-1{
    fill: #F82;
    fill-opacity: .3;
    stroke-dasharray: size| space;
    stroke-dashoffset: 100; */ effect to draw stroke */
  }
  .circle-2{
    fill: #FF0000;
    fill-opacity: .7;
  }
</style>
<svg viewBox="x y minX minY">
  <circle class="circle circle-1" r="25" cx="70" cy="70" />
  <circle class="circle circle-2" r="25" cx="70" cy="70" />
</svg>
```
- Fill
  - **currentColor** | get the color of the parent
  
```html
<script>
  .currentColor{
    color: #00FF00;
  }
</script>
<svg class="currentColor" viewBox="x y minX minY">
  <path
    stroke=#000"
    stroke-width="4"
    fill="currentColor"
    d="M40,20 L40,80 A30,30 0 0,0 100,100z"
  />
</svg>
```
## SMIL
> Frameworks animate css
- `<animate>`
```html
<svg>
  <circle r="25" cx="70" cy="70">
    <animate attributeName="cx" from="0" to="100" dur="5s" repeatCount="infinite" />
  </circle>
</svg>

<!-- or -->
<svg>
  <circle id="animation" r="25" cx="70" cy="70" />
    <animate xlink:href="#animation" attributeName="cx" from="50" to="450" dur="3s" fill="freeze" begin="click" id="animation-circle" />
    <animate xlink:href="#animation" attributeName="cx" from="50" to="450" dur="3s" fill="freeze" begin="animation-circle.begin + 1s" />
</svg>
```

- `<set>` | shortcode for animate
- `<animateMotion>`
```html
<svg>
  <circle id="animation" r="25" cx="70" cy="70" />
    <animateMotion xlink:href="#animation" dur="3s" fill="freeze" begin="click" path="M0,0.........." />
</svg>
```

- `<animateColor>`
- `<animateTransform>`
- `keypoints` attribute

### MORPH PATH

## USING JAVASCRIPT
- **Create** svg element  
  - **NS** are **namespace**
```javascript
const circle = document.createElementNS('http://www.w3.org/2000/svg', "circle");
```
- **Create** attributes
- params(namspace, attributeName, value)
```javascript
circle.setAttributeNS(null, "r", 10);
```
- **AppendChild**
```javascript
draw.appendChild(circle;
```

# OBSERVATIONS

- SVG
  - Minified
  - Support in IE8 >
  - Good acessibility
  - Have tree dom
- `image` vs `background` 
  - Background only load the image when used