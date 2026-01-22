# cpp

## memory O(1) | Sweet Spot

```cpp
class Solution {
public:
    int uniquePathsWithObstacles(vector<vector<int>>& obstacleGrid) {
        // Time Complexity: O(m * n)
        // Memory Complexity: O(1)
        int m = obstacleGrid.size();
        int n = obstacleGrid[0].size();
        if (obstacleGrid[0][0] == 1) return 0;
        obstacleGrid[0][0] = 1;
        for (int i = 1; i < m; i++) {
            obstacleGrid[i][0] = (obstacleGrid[i][0] == 0 && obstacleGrid[i - 1][0] == 1) ? 1 : 0;
        }
        for (int j = 1; j < n; j++) {
            obstacleGrid[0][j] = (obstacleGrid[0][j] == 0 && obstacleGrid[0][j - 1] == 1) ? 1 : 0;
        }
        for (int i = 1; i < m; i++) {
            for (int j = 1; j < n; j++) {
                if (obstacleGrid[i][j] == 0) {
                    obstacleGrid[i][j] = (long long)obstacleGrid[i - 1][j] + obstacleGrid[i][j - 1];
                } else {
                    obstacleGrid[i][j] = 0;
                }
            }
        }
        return obstacleGrid[m - 1][n - 1];
    }
};

```

# java

## memory O(1) | Sweet Spot

```java
class Solution {
    public int uniquePathsWithObstacles(int[][] obstacleGrid) {
        // Time Complexity: O(m * n)
        // Memory Complexity: O(1)
        int m = obstacleGrid.length;
        int n = obstacleGrid[0].length;
        if (obstacleGrid[0][0] == 1) return 0;
        obstacleGrid[0][0] = 1;
        for (int i = 1; i < m; i++) {
            obstacleGrid[i][0] = (obstacleGrid[i][0] == 0 && obstacleGrid[i - 1][0] == 1) ? 1 : 0;
        }
        for (int j = 1; j < n; j++) {
            obstacleGrid[0][j] = (obstacleGrid[0][j] == 0 && obstacleGrid[0][j - 1] == 1) ? 1 : 0;
        }
        for (int i = 1; i < m; i++) {
            for (int j = 1; j < n; j++) {
                if (obstacleGrid[i][j] == 0) {
                    obstacleGrid[i][j] = obstacleGrid[i - 1][j] + obstacleGrid[i][j - 1];
                } else {
                    obstacleGrid[i][j] = 0;
                }
            }
        }
        return obstacleGrid[m - 1][n - 1];
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def uniquePathsWithObstacles(self, obstacleGrid: List[List[int]]) -> int:
        # Time Complexity: O(m * n)
        # Memory Complexity: O(n)
        m, n = len(obstacleGrid), len(obstacleGrid[0])
        dp = [0] * n
        dp[0] = 1 if obstacleGrid[0][0] == 0 else 0
        for i in range(m):
            for j in range(n):
                if obstacleGrid[i][j] == 1:
                    dp[j] = 0
                elif j > 0:
                    dp[j] += dp[j - 1]
        return dp[-1]

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def uniquePathsWithObstacles(self, obstacleGrid):
        """
        :type obstacleGrid: List[List[int]]
        :rtype: int
        """
        # Time Complexity: O(m * n)
        # Memory Complexity: O(n)
        m = len(obstacleGrid)
        n = len(obstacleGrid[0])
        dp = [0] * n
        dp[0] = 1 if obstacleGrid[0][0] == 0 else 0
        for i in range(m):
            for j in range(n):
                if obstacleGrid[i][j] == 1:
                    dp[j] = 0
                elif j > 0:
                    dp[j] += dp[j - 1]
        return dp[-1]

```

# JavaScript

## memory O(1) | Sweet Spot

