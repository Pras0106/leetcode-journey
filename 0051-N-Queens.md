# cpp

## Sweet Spot

```cpp
class Solution {
public:
    vector<vector<string>> solveNQueens(int n) {
        vector<vector<string>> results;
        vector<string> board(n, string(n, '.'));
        vector<bool> cols(n, false), diag1(2 * n - 1, false), diag2(2 * n - 1, false);
        backtrack(0, n, board, results, cols, diag1, diag2);
        return results;
    }

private:
    // Time Complexity: O(N!)
    // Memory Complexity: O(N^2)
    void backtrack(int row, int n, vector<string>& board, vector<vector<string>>& results,
                   vector<bool>& cols, vector<bool>& diag1, vector<bool>& diag2) {
        if (row == n) {
            results.push_back(board);
            return;
        }
        for (int col = 0; col < n; col++) {
            if (cols[col] || diag1[row + col] || diag2[row - col + n - 1]) continue;
            board[row][col] = 'Q';
            cols[col] = diag1[row + col] = diag2[row - col + n - 1] = true;
            backtrack(row + 1, n, board, results, cols, diag1, diag2);
            cols[col] = diag1[row + col] = diag2[row - col + n - 1] = false;
            board[row][col] = '.';
        }
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public List<List<String>> solveNQueens(int n) {
        List<List<String>> results = new ArrayList<>();
        char[][] board = new char[n][n];
        for (int i = 0; i < n; i++) Arrays.fill(board[i], '.');
        boolean[] cols = new boolean[n];
        boolean[] d1 = new boolean[2 * n];
        boolean[] d2 = new boolean[2 * n];
        backtrack(0, n, board, results, cols, d1, d2);
        return results;
    }

    // Time Complexity: O(N!)
    // Memory Complexity: O(N^2)
    private void backtrack(int r, int n, char[][] board, List<List<String>> res, boolean[] c, boolean[] d1, boolean[] d2) {
        if (r == n) {
            List<String> list = new ArrayList<>();
            for (char[] row : board) list.add(new String(row));
            res.add(list);
            return;
        }
        for (int col = 0; col < n; col++) {
            int id1 = r + col, id2 = r - col + n;
            if (c[col] || d1[id1] || d2[id2]) continue;
            board[r][col] = 'Q';
            c[col] = d1[id1] = d2[id2] = true;
            backtrack(r + 1, n, board, res, c, d1, d2);
            c[col] = d1[id1] = d2[id2] = false;
            board[r][col] = '.';
        }
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def solveNQueens(self, n: int) -> List[List[str]]:
        res = []
        board = [['.'] * n for _ in range(n)]
        cols, d1, d2 = set(), set(), set()
        
        # Time Complexity: O(N!)
        # Memory Complexity: O(N^2)
        def backtrack(r):
            if r == n:
                res.append(["".join(row) for row in board])
                return
            for c in range(n):
                if c in cols or (r + c) in d1 or (r - c) in d2:
                    continue
                cols.add(c); d1.add(r + c); d2.add(r - c)
                board[r][c] = 'Q'
                backtrack(r + 1)
                board[r][c] = '.'
                cols.remove(c); d1.remove(r + c); d2.remove(r - c)
        
        backtrack(0)
        return res

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def solveNQueens(self, n):
        """
        :type n: int
        :rtype: List[List[str]]
        """
        res = []
        board = [['.' for _ in range(n)] for _ in range(n)]
        cols, d1, d2 = set(), set(), set()
        
        # Time Complexity: O(N!)
        # Memory Complexity: O(N^2)
        def backtrack(r):
            if r == n:
                res.append(["".join(row) for row in board])
                return
            for c in range(n):
                if c in cols or (r + c) in d1 or (r - c) in d2:
                    continue
                cols.add(c); d1.add(r + c); d2.add(r - c)
                board[r][c] = 'Q'
                backtrack(r + 1)
                board[r][c] = '.'
                cols.remove(c); d1.remove(r + c); d2.remove(r - c)
        
        backtrack(0)
        return res

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number} n
 * @return {string[][]}
 */
var solveNQueens = function(n) {
    const res = [];
    const board = Array.from({ length: n }, () => Array(n).fill('.'));
    const cols = new Set(), d1 = new Set(), d2 = new Set();

    // Time Complexity: O(N!)
    // Memory Complexity: O(N^2)
    function backtrack(r) {
        if (r === n) {
            res.push(board.map(row => row.join('')));
            return;
        }
        for (let c = 0; c < n; c++) {
            if (cols.has(c) || d1.has(r + c) || d2.has(r - c)) continue;
            cols.add(c); d1.add(r + c); d2.add(r - c);
            board[r][c] = 'Q';
            backtrack(r + 1);
            board[r][c] = '.';
            cols.delete(c); d1.delete(r + c); d2.delete(r - c);
        }
    }
    backtrack(0);
    return res;
};

```

