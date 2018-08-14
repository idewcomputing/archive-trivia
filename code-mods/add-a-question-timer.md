# Add a Question Timer
Here are instructions on how to add a time limit for each question.

#### HTML
1. Add a `<div>` tag with `class = 'timer'` and `id = 'time'` on the line after your `<div>` tag for the question.
```html
<div class='timer' id='time'></div>
```
This simply defines a place on the screen for the timer. You can place it differently if you like.

#### Javascript

1. Add the following javascript at the end of the `displayQuestion()` function.
```js
   //timer
   var timeLimit = 3;
   $("#time").html(timeLimit);
   var timer = setInterval(() => {
      timeLimit--;
      $("#time").html(timeLimit);
      if (timeLimit == 0) $("#time").trigger("timeout");
   }, 1000);
   $(".answer-button, #time").on("click timeout", () => {
      clearInterval(timer);
   });
```
The above code does several things. It sets a time limit, displays the timer, starts the timer, sets a trigger event for timeout, and handles cleaning things up when we are done with the timer.

2. Find the following line in your existing code...
```js
$(".answer-button").on("click", (e) => {
```
... and modify it to be like this code.
```js
$(".answer-button, #time").on("click timeout", (e) => {
```
This change allows the timeout trigger to execute the same code that an answer click would. If we didn't do this the game would simply stop and not advance as usual.

#### CSS
1. Add the following to your stylesheet.
```css
.timer {
      font-size: 24px;
      text-align: center;
      color: purple;   
      pointer-events: none;
}
```
Feel free to change the styles.

#### Next Steps

You should have a working timer now. Once you verify everything is working, you can make modifications to change the position of you timer (HTML), the style (CSS), or function (JS). Of course you could get fancy with your timer visually and add sounds.  *Tick-tock...*

---