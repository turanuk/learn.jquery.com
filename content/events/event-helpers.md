---
chapter : events
section : 5
title   : Event Helpers
attribution:  jQuery Fundamentals
---
## Event Helpers

jQuery offers two event-related helper functions that save you a few keystrokes.

### `$.fn.hover`

The `$.fn.hover` method lets you pass one or two functions to be run when the
`mouseenter` and `mouseleave` events occur on an element. If you pass one
function, it will be run for both events; if you pass two functions, the first
will run for `mouseenter`, and the second will run for `mouseleave`.

<div class="example" markdown="1">
### Note

Prior to jQuery 1.4, the `$.fn.hover` method required two functions.
</div>

<div class="example" markdown="1">
The hover helper function

    $('#menu li').hover(function() {
        $(this).toggleClass('hover');
    });
</div>

### `$.fn.toggle`

The `$.fn.toggle` method is triggered by the "click" event and accepts two or
more functions.  Each time the click event occurs, the next function in the
list is called.  Generally, `$.fn.toggle` is used with just two functions;
however, it will accept an unlimited number of functions.  Be careful, though:
providing a long list of functions can be difficult to debug.

<div class="example" markdown="1">
The toggle helper function

    $('p.expander').toggle(
        function() {
            $(this).prev().addClass('open');
        },
        function() {
            $(this).prev().removeClass('open');
        }
    );
</div>