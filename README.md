> This version was just created to update the original `gulp-standard` to v12. It was used in a PR and the author from the original repo has accepted so please use the original one instead. Keeping this here until I can update the projects in which I needed this.

# gulp-standard
- This fork of https://github.com/emgeee/gulp-standard has as only difference to use standardjs v12 instead of v11 (and the name, `gulp-standardjs` instead of `gulp-standard`)
- Thanks to this version bump, a bug for `error: unable to load resolver "node"` when finding `import` statements that happens when using `gulp-standard` doesn't happen anymore with this package.

## Information

<table>
<tr>
<td>Package</td><td>gulp-standardjs</td>
</tr>
<tr>
<td>Description</td>
<td>Standard plugin for gulp</td>
</tr>
<tr>
<td>Node version</td>
<td>>= 0.9</td>
</tr>
<tr>
<td>gulp version</td>
<td>3.x</td>
</tr>
</table>

## Usage

#### Install

```sh
$ npm install --save-dev gulp-standardjs
```

## Examples

```javascript
// include the required packages.
var gulp = require('gulp')
var standard = require('gulp-standardjs')

gulp.task('standard', function () {
  return gulp.src(['./app.js'])
    .pipe(standard())
    .pipe(standard.reporter('default', {
      breakOnError: true,
      quiet: true
    }))
})
```

## Reporters

#### Built-in

You can choose a reporter when you call
````javascript
stuff
  .pipe(standard())
  .pipe(standard.reporter('default', opts))
External
````

You can also use some other custom made reporter
````javascript
var reporter = require(<SOME_REPORTER>)

stuff
  .pipe(standard())
  .pipe(standard.reporter(reporter, opts))
````
OR -
````javascript
stuff
  .pipe(standard())
  .pipe(standard.reporter(<REPORTER NAME>, opts))
````
#### Reporter options

##### breakOnError

Type: `boolean`
Default: `false`

Emit gulp error on reported error

##### breakOnWarning

Type: `boolean`
Default: `false`

Emit gulp error on reported warning

##### quiet

Type: `boolean`
Default: `false`

Suppress success messages, only show errors

##### showRuleNames

Type: `boolean`
Default: `false`

Show rule names for errors/warnings (to ignore specific rules)

##### showFilePath

Type: `boolean`
Default: `false`

Show the full file path with the line and column numbers (useful for IDEs that will link to that location)

## LICENSE [MIT](LICENSE)
