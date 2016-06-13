_Journal, Week 4_
=================


How to create a modal
======================
The jQuery code that creates a modal (popup box) on a webpage is very short and simple.  Here's the JavaScript code.

$( function () {
  "use strict";


  $("#button").on("click",function() {
    $(".modal").addClass("showing");
  });

  $("#background").on("click",function(){
    $(".modal").removeClass("showing");
  });

All jQuery functions begin with a dollar sign. The dollar sign means it's classified as a global variable, meaning that it can be applied to any function or script on the page. (I don't completely understand that concept yet.)

 The "use strict" function makes it so that any undeclared variables (without assigned values) will return an error message.


The next line says to consider the button id.  When it's clicked, run the following function. To the modal class in the html file, add a class called showing. (This class would need to have already been set up in your css file. When the webpage is first loaded, the modal class has a display set to none, so it's not visible on the page.)  When that function runs, the modal will become visible.  It's really cool to observe this happening using Inspect in Chrome.  You can see "class = "showing" magically appear in the html file as you click the button you created.

The final lines make it so that clicking anywhere in the background of the page (that's been given the id of "background") will remove the showing class that we gave to the modal.  It will disappear then, since its original display:none is in control.
