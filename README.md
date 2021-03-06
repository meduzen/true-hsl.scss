# hsl.scss

[HSL colors](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#HSL_colors) [are awesome](https://www.sarasoueidan.com/blog/hex-rgb-to-hsl/). Unfortunately, the [SASS `hsl()` and `hsla()` functions](https://sass-lang.com/documentation/functions/color#hsl) converts the colors to RGB/RGBA format.

_hsl.scss_ replaces the two SASS functions by two others, preserving HSL(A) color declarations.

- [Demo](https://codepen.io/meduzen/pen/BaBKdBb?editors=0100#0)
- [Tweet](https://twitter.com/meduzen/status/1161948600219459584) with screenshots.

## Installation

1. `npm install hsl.scss` pulls the package into your project.
2. `@import '~hsl.scss';` in a SCSS files make `hsl()` and `hsla()` available.

## Usage

Write regular CSS, the syntax is exactly the same:
```scss
:root {

  // hsl()
  color: hsl(15deg, 100%, 50%);

  // separator: coma (`,`)
  --flashy-pink: hsl(15deg, 100%, 50%);

  // separator: space
  $flashy-pink: hsl(15deg 100% 50%);

  // hsl() accepts opacity as fourth parameter          👇
  --hue: 15deg;
  --transparent-flashy-pink: hsl(var(--hue), 100%, 50%, .7);

  // hsla()
  $transparent-flashy-pink: hsla(15deg, 100%, 50%, .7); 

  // hsla(): opacity after a slash (`/`) when separator is a space
  $transparent-flashy-pink: hsla(15deg 100% 50% / .7);
}
```

## Before / after hsl.scss

![Before: lot of issues. Now: no issues anymore.](https://pbs.twimg.com/media/ECASFaIWkAAHdni?format=jpg&name=large)

![Before: boring interpolation. Now: standard CSS.](https://pbs.twimg.com/media/ECASFaQXoAAjNqe?format=jpg&name=large)

## Note

There’s currently no test enforcing the validity of what is passed to `hsl()` and `hsla()`, like in CSS. They are _passthrough_ function.
