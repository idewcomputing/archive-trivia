# Use Category Images for Question Screen Background
**!! Dependency: idewTrivia 1.2 or higher**

Instructions on how to use category images as your question screen background, like below. 

![](catImageAsQuestionBackScreenShot.png)


{% method -%}
### Add Images to Code Folder and Image Names to Spreadsheet

* First place images in your code folder that you want to use. Then update your question bank spreadsheet by inserting a column labeled ```categoryImage```.  
* For each question place the name of the category image in the newly created column. 
* Remember to transform your spreadsheet into a JavaScript object for your ```questions.js``` file. 

{% common -%}
![](categoryImageSpreadsheetScreenShot.png)
{% endmethod %}


{% method -%}
### JS Code

* Once you have category image file names in your question bank, the variable ```trivia.categoryImage``` contains the image file name for the current question's category. 

{% common -%}
Add the highlight JS code to your ```gotoQuestionScreen()``` function.
![](catImageAsQuestionBackJS.png)
{% endmethod %}