# Typescript

## Sweet Spot

```typescript
function solveNQueens(n: number): string[][] {
    const res: string[][] = [];
    const board: string[][] = Array.from({ length: n }, () => Array(n).fill('.'));
    const cols = new Set<number>(), d1 = new Set<number>(), d2 = new Set<number>();

    // Time Complexity: O(N!)
    // Memory Complexity: O(N^2)
    function backtrack(r: number): void {
        if (r === n) {
            res.push(board.map(row => row.join('')));
            return;
        }
        for (let c = 0; c < n; c++) {
            if (cols.has(c) || d1.has(r + c) || d2.has(r - c)) continue;
            cols.add(c); d1.add(r + c); d2.add(r - c);
            board[r][c] = 'Q';
            backtrack(r + 1);
            board[r][c] = '.';
            cols.delete(c); d1.delete(r + c); d2.delete(r - c);
        }
    }
    backtrack(0);
    return res;
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public IList<IList<string>> SolveNQueens(int n) {
        var results = new List<IList<string>>();
        char[][] board = new char[n][];
        for (int i = 0; i < n; i++) {
            board[i] = new string('.', n).ToCharArray();
        }
        bool[] cols = new bool[n], d1 = new bool[2 * n], d2 = new bool[2 * n];
        Backtrack(0, n, board, results, cols, d1, d2);
        return results;
    }

    // Time Complexity: O(N!)
    // Memory Complexity: O(N^2)
    private void Backtrack(int r, int n, char[][] board, IList<IList<string>> res, bool[] c, bool[] d1, bool[] d2) {
        if (r == n) {
            res.Add(board.Select(row => new string(row)).ToList());
            return;
        }
        for (int col = 0; col < n; col++) {
            if (c[col] || d1[r + col] || d2[r - col + n]) continue;
            board[r][col] = 'Q';
            c[col] = d1[r + col] = d2[r - col + n] = true;
            Backtrack(r + 1, n, board, res, c, d1, d2);
            c[col] = d1[r + col] = d2[r - col + n] = false;
            board[r][col] = '.';
        }
    }
}

```

# C

## Sweet Spot

```c
/**
 * Return an array of arrays of size *returnSize.
 * The sizes of the arrays are returned as *returnColumnSizes array.
 * Note: Both returned array and *columnSizes array must be malloced, assume caller calls free().
 */
// Time Complexity: O(N!)
// Memory Complexity: O(N^2)
void solve(int r, int n, int* pos, int* resCount, char**** res, int* cols, int* d1, int* d2) {
    if (r == n) {
        (*res)[*resCount] = malloc(n * sizeof(char*));
        for (int i = 0; i < n; i++) {
            (*res)[*resCount][i] = malloc((n + 1) * sizeof(char));
            for (int j = 0; j < n; j++) {
                (*res)[*resCount][i][j] = (pos[i] == j) ? 'Q' : '.';
            }
            (*res)[*resCount][i][n] = '\0';
        }
        (*resCount)++;
        return;
    }
    for (int c = 0; c < n; c++) {
        if (cols[c] || d1[r + c] || d2[r - c + n]) continue;
        pos[r] = c;
        cols[c] = d1[r + c] = d2[r - c + n] = 1;
        solve(r + 1, n, pos, resCount, res, cols, d1, d2);
        cols[c] = d1[r + c] = d2[r - c + n] = 0;
    }
}

char*** solveNQueens(int n, int* returnSize, int** returnColumnSizes) {
    char*** res = malloc(1000 * sizeof(char**));
    int* pos = malloc(n * sizeof(int));
    int cols[20] = {0}, d1[40] = {0}, d2[40] = {0};
    *returnSize = 0;
    solve(0, n, pos, returnSize, &res, cols, d1, d2);
    *returnColumnSizes = malloc((*returnSize) * sizeof(int));
    for (int i = 0; i < *returnSize; i++) {
        (*returnColumnSizes)[i] = n;
    }
    free(pos);
    return res;
}
```

# Go

## Sweet Spot

