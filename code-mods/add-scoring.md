# Add Scoring

The following code will provide your trivia game with basic scoring by keeping track of how many questions have been attempted and how many questions have been answered correctly. These values can then be presented on the screen. Once you get this basic method working, you could consider modifying the code to create a percentage bar or another more interesting way to display the score. 

### HTML
Add `HTML` where you want the score to be visible. For example, you could place your score at the top of your question screen. Here is a simple `div` tag you could insert.

```html
<div id='score'></div>
```

### Javascript
Define a couple of global variables at the top of your `code.js` file to hold the number of questions answered (count) and number of correct answers (score).

```js
var count = 0;
var score = 0;
```

Find your Javascript function that listens for an answer click. Inside the `if` statement for a correct answer insert the following to increment the score up.

```js
score++;
```
At the bottom of the same function that listens for an answer click, insert the following to increment the total questions attempted and then display the score.

```js
count++;
$("#score").html("Score: " + score + "/" + count);
```
### CSS

Then style the display of the score as you like. For example, you could start with the following.

```css
#score {
  text-align: center;
}
```

---