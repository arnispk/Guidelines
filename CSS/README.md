# CSS Coding Guidelines

## Key principles

**KISS (Keep.It.Simple.Stupid)<br />
& <br />
DRY (Don’t.Repeat.Yourself)**

## Formatting

### General
* four (4) space indent
* properly written, multi-line CSS rules
* meaningful use of whitespace (see also: CSS Ruleset)
* Strings in single quotes. urls being strings, are single quoted as well.
* A value of zero (0) will not be followed by a unit
* Decimals below one (1) will be proceded by a leading zero

### CSS Ruleset
* related selectors on the same line; unrelated selectors on new lines;
* the opening brace ({) spaced from the last selector by a single space;
* each declaration on its own new line;
* a space after the colon (:);
* a trailing semi-colon (;) at the end of all declarations;
* the closing brace (}) on its own new line;
* a new line after the closing brace }
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

In addition meaningful whitespace may be used according to these rules:

* Properties are grouped by type (in order of priority).
  1. Box
  2. Border
  3. Background
  4. Text
  5. Other

An empty line may follow after each type of property for readability.

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
Although there is no such thing as *too much* commeting, please always minify all css on production.

### Documentation
[SassDoc](http://sassdoc.com/) provides tooling for creating (online) documentation for your (SASS)-project. Although it is recommended to use above commenting guidelines, since they will easily merge with i.e SassDoc, creating project Documentation is not obliged yet. 

## Architecture
At Netwerven we use the 7-to-1 Pattern.

### Categories
Categorize your stylesheets.

*7-to-1 Pattern*

1. base/
2. components/
3. layout/
4. pages/
5. themes/
6. utils/
7. vendors/

1 file to rule them all (main.scss). When using critical path, there may be several style files. Critical-path is not mandatory at the moment however.

### Sample Directory Structure
```
sass/
|
|– base/
|   |– _reset.scss       # Reset/normalize
|   |– _typography.scss  # Typography rules
|   ...                  # Etc…
|
|– components/
|   |– _buttons.scss     # Buttons
|   |– _carousel.scss    # Carousel
|   |– _cover.scss       # Cover
|   |– _dropdown.scss    # Dropdown
|   ...                  # Etc…
|
|– layout/
|   |– _navigation.scss  # Navigation
|   |– _grid.scss        # Grid system
|   |– _header.scss      # Header
|   |– _footer.scss      # Footer
|   |– _sidebar.scss     # Sidebar
|   |– _forms.scss       # Forms
|   ...                  # Etc…
|
|– pages/
|   |– _home.scss        # Home specific styles
|   |– _contact.scss     # Contact specific styles
|   ...                  # Etc…
|
|– themes/
|   |– _theme.scss       # Default theme
|   |– _admin.scss       # Admin theme
|   ...                  # Etc…
|
|– utils/
|   |– _variables.scss   # Sass Variables
|   |– _functions.scss   # Sass Functions
|   |– _mixins.scss      # Sass Mixins
|   |– _helpers.scss     # Class & placeholders helpers
|
|– vendors/
|   |– _bootstrap.scss   # Bootstrap
|   |– _jquery-ui.scss   # jQuery UI
|   ...                  # Etc…
|
|
`– main.scss             # Main Sass file
```
## Naming Conventions
Architecture is giving inmidiate directions for naming conventions.  The use of naming convention is beneficial for immediately understanding which category a particular style belongs to and its role within the overall scope of the page.

On large projects, it is more likely to have styles broken up across multiple files. In these cases, naming convention also makes it easier to find which file a style belongs to.

A good naming convention will tell you and your team:

* what type of thing a class does
* where a class can be used
* what (else) a class is related to

## Depth of Applicability
To be updated -> rendering (short movie) and nesting guidelines.

## Suggested reading
[SMACCS](https://drive.google.com/drive/u/0/#folders/0B5-_yPc9Puptc25ROWNleVNkU3c/0B3CJLPTEHpHINEZRRTgyeDE5STA)
[CSS Guidelines] (http://cssguidelin.es/)
[SASS Guidelines](http://sass-guidelin.es/#css-ruleset)
[LESS Guidelines] (http://www.runopencode.com/index.php/how-we-code/css-and-less-coding-standards)
