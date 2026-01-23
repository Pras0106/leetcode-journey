# C++

## Sweet Spot

```cpp
class Solution {
public:
    int maximalRectangle(vector<vector<char>>& matrix) {
        if (matrix.empty()) return 0;
        int rows = matrix.size();
        int cols = matrix[0].size();
        vector<int> heights(cols, 0);
        int maxArea = 0;
        for (int i = 0; i < rows; ++i) {
            for (int j = 0; j < cols; ++j) {
                if (matrix[i][j] == '1') heights[j]++;
                else heights[j] = 0;
            }
            vector<int> s;
            for (int j = 0; j <= cols; ++j) {
                int h = (j == cols) ? 0 : heights[j];
                while (!s.empty() && h < heights[s.back()]) {
                    int height = heights[s.back()];
                    s.pop_back();
                    int width = s.empty() ? j : j - s.back() - 1;
                    maxArea = max(maxArea, height * width);
                }
                s.push_back(j);
            }
        }
        return maxArea;
    }
};
// Time Complexity: O(rows * cols)
// Memory Complexity: O(cols)

```

# java

## Sweet Spot

```java
class Solution {
    public int maximalRectangle(char[][] matrix) {
        if (matrix.length == 0) return 0;
        int cols = matrix[0].length;
        int[] heights = new int[cols];
        int maxArea = 0;
        for (char[] row : matrix) {
            for (int j = 0; j < cols; j++) {
                if (row[j] == '1') heights[j]++;
                else heights[j] = 0;
            }
            int[] stack = new int[cols + 1];
            int top = -1;
            for (int j = 0; j <= cols; j++) {
                int h = (j == cols) ? 0 : heights[j];
                while (top != -1 && h < heights[stack[top]]) {
                    int height = heights[stack[top--]];
                    int width = (top == -1) ? j : j - stack[top] - 1;
                    maxArea = Math.max(maxArea, height * width);
                }
                stack[++top] = j;
            }
        }
        return maxArea;
    }
}
// Time Complexity: O(rows * cols)
// Memory Complexity: O(cols)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def maximalRectangle(self, matrix: List[List[str]]) -> int:
        if not matrix or not matrix[0]:
            return 0
        cols = len(matrix[0])
        heights = [0] * cols
        max_area = 0
        for row in matrix:
            for j in range(cols):
                heights[j] = heights[j] + 1 if row[j] == '1' else 0
            stack = [-1]
            for j in range(cols + 1):
                h = heights[j] if j < cols else 0
                while stack[-1] != -1 and h < heights[stack[-1]]:
                    height = heights[stack.pop()]
                    width = j - stack[-1] - 1
                    max_area = max(max_area, height * width)
                stack.append(j)
        return max_area
# Time Complexity: O(rows * cols)
# Memory Complexity: O(cols)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def maximalRectangle(self, matrix):
        """
        :type matrix: List[List[str]]
        :rtype: int
        """
        if not matrix or not matrix[0]:
            return 0
        cols = len(matrix[0])
        heights = [0] * cols
        max_area = 0
        for row in matrix:
            for j in range(cols):
                heights[j] = heights[j] + 1 if row[j] == '1' else 0
            stack = [-1]
            for j in range(cols + 1):
                h = heights[j] if j < cols else 0
                while stack[-1] != -1 and h < heights[stack[-1]]:
                    height = heights[stack.pop()]
                    width = j - stack[-1] - 1
                    max_area = max(max_area, height * width)
                stack.append(j)
        return max_area
# Time Complexity: O(rows * cols)
# Memory Complexity: O(cols)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {character[][]} matrix
 * @return {number}
 */
var maximalRectangle = function(matrix) {
    if (!matrix.length) return 0;
    const cols = matrix[0].length;
    const heights = new Array(cols).fill(0);
    let maxArea = 0;
    for (let i = 0; i < matrix.length; i++) {
        for (let j = 0; j < cols; j++) {
            heights[j] = matrix[i][j] === '1' ? heights[j] + 1 : 0;
        }
        const stack = [-1];
        for (let j = 0; j <= cols; j++) {
            const h = j === cols ? 0 : heights[j];
            while (stack[stack.length - 1] !== -1 && h < heights[stack[stack.length - 1]]) {
                const height = heights[stack.pop()];
                const width = j - stack[stack.length - 1] - 1;
                maxArea = Math.max(maxArea, height * width);
            }
            stack.push(j);
        }
    }
    return maxArea;
};
// Time Complexity: O(rows * cols)
// Memory Complexity: O(cols)

```

