# minesweeper
Developed an AI for minesweeper game using python and pygame module.
How to play :
run runner.py by "python3 runner.py"


Minesweeper is a puzzle game that consists of a grid of cells, where some of the cells contain hidden “mines.” 
Clicking on a cell that contains a mine detonates the mine, and causes the user to lose the game.
Clicking on a “safe” cell (i.e., a cell that does not contain a mine) reveals a number that indicates how many neighboring cells – where a neighbor is a cell that is one square to the left, right, up, down, or diagonal from the given cell – contain a mine.

We represent an AI’s knowledge about a Minesweeper game is by making each cell a propositional variable that is true if the cell contains a mine, and false otherwise.
The AI would know every time a safe cell is clicked on and would get to see the number for that cell.

There are two main files in this project: runner.py and minesweeper.py. minesweeper.py contains all of the logic the game itself and for the AI to play the game. 
runner.py contains all of the code to run the graphical interface for the game. 

Let’s open up minesweeper.py to understand what’s provided.
There are three classes defined in this file, Minesweeper, which handles the gameplay; Sentence, which represents a logical sentence that contains both a set of cells and a count; and MinesweeperAI, which handles inferring which moves to make based on knowledge.

The Sentence class will be used to represent logical sentences of the form described in the Background.
Each sentence has a set of cells within it and a count of how many of those cells are mines.
The class also contains functions known_mines and known_safes for determining if any of the cells in the sentence are known to be mines or known to be safe.
It also contains functions mark_mine and mark_safe to update a sentence in response to new information about a cell.

Finally, the MinesweeperAI class will implement an AI that can play Minesweeper.
The AI class keeps track of a number of values. self.moves_made contains a set of all cells already clicked on, so the AI knows not to pick those again.
self.mines contains a set of all cells known to be mines.
self.safes contains a set of all cells known to be safe.
And self.knowledge contains a list of all of the Sentences that the AI knows to be true.

Note : When you run your AI (as by clicking “AI Move”), note that it will not always win!
There will be some cases where the AI must guess, because it lacks sufficient information to make a safe move. 
This is to be expected. runner.py will print whether the AI is making a move it believes to be safe or whether it is making a random move.
