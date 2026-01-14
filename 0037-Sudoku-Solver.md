# cpp

## memory O(1) and time O(1) | Sweet Spot

```cpp
class Solution {
public:
    void solveSudoku(vector<vector<char>>& board) {
        solve(board);
    }
    /* Time Complexity: O(1) - Board size is fixed at 9x9 */
    /* Memory Complexity: O(1) - Recursion depth and state are fixed */
private:
    bool solve(vector<vector<char>>& board) {
        for (int r = 0; r < 9; ++r) {
            for (int c = 0; c < 9; ++c) {
                if (board[r][c] == '.') {
                    for (char num = '1'; num <= '9'; ++num) {
                        if (isValid(board, r, c, num)) {
                            board[r][c] = num;
                            if (solve(board)) return true;
                            board[r][c] = '.';
                        }
                    }
                    return false;
                }
            }
        }
        return true;
    }

    bool isValid(vector<vector<char>>& board, int r, int c, char num) {
        for (int i = 0; i < 9; ++i) {
            if (board[r][i] == num) return false;
            if (board[i][c] == num) return false;
            if (board[3 * (r / 3) + i / 3][3 * (c / 3) + i % 3] == num) return false;
        }
        return true;
    }
};

```

# java

## memory O(1) and time O(1) | Sweet Spot

```java
class Solution {
    public void solveSudoku(char[][] board) {
        solve(board);
    }
    // Time Complexity: O(1)
    // Memory Complexity: O(1)
    private boolean solve(char[][] board) {
        for (int i = 0; i < 9; i++) {
            for (int j = 0; j < 9; j++) {
                if (board[i][j] == '.') {
                    for (char c = '1'; c <= '9'; c++) {
                        if (isValid(board, i, j, c)) {
                            board[i][j] = c;
                            if (solve(board)) return true;
                            else board[i][j] = '.';
                        }
                    }
                    return false;
                }
            }
        }
        return true;
    }

    private boolean isValid(char[][] board, int row, int col, char c) {
        for (int i = 0; i < 9; i++) {
            if (board[i][col] == c) return false;
            if (board[row][i] == c) return false;
            if (board[3 * (row / 3) + i / 3][3 * (col / 3) + i % 3] == c) return false;
        }
        return true;
    }
}

```

# python 3.14

## memory O(1) and time O(1) | Sweet Spot

```python 3.14
class Solution:
    # Time Complexity: O(9^k)
    # Memory Complexity: O(1)
    def solveSudoku(self, board: List[List[str]]) -> None:
        rows = [set() for _ in range(9)]
        cols = [set() for _ in range(9)]
        boxes = [set() for _ in range(9)]
        empty_cells = []

        for r in range(9):
            for c in range(9):
                char = board[r][c]
                if char != '.':
                    rows[r].add(char)
                    cols[c].add(char)
                    boxes[(r // 3) * 3 + (c // 3)].add(char)
                else:
                    empty_cells.append((r, c))

        def backtrack(index):
            if index == len(empty_cells):
                return True
            
            r, c = empty_cells[index]
            box_idx = (r // 3) * 3 + (c // 3)
            
            for char in "123456789":
                if char not in rows[r] and char not in cols[c] and char not in boxes[box_idx]:
                    board[r][c] = char
                    rows[r].add(char)
                    cols[c].add(char)
                    boxes[box_idx].add(char)
                    
                    if backtrack(index + 1):
                        return True
                    
                    board[r][c] = '.'
                    rows[r].remove(char)
                    cols[c].remove(char)
                    boxes[box_idx].remove(char)
            
            return False

        backtrack(0)
```

# python 2.7.11

## memory O(1) and time O(1) | Sweet Spot