# Typescript

## Sweet Spot

```typescript
function maximalRectangle(matrix: string[][]): number {
    if (matrix.length === 0) return 0;
    const cols = matrix[0].length;
    const heights = new Array(cols).fill(0);
    let maxArea = 0;
    for (let i = 0; i < matrix.length; i++) {
        for (let j = 0; j < cols; j++) {
            heights[j] = matrix[i][j] === '1' ? heights[j] + 1 : 0;
        }
        const stack: number[] = [-1];
        for (let j = 0; j <= cols; j++) {
            const h = j === cols ? 0 : heights[j];
            while (stack[stack.length - 1] !== -1 && h < heights[stack[stack.length - 1]]) {
                const height = heights[stack.pop()!];
                const width = j - stack[stack.length - 1] - 1;
                maxArea = Math.max(maxArea, height * width);
            }
            stack.push(j);
        }
    }
    return maxArea;
};
// Time Complexity: O(rows * cols)
// Memory Complexity: O(cols)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int MaximalRectangle(char[][] matrix) {
        if (matrix.Length == 0) return 0;
        int cols = matrix[0].Length;
        int[] heights = new int[cols];
        int maxArea = 0;
        foreach (var row in matrix) {
            for (int j = 0; j < cols; j++) {
                heights[j] = row[j] == '1' ? heights[j] + 1 : 0;
            }
            Stack<int> stack = new Stack<int>();
            stack.Push(-1);
            for (int j = 0; j <= cols; j++) {
                int h = (j == cols) ? 0 : heights[j];
                while (stack.Peek() != -1 && h < heights[stack.Peek()]) {
                    int height = heights[stack.Pop()];
                    int width = j - stack.Peek() - 1;
                    maxArea = Math.Max(maxArea, height * width);
                }
                stack.Push(j);
            }
        }
        return maxArea;
    }
}
// Time Complexity: O(rows * cols)
// Memory Complexity: O(cols)

```

# C

## Sweet Spot

```c
#include <stdlib.h>
#include <string.h>

#define MAX(a, b) ((a) > (b) ? (a) : (b))

int maximalRectangle(char** matrix, int matrixSize, int* matrixColSize) {
    if (matrixSize == 0 || matrixColSize[0] == 0) return 0;
    
    int cols = matrixColSize[0];
    int* heights = (int*)calloc(cols, sizeof(int));
    int* stack = (int*)malloc((cols + 1) * sizeof(int));
    int maxArea = 0;

    for (int i = 0; i < matrixSize; i++) {
        for (int j = 0; j < cols; j++) {
            heights[j] = (matrix[i][j] == '1') ? heights[j] + 1 : 0;
        }

        int top = -1;
        for (int j = 0; j <= cols; j++) {
            int currentHeight = (j == cols) ? 0 : heights[j];
            while (top != -1 && currentHeight < heights[stack[top]]) {
                int h = heights[stack[top--]];
                int w = (top == -1) ? j : j - stack[top] - 1;
                maxArea = MAX(maxArea, h * w);
            }
            stack[++top] = j;
        }
    }

    free(heights);
    free(stack);
    return maxArea;
}
// Time Complexity: O(rows * cols)
// Memory Complexity: O(cols)
```

# Go

## Sweet Spot

