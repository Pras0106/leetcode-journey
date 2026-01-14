# cpp

## memory O(1) and time O(1) | Sweet Spot

```cpp
class Solution {
public:
    bool isValidSudoku(vector<vector<char>>& board) {
        int rows[9] = {0}, cols[9] = {0}, boxes[9] = {0};
        for (int r = 0; r < 9; ++r) {
            for (int c = 0; c < 9; ++c) {
                if (board[r][c] == '.') continue;
                int val = board[r][c] - '1';
                int mask = 1 << val;
                int box_idx = (r / 3) * 3 + (c / 3);
                if ((rows[r] & mask) || (cols[c] & mask) || (boxes[box_idx] & mask)) {
                    return false;
                }
                rows[r] |= mask;
                cols[c] |= mask;
                boxes[box_idx] |= mask;
            }
        }
        return true;
        // Time Complexity: O(1) - fixed board size 81 cells
        // Memory Complexity: O(1) - fixed size arrays
    }
};

```

# java

## memory O(1) and time O(1) | Sweet Spot

```java
class Solution {
    public boolean isValidSudoku(char[][] board) {
        int[] rows = new int[9];
        int[] cols = new int[9];
        int[] boxes = new int[9];
        for (int r = 0; r < 9; r++) {
            for (int c = 0; c < 9; c++) {
                if (board[r][c] == '.') continue;
                int val = board[r][c] - '1';
                int mask = 1 << val;
                int boxIdx = (r / 3) * 3 + (c / 3);
                if ((rows[r] & mask) != 0 || (cols[c] & mask) != 0 || (boxes[boxIdx] & mask) != 0) {
                    return false;
                }
                rows[r] |= mask;
                cols[c] |= mask;
                boxes[boxIdx] |= mask;
            }
        }
        return true;
        // Time Complexity: O(1)
        // Memory Complexity: O(1)
    }
}

```

# python 3.14

## memory O(1) and time O(1) | Sweet Spot

```python 3.14
class Solution:
    def isValidSudoku(self, board: List[List[str]]) -> bool:
        rows = [0] * 9
        cols = [0] * 9
        boxes = [0] * 9
        for r in range(9):
            for c in range(9):
                if board[r][c] == '.':
                    continue
                val = int(board[r][c]) - 1
                mask = 1 << val
                box_idx = (r // 3) * 3 + (c // 3)
                if (rows[r] & mask) or (cols[c] & mask) or (boxes[box_idx] & mask):
                    return False
                rows[r] |= mask
                cols[c] |= mask
                boxes[box_idx] |= mask
        return True
        # Time Complexity: O(1)
        # Memory Complexity: O(1)

```

# python 2.7.11

## memory O(1) and time O(1) | Sweet Spot

```python 2.7.11
class Solution(object):
    def isValidSudoku(self, board):
        """
        :type board: List[List[str]]
        :rtype: bool
        """
        rows = [0] * 9
        cols = [0] * 9
        boxes = [0] * 9
        for r in range(9):
            for c in range(9):
                char = board[r][c]
                if char == '.':
                    continue
                val = ord(char) - ord('1')
                mask = 1 << val
                box_idx = (r // 3) * 3 + (c // 3)
                if (rows[r] & mask) or (cols[c] & mask) or (boxes[box_idx] & mask):
                    return False
                rows[r] |= mask
                cols[c] |= mask
                boxes[box_idx] |= mask
        return True
        # Time Complexity: O(1)
        # Memory Complexity: O(1)

```

# JavaScript

## memory O(1) and time O(1) | Sweet Spot

