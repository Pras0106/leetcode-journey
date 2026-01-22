# cpp

## Memory O(1) | Sweet Spot

```cpp
class Solution {
public:
    int minPathSum(vector<vector<int>>& grid) {
        int m = grid.size();
        int n = grid[0].size();
        for (int i = 0; i < m; ++i) {
            for (int j = 0; j < n; ++j) {
                if (i == 0 && j == 0) continue;
                if (i == 0) grid[i][j] += grid[i][j - 1];
                else if (j == 0) grid[i][j] += grid[i - 1][j];
                else grid[i][j] += min(grid[i - 1][j], grid[i][j - 1]);
            }
        }
        return grid[m - 1][n - 1];
    }
};
// Time: O(m * n), Memory: O(1)

```

# java

## Memory O(1) | Sweet Spot

```java
class Solution {
    public int minPathSum(int[][] grid) {
        int m = grid.length;
        int n = grid[0].length;
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (i == 0 && j == 0) continue;
                if (i == 0) grid[i][j] += grid[i][j - 1];
                else if (j == 0) grid[i][j] += grid[i - 1][j];
                else grid[i][j] += Math.min(grid[i - 1][j], grid[i][j - 1]);
            }
        }
        return grid[m - 1][n - 1];
    }
}
// Time: O(m * n), Memory: O(1)

```

# python 3.14

## Memory O(1) | Sweet Spot

```python 3.14
class Solution:
    def minPathSum(self, grid: List[List[int]]) -> int:
        m, n = len(grid), len(grid[0])
        for i in range(m):
            for j in range(n):
                if i == 0 and j == 0: continue
                if i == 0: grid[i][j] += grid[i][j-1]
                elif j == 0: grid[i][j] += grid[i-1][j]
                else: grid[i][j] += min(grid[i-1][j], grid[i][j-1])
        return grid[-1][-1]
# Time: O(m * n), Memory: O(1)

```

# python 2.7.11

## Memory O(1) | Sweet Spot

```python 2.7.11
class Solution(object):
    def minPathSum(self, grid):
        """
        :type grid: List[List[int]]
        :rtype: int
        """
        m = len(grid)
        n = len(grid[0])
        for i in range(m):
            for j in range(n):
                if i == 0 and j == 0: continue
                if i == 0: grid[i][j] += grid[i][j-1]
                elif j == 0: grid[i][j] += grid[i-1][j]
                else: grid[i][j] += min(grid[i-1][j], grid[i][j-1])
        return grid[m-1][n-1]
# Time: O(m * n), Memory: O(1)

```

# JavaScript

## Memory O(1) | Sweet Spot

```javascript
/**
 * @param {number[][]} grid
 * @return {number}
 */
var minPathSum = function(grid) {
    const m = grid.length;
    const n = grid[0].length;
    for (let i = 0; i < m; i++) {
        for (let j = 0; j < n; j++) {
            if (i === 0 && j === 0) continue;
            if (i === 0) grid[i][j] += grid[i][j - 1];
            else if (j === 0) grid[i][j] += grid[i - 1][j];
            else grid[i][j] += Math.min(grid[i - 1][j], grid[i][j - 1]);
        }
    }
    return grid[m - 1][n - 1];
};
// Time: O(m * n), Memory: O(1)

```

# Typescript

## Memory O(1) | Sweet Spot

```typescript
function minPathSum(grid: number[][]): number {
    const m = grid.length;
    const n = grid[0].length;
    for (let i = 0; i < m; i++) {
        for (let j = 0; j < n; j++) {
            if (i === 0 && j === 0) continue;
            if (i === 0) grid[i][j] += grid[i][j - 1];
            else if (j === 0) grid[i][j] += grid[i - 1][j];
            else grid[i][j] += Math.min(grid[i - 1][j], grid[i][j - 1]);
        }
    }
    return grid[m - 1][n - 1];
};
// Time: O(m * n), Memory: O(1)

```

# C#

## Memory O(1) | Sweet Spot

```c#
public class Solution {
    public int MinPathSum(int[][] grid) {
        int m = grid.Length;
        int n = grid[0].Length;
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (i == 0 && j == 0) continue;
                if (i == 0) grid[i][j] += grid[i][j - 1];
                else if (j == 0) grid[i][j] += grid[i - 1][j];
                else grid[i][j] += Math.Min(grid[i - 1][j], grid[i][j - 1]);
            }
        }
        return grid[m - 1][n - 1];
    }
}
// Time: O(m * n), Memory: O(1)

```

