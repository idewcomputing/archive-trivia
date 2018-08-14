# Code Template

The HTML/CSS/JavaScript + Spreadsheet templates ease the process of building the trivia game web app. The source files can be found [here on GitHub](https://github.com/idewcomputing/trivia).

Learn the basic usage of the templates in the *getting started* reference below. You can also find [some code examples](CodeExamples/README.md) for more trivia mods.

This is a work in progress that is rough around the edges. But the library is actively used by high school students to code their own trivia web apps.

### Getting Started

Use the following instructions to get started using the Editey code editor in Google Drive. Be aware that updates to Editey and Google Drive may require you to adapt. You can also [access the full GitHub repository](https://github.com/idewcomputing/trivia).

1. Download [this zipped folder](https://github.com/idewcomputing/trivia/raw/master/triviaMin.zip) to your computer for the minimum trivia code. Or use [this zipped folder](https://github.com/idewcomputing/trivia/raw/master/trivia.zip) for trivia code with a few more features.
2. Unzip (or extract all files) the folder on your computer. Try a right-mouse click on the zipped folder.
3. From your google drive select ‘NEW’ button then ‘folder upload’.
4. Find the unzipped folder called ‘myTriviaApp’ and start the upload.

 **You should see the ‘myTriviaApp’ folder in your google drive now.**
 
5. Open the ‘myTriviaApp’ folder in google drive.
6. Select the ‘NEW’ button, then ‘more’, then ‘Connect More Apps’.
7. Search for ‘editey’ and the push the ‘+ connect’ for Editey (the one in Red).
8. Click ‘OK’ once it is connected.
9. Back in the Google drive folder ‘myTriviaApp’ select the ‘NEW’ button, then ‘more’, then “Editey”.
10. Once Editey starts up select “Allow” and agree to terms. (This may take some time to load)
11. When asked to choose files for the workspace, select all .html, .css, and .js files.

You should be set to try out the Trivia Game!!!!! As you play with it consider what you think could be done better. Whether the graphics, gameplay, feedback, or the questions themselves.

Code Visuals: [HTML/CSS](https://drive.google.com/open?id=1HJ5c7owhhRQNsuLgDIxp94Uuz1m4E1VWnDZyhxdMTlk), [HTML/JS](https://drive.google.com/open?id=1RuUpvW77U8sqtLzZljrRGztXCHcJKFOd-f5CYoh_KKI)

Code Explanation Videos: [HTML](https://drive.google.com/open?id=0B78R6qBzYFtZWnVMQ3BZNHB6YjQ), [CSS](https://drive.google.com/open?id=0B78R6qBzYFtZSjdLNzhjWnVmc3M), [JS](https://drive.google.com/open?id=0B78R6qBzYFtZZlNMNFdWS3BfS1E) 

###Converting the Spreadsheet to a JS Question Bank
Once you have edited the question spreadsheet with your own questions and multiple-choice answers, you can convert them to JS to use in your app.

1. Download your questions spreadsheet as a “CSV” file (comma-separated values). You will find this under ‘File > Download As’ in your Google Sheets document. 
2. Go to http://www.csvjson.com/csv2json and upload your csv file as instructed on the page. 
3. Then click the right arrow to convert your questions to a JSON object. Copy the JSON text (Click in the JSON Text Area then use Ctrl + A then Ctrl + C to copy to clipboard). 
4. Then open the questions.js file in your code folder using Editey and replace the questions in the questionBank variable with your JSON text. **Important:** The question.js file should start with var questionBank=  followed by your questions that should begin with a   [    and end with a    ]   .
5. Refresh your trivia app in Edity and you should see your questions and categories in the game.

