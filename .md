# cpp

## Sweet Spot

```cpp
class Solution {
public:
    bool searchMatrix(vector<vector<int>>& matrix, int target) {
        if (matrix.empty() || matrix[0].empty()) return false;
        int m = matrix.size();
        int n = matrix[0].size();
        int left = 0, right = m * n - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            int val = matrix[mid / n][mid % n];
            if (val == target) return true;
            if (val < target) left = mid + 1;
            else right = mid - 1;
        }
        return false;
    }
};
// Time Complexity: O(log(m * n))
// Memory Complexity: O(1)

```

# java

## Sweet Spot

```java
class Solution {
    public boolean searchMatrix(int[][] matrix, int target) {
        if (matrix == null || matrix.length == 0 || matrix[0].length == 0) return false;
        int m = matrix.length;
        int n = matrix[0].length;
        int left = 0, right = m * n - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            int val = matrix[mid / n][mid % n];
            if (val == target) return true;
            else if (val < target) left = mid + 1;
            else right = mid - 1;
        }
        return false;
    }
}
// Time Complexity: O(log(m * n))
// Memory Complexity: O(1)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def searchMatrix(self, matrix: List[List[int]], target: int) -> bool:
        if not matrix or not matrix[0]: return False
        m, n = len(matrix), len(matrix[0])
        left, right = 0, m * n - 1
        while left <= right:
            mid = (left + right) // 2
            val = matrix[mid // n][mid % n]
            if val == target: return True
            if val < target: left = mid + 1
            else: right = mid - 1
        return False
# Time Complexity: O(log(m * n))
# Memory Complexity: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def searchMatrix(self, matrix, target):
        """
        :type matrix: List[List[int]]
        :type target: int
        :rtype: bool
        """
        if not matrix or not matrix[0]: return False
        m, n = len(matrix), len(matrix[0])
        left, right = 0, m * n - 1
        while left <= right:
            mid = (left + right) // 2
            val = matrix[mid // n][mid % n]
            if val == target: return True
            if val < target: left = mid + 1
            else: right = mid - 1
        return False
# Time Complexity: O(log(m * n))
# Memory Complexity: O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[][]} matrix
 * @param {number} target
 * @return {boolean}
 */
var searchMatrix = function(matrix, target) {
    if (!matrix.length || !matrix[0].length) return false;
    let m = matrix.length, n = matrix[0].length;
    let left = 0, right = m * n - 1;
    while (left <= right) {
        let mid = Math.floor((left + right) / 2);
        let val = matrix[Math.floor(mid / n)][mid % n];
        if (val === target) return true;
        if (val < target) left = mid + 1;
        else right = mid - 1;
    }
    return false;
};
// Time Complexity: O(log(m * n))
// Memory Complexity: O(1)

```

# Typescript

## Sweet Spot

```typescript
function searchMatrix(matrix: number[][], target: number): boolean {
    if (!matrix.length || !matrix[0].length) return false;
    const m = matrix.length, n = matrix[0].length;
    let left = 0, right = m * n - 1;
    while (left <= right) {
        const mid = Math.floor((left + right) / 2);
        const val = matrix[Math.floor(mid / n)][mid % n];
        if (val === target) return true;
        if (val < target) left = mid + 1;
        else right = mid - 1;
    }
    return false;
};
// Time Complexity: O(log(m * n))
// Memory Complexity: O(1)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public bool SearchMatrix(int[][] matrix, int target) {
        if (matrix == null || matrix.Length == 0 || matrix[0].Length == 0) return false;
        int m = matrix.Length;
        int n = matrix[0].Length;
        int left = 0, right = m * n - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            int val = matrix[mid / n][mid % n];
            if (val == target) return true;
            if (val < target) left = mid + 1;
            else right = mid - 1;
        }
        return false;
    }
}
// Time Complexity: O(log(m * n))
// Memory Complexity: O(1)

```

# C

## Sweet Spot

