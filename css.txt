# CSS Study:

## The priorities:
1. Inline CSS
2. Embeded CSS
3. External CSS file
(External and Embeded are same, depends on which one are later applied.)

## Child css always inhert from parent css, if it has no css.

## Styles are cumulative. if no conflict.

## Specification
www.w3.org/Style/CSS/Current-work
www.w3.org/TR

## Checking Browser support
http://caniuse.com/#cats=CSS
http://quirksmode.org/compatibility.html
http://en.wikipedia.org/wiki/Comparison_of_layout_engines_(Cascading_Style_Sheets)

## Web Fonts
@font-face {
  font-family: "fontName";
  src: url('fontName.eot');
}

## Font
* Text transform
h3 {font-variant: small-caps;}
h2 {text-transform: uppercase;}
* text-indent: xx
* letter-spacing
* line-height: x Times than the font.

## Box model
total width = left, right border & padding + content width.

## Vertial margin collapse
====
x
=2=== <--- this won't be works.
=4=== <-- will apply the larger one.
y
====

## width 100% only for content width, not included Padding width.

## OutLINE is poor overall support. and doesn't count in the width.

## CSS has gradient background color

## color:
red, #ffeeff ,rgb(x,x,x)

## { opacity: 0.5; }

## css3 support hsla

## Units:
* Absolute values
in, cm, mm, pt, pc

* Relative values
em, ex, px, gd, rem, vw, vh, vm, ch

## Positioning schemes
* Normal flow
* Element floating
* Absolute positioning

## Floating
* How the width of parent elements affect the floating ability of nested elements.
* Research how margins work between floated elements and static elements.
* How floated elements affect their parents.
* Look into the best practices that have evolved around floats.

## HTML5 new tags for layout
header, nav, article, aside, footer

## Vendor prefixs - indicate the property is experimental
* -ms- Microsoft
* -moz- Mozilla
* -o- Opera
* -khtml- Konqueror
* -webkit- Webkit

## Reset Revisited
http://meyerweb.com/eric/thoughts/2011/01/03/reset-revisited/
http://cssreset.com

## CSS Framework
52framwork html5 + css3
baselinecss.com

## Online tools
css3generator.com
css3.me
css3please.com
layerstyle.org/builder.html
css3.mikeplate.com
css3maker.com
colorzilla.com/gradient-editor
westciv.com/tools/
* checker
validator.w3.org
csslint.net/

## other resources
alvit.de/handbook
css-tricks.com
reference.sitepoint.com/css

## Offset
$("x").offset() // Could get element *left*, *top*