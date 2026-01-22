# cpp

## Sweet Spot

```cpp
class Solution {
public:
    bool exist(vector<vector<char>>& board, string word) {
        int m = board.size();
        int n = board[0].size();
        for (int i = 0; i < m; ++i) {
            for (int j = 0; j < n; ++j) {
                if (dfs(board, word, 0, i, j)) return true;
            }
        }
        return false;
    }

private:
    bool dfs(vector<vector<char>>& board, const string& word, int k, int r, int c) {
        if (k == word.length()) return true;
        if (r < 0 || r >= board.size() || c < 0 || c >= board[0].size() || board[r][c] != word[k]) return false;
        char temp = board[r][c];
        board[r][c] = '\0';
        bool res = dfs(board, word, k + 1, r + 1, c) ||
                   dfs(board, word, k + 1, r - 1, c) ||
                   dfs(board, word, k + 1, r, c + 1) ||
                   dfs(board, word, k + 1, r, c - 1);
        board[r][c] = temp;
        return res;
    }
};
// Time Complexity: O(M * N * 3^L) where L is the length of the word
// Memory Complexity: O(L)

```

# java

## Sweet Spot

```java
class Solution {
    public boolean exist(char[][] board, String word) {
        int m = board.length;
        int n = board[0].length;
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (dfs(board, word, 0, i, j)) return true;
            }
        }
        return false;
    }

    private boolean dfs(char[][] board, String word, int k, int r, int c) {
        if (k == word.length()) return true;
        if (r < 0 || r >= board.length || c < 0 || c >= board[0].length || board[r][c] != word.charAt(k)) return false;
        char temp = board[r][c];
        board[r][c] = '\0';
        boolean res = dfs(board, word, k + 1, r + 1, c) ||
                      dfs(board, word, k + 1, r - 1, c) ||
                      dfs(board, word, k + 1, r, c + 1) ||
                      dfs(board, word, k + 1, r, c - 1);
        board[r][c] = temp;
        return res;
    }
}
// Time Complexity: O(M * N * 3^L)
// Memory Complexity: O(L)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def exist(self, board: List[List[str]], word: str) -> bool:
        m, n = len(board), len(board[0])
        def dfs(k, r, c):
            if k == len(word):
                return True
            if r < 0 or r >= m or c < 0 or c >= n or board[r][c] != word[k]:
                return False
            tmp, board[r][c] = board[r][c], ""
            res = (dfs(k + 1, r + 1, c) or dfs(k + 1, r - 1, c) or 
                   dfs(k + 1, r, c + 1) or dfs(k + 1, r, c - 1))
            board[r][c] = tmp
            return res
        return any(dfs(0, i, j) for i in range(m) for j in range(n))
# Time Complexity: O(M * N * 3^L)
# Memory Complexity: O(L)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def exist(self, board, word):
        """
        :type board: List[List[str]]
        :type word: str
        :rtype: bool
        """
        m, n = len(board), len(board[0])
        def dfs(k, r, c):
            if k == len(word):
                return True
            if r < 0 or r >= m or c < 0 or c >= n or board[r][c] != word[k]:
                return False
            tmp = board[r][c]
            board[r][c] = None
            res = (dfs(k + 1, r + 1, c) or dfs(k + 1, r - 1, c) or 
                   dfs(k + 1, r, c + 1) or dfs(k + 1, r, c - 1))
            board[r][c] = tmp
            return res
        for i in range(m):
            for j in range(n):
                if dfs(0, i, j): return True
        return False
# Time Complexity: O(M * N * 3^L)
# Memory Complexity: O(L)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {character[][]} board
 * @param {string} word
 * @return {boolean}
 */
var exist = function(board, word) {
    const m = board.length, n = board[0].length;
    const dfs = (k, r, c) => {
        if (k === word.length) return true;
        if (r < 0 || r >= m || c < 0 || c >= n || board[r][c] !== word[k]) return false;
        const tmp = board[r][c];
        board[r][c] = '#';
        const res = dfs(k + 1, r + 1, c) || dfs(k + 1, r - 1, c) || 
                    dfs(k + 1, r, c + 1) || dfs(k + 1, r, c - 1);
        board[r][c] = tmp;
        return res;
    };
    for (let i = 0; i < m; i++) {
        for (let j = 0; j < n; j++) {
            if (dfs(0, i, j)) return true;
        }
    }
    return false;
};
// Time Complexity: O(M * N * 3^L)
// Memory Complexity: O(L)

```