```python 2.7.11
class Solution(object):
    def solveSudoku(self, board):
        # Time Complexity: O(9^(n)) where n is the number of empty cells (strictly O(1) as the board is fixed 9x9)
        # Memory Complexity: O(1) as the storage for bitmasks and recursion depth is constant for a 9x9 board
        rows = [0] * 9
        cols = [0] * 9
        boxes = [0] * 9
        empty_cells = []

        for r in range(9):
            for c in range(9):
                if board[r][c] != '.':
                    val = int(board[r][c]) - 1
                    mask = 1 << val
                    rows[r] |= mask
                    cols[c] |= mask
                    boxes[(r // 3) * 3 + (c // 3)] |= mask
                else:
                    empty_cells.append((r, c))

        def backtrack(index):
            if index == len(empty_cells):
                return True
            
            r, c = empty_cells[index]
            box_idx = (r // 3) * 3 + (c // 3)
            
            # Combine masks to find digits already used in row, col, or box
            used = rows[r] | cols[c] | boxes[box_idx]
            
            for val in range(9):
                if not (used & (1 << val)):
                    # Apply choice
                    mask = 1 << val
                    board[r][c] = str(val + 1)
                    rows[r] |= mask
                    cols[c] |= mask
                    boxes[box_idx] |= mask
                    
                    if backtrack(index + 1):
                        return True
                    
                    # Backtrack
                    board[r][c] = '.'
                    rows[r] &= ~mask
                    cols[c] &= ~mask
                    boxes[box_idx] &= ~mask
            return False

        backtrack(0)
```

# JavaScript

## memory O(1) and time O(1) | Sweet Spot

```javascript
/**
 * @param {character[][]} board
 * @return {void} Do not return anything, modify board in-place instead.
 */
var solveSudoku = function(board) {
    solve(board);
};
// Time Complexity: O(1)
// Memory Complexity: O(1)
function solve(board) {
    for (let r = 0; r < 9; r++) {
        for (let c = 0; c < 9; c++) {
            if (board[r][c] === '.') {
                for (let num = 1; num <= 9; num++) {
                    let s = num.toString();
                    if (isValid(board, r, c, s)) {
                        board[r][c] = s;
                        if (solve(board)) return true;
                        board[r][c] = '.';
                    }
                }
                return false;
            }
        }
    }
    return true;
}

function isValid(board, r, c, s) {
    for (let i = 0; i < 9; i++) {
        if (board[i][c] === s) return false;
        if (board[r][i] === s) return false;
        if (board[3 * Math.floor(r / 3) + Math.floor(i / 3)][3 * Math.floor(c / 3) + i % 3] === s) return false;
    }
    return true;
}

```

# Typescript

## memory O(1) and time O(1) | Sweet Spot

```typescript
/**
 Do not return anything, modify board in-place instead.
 */
function solveSudoku(board: string[][]): void {
    solve(board);
};
// Time Complexity: O(1)
// Memory Complexity: O(1)
function solve(board: string[][]): boolean {
    for (let r = 0; r < 9; r++) {
        for (let c = 0; c < 9; c++) {
            if (board[r][c] === '.') {
                for (let num = 1; num <= 9; num++) {
                    let s = num.toString();
                    if (isValid(board, r, c, s)) {
                        board[r][c] = s;
                        if (solve(board)) return true;
                        board[r][c] = '.';
                    }
                }
                return false;
            }
        }
    }
    return true;
}

function isValid(board: string[][], r: number, c: number, s: string): boolean {
    for (let i = 0; i < 9; i++) {
        if (board[i][c] === s) return false;
        if (board[r][i] === s) return false;
        const boxR = 3 * Math.floor(r / 3) + Math.floor(i / 3);
        const boxC = 3 * Math.floor(c / 3) + i % 3;
        if (board[boxR][boxC] === s) return false;
    }
    return true;
}

```

# C#

## memory O(1) and time O(1) | Sweet Spot

