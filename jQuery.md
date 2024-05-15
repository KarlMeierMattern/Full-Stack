> [!NOTE]  
> Highlights information that users should take into account, even when skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]  
> Crucial information necessary for users to succeed.

> [!WARNING]  
> Critical content demanding immediate user attention due to potential risks.

> [!CAUTION]
> Negative potential consequences of an action.

# jQuery  
jQuery is one of the most widely used JavaScript libraries in the world.  
In 2006 when it was released, all major browsers handled JavaScript slightly differently. jQuery simplified the process of writing client-side JavaScript, and also ensured that your code worked the same way in all browsers.  
In this course, you'll learn how to use jQuery to select, remove, clone, and modify different elements on the page.  

- Code you put inside a function will run as soon as your browser has loaded your page.  
- This is important because without your `$(document).ready(function()` your code may run before your HTML is rendered, which would cause bugs.  
- All jQuery functions start with a `$`, usually referred to as a dollar sign operator, or as bling.  
- jQuery often selects an HTML element with a selector, then does something to that element.  
- jQuery's `.addClass()` function allows you to add classes to elements.  

      <script>
        $(document).ready(function() {
          $("button").addClass("animated bounce");
        });
      </script>
- Target the element with class `well` and adds class `animated shake` to them.  

        $(".well").addClass("animated shake");
- Target the element with the id `target3` by using the `$("#target3")` selector.  

        $("#target3").addClass("animated fadeout");
- You can remove classes with jQuery's `removeClass()` function.  

        $("button").removeClass("btn-default");
- jQuery has a function called `.css()` that allows you to change the CSS of an element. This is slightly different from a normal CSS declaration, because the CSS property and its value are in quotes, and separated with a comma instead of a colon.  

        $("#target1").css("color", "blue");
- jQuery has a function called `.prop()` that allows you to adjust the properties of elements.

        // Disable all buttons
        $("button").prop("disabled", true);
- jQuery has a function called `.html()` that lets you add HTML tags and text within an element. Any content previously within the element will be completely replaced with the content you provide using this function.  

        // Rewrite and emphasize the text of a heading
        $("h3").html("<em>jQuery Playground</em>");
- jQuery has a function called `.text()` that only alters text without adding tags.

> [!NOTE]  
> Note that while the `<i>` tag has traditionally been used to emphasize text, it has since been adopted for use as a tag for icons.
> The `<em>` tag is now widely accepted as the tag for emphasis.  

- jQuery has a function called `.remove()` that will remove an HTML element entirely.  

        $("#target4").remove();
- jQuery has a function called `.appendTo()` that allows you to select HTML elements and append them to another element.  

        // move target4 from our right well to our left well
        $("#target4").appendTo("#left-well");
- jQuery has a function called `.clone()` that makes a copy of an element.  

        // Copy target2 from our left-well to our right-well using function chaining
        $("#target2").clone().appendTo("#right-well");
- jQuery has a function called `.parent()` that allows you to access the parent of whichever element you've selected.  

        // Give the parent element of the left-well element a background color of blue
        $("#left-well").parent().css("background-color", "blue")
- jQuery has a function called `.children()` that allows you to access the children of whichever element you've selected.  

        $("#left-well").children().css("color", "blue")
- The `.target:nth-child(n)` CSS selector allows you to select all the nth elements with the target class or element type.  

        // Select the 3rd element with the target class
        $(".target:nth-child(3)").addClass("animated bounce");
- You can target elements based on their positions using `:odd` or `:even` selectors. Note that jQuery is zero-indexed which means the first element in a selection has a position of 0. This can be a little confusing as, counter-intuitively, :odd selects the second element (position 1), fourth element (position 3), and so on.  

        $(".target:odd").addClass("animated shake");
- jQuery can target the body element as well.  

        // entire body fade out
        $("body").addClass("animated fadeOut");
        
        // entire body hinge
        $("body").addClass("animated hinge");










