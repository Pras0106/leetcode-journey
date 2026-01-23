# C++

## Sweet Spot

```cpp
class Solution {
public:
    int largestRectangleArea(vector<int>& heights) {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        int n = heights.size();
        stack<int> s;
        int max_area = 0;
        for (int i = 0; i <= n; i++) {
            int h = (i == n) ? 0 : heights[i];
            while (!s.empty() && heights[s.top()] >= h) {
                int height = heights[s.top()];
                s.pop();
                int width = s.empty() ? i : i - s.top() - 1;
                max_area = max(max_area, height * width);
            }
            s.push(i);
        }
        return max_area;
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public int largestRectangleArea(int[] heights) {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        int n = heights.length;
        int[] stack = new int[n + 1];
        int top = -1;
        int maxArea = 0;
        for (int i = 0; i <= n; i++) {
            int h = (i == n) ? 0 : heights[i];
            while (top != -1 && heights[stack[top]] >= h) {
                int height = heights[stack[top--]];
                int width = (top == -1) ? i : i - stack[top] - 1;
                maxArea = Math.max(maxArea, height * width);
            }
            stack[++top] = i;
        }
        return maxArea;
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def largestRectangleArea(self, heights: List[int]) -> int:
        # Time Complexity: O(n)
        # Memory Complexity: O(n)
        max_area = 0
        stack = []
        heights.append(0)
        for i, h in enumerate(heights):
            while stack and heights[stack[-1]] >= h:
                height = heights[stack.pop()]
                width = i if not stack else i - stack[-1] - 1
                area = height * width
                if area > max_area:
                    max_area = area
            stack.append(i)
        heights.pop()
        return max_area

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def largestRectangleArea(self, heights):
        """
        :type heights: List[int]
        :rtype: int
        """
        # Time Complexity: O(n)
        # Memory Complexity: O(n)
        max_area = 0
        stack = []
        heights_with_sentinel = heights + [0]
        for i, h in enumerate(heights_with_sentinel):
            while stack and heights_with_sentinel[stack[-1]] >= h:
                height = heights_with_sentinel[stack.pop()]
                width = i if not stack else i - stack[-1] - 1
                max_area = max(max_area, height * width)
            stack.append(i)
        return max_area

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} heights
 * @return {number}
 */
var largestRectangleArea = function(heights) {
    // Time Complexity: O(n)
    // Memory Complexity: O(n)
    let maxArea = 0;
    const stack = [];
    for (let i = 0; i <= heights.length; i++) {
        const h = i === heights.length ? 0 : heights[i];
        while (stack.length > 0 && heights[stack[stack.length - 1]] >= h) {
            const height = heights[stack.pop()];
            const width = stack.length === 0 ? i : i - stack[stack.length - 1] - 1;
            maxArea = Math.max(maxArea, height * width);
        }
        stack.push(i);
    }
    return maxArea;
};

```

# Typescript

## Sweet Spot

```typescript
function largestRectangleArea(heights: number[]): number {
    // Time Complexity: O(n)
    // Memory Complexity: O(n)
    let maxArea = 0;
    const stack: number[] = [];
    for (let i = 0; i <= heights.length; i++) {
        const h = i === heights.length ? 0 : heights[i];
        while (stack.length > 0 && heights[stack[stack.length - 1]] >= h) {
            const height = heights[stack.pop()!];
            const width = stack.length === 0 ? i : i - stack[stack.length - 1] - 1;
            maxArea = Math.max(maxArea, height * width);
        }
        stack.push(i);
    }
    return maxArea;
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int LargestRectangleArea(int[] heights) {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        int n = heights.Length;
        Stack<int> stack = new Stack<int>();
        int maxArea = 0;
        for (int i = 0; i <= n; i++) {
            int h = (i == n) ? 0 : heights[i];
            while (stack.Count > 0 && heights[stack.Peek()] >= h) {
                int height = heights[stack.Pop()];
                int width = stack.Count == 0 ? i : i - stack.Peek() - 1;
                maxArea = Math.Max(maxArea, height * width);
            }
            stack.Push(i);
        }
        return maxArea;
    }
}

```

