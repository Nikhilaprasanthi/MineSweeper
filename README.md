Your minesweeper game will be a two dimensional array of buttons.
Make sure all class member variables and methods are labeled appropriately as either public or private
If the user clicks on a button that contains a mine, the game ends and all the mines are displayed
If the user clicks on a button that does not contain a mine, a number appears at that location indicating the number of neighbors that DO contain mines. Recall that each position has at most 8 neighbors. Note that the buttons on the edges have fewer than 8 neighbors. For example, a corner button has only three neighbors.
If the user clicks on a button and no number appears, then there are no mines neighboring that button. Your program should then recursively keep pressing those neighboring buttons that are not next to a mine.
The game should end when all the buttons that contain mines have been correctly marked and all other buttons have been clicked (assuming that you have not been blown up by then!)
Your game should use Math.random() to randomly place the mines.
Suggested steps to completing this assignment:
Work through the minesweeper codingbat problem set
Fork this repository. As you work through the following steps, make sure that your program runs correctly before going to the next step.
On line 2, delete the comment and create two integer constants NUM_ROWS and NUM_COLS and initialize them each with the value 20
Go to line 16, use the constants to initialize the 2d array buttons to have 20 rows and 20 columns
Use nested loops to create a new MSButton for each row column pair
Uncomment the first two lines in the MSButton constructor (around lines 68 and 69), You should now see a grid of buttons. If you click on the button it should turn white.
Go back to lines 2 and 3 and reduce the number of rows and columns to 5. This will make testing the program easier. We'll set the rows and columns back to a larger number when we finish the game. Make sure the program still runs correctly with the smaller number of rows and columns.
Now, got to line 5, and initialize mines to be a new empty ArrayList of type MSButton
Go to line 26 and write the setMines() function. It should generate a random row and column number. Use the contains() function to check to see if the button at that random row and col is already in mines. If it isn't then add it
Uncomment the 3rd and 4th lines of the MSButton draw() function (around lines 98 and 99) so that cells with a mine turn red when clicked. Test out your program to make sure it has the number of mines you expect.
Go to line 59 and finish public boolean isValid(int row, int col) which returns true if (row,col) is a valid location on the grid and false otherwise. Be sure to use your constants for the number of rows and columns
Go to line 67 and finish public int countMines(int row, int col) which counts the bombs in the 8 neighbors--(remember to check to see if the neighboring button is valid first before checking to see if it's a mine)
Now go to the MSButton class and finish public void mousePressed() which should:
set clicked to true
if mouseButton is RIGHT, set flagged to its opposite value (If it's true set it to false or if it is false set it to true) If flagged was set to false also set clicked to false
else if mines contains this button, display the losing message
else if countMines returns a number of neighboring mines greater than zero, set the label to that number.
else recursively call mousePressed with the valid, unclicked, neighboring buttons in all 8 directions
Next, finish public boolean isWon() which determines if the player has won the game
Then finish public void displayWinMessage(). One way to display the message is to use setLabel to change the labels of the buttons
Finish public void displayLosingMessage() to display the positions of all the bombs as well as a losing message
Finally, adjust the number of rows, columns and mines in your game to your desired difficulty level.