```c#
public class Solution {
    public void SolveSudoku(char[][] board) {
        Solve(board);
    }
    // Time Complexity: O(1)
    // Memory Complexity: O(1)
    private bool Solve(char[][] board) {
        for (int r = 0; r < 9; r++) {
            for (int c = 0; c < 9; c++) {
                if (board[r][c] == '.') {
                    for (char num = '1'; num <= '9'; num++) {
                        if (IsValid(board, r, c, num)) {
                            board[r][c] = num;
                            if (Solve(board)) return true;
                            board[r][c] = '.';
                        }
                    }
                    return false;
                }
            }
        }
        return true;
    }

    private bool IsValid(char[][] board, int r, int c, char num) {
        for (int i = 0; i < 9; i++) {
            if (board[i][c] == num) return false;
            if (board[r][i] == num) return false;
            if (board[3 * (r / 3) + i / 3][3 * (c / 3) + i % 3] == num) return false;
        }
        return true;
    }
}

```

# C

## memory O(1) and time O(1) | Sweet Spot

```c
/* Time Complexity: O(1) */
/* Memory Complexity: O(1) */
bool isValid(char** board, int r, int c, char num) {
    for (int i = 0; i < 9; i++) {
        if (board[i][c] == num) return false;
        if (board[r][i] == num) return false;
        if (board[3 * (r / 3) + i / 3][3 * (c / 3) + i % 3] == num) return false;
    }
    return true;
}

bool solve(char** board) {
    for (int r = 0; r < 9; r++) {
        for (int c = 0; c < 9; c++) {
            if (board[r][c] == '.') {
                for (char num = '1'; num <= '9'; num++) {
                    if (isValid(board, r, c, num)) {
                        board[r][c] = num;
                        if (solve(board)) return true;
                        board[r][c] = '.';
                    }
                }
                return false;
            }
        }
    }
    return true;
}

void solveSudoku(char** board, int boardSize, int* boardColSize) {
    solve(board);
}

```

# Go

## memory O(1) and time O(1) | Sweet Spot

```go
func solveSudoku(board [][]byte)  {
    solve(&board)
}
// Time Complexity: O(1)
// Memory Complexity: O(1)
func solve(board *[][]byte) bool {
    for r := 0; r < 9; r++ {
        for c := 0; c < 9; c++ {
            if (*board)[r][c] == '.' {
                for num := byte('1'); num <= byte('9'); num++ {
                    if isValid(board, r, c, num) {
                        (*board)[r][c] = num
                        if solve(board) {
                            return true
                        }
                        (*board)[r][c] = '.'
                    }
                }
                return false
            }
        }
    }
    return true
}

func isValid(board *[][]byte, r, c int, num byte) bool {
    for i := 0; i < 9; i++ {
        if (*board)[i][c] == num || (*board)[r][i] == num || (*board)[3*(r/3)+i/3][3*(c/3)+i%3] == num {
            return false
        }
    }
    return true
}

```

# Kotlin

## memory O(1) and time O(1) | Sweet Spot

```kotlin
class Solution {
    fun solveSudoku(board: Array<CharArray>): Unit {
        solve(board)
    }
    // Time Complexity: O(1)
    // Memory Complexity: O(1)
    private fun solve(board: Array<CharArray>): Boolean {
        for (r in 0 until 9) {
            for (c in 0 until 9) {
                if (board[r][c] == '.') {
                    for (num in '1'..'9') {
                        if (isValid(board, r, c, num)) {
                            board[r][c] = num
                            if (solve(board)) return true
                            board[r][c] = '.'
                        }
                    }
                    return false
                }
            }
        }
        return true
    }

    private fun isValid(board: Array<CharArray>, r: Int, c: Int, num: Char): Boolean {
        for (i in 0 until 9) {
            if (board[i][c] == num) return false
            if (board[r][i] == num) return false
            if (board[3 * (r / 3) + i / 3][3 * (c / 3) + i % 3] == num) return false
        }
        return true
    }
}

```

# swift

## memory O(1) and time O(1) | Sweet Spot

