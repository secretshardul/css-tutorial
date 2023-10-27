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


