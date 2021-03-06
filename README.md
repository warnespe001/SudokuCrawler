Author
======
Spencer Warneke

Description
===========
This is a simple Python project that can solve relatively easy sudoku puzzles read either from user input, or from the internet.

sudoku.py is the main sudoku solving backbone. It begins with an initial board state, and for each cell in the board,
it attempts to whittle down the number of possible values the cell could have until there is only one possibility left.
Unfortunately, this approach does not work for all sudoku puzzles, so I'll likely have to make some revisions to the algorithm, 
like a branching prediction tree, or some other method of inferring cell values.

webCrawl.py uses sudoku.py as a module to solve sudoku puzzles from nine.websudoku.com. It uses a Selenium webdriver to grab the initial board state, solve the puzzle, and then it will write the solution out to the puzzle grid and press the "Finish" button.
It will do this on a loop, to the amazement of anyone standing nearby.

Dependencies
============
* Python 3
* Selenium
* Mozilla Firefox
	* If you use Chrome, you can change the `driver = webdriver.Firefox()` to `driver = webdriver.Chrome()`, although I haven't tested the behavior of this.
	
To Run
======
To solve puzzles from user input:

`<Python 3 Executable> sudoku.py`

This will prompt you for the board state from standard input. It's a chore, though, so be warned.

To solve puzzles from the internet:

`<Python 3 Executable> webCrawl.py`