```swift
class Solution {
    func solveSudoku(_ board: inout [[Character]]) {
        _ = solve(&board)
    }
    // Time Complexity: O(1)
    // Memory Complexity: O(1)
    private func solve(_ board: inout [[Character]]) -> Bool {
        for r in 0..<9 {
            for c in 0..<9 {
                if board[r][c] == "." {
                    for num in 1...9 {
                        let char = Character("\(num)")
                        if isValid(board, r, c, char) {
                            board[r][c] = char
                            if solve(&board) { return true }
                            board[r][c] = "."
                        }
                    }
                    return false
                }
            }
        }
        return true
    }

    private func isValid(_ board: [[Character]], _ r: Int, _ c: Int, _ char: Character) -> Bool {
        for i in 0..<9 {
            if board[i][c] == char { return false }
            if board[r][i] == char { return false }
            if board[3 * (r / 3) + i / 3][3 * (c / 3) + i % 3] == char { return false }
        }
        return true
    }
}

```

# rust

## memory O(1) and time O(1) | Sweet Spot

```rust
impl Solution {
    pub fn solve_sudoku(board: &mut Vec<Vec<char>>) {
        Self::solve(board);
    }
    // Time Complexity: O(1)
    // Memory Complexity: O(1)
    fn solve(board: &mut Vec<Vec<char>>) -> bool {
        for r in 0..9 {
            for c in 0..9 {
                if board[r][c] == '.' {
                    for num in '1'..='9' {
                        if Self::is_valid(board, r, c, num) {
                            board[r][c] = num;
                            if Self::solve(board) { return true; }
                            board[r][c] = '.';
                        }
                    }
                    return false;
                }
            }
        }
        true
    }

    fn is_valid(board: &Vec<Vec<char>>, r: usize, c: usize, num: char) -> bool {
        for i in 0..9 {
            if board[i][c] == num { return false; }
            if board[r][i] == num { return false; }
            if board[3 * (r / 3) + i / 3][3 * (c / 3) + i % 3] == num { return false; }
        }
        true
    }
}

```

# ruby

## memory O(1) and time O(1) | Sweet Spot

```ruby
# Time Complexity: O(9^m) where m is the number of empty cells
# Memory Complexity: O(1) as the state arrays and board are fixed size (9x9)
def solve_sudoku(board)
  rows = Array.new(9, 0)
  cols = Array.new(9, 0)
  boxes = Array.new(9, 0)
  empty_cells = []

  9.times do |r|
    9.times do |c|
      if board[r][c] == '.'
        empty_cells << [r, c]
      else
        num = board[r][c].to_i - 1
        mask = 1 << num
        rows[r] |= mask
        cols[c] |= mask
        boxes[(r / 3) * 3 + (c / 3)] |= mask
      end
    end
  end

  backtrack(board, empty_cells, 0, rows, cols, boxes)
end

# Time Complexity: O(9^m)
# Memory Complexity: O(m) for the recursion stack
def backtrack(board, empty_cells, index, rows, cols, boxes)
  return true if index == empty_cells.length

  r, c = empty_cells[index]
  box_idx = (r / 3) * 3 + (c / 3)
  
  used_mask = rows[r] | cols[c] | boxes[box_idx]

  9.times do |num|
    mask = 1 << num
    if (used_mask & mask) == 0
      board[r][c] = (num + 1).to_s
      rows[r] |= mask
      cols[c] |= mask
      boxes[box_idx] |= mask

      return true if backtrack(board, empty_cells, index + 1, rows, cols, boxes)

      rows[r] &= ~mask
      cols[c] &= ~mask
      boxes[box_idx] &= ~mask
      board[r][c] = '.'
    end
  end

  false
end
```

# php

## memory O(1) and time O(1) | Sweet Spot