# C

## Memory O(1) | Sweet Spot

```c
int minPathSum(int** grid, int gridSize, int* gridColSize) {
    int m = gridSize;
    int n = gridColSize[0];
    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++) {
            if (i == 0 && j == 0) continue;
            if (i == 0) grid[i][j] += grid[i][j - 1];
            else if (j == 0) grid[i][j] += grid[i - 1][j];
            else {
                int left = grid[i][j - 1];
                int up = grid[i - 1][j];
                grid[i][j] += (left < up) ? left : up;
            }
        }
    }
    return grid[m - 1][n - 1];
}
// Time: O(m * n), Memory: O(1)

```

# Go

## Memory O(1) | Sweet Spot

```go
func minPathSum(grid [][]int) int {
    m := len(grid)
    n := len(grid[0])
    for i := 0; i < m; i++ {
        for j := 0; j < n; j++ {
            if i == 0 && j == 0 {
                continue
            }
            if i == 0 {
                grid[i][j] += grid[i][j-1]
            } else if j == 0 {
                grid[i][j] += grid[i-1][j]
            } else {
                if grid[i-1][j] < grid[i][j-1] {
                    grid[i][j] += grid[i-1][j]
                } else {
                    grid[i][j] += grid[i][j-1]
                }
            }
        }
    }
    return grid[m-1][n-1]
}
// Time: O(m * n), Memory: O(1)

```

# Kotlin

## Memory O(1) | Sweet Spot

```kotlin
class Solution {
    fun minPathSum(grid: Array<IntArray>): Int {
        val m = grid.size
        val n = grid[0].size
        for (i in 0 until m) {
            for (j in 0 until n) {
                if (i == 0 && j == 0) continue
                if (i == 0) grid[i][j] += grid[i][j - 1]
                else if (j == 0) grid[i][j] += grid[i - 1][j]
                else grid[i][j] += Math.min(grid[i - 1][j], grid[i][j - 1])
            }
        }
        return grid[m - 1][n - 1]
    }
}
// Time: O(m * n), Memory: O(1)

```

# swift

## Memory O(1) | Sweet Spot

```swift
class Solution {
    func minPathSum(_ grid: [[Int]]) -> Int {
        var grid = grid
        let m = grid.count
        let n = grid[0].count
        for i in 0..<m {
            for j in 0..<n {
                if i == 0 && j == 0 { continue }
                if i == 0 { grid[i][j] += grid[i][j - 1] }
                else if j == 0 { grid[i][j] += grid[i - 1][j] }
                else { grid[i][j] += min(grid[i - 1][j], grid[i][j - 1]) }
            }
        }
        return grid[m - 1][n - 1]
    }
}
// Time: O(m * n), Memory: O(m * n) due to copy, O(1) if in-place allowed

```

# rust

## Memory O(1) | Sweet Spot

```rust
impl Solution {
    pub fn min_path_sum(mut grid: Vec<Vec<i32>>) -> i32 {
        let m = grid.len();
        let n = grid[0].len();
        for i in 0..m {
            for j in 0..n {
                if i == 0 && j == 0 { continue; }
                if i == 0 { grid[i][j] += grid[i][j-1]; }
                else if j == 0 { grid[i][j] += grid[i-1][j]; }
                else { grid[i][j] += std::cmp::min(grid[i-1][j], grid[i][j-1]); }
            }
        }
        grid[m-1][n-1]
    }
}
// Time: O(m * n), Memory: O(1)

```

# ruby

## Memory O(1) | Sweet Spot

```ruby
# @param {Integer[][]} grid
# @return {Integer}
def min_path_sum(grid)
  m = grid.length
  n = grid[0].length
  (0...m).each do |i|
    (0...n).each do |j|
      next if i == 0 && j == 0
      if i == 0
        grid[i][j] += grid[i][j-1]
      elsif j == 0
        grid[i][j] += grid[i-1][j]
      else
        grid[i][j] += [grid[i-1][j], grid[i][j-1]].min
      end
    end
  end
  grid[m-1][n-1]
end
# Time: O(m * n), Memory: O(1)

```

# php

## Memory O(1) | Sweet Spot