```c
bool searchMatrix(int** matrix, int matrixSize, int* matrixColSize, int target) {
    if (matrixSize == 0 || matrixColSize[0] == 0) return false;
    int m = matrixSize, n = matrixColSize[0];
    int left = 0, right = m * n - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        int val = matrix[mid / n][mid % n];
        if (val == target) return true;
        if (val < target) left = mid + 1;
        else right = mid - 1;
    }
    return false;
}
/* Time Complexity: O(log(m * n)) */
/* Memory Complexity: O(1) */

```

# Go

## Sweet Spot

```go
func searchMatrix(matrix [][]int, target int) bool {
    if len(matrix) == 0 || len(matrix[0]) == 0 {
        return false
    }
    m, n := len(matrix), len(matrix[0])
    left, right := 0, m * n - 1
    for left <= right {
        mid := left + (right-left)/2
        val := matrix[mid/n][mid%n]
        if val == target {
            return true
        } else if val < target {
            left = mid + 1
        } else {
            right = mid - 1
        }
    }
    return false
}
// Time Complexity: O(log(m * n))
// Memory Complexity: O(1)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun searchMatrix(matrix: Array<IntArray>, target: Int): Boolean {
        if (matrix.isEmpty() || matrix[0].isEmpty()) return false
        val m = matrix.size
        val n = matrix[0].size
        var left = 0
        var right = m * n - 1
        while (left <= right) {
            val mid = left + (right - left) / 2
            val valAtMid = matrix[mid / n][mid % n]
            if (valAtMid == target) return true
            if (valAtMid < target) left = mid + 1
            else right = mid - 1
        }
        return false
    }
}
// Time Complexity: O(log(m * n))
// Memory Complexity: O(1)

```

# swift

## Sweet Spot

```swift
class Solution {
    func searchMatrix(_ matrix: [[Int]], _ target: Int) -> Bool {
        if matrix.isEmpty || matrix[0].isEmpty { return false }
        let m = matrix.count
        let n = matrix[0].count
        var left = 0
        var right = m * n - 1
        while left <= right {
            let mid = left + (right - left) / 2
            let val = matrix[mid / n][mid % n]
            if val == target { return true }
            if val < target { left = mid + 1 }
            else { right = mid - 1 }
        }
        return false
    }
}
// Time Complexity: O(log(m * n))
// Memory Complexity: O(1)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn search_matrix(matrix: Vec<Vec<i32>>, target: i32) -> bool {
        if matrix.is_empty() || matrix[0].is_empty() { return false; }
        let m = matrix.len();
        let n = matrix[0].len();
        let mut left = 0i32;
        let mut right = (m * n) as i32 - 1;
        while left <= right {
            let mid = left + (right - left) / 2;
            let val = matrix[(mid as usize) / n][(mid as usize) % n];
            if val == target { return true; }
            if val < target { left = mid + 1; }
            else { right = mid - 1; }
        }
        false
    }
}
// Time Complexity: O(log(m * n))
// Memory Complexity: O(1)

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[][]} matrix
# @param {Integer} target
# @return {Boolean}
def search_matrix(matrix, target)
    return false if matrix.empty? || matrix[0].empty?
    m, n = matrix.length, matrix[0].length
    left, right = 0, m * n - 1
    while left <= right
        mid = (left + right) / 2
        val = matrix[mid / n][mid % n]
        return true if val == target
        if val < target
            left = mid + 1
        else
            right = mid - 1
        end
    end
    false
end
# Time Complexity: O(log(m * n))
# Memory Complexity: O(1)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[][] $matrix
     * @param Integer $target
     * @return Boolean
     */
    function searchMatrix($matrix, $target) {
        $m = count($matrix);
        if ($m == 0) return false;
        $n = count($matrix[0]);
        if ($n == 0) return false;
        $left = 0;
        $right = $m * $n - 1;
        while ($left <= $right) {
            $mid = floor(($left + $right) / 2);
            $val = $matrix[floor($mid / $n)][$mid % $n];
            if ($val == $target) return true;
            if ($val < $target) $left = $mid + 1;
            else $right = $mid - 1;
        }
        return false;
    }
}
// Time Complexity: O(log(m * n))
// Memory Complexity: O(1)

```

