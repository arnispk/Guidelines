# PHP coding standards

## Summary
This guide extends and expands on [PSR-1](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-1-basic-coding-standard.md), the basic coding standard and on [PRS-2](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md), the coding style guide, and defines the Netwerven development coding standards.

The intent of this guide is to reduce cognitive friction when scanning code from different authors. It does so by enumerating a shared set of rules and expectations about how to format PHP code.

### Overview
Code MUST follow all rules outlined in PSR-2 with the exceptions / additions described below.

### File Tags
Files not containing only PHP code SHOULD use only the short echo tag.

Example:
```html
This is my <?= $echo ?> Example
```

### Control Structures
Conditional Statements MUST NOT use alternative syntax;

MUST NOT example:
```html
<?php if ( have_posts() ) : while ( have_posts() ) : the_post(); ?>
<?php endwhile; endif; ?>
```

MUST example:
```html
<?php 
if (have_posts()) { 
    while (have_posts()) { 
        the_post();
    } 
} ?>
```

### Methods
The soft limit on method size SHOULD be maximum of 50 lines; automated style checkers MUST warn but MUST NOT error at the soft limit.

## Resources
[PRS-1 Coding Standards](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-1-basic-coding-standard.md)<br />
[PRS-2 Coding Standards](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md)<br />
[Requirement Level Rules](http://www.ietf.org/rfc/rfc2119.txt)
