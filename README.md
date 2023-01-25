# Minesweeper
This is a popular board game shipped with many operating systems by default. The goal of the game is to sweep all mines from a mine field. If the player clicks on the cell which contains a mine, the mine detonates and the game is over.

The game consists of two classes:
-  Board
-  Minesweeper.

Also, we have thirteen images in the src/resources directory.

There are thirteen images used in this game. A cell can be surrounded by maximum of eight mines, so we need numbers one through eight. We need images for an empty cell, a mine, a covered cell, a marked cell and finally for a wrongly marked cell. The size of each of the images is 15x15 px.

A mine field is an array of numbers. For example, 0 denotes an empty cell. Number 10 is used for a cell cover as well as for a mark. Using constants improves readability of the code.

The MINE_CELL represents a cell that contains a mine.

The COVERED_MINE_CELL is used for a field that is covered and contains a mine. The MARKED_MINE_CELLcode> is a covered mine cell that was marked by the user.

These contants determine whether to draw a mine, a mine cover, a mark, and a wrongly marked cell.

The minefield in our game has fourty hidden mines. There are sixteen rows and sixteen columns in the field. So there are two hundred and twenty-six cells together in the minefield.

The field is an array of numbers. Each cell in the field has a specific number. For instance, a mine cell has number 9. A cell with number 2 means it is adjacent to two mines. The numbers are added. For example, a covered mine has number 19, 9 for the mine and 10 for the cell cover and so on.

The minesLeft variable the number of mines to be marked left.

We load our images into the image array. The images are named 0.png, 1.png ... 12.png.

The newGame() initiates the Minesweeper game.

These lines set up the mine field. Every cell is covered by default.

In the while cycle we randomly position all mines in the field.

Each of the cells can be surrounded up to eight cells. (This does not apply to the border cells.) We raise the number for adjacent cells for each of the randomly placed mine. In our example, we add 1 to the top neighbour of the cell in question.

In the find_empty_cells() method, we find empty cells. If the player clicks on a mine cell, the game is over. 

If he clicks on a cell adjacent to a mine, he uncovers a number indicating how many mines the cell is adjacent to. Clicking on an empty cell leads to uncovering many other empty cells plus cells with a number that form a border around a space of empty borders. We use a recursive algorithm to find empty cells

In this code, we check the cell that is located to the left to an empty cell in question. If it is not empty, it is uncovered. If it is empty, we repeat the whole process by recursively calling the find_empty_cells() method.

The paintComponent() method turns numbers into images.

If the game is over and we lost, we show all uncovered mines if any and show all wrongly marked cells if any.

If there is nothing left to uncover, we win. If the inGame variable was set to false, we have lost.

In the mousePressed() method we react to mouse clicks. The Minesweeper game is controlled solely by mouse. We react to left and right mouse clicks.

We determine the x and y coordinates of the mouse pointer.

We compute the corresponding column and row of the mine field.

We check that we are located in the area of the mine field.

The uncovering of the mines is done with the right mouse button.

If we right click on an unmarked cell, we add MARK_FOR_CELL to the number representing the cell. This leads to drawing a covered cell with a mark in the paintComponent() method.

If we left click on a cell that has been already marked, we remove the mark and increase the number of cells to be marked.

Nothing happens if we click on the covered and marked cell. It must by first uncovered by another right click and only then it is possible to left click on it.

A left click removes a cover from the cell.

In case we left clicked on a mine, the game is over. If we left click on an empty cell, we call the find_empty_cells() method which recursively finds all adjacent empty cells.

If the board needs to be repainted (for instance a mark was set or removed), we call the repaint() method

<p align = "center" style="color:red" >
<b> ENJOY </b>
</p>
