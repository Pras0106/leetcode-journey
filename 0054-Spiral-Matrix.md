# cpp

## Sweet Spot

```cpp
class Solution {
public:
    vector<int> spiralOrder(vector<vector<int>>& matrix) {
        if (matrix.empty()) return {};
        int m = matrix.size(), n = matrix[0].size();
        vector<int> res;
        res.reserve(m * n);
        int top = 0, bottom = m - 1, left = 0, right = n - 1;
        while (top <= bottom && left <= right) {
            for (int j = left; j <= right; ++j) res.push_back(matrix[top][j]);
            top++;
            for (int i = top; i <= bottom; ++i) res.push_back(matrix[i][right]);
            right--;
            if (top <= bottom) {
                for (int j = right; j >= left; --j) res.push_back(matrix[bottom][j]);
                bottom--;
            }
            if (left <= right) {
                for (int i = bottom; i >= top; --i) res.push_back(matrix[i][left]);
                left++;
            }
        }
        return res;
        // Time Complexity: O(m * n)
        // Memory Complexity: O(1) excluding output array
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public List<Integer> spiralOrder(int[][] matrix) {
        List<Integer> res = new ArrayList<>();
        if (matrix == null || matrix.length == 0) return res;
        int top = 0, bottom = matrix.length - 1;
        int left = 0, right = matrix[0].length - 1;
        while (top <= bottom && left <= right) {
            for (int j = left; j <= right; j++) res.add(matrix[top][j]);
            top++;
            for (int i = top; i <= bottom; i++) res.add(matrix[i][right]);
            right--;
            if (top <= bottom) {
                for (int j = right; j >= left; j--) res.add(matrix[bottom][j]);
                bottom--;
            }
            if (left <= right) {
                for (int i = bottom; i >= top; i--) res.add(matrix[i][left]);
                left++;
            }
        }
        return res;
        /* Time Complexity: O(m * n) */
        /* Memory Complexity: O(1) excluding output array */
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def spiralOrder(self, matrix: List[List[int]]) -> List[int]:
        if not matrix: return []
        res = []
        top, bottom = 0, len(matrix) - 1
        left, right = 0, len(matrix[0]) - 1
        while top <= bottom and left <= right:
            for j in range(left, right + 1):
                res.append(matrix[top][j])
            top += 1
            for i in range(top, bottom + 1):
                res.append(matrix[i][right])
            right -= 1
            if top <= bottom:
                for j in range(right, left - 1, -1):
                    res.append(matrix[bottom][j])
                bottom -= 1
            if left <= right:
                for i in range(bottom, top - 1, -1):
                    res.append(matrix[i][left])
                left += 1
        return res
        # Time Complexity: O(m * n)
        # Memory Complexity: O(1) excluding output array

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def spiralOrder(self, matrix):
        """
        :type matrix: List[List[int]]
        :rtype: List[int]
        """
        if not matrix: return []
        res = []
        top, bottom = 0, len(matrix) - 1
        left, right = 0, len(matrix[0]) - 1
        while top <= bottom and left <= right:
            for j in range(left, right + 1):
                res.append(matrix[top][j])
            top += 1
            for i in range(top, bottom + 1):
                res.append(matrix[i][right])
            right -= 1
            if top <= bottom:
                for j in range(right, left - 1, -1):
                    res.append(matrix[bottom][j])
                bottom -= 1
            if left <= right:
                for i in range(bottom, top - 1, -1):
                    res.append(matrix[i][left])
                left += 1
        return res
        # Time Complexity: O(m * n)
        # Memory Complexity: O(1) excluding output array

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[][]} matrix
 * @return {number[]}
 */
var spiralOrder = function(matrix) {
    if (matrix.length === 0) return [];
    const res = [];
    let top = 0, bottom = matrix.length - 1;
    let left = 0, right = matrix[0].length - 1;
    while (top <= bottom && left <= right) {
        for (let j = left; j <= right; j++) res.push(matrix[top][j]);
        top++;
        for (let i = top; i <= bottom; i++) res.push(matrix[i][right]);
        right--;
        if (top <= bottom) {
            for (let j = right; j >= left; j--) res.push(matrix[bottom][j]);
            bottom--;
        }
        if (left <= right) {
            for (let i = bottom; i >= top; i--) res.push(matrix[i][left]);
            left++;
        }
    }
    return res;
    // Time Complexity: O(m * n)
    // Memory Complexity: O(1) excluding output array
};

```