```go
func solveNQueens(n int) [][]string {
    res := [][]string{}
    board := make([][]byte, n)
    for i := range board {
        board[i] = make([]byte, n)
        for j := range board[i] { board[i][j] = '.' }
    }
    cols, d1, d2 := make([]bool, n), make([]bool, 2*n), make([]bool, 2*n)
    
    // Time Complexity: O(N!)
    // Memory Complexity: O(N^2)
    var backtrack func(int)
    backtrack = func(r int) {
        if r == n {
            temp := make([]string, n)
            for i := range board { temp[i] = string(board[i]) }
            res = append(res, temp)
            return
        }
        for c := 0; c < n; c++ {
            if cols[c] || d1[r+c] || d2[r-c+n] { continue }
            board[r][c], cols[c], d1[r+c], d2[r-c+n] = 'Q', true, true, true
            backtrack(r + 1)
            board[r][c], cols[c], d1[r+c], d2[r-c+n] = '.', false, false, false
        }
    }
    backtrack(0)
    return res
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun solveNQueens(n: Int): List<List<String>> {
        val res = mutableListOf<List<String>>()
        val board = Array(n) { CharArray(n) { '.' } }
        val cols = BooleanArray(n)
        val d1 = BooleanArray(2 * n)
        val d2 = BooleanArray(2 * n)

        // Time Complexity: O(N!)
        // Memory Complexity: O(N^2)
        fun backtrack(r: Int) {
            if (r == n) {
                res.add(board.map { String(it) })
                return
            }
            for (c in 0 until n) {
                if (cols[c] || d1[r + c] || d2[r - c + n]) continue
                board[r][c] = 'Q'
                cols[c] = true; d1[r + c] = true; d2[r - c + n] = true
                backtrack(r + 1)
                board[r][c] = '.'
                cols[c] = false; d1[r + c] = false; d2[r - c + n] = false
            }
        }
        backtrack(0)
        return res
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func solveNQueens(_ n: Int) -> [[String]] {
        var res = [[String]]()
        var board = Array(repeating: Array(repeating: ".", count: n), count: n)
        var cols = Array(repeating: false, count: n)
        var d1 = Array(repeating: false, count: 2 * n)
        var d2 = Array(repeating: false, count: 2 * n)

        // Time Complexity: O(N!)
        // Memory Complexity: O(N^2)
        func backtrack(_ r: Int) {
            if r == n {
                res.append(board.map { $0.joined() })
                return
            }
            for c in 0..<n {
                if cols[c] || d1[r + c] || d2[r - c + n] { continue }
                board[r][c] = "Q"
                cols[c] = true; d1[r + c] = true; d2[r - c + n] = true
                backtrack(r + 1)
                board[r][c] = "."
                cols[c] = false; d1[r + c] = false; d2[r - c + n] = false
            }
        }
        backtrack(0)
        return res
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn solve_n_queens(n: i32) -> Vec<Vec<String>> {
        let n = n as usize;
        let mut res = Vec::new();
        let mut board = vec![vec!['.'; n]; n];
        let (mut cols, mut d1, mut d2) = (vec![false; n], vec![false; 2*n], vec![false; 2*n]);

        // Time Complexity: O(N!)
        // Memory Complexity: O(N^2)
        fn backtrack(r: usize, n: usize, board: &mut Vec<Vec<char>>, res: &mut Vec<Vec<String>>, 
                    cols: &mut Vec<bool>, d1: &mut Vec<bool>, d2: &mut Vec<bool>) {
            if r == n {
                res.push(board.iter().map(|row| row.iter().collect()).collect());
                return;
            }
            for c in 0..n {
                if cols[c] || d1[r + c] || d2[r + n - c] { continue; }
                board[r][c] = 'Q';
                cols[c] = true; d1[r + c] = true; d2[r + n - c] = true;
                backtrack(r + 1, n, board, res, cols, d1, d2);
                board[r][c] = '.';
                cols[c] = false; d1[r + c] = false; d2[r + n - c] = false;
            }
        }
        backtrack(0, n, &mut board, &mut res, &mut cols, &mut d1, &mut d2);
        res
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer} n
# @return {String[][]}
def solve_n_queens(n)
  res = []
  board = Array.new(n) { "." * n }
  cols = {}
  diag1 = {}
  diag2 = {}

  # Time Complexity: O(N!)
  # Memory Complexity: O(N^2)
  backtrack = lambda do |r|
    if r == n
      res << board.map(&:dup)
      return
    end

    (0...n).each do |c|
      if !cols[c] && !diag1[r - c] && !diag2[r + c]
        cols[c] = diag1[r - c] = diag2[r + c] = true
        board[r][c] = "Q"
        
        backtrack.call(r + 1)
        
        board[r][c] = "."
        cols[c] = diag1[r - c] = diag2[r + c] = false
      end
    end
  end

  backtrack.call(0)
  res
end
```

# php

## Sweet Spot

