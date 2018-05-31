# Add a Start Screen to Your App

## HTML

Add the `HTML` for your start screen like below. You could place it above your "category screen" code.

```markup
    <!-- ||||||||||||||  START SCREEN  ||||||||||||||| -->
    <div class='screen' id='start-screen' hidden>
      <div class='game-title'>Your Trivia App Title</div>
      <button class='start-button'>START</button>
    </div>
```

Modify \(**don't copy and past this code**\) the category screen `HTML` by simply adding `hidden` to the `div` tag as shown below. This will make the category screen hidden by default in the beginning.

```markup
<div class='screen' id='category-screen' hidden>
    <div class='game-title'>Charlie Photon's No Phun Yet Trivia Template</div>
    <div class='instructions'>Choose a cateogry...</div>
    <div class='category-set'></div>
  </div>
```

## Javascript

Replace the statement `displayCategories(questionBank);` in your `main` function with the following statement.

```javascript
displayStartscreen(questionBank);
```

Add the following function above your `function displayCategories(qBank)`.

```javascript
/**
 * Display start screen.
 */
function displayStartscreen(qBank) {
  $("#start-screen").show();
  $('.start-button').click(function () {displayCategories(qBank);$("#start-screen").hide();});
}
```

## CSS

Style your start screen how you like.