# Typescript

## Sweet Spot

```typescript
function spiralOrder(matrix: number[][]): number[] {
    if (matrix.length === 0) return [];
    const res: number[] = [];
    let top = 0, bottom = matrix.length - 1;
    let left = 0, right = matrix[0].length - 1;
    while (top <= bottom && left <= right) {
        for (let j = left; j <= right; j++) res.push(matrix[top][j]);
        top++;
        for (let i = top; i <= bottom; i++) res.push(matrix[i][right]);
        right--;
        if (top <= bottom) {
            for (let j = right; j >= left; j--) res.push(matrix[bottom][j]);
            bottom--;
        }
        if (left <= right) {
            for (let i = bottom; i >= top; i--) res.push(matrix[i][left]);
            left++;
        }
    }
    return res;
    // Time Complexity: O(m * n)
    // Memory Complexity: O(1) excluding output array
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public IList<int> SpiralOrder(int[][] matrix) {
        List<int> res = new List<int>();
        if (matrix.Length == 0) return res;
        int top = 0, bottom = matrix.Length - 1;
        int left = 0, right = matrix[0].Length - 1;
        while (top <= bottom && left <= right) {
            for (int j = left; j <= right; j++) res.Add(matrix[top][j]);
            top++;
            for (int i = top; i <= bottom; i++) res.Add(matrix[i][right]);
            right--;
            if (top <= bottom) {
                for (int j = right; j >= left; j--) res.Add(matrix[bottom][j]);
                bottom--;
            }
            if (left <= right) {
                for (int i = bottom; i >= top; i--) res.Add(matrix[i][left]);
                left++;
            }
        }
        return res;
        // Time Complexity: O(m * n)
        // Memory Complexity: O(1) excluding output array
    }
}

```

# C

## Sweet Spot

```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* spiralOrder(int** matrix, int matrixSize, int* matrixColSize, int* returnSize) {
    if (matrixSize == 0) {
        *returnSize = 0;
        return NULL;
    }
    int m = matrixSize, n = matrixColSize[0];
    int total = m * n;
    int* res = (int*)malloc(sizeof(int) * total);
    *returnSize = total;
    int top = 0, bottom = m - 1, left = 0, right = n - 1;
    int k = 0;
    while (top <= bottom && left <= right) {
        for (int j = left; j <= right; j++) res[k++] = matrix[top][j];
        top++;
        for (int i = top; i <= bottom; i++) res[k++] = matrix[i][right];
        right--;
        if (top <= bottom) {
            for (int j = right; j >= left; j--) res[k++] = matrix[bottom][j];
            bottom--;
        }
        if (left <= right) {
            for (int i = bottom; i >= top; i--) res[k++] = matrix[i][left];
            left++;
        }
    }
    return res;
    /* Time Complexity: O(m * n) */
    /* Memory Complexity: O(1) excluding output array */
}

```

# Go

## Sweet Spot

