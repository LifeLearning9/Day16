# Day16 : You are given a 9x9 Sudoku board as a 2D array. Each cell contains a digit '1'–'9' or '.' (empty). A valid Sudoku board must satisfy: Each row must contain digits 1–9 without repetition. Each column must contain digits 1–9 without repetition. Each of the 9 sub-boxes (3x3) must contain digits 1–9 without repetition

**Testcases**
board1 = [
["5","3",".",".","7",".",".",".","."],
["6",".",".","1","9","5",".",".","."],
[".","9","8",".",".",".",".","6","."],
["8",".",".",".","6",".",".",".","3"],
["4",".",".","8",".","3",".",".","1"],
["7",".",".",".","2",".",".",".","6"],
[".","6",".",".",".",".","2","8","."],
[".",".",".","4","1","9",".",".","5"],
[".",".",".",".","8",".",".","7","9"]
]
output: true

**Intution**
1. If we see a number twice in the same row, it’s invalid.
2. If we see a number twice in the same column, it’s invalid.
3. If we see a number twice in the same 3x3 sub-box, it’s invalid.

**Algorithm Flow**
1. Initialize three data structures:
   rows[9] → track numbers in each row.
   cols[9] → track numbers in each column.
   boxes[9] → track numbers in each 3x3 sub-box.
2.Traverse each cell (i, j) in the board:
3.If it’s '.', skip.
4.Calculate box index: boxIndex = (i // 3) * 3 + (j // 3)
5.If the number already exists in rows[i], cols[j], or boxes[boxIndex], return False.
6.Otherwise, add it to all three sets.
7.If we finish traversal without conflicts, return True.

**Complexity Analysis**

Time Complexity:O(1) (constant time).

Space Complexity:O(1) (constant space)