```go
func maximalRectangle(matrix [][]byte) int {
    if len(matrix) == 0 {
        return 0
    }
    cols := len(matrix[0])
    heights := make([]int, cols)
    maxArea := 0
    for i := 0; i < len(matrix); i++ {
        for j := 0; j < cols; j++ {
            if matrix[i][j] == '1' {
                heights[j]++
            } else {
                heights[j] = 0
            }
        }
        stack := []int{-1}
        for j := 0; j <= cols; j++ {
            h := 0
            if j < cols {
                h = heights[j]
            }
            for len(stack) > 1 && h < heights[stack[len(stack)-1]] {
                height := heights[stack[len(stack)-1]]
                stack = stack[:len(stack)-1]
                width := j - stack[len(stack)-1] - 1
                if height*width > maxArea {
                    maxArea = height * width
                }
            }
            stack = append(stack, j)
        }
    }
    return maxArea
}
// Time Complexity: O(rows * cols)
// Memory Complexity: O(cols)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun maximalRectangle(matrix: Array<CharArray>): Int {
        if (matrix.isEmpty()) return 0
        val cols = matrix[0].size
        val heights = IntArray(cols)
        var maxArea = 0
        for (row in matrix) {
            for (j in 0 until cols) {
                heights[j] = if (row[j] == '1') heights[j] + 1 else 0
            }
            val stack = java.util.ArrayDeque<Int>()
            stack.push(-1)
            for (j in 0..cols) {
                val h = if (j == cols) 0 else heights[j]
                while (stack.peek() != -1 && h < heights[stack.peek()]) {
                    val height = heights[stack.pop()]
                    val width = j - stack.peek() - 1
                    maxArea = Math.max(maxArea, height * width)
                }
                stack.push(j)
            }
        }
        return maxArea
    }
}
// Time Complexity: O(rows * cols)
// Memory Complexity: O(cols)

```

# swift

## Sweet Spot

```swift
class Solution {
    func maximalRectangle(_ matrix: [[Character]]) -> Int {
        guard !matrix.isEmpty else { return 0 }
        let cols = matrix[0].count
        var heights = [Int](repeating: 0, count: cols)
        var maxArea = 0
        for row in matrix {
            for j in 0..<cols {
                heights[j] = row[j] == "1" ? heights[j] + 1 : 0
            }
            var stack = [-1]
            for j in 0...cols {
                let h = j == cols ? 0 : heights[j]
                while stack.last! != -1 && h < heights[stack.last!] {
                    let height = heights[stack.removeLast()]
                    let width = j - stack.last! - 1
                    maxArea = max(maxArea, height * width)
                }
                stack.append(j)
            }
        }
        return maxArea
    }
}
// Time Complexity: O(rows * cols)
// Memory Complexity: O(cols)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn maximal_rectangle(matrix: Vec<Vec<char>>) -> i32 {
        if matrix.is_empty() { return 0; }
        let cols = matrix[0].size();
        let mut heights = vec![0; cols];
        let mut max_area = 0;
        for row in matrix {
            for j in 0..cols {
                if row[j] == '1' { heights[j] += 1; }
                else { heights[j] = 0; }
            }
            let mut stack = vec![];
            for j in 0..=cols {
                let h = if j == cols { 0 } else { heights[j] };
                while let Some(&top_idx) = stack.last() {
                    if h < heights[top_idx] {
                        stack.pop();
                        let height = heights[top_idx];
                        let width = if stack.is_empty() { j as i32 } else { (j - stack.last().unwrap() - 1) as i32 };
                        max_area = max_area.max(height * width);
                    } else { break; }
                }
                stack.push(j);
            }
        }
        max_area
    }
}
// Time Complexity: O(rows * cols)
// Memory Complexity: O(cols)

```

# ruby

## Sweet Spot