# dart

## Sweet Spot

```dart
class Solution {
  bool searchMatrix(List<List<int>> matrix, int target) {
    if (matrix.isEmpty || matrix[0].isEmpty) return false;
    int m = matrix.length;
    int n = matrix[0].length;
    int left = 0;
    int right = m * n - 1;
    while (left <= right) {
      int mid = left + (right - left) ~/ 2;
      int val = matrix[mid ~/ n][mid % n];
      if (val == target) return true;
      if (val < target) {
        left = mid + 1;
      } else {
        right = mid - 1;
      }
    }
    return false;
  }
}
// Time Complexity: O(log(m * n))
// Memory Complexity: O(1)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def searchMatrix(matrix: Array[Array[Int]], target: Int): Boolean = {
        if (matrix.isEmpty || matrix(0).isEmpty) return false
        val m = matrix.length
        val n = matrix(0).length
        var left = 0
        var right = m * n - 1
        while (left <= right) {
            val mid = left + (right - left) / 2
            val midVal = matrix(mid / n)(mid % n)
            if (midVal == target) return true
            else if (midVal < target) left = mid + 1
            else right = mid - 1
        }
        false
    }
}
// Time Complexity: O(log(m * n))
// Memory Complexity: O(1)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec search_matrix(matrix :: [[integer]], target :: integer) :: boolean
  def search_matrix(matrix, target) do
    m = length(matrix)
    n = length(Enum.at(matrix, 0))
    mat_vec = matrix |> Enum.map(&List.to_tuple/1) |> List.to_tuple()
    
    search(mat_vec, target, 0, m * n - 1, n)
  end

  defp search(_mat, _target, left, right, _n) when left > right, do: false
  defp search(mat, target, left, right, n) do
    mid = div(left + right, 2)
    val = elem(elem(mat, div(mid, n)), rem(mid, n))
    cond do
      val == target -> true
      val < target -> search(mat, target, mid + 1, right, n)
      true -> search(mat, target, left, mid - 1, n)
    end
  end
end
# Time Complexity: O(log(m * n))
# Memory Complexity: O(m * n)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec search_matrix(Matrix :: [[integer()]], Target :: integer()) -> boolean().
search_matrix(Matrix, Target) ->
    M = length(Matrix),
    N = length(hd(Matrix)),
    TupleMatrix = list_to_tuple([list_to_tuple(Row) || Row <- Matrix]),
    binary_search(TupleMatrix, Target, 0, M * N - 1, N).

binary_search(_Matrix, _Target, Left, Right, _N) when Left > Right ->
    false;
binary_search(Matrix, Target, Left, Right, N) ->
    Mid = (Left + Right) div 2,
    Row = Mid div N,
    Col = Mid rem N,
    Val = element(Col + 1, element(Row + 1, Matrix)),
    if
        Val == Target -> true;
        Val < Target -> binary_search(Matrix, Target, Mid + 1, Right, N);
        true -> binary_search(Matrix, Target, Left, Mid - 1, N)
    end.
% Time Complexity: O(log(m * n))
% Memory Complexity: O(m * n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (search-matrix matrix target)
  (-> (listof (listof exact-integer?)) exact-integer? boolean?)
  (let* ([m (length matrix)]
         [n (length (car matrix))]
         [vec-matrix (list->vector (map list->vector matrix))])
    (let loop ([left 0]
               [right (- (* m n) 1)])
      (if (> left right)
          #f
          (let* ([mid (quotient (+ left right) 2)]
                 [r (quotient mid n)]
                 [c (remainder mid n)]
                 [val (vector-ref (vector-ref vec-matrix r) c)])
            (cond
              [(= val target) #t]
              [(< val target) (loop (+ mid 1) right)]
              [else (loop left (- mid 1))]))))))
; Time Complexity: O(log(m * n))
; Memory Complexity: O(m * n)

```