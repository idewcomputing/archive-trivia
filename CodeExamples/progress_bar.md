# Add a Progress Bar

{% method -%}
###Add HTML Element to Display Progress Bar
You will want to format your progress bar as you want, but use a descriptive *id* like ```category-progress```. Add the HTML inside your ```question-screen``` div element.
{% common %}
**HTML**
```
<div id='category-progress'>&nbsp;</div>
```
{% endmethod %}
{% method -%}
###Add CSS for a Background Color

{% common %}
**CSS**
```
#category-progress {
  background-color: blue;
}
```
{% endmethod %}
{% method -%}
###Add JS to the updateCategoryMetrics() function
We can calculate the progress. Divide the number of questions answered in a category by the number of question in a category. Then use that value to change the width of an element to simulate progress. 

You could also use ```trivia.successCount(category)``` divided by ```trivia.answeredCount(category)``` to create  a bar displaying a user's correct answer % in that category.
{% common %}
**JS**
```
$('#category-progress').css('width', trivia.answeredCount(category) / trivia.questionCount(category) * 100 + 3 + '%');
```
{% endmethod %}