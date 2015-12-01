# CSS Coding Guidelines

## Development

### General
All scss files **MUST**:
* use and define utf-8 character encoding for each file
* have unix line-endings
* use four (4) space indents
* have properly written, multi-line (S)CSS rules
* use meaningful use of whitespace (see also: CSS Ruleset)
* have strings in single quotes. Urls being strings, are single quoted as well.
* precede decimal numbers below 1 with a zero (eg. 0.4)
* **NOT** assign a unit type to a property value of zero (0px vs 0)

### CSS Ruleset
All CSS rules **MUST** have:
* the opening brace `{` spaced from the last selector by a single space
* each declaration on its own new line
* a space after the colon `:`
* a trailing semi-colon `;` at the end of all declarations
* the closing brace `}` on its own new line

All CSS rules **SHOULD**
* put related selectors on the same line; unrelated selectors on new lines
* have a space before the colon `:`
* have at least one new line after the closing brace `}`

```
// Yep
.foo, .foo-bar,
.baz {
  display: block;
  overflow: hidden;
  margin: 0 auto;
}

// Nope
.foo,
.foo-bar, .baz {
    display: block;
    overflow: hidden;
    margin: 0 auto }
```

In addition, meaningful whitespace may be used according to these rules:

An empty line may follow after each type of property for readability. (especially with the use/need of web-prefixes)

### Commenting
Provide a C-style comment for every module you style. A C-style comment hosts numbered explanations regarding specific parts of the ruleset. Example:
```
/**
 * Helper class to truncate and add ellipsis to a string too long for it to fit
 * on a single line.
 * 1. Prevent content from wrapping, forcing it on a single line.
 * 2. Add ellipsis at the end of the line.
 */
.ellipsis {
  white-space: nowrap; /* 1 */
  text-overflow: ellipsis; /* 2 */
  overflow: hidden;
}
```

When commenting a specific section, use inline comments instead of a C-style block. This makes the comment invisible in the output, even in expanded mode during development. Example:

```
// Add current module to the list of imported modules.
// `!global` flag is required so it actually updates the global variable.
$imported-modules: append($imported-modules, $module) !global;
```

### Documentation
[SassDoc](http://sassdoc.com/) provides tooling for creating (online) documentation for your (SASS)-project. Although it is recommended to use above commenting guidelines, since they will easily merge with i.e SassDoc, creating project Documentation is not obliged yet.

## Production
Always minify css files that are used for production. Serve as small a file as possible. That also means that only those rules are served for a request that are actually needed for that request. Don't try to cram everything into one file, but split it up into multiple files and only load those files that are needed at a particular page that a visitor is viewing.

## Architecture
At Netwerven we use the [7-to-1 Pattern](http://sass-guidelin.es/#the-7-1-pattern). In its core, this approach advocates using a single style sheet. Since this is suboptimal for performance, we're only using the proposed folder structure to organise our sass files.

### Categories
Style rules are organised in the following subfolders:

1. base/<br />
Contains files that have style rules that apply to all pages in the site

2. components/<br />
Each component, that is used in the site, be it a search bar, the main menu, a banner or a block that displays vacancy details, has its styling contained in a single file. The component should be styled in such a way that it's not aware of its context (width of its parent container). This way, components become reusable, easily portable and more maintainable.

3. layout/<br />
Holds files that contain styling for menus, grids, forms etc.

4. themes/<br />
If pages in the site use different set-ups, for instance if some pages have a header image and others don't, there a pages that have three columns and others use four, this folder holds the sass files that define those differences.

5. pages/<br />
Even if different themes have been defined, it might be needed to differentiate between distinct pages in the site. Those rules go here.

6. utils/<br />
Mixins, helpers, functions etc. etc.

7. vendor/<br />
Everything that cannot be resolved through a dependency manager like [Bower](http://bower.io/), composer or NPM, should be placed in this folder. Each file should have a docblock that describes what the contents of the file are for and what the source (url) is.

### Sample Directory Structure
```
sass/
|
|– base/
|   |– _fonts.scss
|   |– _normalize.scss
|   ...
|
|– components/
|   |– _buttons.scss
|   |– _carousel.scss
|   |– _dropdown.scss
|   ...
|
|– layout/
|   |– _grid.scss
|   |– _main-menu.scss
|   |– _site-footer.scss
|   |– _site-header.scss
|   ...
|
|– pages/
|   |– _home.scss
|   |– _contact.scss
|   ...
|
|– themes/
|   |– _main.scss
|   |– _no-header.scss
|   |– _sidebar.scss
|   ...
|
|– utils/
|   |– _variables.scss
|   |– _functions.scss
|   |– _mixins.scss
|   |– _helpers.scss
|   ...
|
|– vendor/
|   |– _jquery-ui.scss
|   |– _select2.scss
|   ...
|
```

## Naming Conventions
A good naming convention will tell you and your team:

* what type of thing a class does
* where a class can be used
* what (else) a class is related to

Don't: 

## Depth of Applicability
To be updated -> rendering (short movie) and nesting guidelines.

## Suggested reading
[SMACCS](https://drive.google.com/drive/u/0/#folders/0B5-_yPc9Puptc25ROWNleVNkU3c/0B3CJLPTEHpHINEZRRTgyeDE5STA)
[CSS Guidelines] (http://cssguidelin.es/)
[SASS Guidelines](http://sass-guidelin.es/#css-ruleset)
[LESS Guidelines] (http://www.runopencode.com/index.php/how-we-code/css-and-less-coding-standards)
