# Backline Grid

A scss port of [responsive-grid](https://github.com/clocklimited/responsive-grid).

A simple `inline-block` based responsive grid, with IE8+ browser support. Only outputs the styles specified to avoid CSS full of unused widths.

## Installation

```sh
npm install --save backline-grid
```

or

```sh
yarn add backline-grid
```

Add `backline-grid` to your node-sass includePaths option.

```js
{
  loader: 'sass-loader',
  options: {
    includePaths: [
      ...require('backline-grid').includePaths
    ]
  }
}
```

Import backline-grid in each `.scss` as required

```scss
@import 'backline-grid';
```

## Usage

Responsive Grid provides a collection of mixins for use.

### `grid-base()`

This will set up the block `.grid` class and the element `.grid__item` class.

---

### `grid-widths($namespace, $columns)`

This will set up width classes based on the `$columns` you include.

#### Examples

- `grid-widths('', 1 3 6)` will set up a whole class, thirds classes, and sixths classes.
- `grid-widths('desktop', 1 2 3)` will set up a `.{$namespace}` class for each of the width classes.

The following variables can be used to change the in-built naming convention, for example, when using with a different language

| Variable name          | Type | Default                      | Description                                         |
| ---------------------- | ---- | ---------------------------- | --------------------------------------------------- |
| \$grid--count-names    | list | one two three … sixteen      | Forms the first half of the grid widths class name  |
| \$grid--fraction-names | list | whole half third … sixteenth | Forms the second half of the grid widths class name |

---

### `grid-pull($namespace, $columns)`

This will set up pull classes based on the `$columns` you include.

#### Examples

- `grid-pull('', 1 3 6)` will set up `.pull-{width}` classes that move the `.grid__item` with a whole class, thirds classes, and sixths classes.
- `grid-pull('desk', 1 2 3)` will set up a `.{$namespace}pull-{width}` class for each of the pull classes.

---

### `grid-push($namespace, $columns)`

This will set up push classes based on the `$columns` you include.

#### Examples

- `grid-push('', 1 3 6)` will set up `.push-{width}` classes that move the `.grid__item` with a whole class, thirds classes, and sixths classes.
- `grid-push('desk', 1 2 3)` will set up a `.{$namespace}push-{width}` class for each of the push classes.

---

### `grid-gutter-modifier($namespace, $gutter)`

This will set up the gutter modifier `.grid--{$namespace}` class and `.grid__item` child selector which modify the gutter width.
Providing an optional `$namespace` allows the mixin to be used to change the base grid gutter at different breakpoints.

#### Examples

- `grid-gutter-modifier('', 10px)` will set up a `.grid` class that will provide a 10px gutter between each `.grid__item`.
- `grid-gutter-modifier('em', 1em)` will set up a `.grid--em` class that will provide a 1em gutter between each `.grid__item`.
- `grid-gutter-modifier('percent', 10%)` will set up a `.grid--percent` class that will provide a 10% gutter between each `.grid__item`.
- `grid-gutter-modifier('pixel', 20px)` will set up a `.grid--pixel` class that will provide a 20px gutter between each `.grid__item`.

---

### `grid-reverse($namespace)`

This will set up modifier `.grid--reverse` class that, when applied, will visually reverse the DOM order of the `.grid__item`'s. Providing a `$namespace` is optional.

---

### `grid-uncompressed()`

Adds a slightly-hacky workaround for non-compressed HTML (avoid if possible)

---

## Development

Clone this repo and install dependencies. All styles have test coverage and Prettier formatting to ensure everything works as expected.

### Running Tests

```sh
yarn test
```
