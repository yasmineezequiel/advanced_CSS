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