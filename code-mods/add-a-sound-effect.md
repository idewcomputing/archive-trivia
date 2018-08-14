# Add a Sound Effect

We will use some very simple Javascript to add sounds to our trivia game. We will simple create a new audio object with one line of code and then use the `.play()` function when we want to play the sound.

###### Example of Basic Audio Code Syntax
```
var myAudio = new Audio("myAudio.mp3");
myAudio.play();
```

That looks easy, right? Let's get started and add a sound that plays when a player gets the correct answer.

### 1. Get the Audio File You Want to Use

- Find an audio file you want to use. `.mp3`, `.m4a`, and `.wav` files will work.
- Create a folder in your trivia app named `sounds`.
- Place your audio file in the `sounds` folder. Your app folder structure should look like the following.
    >- index.html
    >- style.css
    >- code.js
    >- **sounds**
    >    - correct.mp3

### 2. Create Your Audio Object in Code.js

Place the following code at the top of your `main` function with the other variables defined.
```
var correctSound = new Audio("sounds/correct.mp3");
```

### 3. Add the .play() Function in Code.js

Add the following code inside the `if (answerId == "correctAnswer")` [code block](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/block) so that it plays with a correct answer.

```
correctSound.play();
```

**That's it.** It should work. You can now similarly add a sound for incorrect answers and other events where you want a sound effect. Steps 1 and 2 are the same. You will just need to determine where to place the `.play()` function so that it plays at the right time.

---