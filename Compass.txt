# Auto translate command-line
* Single file:
sass --watch input.scss:output.css
* whole folder:
sass --watch stylesheets/scss:stylesheets/compiled
stylesheets/sass/*.scss => stylesheets/compiled/*.css
## translate single file
sass input.scss output.css
# Variable
$company-blue: #1875e7;h1#brand { color: $company-blue;}
## Operations
(+, -, *, /, and %)
## Functions
lightness, hue, saturation
http://sass-lang.com/docs/yardoc/Sass/Script/Functions.html
e.g. $color = rgb(1,2,3)
## Interpolation
$side: top;
border-#{$side}-radius: $radius;
# Nesting
ul.nav { 
  float: right;  li {
    float: left; 
    a {      color: #111;    } 
    &.current {
      font-weight: bold;    }  }}
## Parent References
a {
  color: #ce4dd6; => a {}
  &:hover { color: #ffb3ff; } => a:hover {}
  &:visited { color: #c458cb; } => a:visited {}
}
a { @include link-colors(#333, $hover: #00f, $active: #f00, $visited: #555) }
# Mixin
@mixin big-link { a {xxx} }
#haeder {
  @include big-link
}
## Arguments
@mixin big-link($size: 10px) { a { size: $size } }
#haeder {
  @include big-link
  @include big-link(20px)
}
# @import
Used to import partials. 
like *_rounded.scss*
---
@mixin rounded {}
---
In other scss file, you can:
@import "rounded";
#nav {@include rounded;}
# Selector Inheritance
.error { xxx }
.crucialError {
  @extend .error
  yyy
}
=>
.error, .crucialError { xxx }
.crucialError { yyy }
# Reference
http://sass-lang.com/docs/yardoc/file.SASS_REFERENCE.html