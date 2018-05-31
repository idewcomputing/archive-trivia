# 1 Category Screen HTML & CSS

## 1 Category Screen HTML & CSS

### Objective

Demonstrate that you understand how the category screen is displayed and styled using `html` and `css`.

### Instructions

**1. Copy the following** `html` **into a new** [**CodePen**](https://github.com/cxd/trivia/tree/899184750e77f925563ea0d42b69ca6fbcd424b9/codepen.io/pen/README.md)**.**

```markup
   <!--   category screen   -->
   <div class='screen' id='category-screen' hidden>
      <div class='card'>
         <div id='category-screen-header'></div>
         <div id='category-button-set'></div>
         <div id='category-screen-footer'></div>
      </div>
   </div>
```

The category screen is the first screen the player sees in the game and will offer a choice of question categories for selection. Notice the `html` elements for the header, buttons, and footer.

**2. Insert custom content for the** _**header**_**,** _**category buttons**_**, and** _**footer**_**.** You can make up your own content to insert, but below are examples of modified `html` elements.

> #### Header Example
>
> ```markup
> <div id='category-screen-header'>Welcome. Choose a category.</div>
> ```
>
> #### Category Buttons Example
>
> ```markup
> <div id='category-screen-header'>
>    <button>Science</button>
>    <button>Art</button>
>    <button>Math</button>
>    <button>History</button>
> </div>
> ```
>
> #### Footer Example
>
> ```markup
> <div id='category-screen-footer'>Good luck!</div>
> ```

Notice how the output changes. Let's add a little style next.

**3. Copy the following** `css` **into the appropriate section of your CodePen.**

```css
body {
   margin: 0;
}

button {
   border: 3px solid #999;
   border-radius: 5px;
   background-color: #ddd;
   font-size: 18px;
   cursor: pointer;
   outline: none;
   display: block;
   margin-bottom: 10px;
}

.screen {
   box-sizing: border-box;
   background-color: #ccc;
   margin: 0px;
   padding: 15px 15px;
   width: 100%;
   min-height: 100vh;
}

.card {
   box-sizing: border-box;
   background-color: white;
   border-radius: 15px;
   margin: 0px auto;
   padding: 10px;
   width: calc(100%);
   max-width: 600px;
   min-height: calc(100vh - 30px);
   box-shadow: 3px 5px 5px #888888;
}
```

Make some changes to the styles to get a sense of what is possible.

### ✓ Standard Deliverable

Demonstrate a modified category screen with custom content and at least five noticeable style changes.

### ✓+ Advanced

Figure out how to add a custom font to your page using [Google fonts](https://fonts.google.com/) and demonstrate the result.