```php
class Solution {

    /**
     * @param Integer[][] $grid
     * @return Integer
     */
    function minPathSum(&$grid) {
        $m = count($grid);
        $n = count($grid[0]);
        for ($i = 0; $i < $m; $i++) {
            for ($j = 0; $j < $n; $j++) {
                if ($i == 0 && $j == 0) continue;
                if ($i == 0) $grid[$i][$j] += $grid[$i][$j - 1];
                else if ($j == 0) $grid[$i][$j] += $grid[$i - 1][$j];
                else $grid[$i][$j] += min($grid[$i - 1][$j], $grid[$i][$j - 1]);
            }
        }
        return $grid[$m - 1][$n - 1];
    }
}
// Time: O(m * n), Memory: O(1)

```

# dart

## Memory O(1) | Sweet Spot

```dart
import 'dart:math';

class Solution {
  int minPathSum(List<List<int>> grid) {
    int m = grid.length;
    int n = grid[0].length;
    for (int i = 0; i < m; i++) {
      for (int j = 0; j < n; j++) {
        if (i == 0 && j == 0) continue;
        if (i == 0) {
          grid[i][j] += grid[i][j - 1];
        } else if (j == 0) {
          grid[i][j] += grid[i - 1][j];
        } else {
          grid[i][j] += min(grid[i - 1][j], grid[i][j - 1]);
        }
      }
    }
    return grid[m - 1][n - 1];
  }
}
// Time: O(m * n), Memory: O(1)

```

# scala 3.3.1

## Memory O(1) | Sweet Spot

```scala 3.3.1
object Solution {
    def minPathSum(grid: Array[Array[Int]]): Int = {
        val m = grid.length
        val n = grid(0).length
        for (i <- 0 until m) {
            for (j <- 0 until n) {
                if (i == 0 && j == 0) ()
                else if (i == 0) grid(i)(j) += grid(i)(j - 1)
                else if (j == 0) grid(i)(j) += grid(i - 1)(j)
                else grid(i)(j) += Math.min(grid(i - 1)(j), grid(i)(j - 1))
            }
        }
        grid(m - 1)(n - 1)
    }
}
// Time: O(m * n), Memory: O(1)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec min_path_sum(grid :: [[integer]]) :: integer
  def min_path_sum(grid) do
    n = length(hd(grid))
    initial_row = List.duplicate(:infinity, n)
    
    Enum.reduce(grid, initial_row, fn row, acc_row ->
      Enum.reduce(Enum.with_index(row), [], fn {val, j}, new_acc_row ->
        left = if j == 0, do: :infinity, else: hd(new_acc_row)
        up = Enum.at(acc_row, j)
        
        current = cond do
          j == 0 and up == :infinity -> val
          true -> val + min(left, up)
        end
        [current | new_acc_row]
      end) |> Enum.reverse()
    end) |> List.last()
  end
end
# Time: O(m * n), Memory: O(n)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec min_path_sum(Grid :: [[integer()]]) -> integer().
min_path_sum([FirstRow | Rest]) ->
    % Time: O(m * n), Memory: O(n)
    {FirstDP, _} = lists:mapfoldl(fun(X, Acc) -> {X + Acc, X + Acc} end, 0, FirstRow),
    FinalDP = lists:foldl(fun(Row, PrevDP) ->
        [H | T] = Row,
        [PrevH | PrevT] = PrevDP,
        StartVal = H + PrevH,
        {NewRow, _} = lists:mapfoldl(fun(X, {Left, [Up | Others]}) ->
            V = X + min(Left, Up),
            {V, {V, Others}}
        end, {StartVal, PrevT}, T),
        [StartVal | NewRow]
    end, FirstDP, Rest),
    lists:last(FinalDP).
```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (min-path-sum grid)
  (-> (listof (listof exact-integer?)) exact-integer?)
  (let* ([m (length grid)]
         [n (length (car grid))]
         [dp (make-vector n 0)])
    (for ([i (in-range m)])
      (let ([row (list->vector (list-ref grid i))])
        (for ([j (in-range n)])
          (cond
            [(and (= i 0) (= j 0)) (vector-set! dp j (vector-ref row 0))]
            [(= i 0) (vector-set! dp j (+ (vector-ref dp (- j 1)) (vector-ref row j)))]
            [(= j 0) (vector-set! dp j (+ (vector-ref dp j) (vector-ref row 0)))]
            [else (vector-set! dp j (+ (vector-ref row j) (min (vector-ref dp j) (vector-ref dp (- j 1)))))]))))
    (vector-ref dp (- n 1))))
; Time: O(m * n), Memory: O(n)

```