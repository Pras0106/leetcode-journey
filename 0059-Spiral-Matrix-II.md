# cpp

## Sweet Spot

```cpp
class Solution {
public:
    vector<vector<int>> generateMatrix(int n) {
        // Time Complexity: O(n^2)
        // Memory Complexity: O(n^2)
        vector<vector<int>> matrix(n, vector<int>(n));
        int left = 0, right = n - 1, top = 0, bottom = n - 1;
        int num = 1;
        while (left <= right && top <= bottom) {
            for (int i = left; i <= right; ++i) matrix[top][i] = num++;
            top++;
            for (int i = top; i <= bottom; ++i) matrix[i][right] = num++;
            right--;
            if (top <= bottom) {
                for (int i = right; i >= left; --i) matrix[bottom][i] = num++;
                bottom--;
            }
            if (left <= right) {
                for (int i = bottom; i >= top; --i) matrix[i][left] = num++;
                left++;
            }
        }
        return matrix;
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public int[][] generateMatrix(int n) {
        // Time Complexity: O(n^2)
        // Memory Complexity: O(n^2)
        int[][] matrix = new int[n][n];
        int left = 0, right = n - 1, top = 0, bottom = n - 1;
        int num = 1;
        while (num <= n * n) {
            for (int i = left; i <= right; i++) matrix[top][i] = num++;
            top++;
            for (int i = top; i <= bottom; i++) matrix[i][right] = num++;
            right--;
            for (int i = right; i >= left; i--) matrix[bottom][i] = num++;
            bottom--;
            for (int i = bottom; i >= top; i--) matrix[i][left] = num++;
            left++;
        }
        return matrix;
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def generateMatrix(self, n: int) -> List[List[int]]:
        # Time Complexity: O(n^2)
        # Memory Complexity: O(n^2)
        matrix = [[0] * n for _ in range(n)]
        left, right, top, bottom = 0, n - 1, 0, n - 1
        num = 1
        while num <= n * n:
            for i in range(left, right + 1):
                matrix[top][i] = num
                num += 1
            top += 1
            for i in range(top, bottom + 1):
                matrix[i][right] = num
                num += 1
            right -= 1
            for i in range(right, left - 1, -1):
                matrix[bottom][i] = num
                num += 1
            bottom -= 1
            for i in range(bottom, top - 1, -1):
                matrix[i][left] = num
                num += 1
            left += 1
        return matrix

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def generateMatrix(self, n):
        """
        :type n: int
        :rtype: List[List[int]]
        """
        # Time Complexity: O(n^2)
        # Memory Complexity: O(n^2)
        matrix = [[0 for _ in range(n)] for _ in range(n)]
        left, right, top, bottom = 0, n - 1, 0, n - 1
        num = 1
        while num <= n * n:
            for i in range(left, right + 1):
                matrix[top][i] = num
                num += 1
            top += 1
            for i in range(top, bottom + 1):
                matrix[i][right] = num
                num += 1
            right -= 1
            for i in range(right, left - 1, -1):
                matrix[bottom][i] = num
                num += 1
            bottom -= 1
            for i in range(bottom, top - 1, -1):
                matrix[i][left] = num
                num += 1
            left += 1
        return matrix

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number} n
 * @return {number[][]}
 */
var generateMatrix = function(n) {
    // Time Complexity: O(n^2)
    // Memory Complexity: O(n^2)
    const matrix = Array.from({ length: n }, () => Array(n).fill(0));
    let left = 0, right = n - 1, top = 0, bottom = n - 1;
    let num = 1;
    while (num <= n * n) {
        for (let i = left; i <= right; i++) matrix[top][i] = num++;
        top++;
        for (let i = top; i <= bottom; i++) matrix[i][right] = num++;
        right--;
        for (let i = right; i >= left; i--) matrix[bottom][i] = num++;
        bottom--;
        for (let i = bottom; i >= top; i--) matrix[i][left] = num++;
        left++;
    }
    return matrix;
};

```

# Typescript

## Sweet Spot