```javascript
/**
 * @param {number[][]} obstacleGrid
 * @return {number}
 */
var uniquePathsWithObstacles = function(obstacleGrid) {
    // Time Complexity: O(m * n)
    // Memory Complexity: O(1)
    let m = obstacleGrid.length;
    let n = obstacleGrid[0].length;
    if (obstacleGrid[0][0] === 1) return 0;
    obstacleGrid[0][0] = 1;
    for (let i = 1; i < m; i++) {
        obstacleGrid[i][0] = (obstacleGrid[i][0] === 0 && obstacleGrid[i - 1][0] === 1) ? 1 : 0;
    }
    for (let j = 1; j < n; j++) {
        obstacleGrid[0][j] = (obstacleGrid[0][j] === 0 && obstacleGrid[0][j - 1] === 1) ? 1 : 0;
    }
    for (let i = 1; i < m; i++) {
        for (let j = 1; j < n; j++) {
            if (obstacleGrid[i][j] === 0) {
                obstacleGrid[i][j] = obstacleGrid[i - 1][j] + obstacleGrid[i][j - 1];
            } else {
                obstacleGrid[i][j] = 0;
            }
        }
    }
    return obstacleGrid[m - 1][n - 1];
};

```

# Typescript

## memory O(1) | Sweet Spot

```typescript
function uniquePathsWithObstacles(obstacleGrid: number[][]): number {
    // Time Complexity: O(m * n)
    // Memory Complexity: O(1)
    const m = obstacleGrid.length;
    const n = obstacleGrid[0].length;
    if (obstacleGrid[0][0] === 1) return 0;
    obstacleGrid[0][0] = 1;
    for (let i = 1; i < m; i++) {
        obstacleGrid[i][0] = (obstacleGrid[i][0] === 0 && obstacleGrid[i - 1][0] === 1) ? 1 : 0;
    }
    for (let j = 1; j < n; j++) {
        obstacleGrid[0][j] = (obstacleGrid[0][j] === 0 && obstacleGrid[0][j - 1] === 1) ? 1 : 0;
    }
    for (let i = 1; i < m; i++) {
        for (let j = 1; j < n; j++) {
            if (obstacleGrid[i][j] === 0) {
                obstacleGrid[i][j] = obstacleGrid[i - 1][j] + obstacleGrid[i][j - 1];
            } else {
                obstacleGrid[i][j] = 0;
            }
        }
    }
    return obstacleGrid[m - 1][n - 1];
};

```

# C#

## memory O(1) | Sweet Spot

```c#
public class Solution {
    public int UniquePathsWithObstacles(int[][] obstacleGrid) {
        // Time Complexity: O(m * n)
        // Memory Complexity: O(1)
        int m = obstacleGrid.Length;
        int n = obstacleGrid[0].Length;
        if (obstacleGrid[0][0] == 1) return 0;
        obstacleGrid[0][0] = 1;
        for (int i = 1; i < m; i++) {
            obstacleGrid[i][0] = (obstacleGrid[i][0] == 0 && obstacleGrid[i - 1][0] == 1) ? 1 : 0;
        }
        for (int j = 1; j < n; j++) {
            obstacleGrid[0][j] = (obstacleGrid[0][j] == 0 && obstacleGrid[0][j - 1] == 1) ? 1 : 0;
        }
        for (int i = 1; i < m; i++) {
            for (int j = 1; j < n; j++) {
                if (obstacleGrid[i][j] == 0) {
                    obstacleGrid[i][j] = obstacleGrid[i - 1][j] + obstacleGrid[i][j - 1];
                } else {
                    obstacleGrid[i][j] = 0;
                }
            }
        }
        return obstacleGrid[m - 1][n - 1];
    }
}

```

# C

## Sweet Spot

```c
int uniquePathsWithObstacles(int** obstacleGrid, int obstacleGridSize, int* obstacleGridColSize) {
    // Time Complexity: O(m * n)
    // Memory Complexity: O(n)
    int m = obstacleGridSize;
    int n = obstacleGridColSize[0];
    long long* dp = (long long*)calloc(n, sizeof(long long));
    dp[0] = (obstacleGrid[0][0] == 0) ? 1 : 0;
    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++) {
            if (obstacleGrid[i][j] == 1) {
                dp[j] = 0;
            } else if (j > 0) {
                dp[j] += dp[j - 1];
            }
        }
    }
    int result = (int)dp[n - 1];
    free(dp);
    return result;
}

```