```javascript
/**
 * @param {character[][]} board
 * @return {boolean}
 */
var isValidSudoku = function(board) {
    const rows = new Int32Array(9);
    const cols = new Int32Array(9);
    const boxes = new Int32Array(9);
    for (let r = 0; r < 9; r++) {
        for (let c = 0; c < 9; c++) {
            if (board[r][c] === '.') continue;
            const val = board[r][c].charCodeAt(0) - 49;
            const mask = 1 << val;
            const boxIdx = Math.floor(r / 3) * 3 + Math.floor(c / 3);
            if ((rows[r] & mask) || (cols[c] & mask) || (boxes[boxIdx] & mask)) {
                return false;
            }
            rows[r] |= mask;
            cols[c] |= mask;
            boxes[boxIdx] |= mask;
        }
    }
    return true;
    // Time Complexity: O(1)
    // Memory Complexity: O(1)
};

```

# Typescript

## memory O(1) and time O(1) | Sweet Spot

```typescript
function isValidSudoku(board: string[][]): boolean {
    const rows = new Int32Array(9);
    const cols = new Int32Array(9);
    const boxes = new Int32Array(9);
    for (let r = 0; r < 9; r++) {
        for (let c = 0; c < 9; c++) {
            if (board[r][c] === '.') continue;
            const val = board[r][c].charCodeAt(0) - 49;
            const mask = 1 << val;
            const boxIdx = Math.floor(r / 3) * 3 + Math.floor(c / 3);
            if ((rows[r] & mask) || (cols[c] & mask) || (boxes[boxIdx] & mask)) {
                return false;
            }
            rows[r] |= mask;
            cols[c] |= mask;
            boxes[boxIdx] |= mask;
        }
    }
    return true;
    // Time Complexity: O(1)
    // Memory Complexity: O(1)
};

```

# C#

## memory O(1) and time O(1) | Sweet Spot

```c#
public class Solution {
    public bool IsValidSudoku(char[][] board) {
        int[] rows = new int[9];
        int[] cols = new int[9];
        int[] boxes = new int[9];
        for (int r = 0; r < 9; r++) {
            for (int c = 0; c < 9; c++) {
                if (board[r][c] == '.') continue;
                int val = board[r][c] - '1';
                int mask = 1 << val;
                int boxIdx = (r / 3) * 3 + (c / 3);
                if ((rows[r] & mask) != 0 || (cols[c] & mask) != 0 || (boxes[boxIdx] & mask) != 0) {
                    return false;
                }
                rows[r] |= mask;
                cols[c] |= mask;
                boxes[boxIdx] |= mask;
            }
        }
        return true;
        // Time Complexity: O(1)
        // Memory Complexity: O(1)
    }
}

```

# C

## memory O(1) and time O(1) | Sweet Spot

```c
bool isValidSudoku(char** board, int boardSize, int* boardColSize) {
    int rows[9] = {0}, cols[9] = {0}, boxes[9] = {0};
    for (int r = 0; r < 9; r++) {
        for (int c = 0; c < 9; c++) {
            if (board[r][c] == '.') continue;
            int val = board[r][c] - '1';
            int mask = 1 << val;
            int boxIdx = (r / 3) * 3 + (c / 3);
            if ((rows[r] & mask) || (cols[c] & mask) || (boxes[boxIdx] & mask)) {
                return false;
            }
            rows[r] |= mask;
            cols[c] |= mask;
            boxes[boxIdx] |= mask;
        }
    }
    return true;
    /* Time Complexity: O(1) */
    /* Memory Complexity: O(1) */
}

```

# Go

## memory O(1) and time O(1) | Sweet Spot

```go
func isValidSudoku(board [][]byte) bool {
    var rows, cols, boxes [9]int
    for r := 0; r < 9; r++ {
        for c := 0; c < 9; c++ {
            if board[r][c] == '.' {
                continue
            }
            val := board[r][c] - '1'
            mask := 1 << val
            boxIdx := (r / 3) * 3 + (c / 3)
            if (rows[r] & mask) != 0 || (cols[c] & mask) != 0 || (boxes[boxIdx] & mask) != 0 {
                return false
            }
            rows[r] |= mask
            cols[c] |= mask
            boxes[boxIdx] |= mask
        }
    }
    return true
    // Time Complexity: O(1)
    // Memory Complexity: O(1)
}

```

