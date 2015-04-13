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
* meaningfull use of whitespace (CSS Ruleset)
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

In addition meaningfull whitespace may be used according these rules:

* Properties are grouped by type.
  1. Box
  2. Border
  3. Background
  4. Text
  5. Other

An empty line may follow after each type of property for readability. (especially wiht the use/need of web-prefixes)

### Comments
To be added (when to use '//' vs '/*' i.e. Can be found in SMACCS)

## Architecture
There is a lot to say about different CSS architectures and its advantages/disadvantages comparing to each other. But in general there are guidelines that apply to all of them. Even most of the frequently used Frameworks use some kind of architecture and though not every Framework will fit in neathly with a modularized architecture; with these guidelines, even Frameworks can be easily fit into this architecture. <br />
(And if not, you won't want to use this Framework anyway).

### Categories
Categorize your stylesheets. As in many architectural patterns, their are more ways to build the Pathenon, but two preferred methods are:

1. Base
2. Layout
3. Module
4. State
5. Theme

(SMACCS-approach)

1. base/
2. components/
3. layout/
4. pages/
5. themes/
6. utils/
7. vendors/

(7-to-1 Pattern using SASS)

As you can see, categorizing is slightly arbitrary. One might say "pages" and "vendors" belong to "modules", where others might say that the category "module" is way to general to actually stick to. What stands out however is that both classifications implicate the use of separate files that each are responsible for the styling of only one particular part of your application. In extremis this is applicable to all code within the whole project. (You might even implicate this architecture stands the ground for MVC's such as Angular and/or BEM-projects as well).


### Sample Directory Structure
*SMACCS*
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
*7-to-1*
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
