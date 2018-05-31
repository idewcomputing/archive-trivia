# 2 Category Screen Javascript

#### Code Template Concepts

## 2 Category Screen Javascript

### Objectives

* Demonstrate that you understand how `javascript` can be used to process a list of categories and place a button for each in the `html`. 
* Describe how the `javascript` code eliminates the need to manually create an `html` button for every new category and allows for easier changes by simply editing a single array.

### Instructions

**1. Insert the following** `javascript` **in the appropriate section of your CodePen from the last exercise.** But change the categories in the `trivia.categories` array to something new that isn't the same as your categories from the last exercise. Create at least 5 categories.

```javascript
//create a 'trivia' object
var trivia = {};

//create a categories array for the trivia object
trivia.categories = ["Computer Science", "Biology"];

//clear the category-button-set `html` element using an empty string ("")
$('#category-button-set').html("");

//use forEach() to iterate through each category in the array
trivia.categories.forEach(category => {
    //create a button for this category
    var thisButton = `<button>${category}</button>`;

    //append (add) the button to the appropriate `html` element
    $('#category-button-set').append(thisButton);
});
```

Your CodePen should now display a category screen with the category buttons listed in your array. Now let's do some experiments to understand the code a bit better.

**UNDERSTANDING .html\(\) AND .append\(\)**

**2. Add the following line to the very end of the code.**

```javascript
$('#category-button-set').html("I disrupt!");
```

Notice what the `.html()` function does. It _overwrites_ content in the `html` element with an id of 'category-button-set'.

**3. Change the previous line of code to the following.**

```javascript
$('#category-button-set').append("I disrupt!");
```

Notice how `.append()` just adds text to the end of the content of the `html` element.

> **Do you understand when and why** `.html()` **and** `.append()` **functions are used in the category screen javascript? Be prepared to discuss this.**

**4. Remove your "I disrupt" code line to return to normal.**

**UNDERSTANDING forEach\(\)**

**5. In the** `forEach()` **loop code, change "category" to "c" in the two places "category" is used.** Notice how your code still works as before. The first "c" \(was "category"\) found in `trivia.categories.forEach(c => {` defines the variable name for the current item in the array that can be used within the loop. The second occurrence of "c" \(was "category"\) found in `<button>${c}</button>` allows you to use the value of the current item as you want.

> **Do you understand how** `arrays` **and** `loops` **\(like** `.forEach()`**\) allow you to more easily program changes and handle large amounts of data? Be prepared to discuss this.**

#### UNDERSTANDING TEMPLATE LITERALS \(`back ticks` and `${}`\)

**6. Find the line of code shown below.**

```javascript
var thisButton = `<button>${category}</button>`;
```

Two things to notice.

* The `${...}` syntax allows you to insert a variable value in a string. This is a nice 'template' feature in javascript that is pretty easy to read when coding.
* You must use back ticks \(\` \`\) instead of single or double quotes to use this templating feature. The back tick key is found in the upper-lefthand corner of your keyboard.

Try changing the back ticks to single quotes or removing the `$` to see how this will "break" the code.

### ✓ Standard Deliverables

* Demonstrate working code.
* Explain how arrays and loops work and how they can make working with large data sets easier.

### ✓+ Advanced

Add an `onclick()` \([reference](https://www.w3schools.com/jsref/event_onclick.asp)\) to your buttons that displays an `alert()` \([reference](https://www.w3schools.com/jsref/met_win_alert.asp)\) message when clicked.