```php
class Solution {
    /**
     * @param Integer $n
     * @return String[][]
     */
    function solveNQueens($n) {
        $res = [];
        $board = array_fill(0, $n, str_repeat('.', $n));
        $cols = $d1 = $d2 = [];

        // Time Complexity: O(N!)
        // Memory Complexity: O(N^2)
        $backtrack = function($r) use (&$res, &$board, &$cols, &$d1, &$d2, $n, &$backtrack) {
            if ($r == $n) {
                $res[] = $board;
                return;
            }
            for ($c = 0; $c < $n; $c++) {
                if (isset($cols[$c]) || isset($d1[$r + $c]) || isset($d2[$r - $c])) continue;
                $cols[$c] = $d1[$r + $c] = $d2[$r - $c] = true;
                $board[$r][$c] = 'Q';
                $backtrack($r + 1);
                $board[$r][$c] = '.';
                unset($cols[$c], $d1[$r + $c], $d2[$r - $c]);
            }
        };
        $backtrack(0);
        return $res;
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  List<List<String>> solveNQueens(int n) {
    List<List<String>> res = [];
    List<List<String>> board = List.generate(n, (_) => List.filled(n, '.'));
    Set<int> cols = {}, d1 = {}, d2 = {};

    // Time Complexity: O(N!)
    // Memory Complexity: O(N^2)
    void backtrack(int r) {
      if (r == n) {
        res.add(board.map((row) => row.join('')).toList());
        return;
      }
      for (int c = 0; c < n; c++) {
        if (cols.contains(c) || d1.contains(r + c) || d2.contains(r - c)) continue;
        cols.add(c); d1.add(r + c); d2.add(r - c);
        board[r][c] = 'Q';
        backtrack(r + 1);
        board[r][c] = '.';
        cols.remove(c); d1.remove(r + c); d2.remove(r - c);
      }
    }
    backtrack(0);
    return res;
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def solveNQueens(n: Int): List[List[String]] = {
        var res = List[List[String]]()
        
        // Time Complexity: O(N!)
        // Memory Complexity: O(N^2)
        def solve(r: Int, cols: Int, d1: Int, d2: Int, board: List[Int]): Unit = {
            if (r == n) {
                res = res :+ board.map(c => "." * c + "Q" + "." * (n - c - 1))
                return
            }
            for (c <- 0 until n) {
                if (((cols >> c) & 1) == 0 && ((d1 >> (r + c)) & 1) == 0 && ((d2 >> (r - c + n)) & 1) == 0) {
                    solve(r + 1, cols | (1 << c), d1 | (1 << (r + c)), d2 | (1 << (r - c + n)), board :+ c)
                }
            }
        }
        solve(0, 0, 0, 0, List())
        res
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec solve_n_queens(n :: integer) :: [[String.t]]
  def solve_n_queens(n) do
    # Time Complexity: O(N!)
    # Memory Complexity: O(N^2)
    solve(0, n, [], [], [], [])
  end

  defp solve(r, n, current, cols, d1, d2) when r == n do
    [Enum.map(current, fn c -> 
      String.duplicate(".", c) <> "Q" <> String.duplicate(".", n - c - 1)
    end) |> Enum.reverse()]
  end

  defp solve(r, n, current, cols, d1, d2) do
    0..(n - 1)
    |> Enum.filter(fn c -> 
      c not in cols and (r + c) not in d1 and (r - c) not in d2
    end)
    |> Enum.flat_map(fn c -> 
      solve(r + 1, n, [c | current], [c | cols], [r + c | d1], [r - c | d2])
    end)
  end
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec solve_n_queens(N :: integer()) -> [[unicode:unicode_binary()]].
solve_n_queens(N) ->
  % Time Complexity: O(N!)
  % Memory Complexity: O(N^2)
  solve(0, N, [], [], [], []).

solve(R, N, Current, _Cols, _D1, _D2) when R =:= N ->
  [ [ << << (case C =:= Col of true -> $Q; false -> $. end) >> || Col <- lists:seq(0, N-1) >> || C <- lists:reverse(Current) ] ];
solve(R, N, Current, Cols, D1, D2) ->
  lists:flatmap(fun(C) ->
    case lists:member(C, Cols) orelse lists:member(R + C, D1) orelse lists:member(R - C, D2) of
      true -> [];
      false -> solve(R + 1, N, [C | Current], [C | Cols], [R + C | D1], [R - C | D2])
    end
  end, lists:seq(0, N - 1)).

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (solve-n-queens n)
  (-> exact-integer? (listof (listof string?)))
  ; Time Complexity: O(N!)
  ; Memory Complexity: O(N^2)
  (let solve ([r 0] [cols '()] [d1 '()] [d2 '()] [board '()])
    (if (= r n)
        (list (reverse (map (λ (c) (let ([str (make-string n #\.)]) (string-set! str c #\Q) str)) board)))
        (append-map (λ (c)
                      (if (or (member c cols) (member (+ r c) d1) (member (- r c) d2))
                          '()
                          (solve (+ r 1) (cons c cols) (cons (+ r c) d1) (cons (- r c) d2) (cons c board))))
                    (range n)))))

```