### example 1:
Modify example 1, by adding a button so that when the page first loads, the heading says “Hello World”, but when the button is clicked, the heading changes to “Powered by the DOM”.

### example 2:
Modify Example 1 so that when the page first loads, the heading says “Hello World”, but when the mouse pointer is placed over the heading, the heading changes to “Powered by the DOM”, and when the mouse pointer is moved away from the heading, the heading changes back to “Hello World”.

### example 3:
Modify Lab Exercise 1, so that the button you added toggles the content
That is:
When the page first loads, the heading says “Hello World”
When the button is clicked, the heading changes to “Powered by the DOM”
And then when the same button is clicked again, the heading changes back to “Hello World”
Therefore, the button continues to toggle the content in that manner

### example 4:
Modify Lab Exercise 3, as explained below:
Add another button to the web page
When this button is clicked, the background should change to blue and the text to white
NB: this change should not apply to the text and the background of the buttons themselves but should apply to everything else
When the same button is clicked again, then the background should change back to white and the text to black
That is, the button toggles the behavior

### example 5:
Add functionality to the buttons in the example shown above so that each time the next button is clicked, the background color of the banner changes
And each time the previous button is clicked, the previous background color of the banner is shown
NB:
The colors the banner can change to should be at least 5, and the color changes should NOT be random – they should follow a consistent sequence


### Context: 
A website for an art gallery wants to showcase different art styles. Visitors can cycle through different art styles using provided buttons, and as they do, the background of the showcase banner and a descriptive header change.

### Section One: Layout
Instructions: Write the HTML layout for an art gallery showcase. The layout should consist of:

A banner (div) with an ID of "artShowcase" which initially displays the text "Renaissance Art".
Two buttons below the banner: One labeled "Previous Art Style" and the other "Next Art Style".
Your layout should resemble the following:


### Section Two: DOM Interactivity
Instructions: Using JavaScript, implement the following functionality:

The "artShowcase" banner has a list of five art styles: "Renaissance", "Baroque", "Impressionism", "Cubism", and "Abstract".
Clicking "Next Art Style" cycles forward through the list, and "Previous Art Style" cycles backward.
When the end or beginning of the list is reached, it should wrap around.

# Practice Exam Question: Dynamic Web Page Interaction

## Section One: Layout

Here's the HTML layout for the art gallery showcase:

```html
<div id="artShowcase">
    <h1>Renaissance Art</h1>
</div>
<div id="controls">
    <input type="button" value="Previous Art Style" onclick="changeStyle(-1)" />
    <input type="button" value="Next Art Style" onclick="changeStyle(1)" />
</div>
```

## Section Two: DOM Interactivity

Now, let's implement the JavaScript functionality to cycle through the art styles:

```javascript
let artStyles = ["Renaissance", "Baroque", "Impressionism", "Cubism", "Abstract"];
let currentStyleIndex = 0;

function changeStyle(direction) {
    currentStyleIndex += direction;

    // Ensure the index stays within the bounds of the artStyles array
    if (currentStyleIndex < 0) {
        currentStyleIndex = artStyles.length - 1;
    } else if (currentStyleIndex >= artStyles.length) {
        currentStyleIndex = 0;
    }

    document.getElementById("artShowcase").getElementsByTagName("h1")[0].innerText = artStyles[currentStyleIndex] + " Art";
}
```

To see this in action, you would need to combine the above HTML and JavaScript code in a single HTML document. When you load the page, you'll be able to click the "Previous Art Style" and "Next Art Style" buttons to cycle through the art styles.
