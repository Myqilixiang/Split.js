## Split.js



Split.js is a lightweight (2kb), non-opionionated utility for creating adjustable split views or panes. [Demo](http://nathancahill.github.io/Split.js/).

No dependencies or markup required, just two or more elements with a common parent. Views can be split horizontally or vertically, with draggable gutters inserted between every two elements.

## Installation

Install with Bower:

```shell
bower install split.js
```

Or clone from Github:

```shell
git clone https://github.com/nathancahill/Split.js.git
```


## Documentation

```js
Split(<id[]> element ids, <options> options?)
```

| Options | Type | Default | Description |
|---|---|---|---|
| sizes | Array of numbers | | Initial sizes of each element in percents. |
| minSize | Number or Array of numbers | 100 | Minimum size of each element. |
| gutterSize | Number | 10 | Gutter size in pixels. |
| snapOffset | Number | 30 | Snap to minimum width offset in pixels. |
| direction | String | 'horizontal' | Direction to split: horizontal or vertical. |
| onDrag | Function | | Callback on drag. |
| onDragStart | Function | | Callback on drag start. |
| onDragEnd | Function | | Callback on drag end. |


## Usage Examples

A split with two elements, starting at 25% and 75% wide with 200px minimum width.

```js
Split(['one', 'two'], {
    sizes: [25, 75],
    minSize: 200
});
```

A split with three elements, starting with even widths with 100px, 100px and 300px minimum widths, respectively.

```js
Split(['one', 'two', 'three'], {
    minSize: [100, 100, 300]
});
```

A vertical split with two elements.

```js
Split(['one', 'two'], {
    direction: 'vertical'
});
```

## CSS

In being non-opionionated, the only CSS Split.js sets is the widths or heights of the elements. Everything else is left up to you. However, here's some basic CSS to style the gutters with:

```css
.gutter {
  background-color: #eee;

  background-repeat: no-repeat;
  background-position: 50%;

  cursor: move;
  cursor: grab;
  cursor: -moz-grab;
  cursor: -webkit-grab;
}

.gutter:active { 
  cursor: grabbing;
  cursor: -moz-grabbing;
  cursor: -webkit-grabbing;
}

.gutter.gutter-horizontal {
  background-image: url('grips/vertical.png');
}

.gutter.gutter-vertical {
  background-image: url('grips/horizontal.png');
}
```

Split.js also works best when the elements are sized using `border-box`. The `split` class would have to be added manually to apply these styles:

```css
.split {
  box-sizing: border-box;
}
```

And for horizontal splits, floating the elements with 100% height is useful:

```css
.split, .gutter.gutter-horizontal {
  height: 100%;
  float: left;
}
```
