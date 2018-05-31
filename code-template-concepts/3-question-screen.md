# 3 Question Screen

#### Code Template Concepts

## 3 Question Screen

### Objective

* Demonstrate that you understand how `javascript` can be used to process a list of question _objects_ and place content for each in the `html`. 

### Instructions

**1. The** `html` **and** `css` **for the question screen are very similar to the category screen.** Just copy the source below into a new [CodePen](https://github.com/cxd/trivia/tree/899184750e77f925563ea0d42b69ca6fbcd424b9/codepen.io/pen/README.md).

#### HTML

```markup
<!--   question screen   -->
   <div class='screen' id='question-screen' hidden>
      <div class='card'>
         <div id='question-screen-header'></div>
         <div id='answer-button-set'></div>
         <div id='question-screen-footer'></div>
      </div>
   </div>
```

#### CSS

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

**2. Copy the following** `javascript` **into your CodePen.** We will work with this in the next steps.

#### Javascript

```javascript
  var trivia = {};

  trivia.questions = [
     {
        category: "Programming",
        question: "What does the acronym JSON stand for?",
        correctAnswer: "JavaScript Object Notation",
        incorrectAnswer1: "Java SONar",
        incorrectAnswer2: "JavaScript Open Network",
        incorrectAnswer2: "Javas Semi Online Network" 
     },
     {
        category: "Programming",
        question: "What does the acronym CSV stand for?",
        correctAnswer: "Comma Separated Values",
        incorrectAnswer1: "Computer Sound Values",
        incorrectAnswer2: "Computer Science Values",
        incorrectAnswer2: "Color Saturated Voxels" 
     }
  ];

  var question = trivia.question[0];

  //place the html you want in the header of question screen
  $("#question-screen-header").html(`
        <h5>${question.category}</h5>
        <h1>${question.question}</h1>
    `);

  //create html buttons for answers
  var myAnswerButtons = [
    `<button class='answer correct-answer'>${question.correctAnswer}</button>`,
    `<button class='answer incorrect-answer'>${question.incorrectAnswer1}</button>`,
    `<button class='answer incorrect-answer'>${question.incorrectAnswer2}</button>`,
    `<button class='answer incorrect-answer'>${question.incorrectAnswer3}</button>`
  ];
  $("#answer-button-set").html(myAnswerButtons);
```