```go
func spiralOrder(matrix [][]int) []int {
    if len(matrix) == 0 {
        return []int{}
    }
    m, n := len(matrix), len(matrix[0])
    res := make([]int, 0, m*n)
    top, bottom, left, right := 0, m-1, 0, n-1
    for top <= bottom && left <= right {
        for j := left; j <= right; j++ {
            res = append(res, matrix[top][j])
        }
        top++
        for i := top; i <= bottom; i++ {
            res = append(res, matrix[i][right])
        }
        right--
        if top <= bottom {
            for j := right; j >= left; j-- {
                res = append(res, matrix[bottom][j])
            }
            bottom--
        }
        if left <= right {
            for i := bottom; i >= top; i-- {
                res = append(res, matrix[i][left])
            }
            left++
        }
    }
    return res
    // Time Complexity: O(m * n)
    // Memory Complexity: O(1) excluding output array
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun spiralOrder(matrix: Array<IntArray>): List<Int> {
        if (matrix.isEmpty()) return listOf()
        val res = mutableListOf<Int>()
        var top = 0
        var bottom = matrix.size - 1
        var left = 0
        var right = matrix[0].size - 1
        while (top <= bottom && left <= right) {
            for (j in left..right) res.add(matrix[top][j])
            top++
            for (i in top..bottom) res.add(matrix[i][right])
            right--
            if (top <= bottom) {
                for (j in right downTo left) res.add(matrix[bottom][j])
                bottom--
            }
            if (left <= right) {
                for (i in bottom downTo top) res.add(matrix[i][left])
                left++
            }
        }
        return res
        // Time Complexity: O(m * n)
        // Memory Complexity: O(1) excluding output array
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func spiralOrder(_ matrix: [[Int]]) -> [Int] {
        guard !matrix.isEmpty else { return [] }
        var res = [Int]()
        var top = 0, bottom = matrix.count - 1
        var left = 0, right = matrix[0].count - 1
        while top <= bottom && left <= right {
            for j in stride(from: left, through: right, by: 1) { res.append(matrix[top][j]) }
            top += 1
            for i in stride(from: top, through: bottom, by: 1) { res.append(matrix[i][right]) }
            right -= 1
            if top <= bottom {
                for j in stride(from: right, through: left, by: -1) { res.append(matrix[bottom][j]) }
                bottom -= 1
            }
            if left <= right {
                for i in stride(from: bottom, through: top, by: -1) { res.append(matrix[i][left]) }
                left += 1
            }
        }
        return res
        // Time Complexity: O(m * n)
        // Memory Complexity: O(1) excluding output array
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn spiral_order(matrix: Vec<Vec<i32>>) -> Vec<i32> {
        if matrix.is_empty() { return vec![]; }
        let mut res = Vec::with_capacity(matrix.len() * matrix[0].len());
        let (mut top, mut bottom) = (0, matrix.len() as i32 - 1);
        let (mut left, mut right) = (0, matrix[0].len() as i32 - 1);
        while top <= bottom && left <= right {
            for j in left..=right { res.push(matrix[top as usize][j as usize]); }
            top += 1;
            for i in top..=bottom { res.push(matrix[i as usize][right as usize]); }
            right -= 1;
            if top <= bottom {
                for j in (left..=right).rev() { res.push(matrix[bottom as usize][j as usize]); }
                bottom -= 1;
            }
            if left <= right {
                for i in (top..=bottom).rev() { res.push(matrix[i as usize][left as usize]); }
                left += 1;
            }
        }
        res
        // Time Complexity: O(m * n)
        // Memory Complexity: O(1) excluding output array
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[][]} matrix
# @return {Integer[]}
def spiral_order(matrix)
  return [] if matrix.empty?
  res = []
  top, bottom = 0, matrix.length - 1
  left, right = 0, matrix[0].length - 1
  while top <= bottom && left <= right
    (left..right).each { |j| res << matrix[top][j] }
    top += 1
    (top..bottom).each { |i| res << matrix[i][right] }
    right -= 1
    if top <= bottom
      right.downto(left).each { |j| res << matrix[bottom][j] }
      bottom -= 1
    end
    if left <= right
      bottom.downto(top).each { |i| res << matrix[i][left] }
      left += 1
    end
  end
  res
  # Time Complexity: O(m * n)
  # Memory Complexity: O(1) excluding output array
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[][] $matrix
     * @return Integer[]
     */
    function spiralOrder($matrix) {
        if (empty($matrix)) return [];
        $res = [];
        $top = 0; $bottom = count($matrix) - 1;
        $left = 0; $right = count($matrix[0]) - 1;
        while ($top <= $bottom && $left <= $right) {
            for ($j = $left; $j <= $right; $j++) $res[] = $matrix[$top][$j];
            $top++;
            for ($i = $top; $i <= $bottom; $i++) $res[] = $matrix[$i][$right];
            $right--;
            if ($top <= $bottom) {
                for ($j = $right; $j >= $left; $j--) $res[] = $matrix[$bottom][$j];
                $bottom--;
            }
            if ($left <= $right) {
                for ($i = $bottom; $i >= $top; $i--) $res[] = $matrix[$i][$left];
                $left++;
            }
        }
        return $res;
        // Time Complexity: O(m * n)
        // Memory Complexity: O(1) excluding output array
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  List<int> spiralOrder(List<List<int>> matrix) {
    if (matrix.isEmpty) return [];
    List<int> res = [];
    int top = 0, bottom = matrix.length - 1;
    int left = 0, right = matrix[0].length - 1;
    while (top <= bottom && left <= right) {
      for (int j = left; j <= right; j++) res.add(matrix[top][j]);
      top++;
      for (int i = top; i <= bottom; i++) res.add(matrix[i][right]);
      right--;
      if (top <= bottom) {
        for (int j = right; j >= left; j--) res.add(matrix[bottom][j]);
        bottom--;
      }
      if (left <= right) {
        for (int i = bottom; i >= top; i--) res.add(matrix[i][left]);
        left++;
      }
    }
    return res;
    // Time Complexity: O(m * n)
    // Memory Complexity: O(1) excluding output array
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def spiralOrder(matrix: Array[Array[Int]]): List[Int] = {
        if (matrix.isEmpty) return Nil
        val res = scala.collection.mutable.ListBuffer[Int]()
        var top = 0
        var bottom = matrix.length - 1
        var left = 0
        var right = matrix(0).length - 1
        while (top <= bottom && left <= right) {
            for (j <- left to right) res += matrix(top)(j)
            top += 1
            for (i <- top to bottom) res += matrix(i)(right)
            right -= 1
            if (top <= bottom) {
                for (j <- right to left by -1) res += matrix(bottom)(j)
                bottom -= 1
            }
            if (left <= right) {
                for (i <- bottom to top by -1) res += matrix(i)(left)
                left += 1
            }
        }
        res.toList
        // Time Complexity: O(m * n)
        // Memory Complexity: O(1) excluding output array
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec spiral_order(matrix :: [[integer]]) :: [integer]
  def spiral_order([]), do: []
  def spiral_order(matrix) do
    m = length(matrix)
    n = length(hd(matrix))
    mat_vec = Enum.map(matrix, &List.to_tuple/1) |> List.to_tuple()
    
    solve(mat_vec, 0, m - 1, 0, n - 1, [])
  end

  defp solve(_mat, top, bottom, left, right, acc) when top > bottom or left > right do
    Enum.reverse(acc)
  end

  defp solve(mat, top, bottom, left, right, acc) do
    acc = Enum.reduce(left..right, acc, fn j, a -> [elem(elem(mat, top), j) | a] end)
    top = top + 1
    if top <= bottom do
      acc = Enum.reduce(top..bottom, acc, fn i, a -> [elem(elem(mat, i), right) | a] end)
      right = right - 1
      if left <= right do
        acc = Enum.reduce(right..left, acc, fn j, a -> [elem(elem(mat, bottom), j) | a] end)
        bottom = bottom - 1
        if top <= bottom do
          acc = Enum.reduce(bottom..top, acc, fn i, a -> [elem(elem(mat, i), left) | a] end)
          solve(mat, top, bottom, left + 1, right, acc)
        else
          Enum.reverse(acc)
        end
      else
        Enum.reverse(acc)
      end
    else
      Enum.reverse(acc)
    end
  end
  # Time Complexity: O(m * n)
  # Memory Complexity: O(m * n) for tuple conversion
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec spiral_order(Matrix :: [[integer()]]) -> [integer()].
spiral_order([]) -> [];
spiral_order(Matrix) ->
    Rows = length(Matrix),
    Cols = length(hd(Matrix)),
    Mat = list_to_tuple([list_to_tuple(R) || R <- Matrix]),
    lists:reverse(solve(Mat, 0, Rows - 1, 0, Cols - 1, [])).

solve(_Mat, T, B, L, R, Acc) when T > B; L > R -> Acc;
solve(Mat, T, B, L, R, Acc0) ->
    Acc1 = loop_j(Mat, T, L, R, 1, Acc0),
    T1 = T + 1,
    case T1 > B of
        true -> Acc1;
        false ->
            Acc2 = loop_i(Mat, R, T1, B, 1, Acc1),
            R1 = R - 1,
            case L > R1 of
                true -> Acc2;
                false ->
                    Acc3 = loop_j(Mat, B, R1, L, -1, Acc2),
                    B1 = B - 1,
                    case T1 > B1 of
                        true -> Acc3;
                        false ->
                            Acc4 = loop_i(Mat, L, B1, T1, -1, Acc3),
                            solve(Mat, T1, B1, L + 1, R1, Acc4)
                    end
            end
    end.

loop_j(_Mat, _Row, J, End, Step, Acc) ->
    Item = elem_at(_Mat, _Row, J),
    NewAcc = [Item | Acc],
    if J == End -> NewAcc; true -> loop_j(_Mat, _Row, J + Step, End, Step, NewAcc) end.

loop_i(_Mat, _Col, I, End, Step, Acc) ->
    Item = elem_at(_Mat, I, _Col),
    NewAcc = [Item | Acc],
    if I == End -> NewAcc; true -> loop_i(_Mat, _Col, I + Step, End, Step, NewAcc) end.

elem_at(Mat, R, C) -> element(C + 1, element(R + 1, Mat)).
% Time Complexity: O(m * n)
% Memory Complexity: O(m * n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (spiral-order matrix)
  (-> (listof (listof exact-integer?)) (listof exact-integer?))
  (if (null? matrix) '()
      (let* ([m (length matrix)]
             [n (length (car matrix))]
             [vec-mat (list->vector (map list->vector matrix))])
        (let loop ([top 0] [bottom (- m 1)] [left 0] [right (- n 1)] [res '()])
          (cond
            [(or (> top bottom) (> left right)) (reverse res)]
            [else
             (let* ([res1 (let j-loop ([j left] [acc res])
                            (if (> j right) acc (j-loop (+ j 1) (cons (vector-ref (vector-ref vec-mat top) j) acc))))]
                    [top-next (+ top 1)])
               (if (> top-next bottom) (reverse res1)
                   (let* ([res2 (let i-loop ([i top-next] [acc res1])
                                  (if (> i bottom) acc (i-loop (+ i 1) (cons (vector-ref (vector-ref vec-mat i) right) acc))))]
                          [right-next (- right 1)])
                     (if (> left right-next) (reverse res2)
                         (let* ([res3 (let j-down ([j right-next] [acc res2])
                                        (if (< j left) acc (j-down (- j 1) (cons (vector-ref (vector-ref vec-mat bottom) j) acc))))]
                                [bottom-next (- bottom 1)])
                           (if (> top-next bottom-next) (reverse res3)
                               (let* ([res4 (let i-down ([i bottom-next] [acc res3])
                                              (if (< i top-next) acc (i-down (- i 1) (cons (vector-ref (vector-ref vec-mat i) left) acc))))])
                                 (loop top-next bottom-next (+ left 1) right-next res4))))))))])))))
; Time Complexity: O(m * n)
; Memory Complexity: O(m * n) for vector conversion

```