```ruby
# @param {Character[][]} matrix
# @return {Integer}
def maximal_rectangle(matrix)
    return 0 if matrix.empty?
    cols = matrix[0].length
    heights = Array.new(cols, 0)
    max_area = 0
    matrix.each do |row|
        row.each_with_index { |val, j| heights[j] = val == '1' ? heights[j] + 1 : 0 }
        stack = [-1]
        (0..cols).each do |j|
            h = j == cols ? 0 : heights[j]
            while stack.last != -1 && h < heights[stack.last]
                height = heights[stack.pop]
                width = j - stack.last - 1
                max_area = [max_area, height * width].max
            end
            stack.push(j)
        end
    end
    max_area
end
# Time Complexity: O(rows * cols)
# Memory Complexity: O(cols)
```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param String[][] $matrix
     * @return Integer
     */
    function maximalRectangle($matrix) {
        if (empty($matrix)) return 0;
        $cols = count($matrix[0]);
        $heights = array_fill(0, $cols, 0);
        $maxArea = 0;
        foreach ($matrix as $row) {
            for ($j = 0; $j < $cols; $j++) {
                $heights[$j] = $row[$j] == '1' ? $heights[$j] + 1 : 0;
            }
            $stack = [-1];
            for ($j = 0; $j <= $cols; $j++) {
                $h = $j == $cols ? 0 : $heights[$j];
                while (end($stack) != -1 && $h < $heights[end($stack)]) {
                    $height = $heights[array_pop($stack)];
                    $width = $j - end($stack) - 1;
                    $maxArea = max($maxArea, $height * $width);
                }
                $stack[] = $j;
            }
        }
        return $maxArea;
    }
}
// Time Complexity: O(rows * cols)
// Memory Complexity: O(cols)

```

# dart

## Sweet Spot

```dart
import 'dart:math';

class Solution {
  int maximalRectangle(List<List<String>> matrix) {
    if (matrix.isEmpty) return 0;
    int cols = matrix[0].length;
    List<int> heights = List.filled(cols, 0);
    int maxArea = 0;
    for (var row in matrix) {
      for (int j = 0; j < cols; j++) {
        heights[j] = row[j] == '1' ? heights[j] + 1 : 0;
      }
      List<int> stack = [-1];
      for (int j = 0; j <= cols; j++) {
        int h = j == cols ? 0 : heights[j];
        while (stack.last != -1 && h < heights[stack.last]) {
          int height = heights[stack.removeLast()];
          int width = j - stack.last - 1;
          maxArea = max(maxArea, height * width);
        }
        stack.add(j);
      }
    }
    return maxArea;
  }
}
// Time Complexity: O(rows * cols)
// Memory Complexity: O(cols)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def maximalRectangle(matrix: Array[Array[Char]]): Int = {
        if (matrix.isEmpty) return 0
        val cols = matrix(0).length
        val heights = Array.fill(cols)(0)
        var maxArea = 0
        for (row <- matrix) {
            for (j <- 0 until cols) {
                heights(j) = if (row(j) == '1') heights(j) + 1 else 0
            }
            val stack = scala.collection.mutable.Stack[Int](-1)
            for (j <- 0 to cols) {
                val h = if (j == cols) 0 else heights(j)
                while (stack.top != -1 && h < heights(stack.top)) {
                    val height = heights(stack.pop())
                    val width = j - stack.top - 1
                    maxArea = Math.max(maxArea, height * width)
                }
                stack.push(j)
            }
        }
        maxArea
    }
}
// Time Complexity: O(rows * cols)
// Memory Complexity: O(cols)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec maximal_rectangle(matrix :: [[char]]) :: integer
  def maximal_rectangle([]), do: 0
  def maximal_rectangle(matrix) do
    cols = length(hd(matrix))
    initial_heights = Tuple.duplicate(0, cols)
    process_rows(matrix, initial_heights, 0)
  end

  defp process_rows([], _heights, max_area), do: max_area
  defp process_rows([row | rest], heights, max_area) do
    new_heights = update_heights(row, heights, 0, tuple_size(heights))
    row_max = largest_rectangle_in_histogram(new_heights)
    process_rows(rest, new_heights, max(max_area, row_max))
  end

  defp update_heights([], heights, _, _), do: heights
  defp update_heights([char | rest], heights, i, size) do
    val = if char == 49, do: elem(heights, i) + 1, else: 0
    update_heights(rest, put_elem(heights, i, val), i + 1, size)
  end

  defp largest_rectangle_in_histogram(heights) do
    size = tuple_size(heights)
    histogram_loop(heights, 0, size, [-1], 0)
  end

  defp histogram_loop(heights, i, size, stack, max_a) when i <= size do
    h = if i == size, do: 0, else: elem(heights, i)
    case stack do
      [top | rest] when top != -1 and h < elem(heights, top) ->
        height = elem(heights, top)
        width = i - hd(rest) - 1
        histogram_loop(heights, i, size, rest, max(max_a, height * width))
      _ ->
        histogram_loop(heights, i + 1, size, [i | stack], max_a)
    end
  end
  defp histogram_loop(_, _, _, _, max_a), do: max_a
