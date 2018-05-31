# Add Changing Background Images

These instructions will lead you through the steps to add unique background images for each question. You could have a unique image for each question or for each category. It's up to you. You will see how to use Javascript to edit the style \(CSS\) of HTML elements programatically.

## 1. Find or create the images you want to use.

File types like `.png`, `.gif`, or `jpg` are best. Give your images short but descriptive names. It will make things easier later.

## 2. Place files in an `images` folder

Place your image files in an `images` folder within your trivia app folder. Your file structure should look something like the following.

> * index.html
> * style.css
> * code.js
> * **sounds**
>   * correct.mp3
> * **images**
>   * myImage1.png
>   * myImage2.png

## 3. Modify your questions spreadsheet

In your questions spreadsheet, add a new column for image file names that you want displayed for each question. See the example below with a `backgroundImage` column. Then add image file names for the questions. You don't have to have an image for every question. You may choose to leave some questions with an empty `backgroundImage` cell.

| id | category | backgroundImage | question | correctAnswer | incorrectAnswer1 | incorrectAnswer2 | incorrectAnswer3 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | Seasons Change | seasons.png | Why is it hotter in the summer than the winter? | Earth's Tilt | Earth's Distance from the Sun | El Nino | Winter has More Clouds |
| ... | ... | ... | ... | ... | ... | ... | ... |

## 4. Add HTML Wrapper Element

We need to "wrap" the trivia app in an HTML element so that we can modify the background image as needed. Add the following code just after the opening `<body>` tag.

```markup
<div class='wrapper'>
```

Then add the following code just before the closing `</body>` tag. \(Actually, to keep things visually organized, you can place it a bit higher -- just before the `script` tags for the Javascript libraries.\) This "closes" our wrapping element to enclose all visible html elements.

```markup
</div>
```

## 5. Add JS code to the `displayQuestion()` function.

Add the following line of code to the top of the `displayQuestion()` function to have the image fill the background of the whole screen.

```javascript
  if (question.backgroundImage) {
    $(".wrapper").css("background","url(images/" + question.backgroundImage + ")");
    $(".wrapper").css("background-size", "cover");
    $(".wrapper").css("background-repeat", "no-repeat");
  } else {
    $(".wrapper").css("background", "none");
  }
```

## 6. Add JS code to the `displayCategories()` function.

Add the following line of code to ensure that the background image is cleared from the previous question view if the user is sent back to the category screen.

```javascript
$(".wrapper").css('background', 'none');
```

You will likely want to make modifications to the code to get the style just how you want. Use [this W3schools link](https://www.w3schools.com/css/css_background.asp) for help.

