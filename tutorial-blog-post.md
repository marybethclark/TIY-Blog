**The Amazing Color-Changing Card Flip Trick**

Today I will explain to you how to create a webpage with a colored card on it that will flip and change color after being flipped.

The first step will happen in your index.html file.
In the body section you will be creating an invisible checkbox. This is so that we can click on the colored card and have it actually respond, but not have a check box showing on the webpage.

The element tag needed for any element where the user will be interacting with the page is called "input". There are several different kinds of input, including a check box that can be clicked, a radio button that can be clicked, and a text box (where the user would type something into the box.)  In my tutorial I'll be using a checkbox.  The next step is to indicate what kind of input needs to be added. We do this by typing:

< input type= "checkbox".


Next, we need to assign our checkbox an attribute (such as id or class) and that attribute's value. Actually, on my webpage we won't ever need to make use of the checkbox's attribute, since my checkbox is invisible. But it's a good habit to get into assigning an id or class to your individual elements. That way if you do want to change the way they look on the page, you'll have a way to control them in your CSS stylesheet.  I chose to use an id and, for clarity's sake, I made the id for my checkbox be "checkbox". You can make it be whatever you word you want, but to avoid confusion later, why not make it a logical name?

On the next line you should assign a label tag to your check box. This would only be used by a visually impaired person. It would let them know what it was they were dealing with on the screen.

The "card" class is what we'll be using in our styles.css file to make the card look the way we want. Below is what you will have in the body section of your index.html file:

< body>

    < input type= "checkbox" id= "checkbox">
    < label class="card" for="checkbox"></label>
< /body>

In your styles.css file, you will first begin to build your card.  We do this by typing:

.card{

The first line- ".card" tells the CSS file "I'm about to tell you some things I want you to do to my card class that I set up in my HTML file." The opening curly bracket indicates the start of the styling information to be applied to that card class.  The period before the word class lets the CSS file know that it's a class we're referring to.  (A handy mnemonic device for remembering that "." and class go together is to think of the "class periods" in a school day schedule.)

 We want our card to be a square, so we need to give it a width and height that are equal to each other, such as 200 pixels, in my example. (If we just gave it a height value, it would show up as a long rectangle, extending across the width of the screen.)
Next, type:

width:200px;
height:200px;

Next, we need to tell css what color to make the card (background).

Type:

background:steelblue;

NOTE: each css property, such as "background" and its chosen value, such as "steelblue", must be followed by a semicolon.

Next, tell css to display the card as a block.  Type:

display:block;

Now tell css how long to spend when it changes the background color and when it flips the card. (We haven't told it to do either of those things just yet. We're just setting it up.)
Type:

transition: background 1s, transform 1s;

This tells css, "When the time comes, spend 1 second changing the background color of the card and spend 1 second on the transformation (that I'll tell you about later.)

Now seal it up with a curly bracket } on the next line.

So far, your styles.css file should look like this:

.card{

  width: 200px;
  height: 200px;
  background: steelblue;
  display: block;
  transition: background 1s, transform 1s;
}

At this point, we're ready to tell css where that invisible checkbox should be hiding.  We want it to  be the exact size and location as our card, so that when someone clicks on any part of the card, the checkbox will be checked. To make the checkbox invisible, we give its property "display" a value of "none". ("Don't display it!")

Here's what to type.  Note that the element we use is "input", rather than the class of "checkbox"..

input{
  width: 200px;
  height: 200px;
  display: none;
}

And finally, tell the css file what to do when the invisible checkbox has been clicked.  You'll link that action to the card class with a plus sign (+), since the card is what will be affected by the click.  Check the invisible checkbox is checked, the card's background color will become light coral, and it will rotate on it's vertical (Y) axis.  Here's what to type;

input:checked + .card{
  background: lightcoral;
  transform: rotateY(180deg);
}

If all is correct, you show now have a lovely blue square that flips over to a coral square when clicked!
