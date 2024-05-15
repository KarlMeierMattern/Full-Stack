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
- 