# C

## Sweet Spot

```c
int largestRectangleArea(int* heights, int heightsSize) {
    // Time Complexity: O(n)
    // Memory Complexity: O(n)
    int* stack = (int*)malloc((heightsSize + 1) * sizeof(int));
    int top = -1;
    int maxArea = 0;
    for (int i = 0; i <= heightsSize; i++) {
        int h = (i == heightsSize) ? 0 : heights[i];
        while (top != -1 && heights[stack[top]] >= h) {
            int height = heights[stack[top--]];
            int width = (top == -1) ? i : i - stack[top] - 1;
            int area = height * width;
            if (area > maxArea) maxArea = area;
        }
        stack[++top] = i;
    }
    free(stack);
    return maxArea;
}

```

# Go

## Sweet Spot

```go
func largestRectangleArea(heights []int) int {
    // Time Complexity: O(n)
    // Memory Complexity: O(n)
    maxArea := 0
    stack := []int{}
    for i := 0; i <= len(heights); i++ {
        h := 0
        if i < len(heights) {
            h = heights[i]
        }
        for len(stack) > 0 && heights[stack[len(stack)-1]] >= h {
            height := heights[stack[len(stack)-1]]
            stack = stack[:len(stack)-1]
            width := i
            if len(stack) > 0 {
                width = i - stack[len(stack)-1] - 1
            }
            if height*width > maxArea {
                maxArea = height * width
            }
        }
        stack = append(stack, i)
    }
    return maxArea
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun largestRectangleArea(heights: IntArray): Int {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        val stack = java.util.ArrayDeque<Int>()
        var maxArea = 0
        for (i in 0..heights.size) {
            val h = if (i == heights.size) 0 else heights[i]
            while (!stack.isEmpty() && heights[stack.peek()] >= h) {
                val height = heights[stack.pop()]
                val width = if (stack.isEmpty()) i else i - stack.peek() - 1
                maxArea = Math.max(maxArea, height * width)
            }
            stack.push(i)
        }
        return maxArea
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func largestRectangleArea(_ heights: [Int]) -> Int {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        var maxArea = 0
        var stack = [Int]()
        for i in 0...heights.count {
            let h = i == heights.count ? 0 : heights[i]
            while !stack.isEmpty && heights[stack.last!] >= h {
                let height = heights[stack.removeLast()]
                let width = stack.isEmpty ? i : i - stack.last! - 1
                maxArea = max(maxArea, height * width)
            }
            stack.append(i)
        }
        return maxArea
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn largest_rectangle_area(heights: Vec<i32>) -> i32 {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        let mut max_area = 0;
        let mut stack = Vec::new();
        let n = heights.len();
        for i in 0..=n {
            let h = if i == n { 0 } else { heights[i] };
            while let Some(&last_idx) = stack.last() {
                if heights[last_idx] >= h {
                    stack.pop();
                    let height = heights[last_idx];
                    let width = if stack.is_empty() { i as i32 } else { (i - stack.last().unwrap() - 1) as i32 };
                    max_area = max_area.max(height * width);
                } else {
                    break;
                }
            }
            stack.push(i);
        }
        max_area
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} heights
# @return {Integer}
def largest_rectangle_area(heights)
    # Time Complexity: O(n)
    # Memory Complexity: O(n)
    max_area = 0
    stack = []
    n = heights.length
    (0..n).each do |i|
        h = i == n ? 0 : heights[i]
        while !stack.empty? && heights[stack.last] >= h
            height = heights[stack.pop]
            width = stack.empty? ? i : i - stack.last - 1
            max_area = [max_area, height * width].max
        end
        stack.push(i)
    end
    max_area
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[] $heights
     * @return Integer
     */
    function largestRectangleArea($heights) {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        $maxArea = 0;
        $stack = [];
        $n = count($heights);
        for ($i = 0; $i <= $n; $i++) {
            $h = ($i == $n) ? 0 : $heights[$i];
            while (!empty($stack) && $heights[end($stack)] >= $h) {
                $height = $heights[array_pop($stack)];
                $width = empty($stack) ? $i : $i - end($stack) - 1;
                $maxArea = max($maxArea, $height * $width);
            }
            array_push($stack, $i);
        }
        return $maxArea;
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  int largestRectangleArea(List<int> heights) {
    // Time Complexity: O(n)
    // Memory Complexity: O(n)
    int maxArea = 0;
    List<int> stack = [];
    int n = heights.length;
    for (int i = 0; i <= n; i++) {
      int h = (i == n) ? 0 : heights[i];
      while (stack.isNotEmpty && heights[stack.last] >= h) {
        int height = heights[stack.removeLast()];
        int width = stack.isEmpty ? i : i - stack.last - 1;
        int area = height * width;
        if (area > maxArea) maxArea = area;
      }
      stack.add(i);
    }
    return maxArea;
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def largestRectangleArea(heights: Array[Int]): Int = {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        val n = heights.length
        val stack = scala.collection.mutable.Stack[Int]()
        var maxArea = 0
        for (i <- 0 to n) {
            val h = if (i == n) 0 else heights(i)
            while (stack.nonEmpty && heights(stack.top) >= h) {
                val height = heights(stack.pop())
                val width = if (stack.isEmpty) i else i - stack.top - 1
                maxArea = Math.max(maxArea, height * width)
            }
            stack.push(i)
        }
        maxArea
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec largest_rectangle_area(heights :: [integer]) :: integer
  def largest_rectangle_area(heights) do
    # Time Complexity: O(n)
    # Memory Complexity: O(n)
    h_vec = List.to_tuple(heights ++ [0])
    n = tuple_size(h_vec)
    solve(h_vec, 0, n, [], 0)
  end

  defp solve(_h, i, n, _stack, max_a) when i == n, do: max_a
  defp solve(h, i, n, [], max_a) do
    solve(h, i + 1, n, [i], max_a)
  end
  defp solve(h, i, n, [top | rest] = stack, max_a) do
    hi = elem(h, i)
    ht = elem(h, top)
    if ht >= hi do
      width = if rest == [], do: i, else: i - hd(rest) - 1
      solve(h, i, n, rest, max(max_a, ht * width))
    else
      solve(h, i + 1, n, [i | stack], max_a)
    end
  end
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec largest_rectangle_area(Heights :: [integer()]) -> integer().
largest_rectangle_area(Heights) ->
    % Time Complexity: O(n)
    % Memory Complexity: O(n)
    HVec = list_to_tuple(Heights ++ [0]),
    solve(HVec, 0, tuple_size(HVec), [], 0).

solve(_, I, N, _, MaxA) when I =:= N -> MaxA;
solve(H, I, N, [], MaxA) -> solve(H, I + 1, N, [I], MaxA);
solve(H, I, N, [Top | Rest] = Stack, MaxA) ->
    HI = element(I + 1, H),
    HT = element(Top + 1, H),
    if
        HT >= HI ->
            Width = case Rest of
                [] -> I;
                [NextTop | _] -> I - NextTop - 1
            end,
            solve(H, I, N, Rest, max(MaxA, HT * Width));
        true ->
            solve(H, I + 1, N, [I | Stack], MaxA)
    end.

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (largest-rectangle-area heights)
  (-> (listof exact-integer?) exact-integer?)
  ; Time Complexity: O(n)
  ; Memory Complexity: O(n)
  (let* ([h-list (append heights '(0))]
         [h-vec (list->vector h-list)]
         [n (vector-length h-vec)])
    (let loop ([i 0] [stack '()] [max-a 0])
      (cond
        [(= i n) max-a]
        [(null? stack) (loop (+ i 1) (list i) max-a)]
        [else
         (let ([hi (vector-ref h-vec i)]
               [ht (vector-ref h-vec (car stack))])
           (if (>= ht hi)
               (let* ([top (car stack)]
                      [rest (cdr stack)]
                      [width (if (null? rest) i (- (- i (car rest)) 1))])
                 (loop i rest (max max-a (* ht width))))
               (loop (+ i 1) (cons i stack) max-a)))]))))

```