end
# Time Complexity: O(rows * cols)
# Memory Complexity: O(cols)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec maximal_rectangle(Matrix :: [[char()]]) -> integer().
maximal_rectangle([]) -> 0;
maximal_rectangle(Matrix) ->
    Cols = length(hd(Matrix)),
    Heights = list_to_tuple(lists:duplicate(Cols, 0)),
    process_rows(Matrix, Heights, 0).

process_rows([], _, MaxArea) -> MaxArea;
process_rows([Row | Rest], Heights, MaxArea) ->
    NewHeights = update_heights(Row, Heights, 1),
    RowMax = largest_rectangle(NewHeights),
    process_rows(Rest, NewHeights, max(MaxArea, RowMax)).

update_heights([], Heights, _) -> Heights;
update_heights([$1 | Rest], Heights, I) ->
    update_heights(Rest, setelement(I, Heights, element(I, Heights) + 1), I + 1);
update_heights([$0 | Rest], Heights, I) ->
    update_heights(Rest, setelement(I, Heights, 0), I + 1).

largest_rectangle(Heights) ->
    Size = tuple_size(Heights),
    histogram_loop(Heights, 1, Size, [0], 0).

histogram_loop(Heights, I, Size, Stack, MaxA) when I =< Size + 1 ->
    H = case I > Size of true -> 0; false -> element(I, Heights) end,
    case Stack of
        [Top | Rest] when Top > 0, H < element(Top, Heights) ->
            Height = element(Top, Heights),
            Width = I - hd(Rest) - 1,
            histogram_loop(Heights, I, Size, Rest, max(MaxA, Height * Width));
        _ ->
            histogram_loop(Heights, I + 1, Size, [I | Stack], MaxA)
    end;
histogram_loop(_, _, _, _, MaxA) -> MaxA.
% Time Complexity: O(rows * cols)
% Memory Complexity: O(cols)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (maximal-rectangle matrix)
  (-> (listof (listof char?)) exact-integer?)
  (if (null? matrix) 0
      (let* ([cols (length (car matrix))]
             [heights (make-vector cols 0)])
        (for/fold ([max-area 0])
                  ([row (in-list matrix)])
          (for ([j (in-range cols)]
                [char (in-list row)])
            (vector-set! heights j (if (char=? char #\1) (+ 1 (vector-ref heights j)) 0)))
          (let ([row-max (let loop ([j 0] [stack '(-1)] [m-area 0])
                           (if (<= j cols)
                               (let ([h (if (= j cols) 0 (vector-ref heights j))])
                                 (if (and (not (= (car stack) -1)) (< h (vector-ref heights (car stack))))
                                     (let* ([height (vector-ref heights (car stack))]
                                            [new-stack (cdr stack)]
                                            [width (- j (car new-stack) 1)])
                                       (loop j new-stack (max m-area (* height width))))
                                     (loop (+ j 1) (cons j stack) m-area)))
                               m-area))])
            (max max-area row-max))))))
; Time Complexity: O(rows * cols)
; Memory Complexity: O(cols)

```