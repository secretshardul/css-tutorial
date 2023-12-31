# CSS tutorial

## Syntax

CSS syntax comprises of two parts

1. Selector: Selects an element, class, id etc
2. Declaration: Defines property-value pairs for selectors

```css
/* This is a comment */
selector {
  property: value;
}
```

## Selectors

Selectors select HTML elements for styling. They are of 5 types

### Simple selectors

1. **Element based**
  - Select all HTML elements with the given tag
  - eg. `p`, `div`

```css
p {
}
```

2. **ID based**
  - Select by ID
  - Uses `#`

```css
#para1 {
}
```

3. **Class based**
  - Select by class
  - Uses `.`
  - Can be combined with element based selectors to find elements of a certain type with a given class.

```css
.center {
}

/* Select p elements of class center */
p.center {
}
```

4. **Universal selector**:
  - Use `*` to select all HTML elements

```css
* {

}
```

### Grouping selectors

```css
h1, h2, p {
}
```

### Other selector types

- **Combination selectors**: Select elements based on some relationship between them

- **Pseudo-class selectors**: Select elements based on certain state

- **Pseudo-elements selectors**: Select and style part of an element

- **Attribute selectors**: Select elements based on attribute or attribute value


## Ways to add CSS

### 1. External CSS with stylesheet

Separating content and presentation is a good practice.

```html
<head>
  <link rel="stylesheet" type="text/css" href="styles.css" />
</head>
```

### 2. Internal CSS

Add styles to `<styles>`

```html
<head>
  <style>
    p {
      background-color: blue;
    }
  </style>
</head>
```

### 3. Inline CSS

Not considered a good practice

```html
<body>
  <p style="color:blue;text-align:center;">good game</p>
</body>
```

### Multiple style sheets

The last read sheet gets precedence. The styles from the external sheet will apply. If the external stylesheet were to be inserted before, the internal CSS would gain precedence.

```html
<head>
  <style>
    p {

    }
  </style>
  <link rel="stylesheet" type="text/css" href="styles.css" />
<head>
```

### Cascading order

Stylesheets cascade into a virtual style sheet, where number 1 has highest priority

1. Inline style
2. External and internal style sheets
3. Browser defaults

## Colors

### Colors can be defined using

```html
<h1 style="color:Tomato;">Predefined color</h1>
<h1 style="color:rgb(255, 99, 71);">RGB color</h1>
<h1 style="color:rgba(255, 99, 71, 50%);">RGBA color</h1>
<h1 style="color:hsl(120, 100%, 50%);">HSL color</h1>
<h1 style="color:hsla(120, 100%, 50%, 50%);">HSLA color</h1>
```

1. Predefined color names

  - `Red`, `Tomato` etc
  - [There are 140 defined color names](https://www.w3schools.com/colors/colors_names.asp)


2. RGB and RGBA
  - eg. `rgb(255, 99, 71)`, `rgba(255, 99, 50%)`
  - A stands for alpha, i.e. transparency

```
```

3. HSL (hue, saturation, lightness) and HSLA
  - Hue: Degrees in the color wheel
  - Saturation: Intensity of the color in percentage
  - Lightness: How much light to give to the color. 0% is dark, 100% is full light
  - eg. `(120, 100%, 50%)`, `(120, 100%, 50%, 50%)`

### Color elements

```html
<p style="background-color:Red;">Background color</p>
<p style="color:Blue;">Text color</p>
<p style="border: 2px solid Red;">Border color</p>
```

1. Background color: `background-color`
2. Text color: `color`
3. Border color: `border`. It has 3 values
  1. Text size in px
  2. Border style: `solid`, `dotted` etc
  3. Color


## Backgrounds

### 1. `background-color`


### 2. `background-image`

```css
body {
  background-image: url("paper.gif");
}
```

- The image is repeated by default so that the whole element is covered.

### 3. `background-repeat`

Use `background-repeat` to modify repeat behavior
- `no-repeat` to disable repeats
- `repeat-x` or `repeat-y` to only repeat in one axis

### 4. `background-attachment`

- `scroll`: Image scrolls with rest of the page
- `fixed`: No scrolling

### 5. `background-position`

sets starting position of the image-`right top`, `left bottom` etc

### 6. `background` shorthand

Combines background properties into one property in order

1. `background-color`
2. `background-image`
3. `background-repeat`
4. `background-attachment`
5. `background-position`

```css
body {
  background: #ffffff url("img_tree.png") no-repeat fixed right top;
}
```

## Distance Units

Used for length values like `margin`, `padding` etc

### Absolute units

- `cm`, `mm`, `inch`
- `px`: Equals to one pixel on low resolution screens and multiple pixels on larger screens

### Relative units

Use `em` and `rem` for responsive layouts. There are other less commonly units too.

- `em`: Relative to font size of element. `1em` is twice of the font size.
- `rem`: Relative to font size of root element
- `%`: Relative to parent element
- `ch`: Relative to the width of `0` (zero)

## Margins

Margins create space **around elements**, outside of their borders.

### Margin properties

Define margins with these four properties
  1. `margin-top`
  2. `margin-right`
  3. `margin-bottom`
  4. `margin-left`

- Or use `margin` as a shorthand.
  1. If 4 values are provided, eg `margin: 25px 50px 75px 100px;`, they are in the order top, right, bottom left (clockwise order)
  2. We can also use 3, 2 or one value. The missing values are replicated, i.e.
    - For 3 values: top, right and left, bottom
    - For 2 values: top and bottom, right and left
    - For 1 value: All sides

### Margin values

- `px`, `cm` or `inch`
- `auto` automatically adds margin to fill up space in the parent. This can be used to horizontally center elements.
- `inherit` inherits the value from its parent.

### Margin collapse

The actual margin is 50 and not 70 (50+20). CSS uses the greater of two adjacent margins for top and bottom margins. This does not apply to left and right margins.

```html
<body>
  <h1 style="margin-bottom:50px">First</h1>
  <h1 style="margin-top:20px">Second</h2>
</body>
```

## Padding