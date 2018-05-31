# Add Image as Part of the Question

This is very similar to the instructions for adding a background image to questions. These instructions will lead you through the steps to add an image for each question. You could have a unique image for each question or just some of them. It's up to you. You will see how to use Javascript to edit the style \(CSS\) of HTML elements programatically.

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

In your questions spreadsheet, add a new column for image file names that you want displayed for each question. See the example below with a `questionImage` column. Then add image file names for the questions. You don't have to have an image for every question. You may choose to leave some questions with an empty `questionImage` cell.

| id | category | questionImage | question | correctAnswer | incorrectAnswer1 | incorrectAnswer2 | incorrectAnswer3 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | Seasons Change | anemometer.png | What is this? | anemometer | wind mill | photometer | thermometer |
| ... | ... | ... | ... | ... | ... | ... | ... |

## 4. Add HTML for Image

Add the following tag to your `HTML` just after your question `div`tag. You can place it somewhere else if you like, but this is a reasonable spot.

```markup
<img class='question-image' id='question-image'>
```

## 5. Add JS code to the `displayQuestion()` function.

Add the following line of code to the top of the `displayQuestion()` function to have the image fill the background of the whole screen.

```javascript
  if (question.questionImage) {
    $("#question-image").attr("src","images/" + question.questionImage).show();
  } else {
    $("#question-image").hide();
  }
```

## 6. Modify CSS

You will want to style your image in `CSS`. For example, at the least, you probably want to limit how large your image will be using something like `max-width`.

```css
.question-image{
  max-width: 100px;
}
```