# Typescript

## Sweet Spot

```typescript
function exist(board: string[][], word: string): boolean {
    const m = board.length, n = board[0].length;
    const dfs = (k: number, r: number, c: number): boolean => {
        if (k === word.length) return true;
        if (r < 0 || r >= m || c < 0 || c >= n || board[r][c] !== word[k]) return false;
        const tmp = board[r][c];
        board[r][c] = '#';
        const res = dfs(k + 1, r + 1, c) || dfs(k + 1, r - 1, c) || 
                    dfs(k + 1, r, c + 1) || dfs(k + 1, r, c - 1);
        board[r][c] = tmp;
        return res;
    };
    for (let i = 0; i < m; i++) {
        for (let j = 0; j < n; j++) {
            if (dfs(0, i, j)) return true;
        }
    }
    return false;
};
// Time Complexity: O(M * N * 3^L)
// Memory Complexity: O(L)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public bool Exist(char[][] board, string word) {
        int m = board.Length, n = board[0].Length;
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (Dfs(board, word, 0, i, j)) return true;
            }
        }
        return false;
    }

    private bool Dfs(char[][] board, string word, int k, int r, int c) {
        if (k == word.Length) return true;
        if (r < 0 || r >= board.Length || c < 0 || c >= board[0].Length || board[r][c] != word[k]) return false;
        char tmp = board[r][c];
        board[r][c] = '\0';
        bool res = Dfs(board, word, k + 1, r + 1, c) || Dfs(board, word, k + 1, r - 1, c) || 
                   Dfs(board, word, k + 1, r, c + 1) || Dfs(board, word, k + 1, r, c - 1);
        board[r][c] = tmp;
        return res;
    }
}
// Time Complexity: O(M * N * 3^L)
// Memory Complexity: O(L)

```

# C

## Sweet Spot

```c
bool dfs(char** board, int boardSize, int boardColSize, char* word, int k, int r, int c) {
    if (word[k] == '\0') return true;
    if (r < 0 || r >= boardSize || c < 0 || c >= boardColSize || board[r][c] != word[k]) return false;
    char tmp = board[r][c];
    board[r][c] = '\0';
    bool res = dfs(board, boardSize, boardColSize, word, k + 1, r + 1, c) ||
               dfs(board, boardSize, boardColSize, word, k + 1, r - 1, c) ||
               dfs(board, boardSize, boardColSize, word, k + 1, r, c + 1) ||
               dfs(board, boardSize, boardColSize, word, k + 1, r, c - 1);
    board[r][c] = tmp;
    return res;
}

bool exist(char** board, int boardSize, int* boardColSize, char* word) {
    for (int i = 0; i < boardSize; i++) {
        for (int j = 0; j < boardColSize[i]; j++) {
            if (dfs(board, boardSize, boardColSize[i], word, 0, i, j)) return true;
        }
    }
    return false;
}
// Time Complexity: O(M * N * 3^L)
// Memory Complexity: O(L)

```

# Go

## Sweet Spot

