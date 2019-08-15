https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#HSL_colors


# hsl.scss

[HSL colors](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#HSL_colors) [are awesome](https://www.sarasoueidan.com/blog/hex-rgb-to-hsl/). Unfortunately, the [SASS `hsl()` and `hsla()` functions](https://sass-lang.com/documentation/functions/color#hsl) converts the colors to RGB/RGBA format.

_hsl.scss_ replaces the two SASS functions by two others, preserving HSL(A) color declarations.

## Installation

1. `npm install hsl.scss` pulls the package into your project.
2. `@import '~hsl.scss';` in a SCSS files make `hsl()` and `hsla()` available.

## Usage

Write colors:
```scss
:root {
  color: hsl(15deg, 100%, 50%);
  --flashy-pink: hsl(15deg, 100%, 50%);  // coma as separator
  $flashy-pink: hsl(15deg 100% 50%); // space as separator

  --hue: 15deg;
  --transparent-flashy-pink: hsl(var(--hue), 100%, 50%, .7);
  $transparent-flashy-pink: hsla(15deg, 100%, 50%, .7); // opacity after a coma
  $transparent-flashy-pink: hsla(15deg 100% 50% / .7); // opacity after a slash
}
```
