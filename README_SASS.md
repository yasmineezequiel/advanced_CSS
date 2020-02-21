SASS: is a css pre-processor, an extension of CSS that adds power and elegance to the basic language. 

Sass features
Variables: for reusable values such as colors, font-sizes, spacing...
Nesting: to nest selectors, less code.
Operators: mathematical operation
Partials and imports: to write CSS in different files and importing them all into one single file.
Mixins: to write reusable pieces of css code.
Functions: similar to mixins but produces a value that can be than used 
Extends: different selectors inherit declarations that are common to all of them
Control directives: for writing complex code using conditionals and loops.

Sass syntex ex:
.navigation
    list-style: none
    float: left

    & li
    display: inline-block
    margin-left: 30px
// is indentation sensitive and no use of curly brackets nor semi-columns


SCSS syntax ex:
.navigation {
    list-style: none;
    float: left;

    & li {
    display: inline-block;
    margin-left: 30px;
    }
}
//preserves the way that original css syntex looks like

// In this example I am using variables, nasting, mixins, functions and placeholder in order to understand sass functionalities.
* {
  margin: 0;
  padding: 0;
}

$color-primary: #f9ed69; // yellow
$color-secondary: #f08a5d; // orange
$color-tertiary: #b83b5e; // pink
$color-text-dark: #333; // dark gray
$color-text-light: #eeeeee; // light 
$width-button: 150px;

// sass mixin can be reused in order not to repeat styling code with passing @include "variable name" syntex:
    @mixin clearfix {
    &::after {
    content: "";
    clear: both;
    display:table;
   }
}

// sass mixin can be reused in order not to repeat styling code with @include "variable name" syntex:
 @mixin style-link-text($col) {
  text-decoration: none;
  text-transform: uppercase;
  color: $col;
}

// sass is possible to make calculations with functions ex:
@function divide($a, $b) {
  @return $a /$b;
}

// using the function
nav {
  margin: divide(60, 2) * 1px; // 30px
  background-color: $color-primary;
  @include clearfix;
}


.navigation {
  list-style: none;
  float: left;
  
  li {
    display: inline-block;
    margin-left: 30px;
    
    &:first-child {
      margin: 0;
    }
    
    a:link {
      @include style-link-text($color-text-dark);
    }
  }
}

.buttons {
  float: right;
}
//Placeholder example with passing syntex @extend eliminating extra code. Placeholders are used when the elements or selectors are related.
%btn-placeholder {
  padding: 10px;
  display: inline-block;
  text-align: center;
  border-radius: 100px;
  width: $width-button;
  @include style-link-text($color-text-light);
}

.btn-main {
  &:link {
    @extend %btn-placeholder;
    background-color: $color-secondary;
  }
  &:hover {
    background-color: darken($color-secondary, 10%);
  }
}

.btn-hot {
  &:link {
    @extend %btn-placeholder;
    background-color: $color-tertiary;
  }
  &:hover {
    background-color: darken($color-tertiary, 10%);
  }
}