```typescript
function generateMatrix(n: number): number[][] {
    // Time Complexity: O(n^2)
    // Memory Complexity: O(n^2)
    const matrix: number[][] = Array.from({ length: n }, () => Array(n).fill(0));
    let left = 0, right = n - 1, top = 0, bottom = n - 1;
    let num = 1;
    while (num <= n * n) {
        for (let i = left; i <= right; i++) matrix[top][i] = num++;
        top++;
        for (let i = top; i <= bottom; i++) matrix[i][right] = num++;
        right--;
        for (let i = right; i >= left; i--) matrix[bottom][i] = num++;
        bottom--;
        for (let i = bottom; i >= top; i--) matrix[i][left] = num++;
        left++;
    }
    return matrix;
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int[][] GenerateMatrix(int n) {
        // Time Complexity: O(n^2)
        // Memory Complexity: O(n^2)
        int[][] matrix = new int[n][];
        for (int i = 0; i < n; i++) matrix[i] = new int[n];
        int left = 0, right = n - 1, top = 0, bottom = n - 1;
        int num = 1;
        while (num <= n * n) {
            for (int i = left; i <= right; i++) matrix[top][i] = num++;
            top++;
            for (int i = top; i <= bottom; i++) matrix[i][right] = num++;
            right--;
            for (int i = right; i >= left; i--) matrix[bottom][i] = num++;
            bottom--;
            for (int i = bottom; i >= top; i--) matrix[i][left] = num++;
            left++;
        }
        return matrix;
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
int** generateMatrix(int n, int* returnSize, int** returnColumnSizes) {
    // Time Complexity: O(n^2)
    // Memory Complexity: O(n^2)
    *returnSize = n;
    *returnColumnSizes = (int*)malloc(n * sizeof(int));
    int** matrix = (int**)malloc(n * sizeof(int*));
    for (int i = 0; i < n; i++) {
        matrix[i] = (int*)calloc(n, sizeof(int));
        (*returnColumnSizes)[i] = n;
    }
    int left = 0, right = n - 1, top = 0, bottom = n - 1;
    int num = 1;
    while (num <= n * n) {
        for (int i = left; i <= right; i++) matrix[top][i] = num++;
        top++;
        for (int i = top; i <= bottom; i++) matrix[i][right] = num++;
        right--;
        for (int i = right; i >= left; i--) matrix[bottom][i] = num++;
        bottom--;
        for (int i = bottom; i >= top; i--) matrix[i][left] = num++;
        left++;
    }
    return matrix;
}

```

# Go

## Sweet Spot