```go
func exist(board [][]byte, word string) bool {
    m, n := len(board), len(board[0])
    var dfs func(int, int, int) bool
    dfs = func(k, r, c int) bool {
        if k == len(word) {
            return true
        }
        if r < 0 || r >= m || c < 0 || c >= n || board[r][c] != word[k] {
            return false
        }
        tmp := board[r][c]
        board[r][c] = 0
        res := dfs(k+1, r+1, c) || dfs(k+1, r-1, c) || dfs(k+1, r, c+1) || dfs(k+1, r, c-1)
        board[r][c] = tmp
        return res
    }
    for i := 0; i < m; i++ {
        for j := 0; j < n; j++ {
            if dfs(0, i, j) {
                return true
            }
        }
    }
    return false
}
// Time Complexity: O(M * N * 3^L)
// Memory Complexity: O(L)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun exist(board: Array<CharArray>, word: String): Boolean {
        val m = board.size
        val n = board[0].size
        for (i in 0 until m) {
            for (j in 0 until n) {
                if (dfs(board, word, 0, i, j)) return true
            }
        }
        return false
    }

    private fun dfs(board: Array<CharArray>, word: String, k: Int, r: Int, c: Int): Boolean {
        if (k == word.length) return true
        if (r < 0 || r >= board.size || c < 0 || c >= board[0].size || board[r][c] != word[k]) return false
        val tmp = board[r][c]
        board[r][c] = '\u0000'
        val res = dfs(board, word, k + 1, r + 1, c) || dfs(board, word, k + 1, r - 1, c) ||
                  dfs(board, word, k + 1, r, c + 1) || dfs(board, word, k + 1, r, c - 1)
        board[r][c] = tmp
        return res
    }
}
// Time Complexity: O(M * N * 3^L)
// Memory Complexity: O(L)

```

# swift

## Sweet Spot

```swift
class Solution {
    func exist(_ board: [[Character]], _ word: String) -> Bool {
        var board = board
        let wordArr = Array(word)
        let m = board.count
        let n = board[0].count
        
        func dfs(_ k: Int, _ r: Int, _ c: Int) -> Bool {
            if k == wordArr.count { return true }
            if r < 0 || r >= m || c < 0 || c >= n || board[r][c] != wordArr[k] { return false }
            let tmp = board[r][c]
            board[r][c] = " "
            let res = dfs(k + 1, r + 1, c) || dfs(k + 1, r - 1, c) || 
                      dfs(k + 1, r, c + 1) || dfs(k + 1, r, c - 1)
            board[r][c] = tmp
            return res
        }
        
        for i in 0..<m {
            for j in 0..<n {
                if dfs(0, i, j) { return true }
            }
        }
        return false
    }
}
// Time Complexity: O(M * N * 3^L)
// Memory Complexity: O(L)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn exist(mut board: Vec<Vec<char>>, word: String) -> bool {
        let word: Vec<char> = word.chars().collect();
        let m = board.len();
        let n = board[0].len();
        for i in 0..m {
            for j in 0..n {
                if Self::dfs(&mut board, &word, 0, i as i32, j as i32) {
                    return true;
                }
            }
        }
        false
    }

    fn dfs(board: &mut Vec<Vec<char>>, word: &[char], k: usize, r: i32, c: i32) -> bool {
        if k == word.len() { return true; }
        if r < 0 || r >= board.len() as i32 || c < 0 || c >= board[0].len() as i32 { return false; }
        if board[r as usize][c as usize] != word[k] { return false; }
        
        let tmp = board[r as usize][c as usize];
        board[r as usize][c as usize] = '\0';
        let res = Self::dfs(board, word, k + 1, r + 1, c) ||
                  Self::dfs(board, word, k + 1, r - 1, c) ||
                  Self::dfs(board, word, k + 1, r, c + 1) ||
                  Self::dfs(board, word, k + 1, r, c - 1);
        board[r as usize][c as usize] = tmp;
        res
    }
}
// Time Complexity: O(M * N * 3^L)
// Memory Complexity: O(L)

```

# ruby

## Sweet Spot

```ruby
# @param {Character[][]} board
# @param {String} word
# @return {Boolean}
def exist(board, word)
  m = board.length
  n = board[0].length
  return false if word.length > m * n

  board_counts = Hash.new(0)
  board.each { |row| row.each { |char| board_counts[char] += 1 } }
  
  word_counts = Hash.new(0)
  word.each_char { |char| word_counts[char] += 1 }
  
  word_counts.each do |char, count|
    return false if board_counts[char] < count
  end

  if board_counts[word[0]] > board_counts[word[-1]]
    word = word.reverse
  end

  def dfs(board, word, k, r, c, m, n)
    return true if k == word.length
    return false if r < 0 || r >= m || c < 0 || c >= n || board[r][c] != word[k]

    tmp = board[r][c]
    board[r][c] = nil
    
    res = dfs(board, word, k + 1, r + 1, c, m, n) ||
          dfs(board, word, k + 1, r - 1, c, m, n) ||
          dfs(board, word, k + 1, r, c + 1, m, n) ||
          dfs(board, word, k + 1, r, c - 1, m, n)
    
    board[r][c] = tmp
    res
  end

  (0...m).each do |i|
    (0...n).each do |j|
      return true if dfs(board, word, 0, i, j, m, n)
    end
  end

  false
end
# Time Complexity: O(M * N * 3^L)
# Memory Complexity: O(L)
```

