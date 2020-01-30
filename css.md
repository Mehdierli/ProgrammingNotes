## Explain the three main ways to apply CSS styles to a web page  
* inline style, which use style attribute with html tag
* use style tag within head tag.
* external style, which use link element to link to external style sheet.

## What is CSS selector? Name some.
* selector is use to select elements in html, and style it.
* selector are patterns used to select element that you want style.
* such as class selector, id selector, element selector, universal selector

## SASS(SCSS)/LESS
* sass is preprocessor to help us maintain css file easier.
* preprocessing the sass file and save it as normal css file.
* we use it because it let us write css easier, 
* the syntax of sass is stronger than css, such as it support nested selector.
* sass has some features such variable, mixinx, inheritance to let us write css easier.
+ variable 
    - variable could be reused in sass file, 
    - it start with $, ex. $primary-color:white; call $primary-color to use.
+ nested
    - such as html, tags are nested
    - sass could also nested
    '''
    nav{
        ul{
            margin:0;
        }
        a{
            margin:0;
        }
    }
    '''
+ module
    - could split sass into multiple scss files, import module: @use 'base'
+ mixin
    - usually use for vendor prefixes
    '''
    @mixin transform($property) {
        -webkit-transform: $property;
        -ms-transform: $property;
        transform: $property;
    }
    .box { @include transform(rotate(30deg)); }
    '''
## CSS box model/ box-sizing
+ box model 
    - is a box wrap around every html element
    - consist of margin, border, padding, content.
+ box sizing
    - define how the total width and height of an element be calculated.
    - content-box, its width and height property include content
    - border-box, its width and height property include padding, border and content

## CSS Flexbox
* flexbox is layout module, it is an container to help developers easier design the responsive layout.
* it is one dimension, we manipulate the row or the column

## CSS Grid
* it offer a grid based layout system, making desing web page easier.
* it is two dimension system, which means we manipulate the rows and columns.  

## CSS resetting
* resetting is a set of css rule for every html element.
* because each browser has its own default stylesheet, 
* with resetting could avoid cross-browser difference as much as possible.
* that means make you website looks same in every browser.

## What is a Grid System in CSS?
* relate to layout with rows and columns

## How would you approach fixing browser-specific styling issues
* use css resetting to reset its default behavior

## Describe pseudo-elements and discuss what they are used for 
* is a keyword that add to selector that let you style a specific part of the selected element.

## Responsive image in HTML5
* it will automatically fit the screen size.
* set its width and height property to get the effect.

## CSS position
* static, default value, positioned according to the normal flow of page
* relative, positioned relative to its normal position.
* fixed, positioned relative to the viewport, which means it will stay the same place even the page scroll
* absolute, position relative to its nearest positioned ancestor.
* sticky, positioned base on the page scroll. it toggle between relative and fixed base on the scroll position.

## CSS Z-index
* it specifies the stack order of element.

## Display:none vs visibility: hidden
* display none will remove the element, it doesn't take place.
* visibility hidden will hidden but still take place, it will leave empty space.

## What kind of grid system did u use before
* flex, grid, bootstrap.

## coding a website to be responsive vs using a mobile-first strategy
* when design a responsive website, we should be use mobile-first strategy.
* which means the smartphone or mobile device take high priority than the desktop。
* use media for desktop.