```go
func generateMatrix(n int) [][]int {
    // Time Complexity: O(n^2)
    // Memory Complexity: O(n^2)
    matrix := make([][]int, n)
    for i := range matrix {
        matrix[i] = make([]int, n)
    }
    left, right, top, bottom := 0, n-1, 0, n-1
    num := 1
    for num <= n*n {
        for i := left; i <= right; i++ {
            matrix[top][i] = num
            num++
        }
        top++
        for i := top; i <= bottom; i++ {
            matrix[i][right] = num
            num++
        }
        right--
        for i := right; i >= left; i-- {
            matrix[bottom][i] = num
            num++
        }
        bottom--
        for i := bottom; i >= top; i-- {
            matrix[i][left] = num
            num++
        }
        left++
    }
    return matrix
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun generateMatrix(n: Int): Array<IntArray> {
        // Time Complexity: O(n^2)
        // Memory Complexity: O(n^2)
        val matrix = Array(n) { IntArray(n) }
        var left = 0
        var right = n - 1
        var top = 0
        var bottom = n - 1
        var num = 1
        while (num <= n * n) {
            for (i in left..right) matrix[top][i] = num++
            top++
            for (i in top..bottom) matrix[i][right] = num++
            right--
            for (i in right downTo left) matrix[bottom][i] = num++
            bottom--
            for (i in bottom downTo top) matrix[i][left] = num++
            left++
        }
        return matrix
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func generateMatrix(_ n: Int) -> [[Int]] {
        // Time Complexity: O(n^2)
        // Memory Complexity: O(n^2)
        var matrix = Array(repeating: Array(repeating: 0, count: n), count: n)
        var left = 0, right = n - 1, top = 0, bottom = n - 1
        var num = 1
        while num <= n * n {
            for i in left...right {
                matrix[top][i] = num
                num += 1
            }
            top += 1
            if top > bottom { break }
            for i in top...bottom {
                matrix[i][right] = num
                num += 1
            }
            right -= 1
            if left > right { break }
            for i in (left...right).reversed() {
                matrix[bottom][i] = num
                num += 1
            }
            bottom -= 1
            if top > bottom { break }
            for i in (top...bottom).reversed() {
                matrix[i][left] = num
                num += 1
            }
            left += 1
        }
        return matrix
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn generate_matrix(n: i32) -> Vec<Vec<i32>> {
        // Time Complexity: O(n^2)
        // Memory Complexity: O(n^2)
        let n = n as usize;
        let mut matrix = vec![vec![0; n]; n];
        let (mut left, mut right, mut top, mut bottom) = (0, n as i32 - 1, 0, n as i32 - 1);
        let mut num = 1;
        while num <= (n * n) as i32 {
            for i in left..=right {
                matrix[top as usize][i as usize] = num;
                num += 1;
            }
            top += 1;
            for i in top..=bottom {
                matrix[i as usize][right as usize] = num;
                num += 1;
            }
            right -= 1;
            for i in (left..=right).rev() {
                matrix[bottom as usize][i as usize] = num;
                num += 1;
            }
            bottom -= 1;
            for i in (top..=bottom).rev() {
                matrix[i as usize][left as usize] = num;
                num += 1;
            }
            left += 1;
        }
        matrix
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer} n
# @return {Integer[][]}
def generate_matrix(n)
    # Time Complexity: O(n^2)
    # Memory Complexity: O(n^2)
    matrix = Array.new(n) { Array.new(n, 0) }
    left, right, top, bottom = 0, n - 1, 0, n - 1
    num = 1
    while num <= n * n
        (left..right).each { |i| matrix[top][i] = num; num += 1 }
        top += 1
        (top..bottom).each { |i| matrix[i][right] = num; num += 1 }
        right -= 1
        right.downto(left).each { |i| matrix[bottom][i] = num; num += 1 }
        bottom -= 1
        bottom.downto(top).each { |i| matrix[i][left] = num; num += 1 }
        left += 1
    end
    matrix
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer $n
     * @return Integer[][]
     */
    function generateMatrix($n) {
        // Time Complexity: O(n^2)
        // Memory Complexity: O(n^2)
        $matrix = array_fill(0, $n, array_fill(0, $n, 0));
        $left = 0; $right = $n - 1; $top = 0; $bottom = $n - 1;
        $num = 1;
        while ($num <= $n * $n) {
            for ($i = $left; $i <= $right; $i++) $matrix[$top][$i] = $num++;
            $top++;
            for ($i = $top; $i <= $bottom; $i++) $matrix[$i][$right] = $num++;
            $right--;
            for ($i = $right; $i >= $left; $i--) $matrix[$bottom][$i] = $num++;
            $bottom--;
            for ($i = $bottom; $i >= $top; $i--) $matrix[$i][$left] = $num++;
            $left++;
        }
        return $matrix;
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  List<List<int>> generateMatrix(int n) {
    // Time Complexity: O(n^2)
    // Memory Complexity: O(n^2)
    List<List<int>> matrix = List.generate(n, (_) => List.filled(n, 0));
    int left = 0, right = n - 1, top = 0, bottom = n - 1;
    int num = 1;
    while (num <= n * n) {
      for (int i = left; i <= right; i++) matrix[top][i] = num++;
      top++;
      for (int i = top; i <= bottom; i++) matrix[i][right] = num++;
      right--;
      for (int i = right; i >= left; i--) matrix[bottom][i] = num++;
      bottom--;
      for (int i = bottom; i >= top; i--) matrix[i][left] = num++;
      left++;
    }
    return matrix;
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def generateMatrix(n: Int): Array[Array[Int]] = {
        // Time Complexity: O(n^2)
        // Memory Complexity: O(n^2)
        val matrix = Array.ofDim[Int](n, n)
        var left = 0
        var right = n - 1
        var top = 0
        var bottom = n - 1
        var num = 1
        while (num <= n * n) {
            for (i <- left to right) { matrix(top)(i) = num; num += 1 }
            top += 1
            for (i <- top to bottom) { matrix(i)(right) = num; num += 1 }
            right -= 1
            for (i <- right to left by -1) { matrix(bottom)(i) = num; num += 1 }
            bottom -= 1
            for (i <- bottom to top by -1) { matrix(i)(left) = num; num += 1 }
            left += 1
        }
        matrix
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec generate_matrix(n :: integer) :: [[integer]]
  def generate_matrix(n) do
    # Time Complexity: O(n^2)
    # Memory Complexity: O(n^2)
    map = fill(%{}, 1, 0, n - 1, 0, n - 1)
    Enum.map(0..(n - 1), fn r ->
      Enum.map(0..(n - 1), fn c -> Map.get(map, {r, c}) end)
    end)
  end

  defp fill(map, num, left, right, top, bottom) when left <= right and top <= bottom do
    {map, num} = Enum.reduce(left..right, {map, num}, fn c, {m, v} -> {Map.put(m, {top, c}, v), v + 1} end)
    top = top + 1
    if top > bottom do map else
      {map, num} = Enum.reduce(top..bottom, {map, num}, fn r, {m, v} -> {Map.put(m, {r, right}, v), v + 1} end)
      right = right - 1
      if left > right do map else
        {map, num} = Enum.reduce(right..left, {map, num}, fn c, {m, v} -> {Map.put(m, {bottom, c}, v), v + 1} end)
        bottom = bottom - 1
        if top > bottom do map else
          {map, num} = Enum.reduce(bottom..top, {map, num}, fn r, {m, v} -> {Map.put(m, {r, left}, v), v + 1} end)
          fill(map, num, left + 1, right, top, bottom)
        end
      end
    end
  end
  defp fill(map, _, _, _, _, _), do: map
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec generate_matrix(N :: integer()) -> [[integer()]].
generate_matrix(N) ->
  % Time Complexity: O(N^2)
  % Memory Complexity: O(N^2)
  Map = fill(#{}, 1, 0, N - 1, 0, N - 1),
  [[maps:get({R, C}, Map) || C <- lists:seq(0, N - 1)] || R <- lists:seq(0, N - 1)].

fill(Map, _Num, Left, Right, Top, Bottom) when Left > Right; Top > Bottom -> Map;
fill(Map, Num, Left, Right, Top, Bottom) ->
  {M1, N1} = lists:foldl(fun(C, {M, V}) -> {M#{{Top, C} => V}, V + 1} end, {Map, Num}, lists:seq(Left, Right)),
  T1 = Top + 1,
  if T1 > Bottom -> M1; true ->
    {M2, N2} = lists:foldl(fun(R, {M, V}) -> {M#{{R, Right} => V}, V + 1} end, {M1, N1}, lists:seq(T1, Bottom)),
    R1 = Right - 1,
    if Left > R1 -> M2; true ->
      {M3, N3} = lists:foldl(fun(C, {M, V}) -> {M#{{Bottom, C} => V}, V + 1} end, {M2, N2}, lists:seq(R1, Left, -1)),
      B1 = Bottom - 1,
      if T1 > B1 -> M3; true ->
        {M4, N4} = lists:foldl(fun(R, {M, V}) -> {M#{{R, Left} => V}, V + 1} end, {M3, N3}, lists:seq(B1, T1, -1)),
        fill(M4, N4, Left + 1, R1, T1, B1)
      end
    end
  end.
```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (generate-matrix n)
  (-> exact-integer? (listof (listof exact-integer?)))
  ; Time Complexity: O(n^2)
  ; Memory Complexity: O(n^2)
  (let ([vec (make-vector (* n n) 0)])
    (define (idx r c) (+ (* r n) c))
    (let loop ([num 1] [left 0] [right (- n 1)] [top 0] [bottom (- n 1)])
      (if (<= num (* n n))
          (begin
            (for ([c (in-range left (+ right 1))])
              (vector-set! vec (idx top c) num)
              (set! num (+ num 1)))
            (set! top (+ top 1))
            (for ([r (in-range top (+ bottom 1))])
              (vector-set! vec (idx r right) num)
              (set! num (+ num 1)))
            (set! right (- right 1))
            (when (<= top bottom)
              (for ([c (in-range right (- left 1) -1)])
                (vector-set! vec (idx bottom c) num)
                (set! num (+ num 1)))
              (set! bottom (- bottom 1)))
            (when (<= left right)
              (for ([r (in-range bottom (- top 1) -1)])
                (vector-set! vec (idx r left) num)
                (set! num (+ num 1)))
              (set! left (+ left 1)))
            (loop num left right top bottom))
          (for/list ([r (in-range n)])
            (for/list ([c (in-range n)])
              (vector-ref vec (idx r c))))))))

```