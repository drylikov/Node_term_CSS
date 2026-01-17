
# term-css

  Terminal CSS styling using node-css.

## Installation

    $ npm install term-css

## Example

js:

```js

var css = require('term-css')
  , fs = require('fs')
  , style = fs.readFileSync('pet.css', 'utf8');

var tobi = {
  name: 'tobi',
  species: 'ferret',
  age: 2
};

var loki = {
  name: 'loki',
  species: 'ferret',
  age: 1
};

var fn = css.compile('  {name} is a {species}, he is {age} years old', style);

console.log();
console.log(fn(tobi));
console.log(fn(loki));
console.log();

```

css:

```css
name {
  color: cyan;
  font-weight: bold;
}

species {
  color: white;
  font-weight: bold;
  background: black;
}

age {
  color: red;
  text-decoration: underline;
}
```

## CSS properties

  The following CSS properties / values are understood:
  
  - `text-decoration: <underline|inverse>`
  - `font-weight: <bold>`
  - `font-style: <italic>`
  - `color: <grey|gray|black|blue|cyan|green|red|magenta|yellow>`
  - `background: <grey|gray|black|blue|cyan|green|red|magenta|yellow>`

## Substitution

  term-css substitutes tokens with properties in the object passed,
  for example `{name}` will access `{ name: "tobi" }`, whereas 
  `{labels.visits}` will access `{ labels: { visits: 'Visits' } }`.

  For styling purposes you may also assign a classname, for example
  instead of styling "labels.visits", "labels.uptime" separately,
  you may use `{label labels.visits}` and `{label labels.uptime}`.

## Omitting styles

 To output a plain string but use the same format, simply omit the css
 string from the `.compile(fmt, style)` call.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
