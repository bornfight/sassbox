Sassbox
======================

Set of SCSS helpers, mixins and base css to startup your front end project. 

Installation
------------

npm install --save @degordian/sassbox

Usage
------------


### Gulp

```
// Gulpfile.js
gulp.task('sass', function() {
  return gulp.src('path_to_scss/style.scss')
      .pipe(sass({
          includePaths: ['node_modules/@degordian/sassbox/src']
      })
      .pipe(gulp.dest('dist/css'));
});
```

__Usage in SCSS__
```
/* style.scss */
@import "sassbox";

or import individual modules:

@import "base";
@import "helpers";
@import "layout";
@import "zkeleton";
```


### Webpack

You need to have `sass-loader` installed and enabled:

```
npm install sass-loader --save-dev
```

```
// webpack.config.js
loaders: [
  {
    test: /\.scss$/,
    loader: 'style!css!sass'
  }
]
```

__Usage in SCSS__

```
/* style.scss */
@import "~@degordian/sassbox/src/sassbox";

or import individual modules:

@import "~@degordian/sassbox/src/base";
@import "~@degordian/sassbox/src/helpers";
@import "~@degordian/sassbox/src/layout";
@import "~@degordian/sassbox/src/zkeleton";
```


Overriding defaults
------------

If you need to override some default variables, just define them before importing the sassbox modules.

```
/* _overrides.scss */

$font-primary: 'Lato', sans-serif; 

/* style.scss */

@import "overrides";
@import "sassbox";


/* style.css */ 

html {
...
font-family: 'Lato', sans-serif;
...
}

```

Suggested overrides
-------------------

```
/* _colors.scss */

$c-white: #ffffff !default;
$c-black: #000000 !default;

$default-body-text-color: $c-black !default;
$default-body-link-color: $c-black !default;

$default-selection-text-color: $c-white !default;
$default-selection-bg-color: $c-black !default;

/* _z-index.scss */ 

$z-layers: (
        highest : 50,
        banner : 20,
        menu : 10,
        header : 2,
        default : 1
) !default;

/* _typography.scss */

$browser-context: 18 !default; // px
$browser-line-height: 18 !default; // px

$font-primary: Helvetica, Arial, sans-serif !default;

/* _routes.scss */

$img-link-type: REL !default;

/* _grid-values.scss */

$z-grid-number: 24 !default;
$zgrid-default-gutter: 0 !default;
```