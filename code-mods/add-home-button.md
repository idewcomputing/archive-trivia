# Add Home Button

## HTML

Add the button HTML where you want.

```markup
<button id="home">Home</button>
```

## Javascript

Place the following just before the `$("#spinner").click...` in the `main` function. This assumes you have implemented the "start screen" modification. If not, you could replace the `displayStartscreen(questionBank)` with `displayCategories(questionBank)`.

```javascript
$("#home").click(function(){
    $("#question-screen").hide();
    $("#category-screen").hide();
    displayStartscreen(questionBank);
});
```

