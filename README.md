# hsl.scss

[HSL colors](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#HSL_colors) [are awesome](https://www.sarasoueidan.com/blog/hex-rgb-to-hsl/). Unfortunately, under `node-sass` the [SASS `hsl()` and `hsla()` functions](https://sass-lang.com/documentation/functions/color#hsl) converts to other formats (hex or RGB/RGBA). And the situation [isn’t better in Dart SASS](https://github.com/meduzen/true-hsl.scss/issues/2).

_hsl.scss_ overwrites SASS `hsl` and `hsla` with passthrough functions, preserving HSL(A) color declarations without transformation nor validation.

- [Demo](https://codepen.io/meduzen/pen/BaBKdBb?editors=0100#0)
- [Tweet](https://twitter.com/meduzen/status/1161948600219459584) with screenshots.

## Installation

`npm install hsl.scss -D` pulls the package into your project.

- In a `node-sass` project, `@import 'hsl.scss';` in a SCSS files make `hsl()` and `hsla()` available.
- In a Dart SASS project, `@use 'hsl.scss' as *` is required in every SCSS files where `hsl()` or `hsla()` are used.

## Usage

You can now expect `hsl` and `hsla` to behave like they do using standard CSS:

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

## Before / after `hsl.scss` when using `node-sass`

![Before: lot of issues. Now: no issues anymore.](https://pbs.twimg.com/media/ECASFaIWkAAHdni?format=jpg&name=large)

![Before: boring interpolation. Now: standard CSS.](https://pbs.twimg.com/media/ECASFaQXoAAjNqe?format=jpg&name=large)
