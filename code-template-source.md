# Code Template Source

There are three files in the code template, `index.html` `style.css` and `code.js`. Below you will find the complete source for each of these files.

## index.html

Notice the sections for the category screen and question screen. You will find no trivia content inside the tags since we will fill that in with Javascript. You will likely not need to make many changes to the html. If you do make changes, do so with care.

```markup
<!DOCTYPE html>
<html>

<head>
   <meta charset="UTF-8">
   <title>Trivia 2.0</title>
   <link rel="stylesheet" href="style.css">
</head>

<body>
   <!--   category screen   -->
   <div class='screen' id='category-screen' hidden>
      <div class='card'>
         <div id='category-screen-header'></div>
         <div id='category-button-set'></div>
         <div id='category-screen-footer'></div>
      </div>
   </div>
   <!--   question screen   -->
   <div class='screen' id='question-screen' hidden>
      <div class='card'>
         <div id='question-screen-header'></div>
         <div id='answer-set'></div>
         <div id='question-screen-footer'></div>
      </div>
   </div>
   <!--   Javascript libraries   -->
   <script src='https://cdnjs.cloudflare.com/ajax/libs/tabletop.js/1.5.1/tabletop.min.js'></script>
   <script src='https://code.jquery.com/jquery-2.2.4.min.js'></script>
   <script src='https://cdn.jsdelivr.net/gh/idewcomputing/utilities@0.2/trivia/trivia.js'></script>
   <script src='code.js'></script>
</body>

</html>
```

## style.css

Here we have some basic styling for the trivia app to get you started. You will likely make many changes to this file.

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

.next-button {
   color: white;
   background-color: black;
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

## code.js

While this code looks quite complicated at first glance, you will be able to understand it and make edits to customize your game. We will provide help on making modifications to add fun features to your game.

```javascript
/// iDEW Trivia Template 2.1 (Fall 2018) - Dependency on `trivia.js` utility library and tabletop.js library

window.onload = setup;

function setup() {
  var googleSheetLink = "1B3RFU17Y3gE7hcsarU81TM7FPudDTmt0OJz2vws4uw4";
  trivia.loadQuestionBank(googleSheetLink).then(displayCategoryScreen);
}

///////////// Functions Preparing the Display Output  ////////////////////

function displayCategoryScreen() {
  //hide all screens then show category screen
  $(".screen").hide();
  $("#category-screen").show();

  //place the html you want in the header of category screen
  $("#category-screen-header").html(`
      <h2>Charlie Photon's No Phun Yet Trivia Template</h2>
      <h3>Choose a category</h3>
    `);

  //create an html button for each category and append to category-button-set
  $("#category-button-set").html("");
  trivia.categories.forEach(cat => {
    var disabledText = '';
    if (!trivia.getUnansweredQuestionFromCategory(cat)) disabledText = "disabled";
    var btn = `<button class='category-button' onclick='onClickedCategory("${cat}");' ${disabledText}>${cat}</button>`; 
    $("#category-button-set").append(btn);
  });

  //place some data at the bottom about how many questions have been answered so far
  var metrics = `${trivia.countAnsweredQuestions()} of ${trivia.countAllQuestions()} questions answered.`;
  $("#category-screen-footer").html(metrics);
}

function displayQuestionScreen(question) {
  trivia.currentQuestion = question; //keep track of current question

  //hide all screens then show question screen
  $(".screen").hide();
  $("#question-screen").show();

  //place the html you want in the header of question screen
  $("#question-screen-header").html(`
        <h5>${question.category}</h5>
        <h1>${question.question}</h1>
    `);

  //create html buttons for answers
  var myAnswerButtons = [
    `<button class='answer correct-answer' onclick='onClickedAnswer(true);'>${question.correctAnswer}</button>`,
    `<button class='answer incorrect-answer' onclick='onClickedAnswer(false);'>${question.incorrectAnswer1}</button>`,
    `<button class='answer incorrect-answer' onclick='onClickedAnswer(false);'>${question.incorrectAnswer2}</button>`,
    `<button class='answer incorrect-answer' onclick='onClickedAnswer(false);'>${question.incorrectAnswer3}</button>`
  ];
  $("#answer-button-set").html(trivia.getShuffledArray(myAnswerButtons)); //*shuffle answers

  //create html button for 'next' and hide for now
  $("#question-screen-footer").html(`<button class="next-button" onclick="onClickedNext()">Next</button>`);
  $("#question-screen-footer").hide(); // hide until after answer click
}

////////////// Functions Called by Trivia Events ///////////////////

function onClickedCategory(category) {
  trivia.currentCategory = category;
  var question = trivia.getUnansweredQuestionFromCategory(category);
  if (question) displayQuestionScreen(question);
}

function onClickedAnswer(isCorrect) {
  trivia.currentQuestion.wasCorrectResponse = isCorrect;
  $("#question-screen-footer").show(); //shows next button
  if (isCorrect) $("#question-screen-footer").append("Nice job!");
  else $("#question-screen-footer").append("Better luck next time!");
  $(".correct-answer").css("background-color", "#dfd");
}

function onClickedNext() {
  var nextQ = trivia.getUnansweredQuestionFromCategory(trivia.currentCategory);
  if (nextQ) displayQuestionScreen(nextQ);
  else displayCategoryScreen();
}
```

