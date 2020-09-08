# mml-to-chtml

This MathJax wrapper converts Mathematical Markup Language (MML) to Compact Hypertext Markup Language (CHTML). This package doesn't use any webworkers, webviews ; so It can be used for your NodeJS, React and React Native projects.

**This project is still in its early development stages.**

For any bugs, typos, errors, feel free to open an issue on the associated Github repository.

## Installation

```cli
npm install mml-to-chtml --save
```

## Examples

### JS (with the `options` parameter)

```js
const MMLToCHTML = require("mml-to-chtml");

const myMMLEquation = `<math xmlns="http://www.w3.org/1998/Math/MathML" display="block">
        <mi>x</mi> <mo>=</mo>
        <mrow>
          <mfrac>
            <mrow>
              <mo>&#x2212;</mo>
              <mi>b</mi>
              <mo>&#x00B1;</mo>
              <msqrt>
                <msup><mi>b</mi><mn>2</mn></msup>
                <mo>&#x2212;</mo>
                <mn>4</mn><mi>a</mi><mi>c</mi>
              </msqrt>
            </mrow>
            <mrow> <mn>2</mn><mi>a</mi> </mrow>
          </mfrac>
        </mrow>
        <mtext>.</mtext>
      </math>`;

const options = {
    width: 1280,
    ex: 8,
    em: 16,
    fontURL: "https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2"
};

const CHTMLEquation = MMLToCHTML(myMMLEquation, options); // returns <mjx-math display="true" style="margin-left: 0; margin-right: 0" class=" MJX-TEX"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi> ...
```

### TS (without the `options` parameter)

```ts
import MMLToCHTML from "mml-to-chtml";

const myMMLEquation = `<math xmlns="http://www.w3.org/1998/Math/MathML" display="block">
        <mi>x</mi> <mo>=</mo>
        <mrow>
          <mfrac>
            <mrow>
              <mo>&#x2212;</mo>
              <mi>b</mi>
              <mo>&#x00B1;</mo>
              <msqrt>
                <msup><mi>b</mi><mn>2</mn></msup>
                <mo>&#x2212;</mo>
                <mn>4</mn><mi>a</mi><mi>c</mi>
              </msqrt>
            </mrow>
            <mrow> <mn>2</mn><mi>a</mi> </mrow>
          </mfrac>
        </mrow>
        <mtext>.</mtext>
      </math>`;

const CHTMLEquation = MMLToCHTML(myMMLEquation); // returns <mjx-math display="true" style="margin-left: 0; margin-right: 0" class=" MJX-TEX"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi> ...
```

## Documentation

`MMLToCHTML(equation, options)` : **string** _The returned Compact Hypertext Markup Language equation_

> `equation` : **string** _The Mathematical Markup Language equation_
>
> `options` ?: **object** _The options of the retuned Compact Hypertext Markup Language_
>
> > `width` ?: **number** _The width of container in pixels_
> >
> > `ex` ?: **number** _The ex-size in pixels_
> >
> > `em` ?: **number** _The em-size in pixels_
> >
> > `fontURL` ?: **string** _The URL to use for web fonts_

### Notation

?: = optional parameter

## Notes

### Useful links

This wrapper is inspired by this project : https://github.com/mathjax/MathJax-demos-node/tree/master/direct.

### Typescript

You **DON'T** have to install any types `@types/mml-to-chtml`.
