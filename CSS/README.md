# Netwerven Styling Guidelines

These are the Coding Guidelines for Frontend Developers at Netwerven. These guidelines are a summary of different guidelines and best-practices from all over the web, best matching with Ways of Workin (WoW) within Netwerven. Although these guidelines should not change too often, there may be new insights and/or new syntaxes to work with, that need there own guidelines. Also, these guidelines may be updated

Version 1.0


## Key principles
Whatever syntax you choose and whatever approach you prefer when styling a frontend-application; at all times:

**KISS (Keep.It.Simple.Stupid)<br />
& <br />
DRY (Don’t.Repeat.Yourself)**

However, all that follows are guidelines, not rigid rules. Sometimes pragmatism, might be favoured over guidelines. One of these is the use of a “shame”-module. It might not be the “cleanest” or “best” answer to a problem, but it might be a pragmatic answer at a certain point of time.

## Formatting

### General
* four (4) space indent
* properly written, multi-line CSS rules
* meaningfull use of whitespace (see also: CSS Ruleset)
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

In addition meaningfull whitespace may be used according these rules:

* Properties are grouped by type (in order of priority).
  1. Box
  2. Border
  3. Background
  4. Text
  5. Other

An empty line may follow after each type of property for readability.

### Commenting
Ideally, any CSS ruleset should be preceded by a C-style comment explaining the point of the CSS block. This comment also hosts numbered explanations regarding specific parts of the ruleset. Example:
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
Although there is no such thing as *too much* commeting, please do never deploy your comments to a production environment. This is easily managed by minifying all css before deployment.

### Documentation
[SassDoc](http://sassdoc.com/) provides tooling for creating (online) documentation for your (SASS)-project. Although it is recommended to use above commenting guidelines, since they will easily merge with i.e SassDoc, creating project Documentation is not obliged yet. 

## Architecture
There is a lot to say about different CSS architectures and its advantages/disadvantages comparing to each other. But in general there are guidelines that apply to all of them. Even most of the frequently used Frameworks use some kind of architecture and though not every Framework will fit in neathly with a modularized architecture; with these guidelines, even Frameworks can be easily modified into this structure. <br />
(And if not, you won't want to use this Framework anyway).

### Categories
Categorize your stylesheets. As in many architectural patterns, their are more ways to build the Pathenon, but two preferred methods are:

*SMACCS-approach*

1. Base
2. Layout
3. Module
4. State
5. Theme

*7-to-1 Pattern*

1. base/
2. components/
3. layout/
4. pages/
5. themes/
6. utils/
7. vendors/

As you can see, categorizing is slightly arbitrary. One might say "pages" and "vendors" belong to "modules", where others might say that the category "module" is way to general to actually stick to. What stands out however is that both classifications implicate the use of separate files that each are responsible for the styling of only one particular part of your application. In extremis this is applicable to all code within the whole project. (You might even implicate this architecture stands the ground for MVC's such as Angular and/or BEM-projects as well).


### Sample Directory Structure
**SMACCS**
```
sass/
|
|- layout
|  |- grid.scss
|  |- alternate.scss
|- module/
|     |- callout.scss
|     |- bookmarks.scss
|     |- btn.scss
|     |- btn-compose.scss
|- base.scss
|- states.scss
|- site-settings.scss
|- mixins.scss
```
**7-to-1**
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
Following above architecture (both structures) are giving inmidiate directions for naming conventions.  The use of naming convention is beneficial for immediately understanding which category a particular style belongs to and its role within the overall scope of the page.

On large projects, it is more likely to have styles broken up across multiple files. In these cases, naming convention also makes it easier to find which file a style belongs to.

A good naming convention will tell you and your team:

* what type of thing a class does
* where a class can be used
* what (else) a class might be related to

Following the architecture described above, styles can be prefixed by its category. Such as ```grid-``` for grid-styles, or ```l-``` for lay-out. Using ```is-``` for states, might be usefull as well. The use of the prefix ```module``` would be verbose, since the module-class would use the name of the module itself.

## Depth of Applicability
To be updated -> rendering (short movie) and nesting guidelines.

## Suggested reading
[SMACCS](https://drive.google.com/drive/u/0/#folders/0B5-_yPc9Puptc25ROWNleVNkU3c/0B3CJLPTEHpHINEZRRTgyeDE5STA)
[CSS Guidelines] (http://cssguidelin.es/)
[SASS Guidelines](http://sass-guidelin.es/#css-ruleset)
[LESS Guidelines] (http://www.runopencode.com/index.php/how-we-code/css-and-less-coding-standards)
