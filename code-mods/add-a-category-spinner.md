# Add a Category Spinner

![](/CodeExamples/catSpinner.png)

### Add Image to Code Folder

1. Create a spinner image using [this Google drawing](https://drive.google.com/open?id=1gLv3QzHR0MHhWFtJSDtamb62IIMN8txyUMZR8oYehDg) as a start.
2. Once you have designed your spinner, export the Google drawing to a ```.png```.
3. Place the ```.png``` file in your code folder.  

 
### Add an Image Tag to your HTML  

Place an HTML tag like the one below to your `category screen` section.
    ```
    <img id='spinner' src='spinner.png'/>
    ```

### Add this CSS style 

```
#spinner {
    -webkit-transition: -webkit-transform 2s ease-out;
}
```

### JavaScript

**Add the following function to the bottom of your code.js file, but just above the `window.onload` line.**

```
//spinner code below

function rotateSpinner(deg) {
    var css = '-webkit-transform: rotate(' + deg + 'deg);';
    document.getElementById('spinner').setAttribute(
        'style', css
    );
}
```
**Add the following code just above the function that listens for a category button click `$(".category-set").on("click", ...`.** Your spinner will basically override your category buttons. It is up to you if you want to have both the spinner and buttons, or just the spinner.

```
$("#spinner").click(function() {
    //this.removeAttribute('style');
    var deg = 500 + Math.round(Math.random() * 500);
    rotateSpinner(deg);
    setTimeout(function() {
      if (deg % 360 < 90) {
        currentCategory = "Digital Agility"; //replace the category name
      } else if (deg % 360 < 180) {
        currentCategory = "Seasons Change"; //replace the category name
      } else if (deg % 360 < 270) {
        currentCategory = "Digital Agility"; //replace the category name
      } else if (deg % 360 < 360) {
        currentCategory = "Seasons Change"; //replace the category name
      }
      currentQuestion = getUnansweredQuestions(questionBank, currentCategory)[0];
      if (currentQuestion) {
        displayQuestion(currentQuestion);
        $("#category-screen").hide();
        rotateSpinner(0);
      }
      else {
        rotateSpinner(0);
        alert("Spin again. That category is finished.");
        
      }
    }, 3000); //wait additional 1 second after the spinner is done
  });

```

**\*Important\***
1. Replace the category names in the code above to match your categories.
2. If you have more than 4 categories, you will have to adjust the ```if``` and ```if else``` statements to match the angles of your spinner sections etc.


---