# Kotlin

## memory O(1) and time O(1) | Sweet Spot

```kotlin
class Solution {
    fun isValidSudoku(board: Array<CharArray>): Boolean {
        val rows = IntArray(9)
        val cols = IntArray(9)
        val boxes = IntArray(9)
        for (r in 0 until 9) {
            for (c in 0 until 9) {
                if (board[r][c] == '.') continue
                val value = board[r][c] - '1'
                val mask = 1 shl value
                val boxIdx = (r / 3) * 3 + (c / 3)
                if ((rows[r] and mask) != 0 || (cols[c] and mask) != 0 || (boxes[boxIdx] and mask) != 0) {
                    return false
                }
                rows[r] = rows[r] or mask
                cols[c] = cols[c] or mask
                boxes[boxIdx] = boxes[boxIdx] or mask
            }
        }
        return true
        // Time Complexity: O(1)
        // Memory Complexity: O(1)
    }
}

```

# swift

## memory O(1) and time O(1) | Sweet Spot

```swift
class Solution {
    func isValidSudoku(_ board: [[Character]]) -> Bool {
        var rows = Array(repeating: 0, count: 9)
        var cols = Array(repeating: 0, count: 9)
        var boxes = Array(repeating: 0, count: 9)
        for r in 0..<9 {
            for c in 0..<9 {
                let char = board[r][c]
                if char == "." { continue }
                if let val = char.wholeNumberValue {
                    let mask = 1 << (val - 1)
                    let boxIdx = (r / 3) * 3 + (c / 3)
                    if (rows[r] & mask) != 0 || (cols[c] & mask) != 0 || (boxes[boxIdx] & mask) != 0 {
                        return false
                    }
                    rows[r] |= mask
                    cols[c] |= mask
                    boxes[boxIdx] |= mask
                }
            }
        }
        return true
        // Time Complexity: O(1)
        // Memory Complexity: O(1)
    }
}

```

# rust

## memory O(1) and time O(1) | Sweet Spot

```rust
impl Solution {
    pub fn is_valid_sudoku(board: Vec<Vec<char>>) -> bool {
        let mut rows = [0u16; 9];
        let mut cols = [0u16; 9];
        let mut boxes = [0u16; 9];
        for r in 0..9 {
            for c in 0..9 {
                if board[r][c] == '.' { continue; }
                let val = (board[r][c] as u8 - b'1');
                let mask = 1 << val;
                let box_idx = (r / 3) * 3 + (c / 3);
                if (rows[r] & mask) != 0 || (cols[c] & mask) != 0 || (boxes[box_idx] & mask) != 0 {
                    return false;
                }
                rows[r] |= mask;
                cols[c] |= mask;
                boxes[box_idx] |= mask;
            }
        }
        true
        // Time Complexity: O(1)
        // Memory Complexity: O(1)
    }
}

```

# ruby

## memory O(1) and time O(1) | Sweet Spot

```ruby
# @param {Character[][]} board
# @return {Boolean}
def is_valid_sudoku(board)
    rows = Array.new(9, 0)
    cols = Array.new(9, 0)
    boxes = Array.new(9, 0)
    (0..8).each do |r|
        (0..8).each do |c|
            char = board[r][c]
            next if char == '.'
            val = char.to_i - 1
            mask = 1 << val
            box_idx = (r / 3) * 3 + (c / 3)
            return false if (rows[r] & mask) != 0 || (cols[c] & mask) != 0 || (boxes[box_idx] & mask) != 0
            rows[r] |= mask
            cols[c] |= mask
            boxes[box_idx] |= mask
        end
    end
    true
    # Time Complexity: O(1)
    # Memory Complexity: O(1)
end

```

# php

## memory O(1) and time O(1) | Sweet Spot