# php

## Sweet Spot

```php
class Solution {
    /**
     * @param String[][] $board
     * @param String $word
     * @return Boolean
     */
    function exist($board, $word) {
        $m = count($board);
        $n = count($board[0]);
        for ($i = 0; $i < $m; $i++) {
            for ($j = 0; $j < $n; $j++) {
                if ($this->dfs($board, $word, 0, $i, $j)) return true;
            }
        }
        return false;
    }

    function dfs(&$board, $word, $k, $r, $c) {
        if ($k == strlen($word)) return true;
        if ($r < 0 || $r >= count($board) || $c < 0 || $c >= count($board[0]) || $board[$r][$c] !== $word[$k]) return false;
        $tmp = $board[$r][$c];
        $board[$r][$c] = '#';
        $res = $this->dfs($board, $word, $k + 1, $r + 1, $c) ||
               $this->dfs($board, $word, $k + 1, $r - 1, $c) ||
               $this->dfs($board, $word, $k + 1, $r, $c + 1) ||
               $this->dfs($board, $word, $k + 1, $r, $c - 1);
        $board[$r][$c] = $tmp;
        return $res;
    }
}
// Time Complexity: O(M * N * 3^L)
// Memory Complexity: O(L)

```

# dart

## Sweet Spot

```dart
class Solution {
  bool exist(List<List<String>> board, String word) {
    int m = board.length;
    int n = board[0].length;
    for (int i = 0; i < m; i++) {
      for (int j = 0; j < n; j++) {
        if (_dfs(board, word, 0, i, j)) return true;
      }
    }
    return false;
  }

  bool _dfs(List<List<String>> board, String word, int k, int r, int c) {
    if (k == word.length) return true;
    if (r < 0 || r >= board.length || c < 0 || c >= board[0].length || board[r][c] != word[k]) return false;
    String tmp = board[r][c];
    board[r][c] = '#';
    bool res = _dfs(board, word, k + 1, r + 1, c) ||
               _dfs(board, word, k + 1, r - 1, c) ||
               _dfs(board, word, k + 1, r, c + 1) ||
               _dfs(board, word, k + 1, r, c - 1);
    board[r][c] = tmp;
    return res;
  }
}
// Time Complexity: O(M * N * 3^L)
// Memory Complexity: O(L)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
import scala.util.boundary, boundary.break

object Solution {
    def exist(board: Array[Array[Char]], word: String): Boolean = {
        val m = board.length
        val n = board(0).length

        def dfs(k: Int, r: Int, c: Int): Boolean = {
            if (k == word.length) true
            else if (r < 0 || r >= m || c < 0 || c >= n || board(r)(c) != word(k)) false
            else {
                val tmp = board(r)(c)
                board(r)(c) = '\u0000'
                val res = dfs(k + 1, r + 1, c) || dfs(k + 1, r - 1, c) || 
                          dfs(k + 1, r, c + 1) || dfs(k + 1, r, c - 1)
                board(r)(c) = tmp
                res
            }
        }

        boundary {
            for (i <- 0 until m; j <- 0 until n) {
                if (dfs(0, i, j)) break(true)
            }
            false
        }
    }
}
// Time Complexity: O(M * N * 4^L)
// Memory Complexity: O(L)
```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec exist(board :: [[char]], word :: String.t()) :: boolean
  def exist(board, word) do
    matrix = board |> Enum.map(&List.to_tuple/1) |> List.to_tuple()
    m = tuple_size(matrix)
    n = tuple_size(elem(matrix, 0))
    target = String.to_charlist(word)

    Enum.any?(0..(m - 1), fn r ->
      Enum.any?(0..(n - 1), fn c ->
        dfs(matrix, target, r, c, m, n, MapSet.new())
      end)
    end)
  end

  defp dfs(matrix, [char | rest], r, c, m, n, visited) do
    if r >= 0 and r < m and c >= 0 and c < n and
         elem(elem(matrix, r), c) == char and not MapSet.member?(visited, {r, c}) do
      if rest == [] do
        true
      else
        new_visited = MapSet.put(visited, {r, c})

        dfs(matrix, rest, r + 1, c, m, n, new_visited) or
          dfs(matrix, rest, r - 1, c, m, n, new_visited) or
          dfs(matrix, rest, r, c + 1, m, n, new_visited) or
          dfs(matrix, rest, r, c - 1, m, n, new_visited)
      end
    else
      false
    end
  end
