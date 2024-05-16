# Saas  
"Syntactically Awesome StyleSheets" is a language extension of CSS.  
It adds features that aren't available in basic CSS, which make it easier for you to simplify and maintain the style sheets for your projects.  

- Sass uses variables that are declared and set to store data, similar to JavaScript. In Sass, variables start with a `$` followed by the variable name.  

        $main-fonts: Arial, sans-serif;
        
        h1 {
          font-family: $main-fonts;
        }
- In Sass, a mixin is a group of CSS declarations that can be reused throughout the style sheet.  
- The `@if` directive in Sass is useful to test for a specific case - it works just like the if statement in JavaScript.  

        @mixin border-stroke($val) {
            @if $val == light {
              border: 1px solid black;
            }
            @else if $val == medium {
              border: 3px solid black;
            }
            @else {
              border: none;
            }
          }
        
          #box {
            width: 150px;
            @include border-stroke(medium);
          }
- The `@for` directive adds styles in a loop and can be used in two ways: "start through end" or "start to end".  
- The main difference is that the "start to end" excludes the end number as part of the count, and "start through end" includes the end number as part of the count.

        // The #{$i} part is the syntax to combine a variable (i) with text to make a string.
        @for $i from 1 through 22 {
          .col-#{$i} { width: 100%/12 * $i; }
        }

        // When the Sass file is converted to CSS, it looks like this:
        .col-1 {
          width: 8.33333%;
        }
        
        .col-2 {
          width: 16.66667%;
        }
- Sass also offers the `@each` directive which loops over each item in a list or map.
- The `$key` variable is needed to reference the keys in the map.  

        @each $color in blue, red {
          .#{$color}-text {color: $color;}
        }

        // A map has slightly different syntax. Here's an example:
        $colors: (color1: blue, color2: red);
        
        @each $key, $color in $colors {
          .#{$color}-text {color: $color;}
        }

        // Both of the above code examples are converted into the following CSS:
        .blue-text {
          color: blue;
        }
        
        .red-text {
          color: red;
        }
- The `@while` directive is an option with similar functionality to the JavaScript while loop. It creates CSS rules until a condition is met.

        $x: 1;
        @while $x < 13 {
          .col-#{$x} { width: 100%/12 * $x;}
          $x: $x + 1;
        }
- **Partials** in Sass are separate files that hold segments of CSS code.  
- These are imported and used in other Sass files. This is a great way to group similar code into a module to keep it organized.  
- Names for partials start with the underscore (_) character, which tells Sass it is a small segment of CSS and not to convert it into a CSS file.  
- Also, Sass files end with the .scss file extension.  
- To bring the code in the partial into another Sass file, use the `@import` directive.  
- Underscore and file extension are not needed in the import statement as Sass understands it is a partial.  

        import the "_mixins.scss" into the "main.scss" file
        @import 'mixins'
- Sass has a feature called `@extend` that makes it easy to borrow the CSS rules from one element and build upon them in another.  

        .panel{
          height: 70px;
          border: 2px solid green;
        }
  
        // Extend the .panel properties, but also add a width property
        .big-panel{
          @extend .panel;
          width: 150px;
        }