```php
class Solution {

    /**
     * @param String[][] $board
     * @return Boolean
     */
    function isValidSudoku($board) {
        $rows = array_fill(0, 9, 0);
        $cols = array_fill(0, 9, 0);
        $boxes = array_fill(0, 9, 0);
        for ($r = 0; $r < 9; $r++) {
            for ($c = 0; $c < 9; $c++) {
                if ($board[$r][$c] === '.') continue;
                $val = (int)$board[$r][$c] - 1;
                $mask = 1 << $val;
                $boxIdx = (int)($r / 3) * 3 + (int)($c / 3);
                if (($rows[$r] & $mask) || ($cols[$c] & $mask) || ($boxes[$boxIdx] & $mask)) {
                    return false;
                }
                $rows[$r] |= $mask;
                $cols[$c] |= $mask;
                $boxes[$boxIdx] |= $mask;
            }
        }
        return true;
        // Time Complexity: O(1)
        // Memory Complexity: O(1)
    }
}

```

# dart

## memory O(1) and time O(1) | Sweet Spot

```dart
class Solution {
  bool isValidSudoku(List<List<String>> board) {
    List<int> rows = List.filled(9, 0);
    List<int> cols = List.filled(9, 0);
    List<int> boxes = List.filled(9, 0);
    for (int r = 0; r < 9; r++) {
      for (int c = 0; c < 9; c++) {
        if (board[r][c] == '.') continue;
        int val = int.parse(board[r][c]) - 1;
        int mask = 1 << val;
        int boxIdx = (r ~/ 3) * 3 + (c ~/ 3);
        if ((rows[r] & mask) != 0 || (cols[c] & mask) != 0 || (boxes[boxIdx] & mask) != 0) {
          return false;
        }
        rows[r] |= mask;
        cols[c] |= mask;
        boxes[boxIdx] |= mask;
      }
    }
    return true;
    // Time Complexity: O(1)
    // Memory Complexity: O(1)
  }
}

```

# scala 3.3.1

## memory O(1) and time O(1) | Sweet Spot

```scala 3.3.1
import scala.util.boundary, boundary.break

object Solution {
    def isValidSudoku(board: Array[Array[Char]]): Boolean = {
        // Time Complexity: O(1)
        // Memory Complexity: O(1)
        boundary {
            val rows = Array.fill(9)(0)
            val cols = Array.fill(9)(0)
            val boxes = Array.fill(9)(0)

            for (r <- 0 until 9) {
                for (c <- 0 until 9) {
                    if (board(r)(c) != '.') {
                        val valBit = board(r)(c) - '1'
                        val mask = 1 << valBit
                        val boxIdx = (r / 3) * 3 + (c / 3)

                        if ((rows(r) & mask) != 0 || (cols(c) & mask) != 0 || (boxes(boxIdx) & mask) != 0) {
                            break(false)
                        }

                        rows(r) |= mask
                        cols(c) |= mask
                        boxes(boxIdx) |= mask
                    }
                }
            }
            true
        }
    }
}
```

# Elixir 1.17 with Erlang/OTP 26