end
# Time Complexity: O(M * N * 3^L)
# Memory Complexity: O(L)
```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec exist(Board :: [[char()]], Word :: unicode:unicode_binary()) -> boolean().
exist(Board, Word) ->
    Matrix = list_to_tuple([list_to_tuple(Row) || Row <- Board]),
    M = tuple_size(Matrix),
    N = tuple_size(element(1, Matrix)),
    Target = unicode:characters_to_list(Word),
    check_cells(0, 0, M, N, Matrix, Target).

check_cells(R, _C, M, _N, _Matrix, _Target) when R >= M -> false;
check_cells(R, C, M, N, Matrix, Target) when C >= N -> check_cells(R + 1, 0, M, N, Matrix, Target);
check_cells(R, C, M, N, Matrix, Target) ->
    case dfs(R, C, Matrix, Target, M, N, sets:new()) of
        true -> true;
        false -> check_cells(R, C + 1, M, N, Matrix, Target)
    end.

dfs(_R, _C, _Matrix, [], _M, _N, _Visited) -> true;
dfs(R, C, Matrix, [Char | Rest], M, N, Visited) ->
    ValidCoord = R >= 0 andalso R < M andalso C >= 0 andalso C < N,
    if 
        ValidCoord ->
            CellValue = element(C + 1, element(R + 1, Matrix)),
            IsVisited = sets:is_element({R, C}, Visited),
            if CellValue =:= Char andalso not IsVisited ->
                NewVisited = sets:add_element({R, C}, Visited),
                dfs(R + 1, C, Matrix, Rest, M, N, NewVisited) orelse
                dfs(R - 1, C, Matrix, Rest, M, N, NewVisited) orelse
                dfs(R, C + 1, Matrix, Rest, M, N, NewVisited) orelse
                dfs(R, C - 1, Matrix, Rest, M, N, NewVisited);
               true -> false
            end;
        true -> false
    end.
% Time Complexity: O(M * N * 3^L)
% Memory Complexity: O(L)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (exist board word)
  (-> (listof (listof char?)) string? boolean?)
  (let* ([m (length board)]
         [n (length (car board))]
         [vec-board (list->vector (map list->vector board))]
         [target (string->list word)])
    (define (dfs k r c visited)
      (cond
        [(= k (length target)) #t]
        [(or (< r 0) (>= r m) (< c 0) (>= c n)
             (set-member? visited (cons r c))
             (not (char=? (vector-ref (vector-ref vec-board r) c) (list-ref target k)))) #f]
        [else
         (let ([new-visited (set-add visited (cons r c))])
           (or (dfs (+ k 1) (+ r 1) c new-visited)
               (dfs (+ k 1) (- r 1) c new-visited)
               (dfs (+ k 1) r (+ c 1) new-visited)
               (dfs (+ k 1) r (- c 1) new-visited)))]))
    (let loop ([r 0])
      (if (= r m) #f
          (let inner ([c 0])
            (if (= c n) (loop (+ r 1))
                (if (dfs 0 r c (set)) #t (inner (+ c 1)))))))))
; Time Complexity: O(M * N * 3^L)
; Memory Complexity: O(L)

```