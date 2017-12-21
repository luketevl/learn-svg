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


# OBSERVATIONS

- SVG
  - Minified
  - Support in IE8 >
  - Good acessibility
  - Have tree dom
- `image` vs `background` 
  - Background only load the image when used