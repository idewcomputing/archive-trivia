# Code Template

<iframe style="border: 1px solid #555" width="500" height=" 400" src="https://9160006df4df4eda947727d9f16914bc.codepen.website"></iframe>

### Getting Started with the Base Code

**Option 1 with CodePen**

1. Login to [CodePen](https://codepen.io).
2. Go to [this project](https://codepen.io/jlyst/project/editor/ZKoJvZ/#).
3. Click the `fork` button at the top to make a project copy in your CodePen account.

**Option 2 with a Common Code Editor (like Editey in Google Drive)**

1. In your code folder create empty `index.html`, `style.css`, and `code.js` files. (Specific Editey Instructions on setting up an empty project can be found [here](https://docs.google.com/document/d/1eWraL0zTOZNGMtN_OL4FThP-lA0TzqHsF0KtQ53L_JQ/edit?usp=sharing).)

2. Copy the corresponding code from [the CodePen project](https://codepen.io/jlyst/project/editor/ZKoJvZ/#) into each of the files using your code editor.

**Option 3 ... just give me the files**
Dowload the latest version of the trivia app files from [this folder](https://drive.google.com/drive/folders/1P1lA98qVEmzh7v6ofy74OrTX4RkzFDlW?usp=sharing).

> ##### Preview the trivia game to ensure that it is working for you with the sample questions.


### Next create your own question database in Google Drive and connect it to your trivia app.
1. Login to Google Drive.
2. Go to [this spreadsheet](https://docs.google.com/spreadsheets/d/1r58warugRYIwFIAkH2rk4h7OboZnDe1l5C23EXn4nY0/edit?usp=sharing).
3. Create your own copy of the spreadsheet by selecting `File > Make a copy...`.
4. Now publish your copy of the spreadsheet by selecting `File > Publish to the web...` and click the `Publish` button.
5. Once your spreadsheet is published, click the `share` button (upper right-hand side) of the spreadsheet page and copy the shareable link. (Make sure your link is set to `Anyone with the link can view`.)
6. Find the code below in your CodePen project `code.js` file. It is near the bottom. Replace your link as the `key`.
```js
function setup() {
	Tabletop.init({
		key: "https://docs.google.com/spreadsheets/d/14z4Irs400-SEr9Enn_y6G-2t0p6b-fhxmzUtJNQphO4/edit?usp=sharing",
		callback: data => {
			var questionBank = getShuffledArray(data["Sheet1"].elements); //shuffle question order
			main(questionBank);
		}
	});
}
```

7. Verify that you can make changes to the questions in your spreadsheet and see those changes in your trivia app.  If using CodePen, click `Save All + Run`. If using Editey in Google Drive, click the preview window's refresh button.



---