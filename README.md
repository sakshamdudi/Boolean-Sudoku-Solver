# Boolean-Sudoku-Solver
// Sudoku solver and validator
We all love solving puzzles, crosswords but often get tired when we are unable to get the solution. 
So, in our project, we have designed a Sudoku solver and validator mainly using Bool functions in C++. 
The use of Bool functions increases the execution speed of the Sudoku solver significantly and also makes it easier to understand.
//Intro
Sudoku is a very popular puzzle that consists of placing several numbers in a squared grid according to some simple rules. 
This involves logic and combinatorial number placements by applying satisfiability (SAT/SMT).
We all have played Sudoku at some time in our lives, especially during the current lockdown, and have scratched our heads trying to find the answers. 
Therefore, this project not only hopes to solve the Sudoku but in an easier, faster, and interesting way. 
//Algortithm used

FOR SOLVER:
Start
We will start with an empty cell.
We will generate a list of all possible values that can be filled in that cell.
We traverse over this list and start with the first value and place it in the required cell.
We move on to the next cell. We again generate a list of possibilities. However, if no list can be generated, then this means that there is something wrong with the value of the previous cell. We then move back to the previous cell and place the next value on the generated list in the cell now. We repeat this step until the current cell has a valid value placed inside it.
We stop when we reach the last cell. And have placed a valid value.
Stop

IMPLEMENTATION DETAILS
Input the values for each cell for the sudoku you wish to be solved. Input 0 for empty cells.
The function “setCellValue” then passes these values to their respective cells. Not just it takes the value but also checks if the puzzle is valid by checking if the value occurs in that row, column, or 3X3 grid or not. This is done using the function cellValueValid and ThreeByThreeGirdValid
Then the function SingleCellSolve is called. This is the main function that solves the puzzle by each cell one by one.We will only go to the cells which have 0 in them and are, thus, editable.
After this, we have made a class called Possibilities which will calculate all the possible values for a cell. This class stores the values in a linked list.
From the possible values, we check for each value if the value is valid or not. By valid, we mean if that possible value occurs in that row, column, or 3X3 grid or not. This is done using the function cellValueValid and ThreeByThreeGirdValid.
We assign each cell a value one by one after checking its validity.
However, since each cell may have more than 1 value, a cell once assigned a value might change later. Once fixed, that value is later on eliminated. This process is done by backtracking by checking the validity of previous cells again and again after moving on to the other. 



FOR VALIDATOR:
Start
The values in all the cells are traversed one by one and checked to see whether they are in the range of 1-9. If not, then the puzzle is invalid.
Every row is checked to see if it contains 1-9 at least and at most once. If not, then the puzzle is invalid.
Every column is checked to see if it contains 1-9 at least and at most once. If not, the solution is invalid.
Every 3x3 grid is checked to see if it contains 1-9 at least and at most once. If not, the solution is invalid.
If all the criteria have been satisfied, the solution is valid.
Stop
//
//
//
//