```php
class Solution {
    private $rows = [];
    private $cols = [];
    private $boxes = [];

    /**
     * @param String[][] $board
     * @return NULL
     */
    function solveSudoku(&$board) {
        // Time Complexity: O(9^(m)) where m is the number of empty cells
        // Memory Complexity: O(1) as the board size is fixed at 81 cells
        $this->rows = array_fill(0, 9, array_fill(1, 9, false));
        $this->cols = array_fill(0, 9, array_fill(1, 9, false));
        $this->boxes = array_fill(0, 9, array_fill(1, 9, false));

        for ($r = 0; $r < 9; $r++) {
            for ($c = 0; $c < 9; $c++) {
                if ($board[$r][$c] !== '.') {
                    $num = (int)$board[$r][$c];
                    $boxIdx = (int)($r / 3) * 3 + (int)($c / 3);
                    $this->rows[$r][$num] = true;
                    $this->cols[$c][$num] = true;
                    $this->boxes[$boxIdx][$num] = true;
                }
            }
        }

        $this->backtrack($board, 0, 0);
    }

    private function backtrack(&$board, $r, $c) {
        if ($r == 9) return true;
        
        $nextR = ($c == 8) ? $r + 1 : $r;
        $nextC = ($c == 8) ? 0 : $c + 1;

        if ($board[$r][$c] !== '.') {
            return $this->backtrack($board, $nextR, $nextC);
        }

        $boxIdx = (int)($r / 3) * 3 + (int)($c / 3);

        for ($num = 1; $num <= 9; $num++) {
            if (!$this->rows[$r][$num] && !$this->cols[$c][$num] && !$this->boxes[$boxIdx][$num]) {
                $board[$r][$c] = (string)$num;
                $this->rows[$r][$num] = true;
                $this->cols[$c][$num] = true;
                $this->boxes[$boxIdx][$num] = true;

                if ($this->backtrack($board, $nextR, $nextC)) return true;

                $board[$r][$c] = '.';
                $this->rows[$r][$num] = false;
                $this->cols[$c][$num] = false;
                $this->boxes[$boxIdx][$num] = false;
            }
        }

        return false;
    }
}
```

# dart

## memory O(1) and time O(1) | Sweet Spot

```dart
class Solution {
  void solveSudoku(List<List<String>> board) {
    _solve(board);
  }
  // Time Complexity: O(1)
  // Memory Complexity: O(1)
  bool _solve(List<List<String>> board) {
    for (int r = 0; r < 9; r++) {
      for (int c = 0; c < 9; c++) {
        if (board[r][c] == '.') {
          for (int num = 1; num <= 9; num++) {
            String s = num.toString();
            if (_isValid(board, r, c, s)) {
              board[r][c] = s;
              if (_solve(board)) return true;
              board[r][c] = '.';
            }
          }
          return false;
        }
      }
    }
    return true;
  }

  bool _isValid(List<List<String>> board, int r, int c, String s) {
    for (int i = 0; i < 9; i++) {
      if (board[i][c] == s) return false;
      if (board[r][i] == s) return false;
      if (board[3 * (r ~/ 3) + (i ~/ 3)][3 * (c ~/ 3) + (i % 3)] == s) return false;
    }
    return true;
  }
}

```

# scala 3.3.1

## memory O(1) and time O(1) | Sweet Spot

```scala 3.3.1
import scala.util.boundary, boundary.break

object Solution {
    def solveSudoku(board: Array[Array[Char]]): Unit = {
        solve(board)
    }

    /* Time Complexity: O(9^(n*n)) where n=9, effectively O(1) for a fixed 9x9 board */
    /* Memory Complexity: O(n*n) where n=9, effectively O(1) for fixed recursion depth */
    private def solve(board: Array[Array[Char]]): Boolean = {
        boundary {
            for (r <- 0 until 9; c <- 0 until 9) {
                if (board(r)(c) == '.') {
                    for (num <- '1' to '9') {
                        if (isValid(board, r, c, num)) {
                            board(r)(c) = num
                            if (solve(board)) break(true)
                            board(r)(c) = '.'
                        }
                    }
                    break(false)
                }
            }
            true
        }
    }

    private def isValid(board: Array[Array[Char]], r: Int, c: Int, num: Char): Boolean = {
        boundary {
            for (i <- 0 until 9) {
                if (board(i)(c) == num) break(false)
                if (board(r)(i) == num) break(false)
                if (board(3 * (r / 3) + i / 3)(3 * (c / 3) + i % 3) == num) break(false)
            }
            true
        }
    }
}
```