# Go

## Sweet Spot

```go
func uniquePathsWithObstacles(obstacleGrid [][]int) int {
    // Time Complexity: O(m * n)
    // Memory Complexity: O(n)
    m := len(obstacleGrid)
    n := len(obstacleGrid[0])
    dp := make([]int, n)
    if obstacleGrid[0][0] == 0 {
        dp[0] = 1
    }
    for i := 0; i < m; i++ {
        for j := 0; j < n; j++ {
            if obstacleGrid[i][j] == 1 {
                dp[j] = 0
            } else if j > 0 {
                dp[j] += dp[j-1]
            }
        }
    }
    return dp[n-1]
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun uniquePathsWithObstacles(obstacleGrid: Array<IntArray>): Int {
        // Time Complexity: O(m * n)
        // Memory Complexity: O(n)
        val m = obstacleGrid.size
        val n = obstacleGrid[0].size
        val dp = IntArray(n)
        dp[0] = if (obstacleGrid[0][0] == 0) 1 else 0
        for (i in 0 until m) {
            for (j in 0 until n) {
                if (obstacleGrid[i][j] == 1) {
                    dp[j] = 0
                } else if (j > 0) {
                    dp[j] += dp[j - 1]
                }
            }
        }
        return dp[n - 1]
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func uniquePathsWithObstacles(_ obstacleGrid: [[Int]]) -> Int {
        // Time Complexity: O(m * n)
        // Memory Complexity: O(n)
        let m = obstacleGrid.count
        let n = obstacleGrid[0].count
        var dp = [Int](repeating: 0, count: n)
        dp[0] = obstacleGrid[0][0] == 0 ? 1 : 0
        for i in 0..<m {
            for j in 0..<n {
                if obstacleGrid[i][j] == 1 {
                    dp[j] = 0
                } else if j > 0 {
                    dp[j] += dp[j - 1]
                }
            }
        }
        return dp[n - 1]
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn unique_paths_with_obstacles(obstacle_grid: Vec<Vec<i32>>) -> i32 {
        // Time Complexity: O(m * n)
        // Memory Complexity: O(n)
        let m = obstacle_grid.len();
        let n = obstacle_grid[0].len();
        let mut dp = vec![0; n];
        if obstacle_grid[0][0] == 0 {
            dp[0] = 1;
        }
        for i in 0..m {
            for j in 0..n {
                if obstacle_grid[i][j] == 1 {
                    dp[j] = 0;
                } else if j > 0 {
                    dp[j] += dp[j - 1];
                }
            }
        }
        dp[n - 1]
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[][]} obstacle_grid
# @return {Integer}
def unique_paths_with_obstacles(obstacle_grid)
    # Time Complexity: O(m * n)
    # Memory Complexity: O(n)
    m = obstacle_grid.length
    n = obstacle_grid[0].length
    dp = Array.new(n, 0)
    dp[0] = obstacle_grid[0][0] == 0 ? 1 : 0
    m.times do |i|
        n.times do |j|
            if obstacle_grid[i][j] == 1
                dp[j] = 0
            elsif j > 0
                dp[j] += dp[j - 1]
            end
        end
    end
    dp[n - 1]
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[][] $obstacleGrid
     * @return Integer
     */
    function uniquePathsWithObstacles($obstacleGrid) {
        // Time Complexity: O(m * n)
        // Memory Complexity: O(n)
        $m = count($obstacleGrid);
        $n = count($obstacleGrid[0]);
        $dp = array_fill(0, $n, 0);
        $dp[0] = ($obstacleGrid[0][0] == 0) ? 1 : 0;
        for ($i = 0; $i < $m; $i++) {
            for ($j = 0; $j < $n; $j++) {
                if ($obstacleGrid[$i][$j] == 1) {
                    $dp[$j] = 0;
                } else if ($j > 0) {
                    $dp[$j] += $dp[$j - 1];
                }
            }
        }
        return $dp[$n - 1];
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  int uniquePathsWithObstacles(List<List<int>> obstacleGrid) {
    // Time Complexity: O(m * n)
    // Memory Complexity: O(n)
    int m = obstacleGrid.length;
    int n = obstacleGrid[0].length;
    List<int> dp = List.filled(n, 0);
    dp[0] = obstacleGrid[0][0] == 0 ? 1 : 0;
    for (int i = 0; i < m; i++) {
      for (int j = 0; j < n; j++) {
        if (obstacleGrid[i][j] == 1) {
          dp[j] = 0;
        } else if (j > 0) {
          dp[j] += dp[j - 1];
        }
      }
    }
    return dp[n - 1];
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def uniquePathsWithObstacles(obstacleGrid: Array[Array[Int]]): Int = {
        // Time Complexity: O(m * n)
        // Memory Complexity: O(n)
        val m = obstacleGrid.length
        val n = obstacleGrid(0).length
        val dp = Array.fill(n)(0)
        if (obstacleGrid(0)(0) == 0) dp(0) = 1
        for (i <- 0 until m) {
            for (j <- 0 until n) {
                if (obstacleGrid(i)(j) == 1) {
                    dp(j) = 0
                } else if (j > 0) {
                    dp(j) += dp(j - 1)
                }
            }
        }
        dp(n - 1)
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec unique_paths_with_obstacles(obstacle_grid :: [[integer]]) :: integer
  def unique_paths_with_obstacles(obstacle_grid) do
    # Time Complexity: O(m * n)
    # Memory Complexity: O(n)
    n = length(Enum.at(obstacle_grid, 0))
    initial_dp = Tuple.duplicate(0, n)
    initial_dp = if hd(hd(obstacle_grid)) == 0, do: put_elem(initial_dp, 0, 1), else: initial_dp

    final_dp = Enum.reduce(obstacle_grid, initial_dp, fn row, acc_dp ->
      Enum.with_index(row) |> Enum.reduce(acc_dp, fn {cell, j}, inner_dp ->
        cond do
          cell == 1 -> put_elem(inner_dp, j, 0)
          j > 0 -> put_elem(inner_dp, j, elem(inner_dp, j) + elem(inner_dp, j - 1))
          true -> inner_dp
        end
      end)
    end)
    elem(final_dp, n - 1)
  end
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec unique_paths_with_obstacles(ObstacleGrid :: [[integer()]]) -> integer().
unique_paths_with_obstacles(ObstacleGrid) ->
  % Time Complexity: O(m * n)
  % Memory Complexity: O(n)
  N = length(hd(ObstacleGrid)),
  InitialDp = erlang:make_tuple(N, 0),
  DpStart = case hd(hd(ObstacleGrid)) of
    0 -> setelement(1, InitialDp, 1);
    1 -> InitialDp
  end,
  FinalDp = lists:foldl(fun(Row, AccDp) ->
    {_, NewDp} = lists:foldl(fun(Cell, {J, InnerDp}) ->
      UpdatedDp = if
        Cell == 1 -> setelement(J, InnerDp, 0);
        J > 1 -> setelement(J, InnerDp, element(J, InnerDp) + element(J - 1, InnerDp));
        true -> InnerDp
      end,
      {J + 1, UpdatedDp}
    end, {1, AccDp}, Row),
    NewDp
  end, DpStart, ObstacleGrid),
  element(N, FinalDp).

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (unique-paths-with-obstacles obstacleGrid)
  (-> (listof (listof exact-integer?)) exact-integer?)
  ; Time Complexity: O(m * n)
  ; Memory Complexity: O(n)
  (let* ([m (length obstacleGrid)]
         [n (length (car obstacleGrid))]
         [dp (make-vector n 0)])
    (when (= (car (car obstacleGrid)) 0)
      (vector-set! dp 0 1))
    (for ([row obstacleGrid])
      (for ([cell row]
            [j (in-range n)])
        (cond
          [(= cell 1) (vector-set! dp j 0)]
          [(> j 0) (vector-set! dp j (+ (vector-ref dp j) (vector-ref dp (- j 1))))])))
    (vector-ref dp (- n 1))))

```