## memory O(1) and time O(1) | Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  import Bitwise

  @spec is_valid_sudoku(board :: [[char]]) :: boolean
  def is_valid_sudoku(board) do
    # Time Complexity: O(1)
    # Space Complexity: O(1)
    board_tuple = List.to_tuple(Enum.map(board, &List.to_tuple/1))
    
    rows_valid = Enum.all?(0..8, fn r -> row_to_bits(elem(board_tuple, r)) != :invalid end)
    cols_valid = Enum.all?(0..8, fn c -> col_to_bits(board_tuple, c) != :invalid end)
    boxes_valid = Enum.all?(0..8, fn b -> box_to_bits(board_tuple, b) != :invalid end)

    rows_valid and cols_valid and boxes_valid
  end

  defp row_to_bits(row_tuple) do
    # Time Complexity: O(1)
    # Space Complexity: O(1)
    Enum.reduce_while(0..8, 0, fn i, acc ->
      case elem(row_tuple, i) do
        ?. -> {:cont, acc}
        char ->
          bit = 1 <<< (char - ?1)
          if (acc &&& bit) != 0, do: {:halt, :invalid}, else: {:cont, acc ||| bit}
      end
    end)
  end

  defp col_to_bits(board_tuple, c) do
    # Time Complexity: O(1)
    # Space Complexity: O(1)
    Enum.reduce_while(0..8, 0, fn r, acc ->
      case elem(elem(board_tuple, r), c) do
        ?. -> {:cont, acc}
        char ->
          bit = 1 <<< (char - ?1)
          if (acc &&& bit) != 0, do: {:halt, :invalid}, else: {:cont, acc ||| bit}
      end
    end)
  end

  defp box_to_bits(board_tuple, b) do
    # Time Complexity: O(1)
    # Space Complexity: O(1)
    r_start = div(b, 3) * 3
    c_start = rem(b, 3) * 3
    Enum.reduce_while(0..8, 0, fn i, acc ->
      char = elem(elem(board_tuple, r_start + div(i, 3)), c_start + rem(i, 3))
      case char do
        ?. -> {:cont, acc}
        _ ->
          bit = 1 <<< (char - ?1)
          if (acc &&& bit) != 0, do: {:halt, :invalid}, else: {:cont, acc ||| bit}
      end
    end)
  end
end
```

# Erlang/OTP 26

## memory O(1) and time O(1) | Sweet Spot

```erlang/otp 26
-spec is_valid_sudoku(Board :: [[char()]]) -> boolean().
is_valid_sudoku(Board) ->
    Rows = Board,
    Cols = [[lists:nth(C, R) || R <- Board] || C <- lists:seq(1, 9)],
    Boxes = [extract_box(Board, B) || B <- lists:seq(0, 8)],
    lists:all(fun check_unique/1, Rows) andalso
    lists:all(fun check_unique/1, Cols) andalso
    lists:all(fun check_unique/1, Boxes).

extract_box(Board, B) ->
    RStart = (B div 3) * 3,
    CStart = (B rem 3) * 3,
    [lists:nth(CStart + (I rem 3) + 1, lists:nth(RStart + (I div 3) + 1, Board)) || I <- lists:seq(0, 8)].

check_unique(List) ->
    Digits = [X || X <- List, X /= $.],
    length(Digits) == sets:size(sets:from_list(Digits)).
% Time Complexity: O(1)
% Memory Complexity: O(1)

```

# Racket CS v8.15

## memory O(1) and time O(1) | Sweet Spot

```racket CS v8.15
(define/contract (is-valid-sudoku board)
  (-> (listof (listof char?)) boolean?)
  (let ([vec-board (list->vector (map list->vector board))])
    (define (check set mask val)
      (let ([bit (arithmetic-shift 1 (- (char->integer val) (char->integer #\1)))])
        (if (zero? (bitwise-and mask bit))
            (bitwise-ior mask bit)
            #f)))
    (define (validate cells)
      (let loop ([cells cells] [mask 0])
        (cond
          [(empty? cells) #t]
          [(char=? (car cells) #\.) (loop (cdr cells) mask)]
          [else (let ([next-mask (check mask mask (car cells))])
                  (if next-mask (loop (cdr cells) next-mask) #f))])))
    (and
     (for/and ([r (in-range 9)]) (validate (vector->list (vector-ref vec-board r))))
     (for/and ([c (in-range 9)]) (validate (for/list ([r (in-range 9)]) (vector-ref (vector-ref vec-board r) c))))
     (for/and ([b (in-range 9)])
       (let ([rs (* (quotient b 3) 3)] [cs (* (remainder b 3) 3)])
         (validate (for/list ([i (in-range 9)]) 
                     (vector-ref (vector-ref vec-board (+ rs (quotient i 3))) (+ cs (remainder i 3))))))))))
; Time Complexity: O(1)
; Memory Complexity: O(1)

```