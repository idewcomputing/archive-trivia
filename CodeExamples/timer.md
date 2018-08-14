# Add a Countdown Timer to Questions
**!! Dependency: idewTrivia 1.3 or higher**
{% method -%}
###Add HTML Element to Display Timer
You will want to format your timer as you want, but use a descriptive *id* like ```timer```. Add the HTML inside your ```question-screen``` div element.
{% common %}
**HTML**
```
Time Remaining: <span id='timer'></span>
```
{% endmethod %}

{% method -%}

###Add JavaScript Timer Variable to the Top of App Code 
Add a variable timer to the top of your code just below ```var triva```. This creates a 'global' variable that all functions can access.
{% common %}
**JS**
```
    var timer;
```
{% endmethod %}

{% method -%}
###Add JavaScript to *gotoQuestionScreen* Function
Add JavaScript for the timer inside (and at the top of) the ```gotoQuestionScreen()``` function.
{% common %}
**JS**
```
    var time = 5;//set your timer in seconds
    $('#timer').html(time);
    if (timer) clearInterval(timer);
    timer = setInterval(function() {
        time = time - 1; //count up by 1
        $('#timer').html(time);
        if (time == 0) {
            trivia.timeExpired();
            clearInterval(timer);//resets timer
        }
    }, 1000); //in milliseconds = 1 second increment for timer increment for timer
```
{% endmethod %}
{% method -%}
###Add JavaScript to *onAnswer* Function
Add JavaScript to stop the timer inside (and at the top of) the ```onAnswer()``` function. This stops the timer when somebody selects an answer
{% common %}
**JS**
```
    clearInterval(timer);
```
{% endmethod %}

