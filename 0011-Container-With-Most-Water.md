# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int maxArea(vector<int>& height) {
        int max_v = 0, left = 0, right = height.size() - 1;
        while (left < right) {
            int h = std::min(height[left], height[right]);
            max_v = std::max(max_v, h * (right - left));
            if (height[left] < height[right]) left++;
            else right--;
        }
        return max_v;
    }
};
// Time: O(n), Memory: O(1)

```

# java

## Sweet Spot

```java
class Solution {
    public int maxArea(int[] height) {
        int maxV = 0, left = 0, right = height.length - 1;
        while (left < right) {
            int h = Math.min(height[left], height[right]);
            maxV = Math.max(maxV, h * (right - left));
            if (height[left] < height[right]) left++;
            else right--;
        }
        return maxV;
    }
}
// Time: O(n), Memory: O(1)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def maxArea(self, height: List[int]) -> int:
        max_v, left, right = 0, 0, len(height) - 1
        while left < right:
            h_left, h_right = height[left], height[right]
            current_v = (h_left if h_left < h_right else h_right) * (right - left)
            if current_v > max_v: max_v = current_v
            if h_left < h_right: left += 1
            else: right -= 1
        return max_v
# Time: O(n), Memory: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def maxArea(self, height):
        """
        :type height: List[int]
        :rtype: int
        """
        max_v, left, right = 0, 0, len(height) - 1
        while left < right:
            h_l, h_r = height[left], height[right]
            curr = min(h_l, h_r) * (right - left)
            if curr > max_v: max_v = curr
            if h_l < h_r: left += 1
            else: right -= 1
        return max_v
# Time: O(n), Memory: O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} height
 * @return {number}
 */
var maxArea = function(height) {
    let maxV = 0, left = 0, right = height.length - 1;
    while (left < right) {
        let hL = height[left], hR = height[right];
        let h = hL < hR ? hL : hR;
        let area = h * (right - left);
        if (area > maxV) maxV = area;
        if (hL < hR) left++;
        else right--;
    }
    return maxV;
};
// Time: O(n), Memory: O(1)

```

# Typescript

## Sweet Spot

```typescript
function maxArea(height: number[]): number {
    let maxV: number = 0, left: number = 0, right: number = height.length - 1;
    while (left < right) {
        const hL = height[left], hR = height[right];
        const h = hL < hR ? hL : hR;
        const area = h * (right - left);
        if (area > maxV) maxV = area;
        if (hL < hR) left++;
        else right--;
    }
    return maxV;
};
// Time: O(n), Memory: O(1)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int MaxArea(int[] height) {
        int maxV = 0, left = 0, right = height.Length - 1;
        while (left < right) {
            int hL = height[left], hR = height[right];
            int h = hL < hR ? hL : hR;
            int area = h * (right - left);
            if (area > maxV) maxV = area;
            if (hL < hR) left++;
            else right--;
        }
        return maxV;
    }
}
// Time: O(n), Memory: O(1)

```

# C

## Sweet Spot

```c
int maxArea(int* height, int heightSize) {
    int maxV = 0, left = 0, right = heightSize - 1;
    while (left < right) {
        int hL = height[left], hR = height[right];
        int h = hL < hR ? hL : hR;
        int area = h * (right - left);
        if (area > maxV) maxV = area;
        if (hL < hR) left++;
        else right--;
    }
    return maxV;
}
// Time: O(n), Memory: O(1)

```

# Go

## Sweet Spot

```go
func maxArea(height []int) int {
    maxV, left, right := 0, 0, len(height)-1
    for left < right {
        hL, hR := height[left], height[right]
        h := hL
        if hR < hL {
            h = hR
        }
        area := h * (right - left)
        if area > maxV {
            maxV = area
        }
        if hL < hR {
            left++
        } else {
            right--
        }
    }
    return maxV
}
// Time: O(n), Memory: O(1)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun maxArea(height: IntArray): Int {
        var maxV = 0
        var left = 0
        var right = height.size - 1
        while (left < right) {
            val hL = height[left]
            val hR = height[right]
            val h = if (hL < hR) hL else hR
            val area = h * (right - left)
            if (area > maxV) maxV = area
            if (hL < hR) left++ else right--
        }
        return maxV
    }
}
// Time: O(n), Memory: O(1)

```

# swift

## Sweet Spot

```swift
class Solution {
    func maxArea(_ height: [Int]) -> Int {
        var maxV = 0, left = 0, right = height.count - 1
        while left < right {
            let hL = height[left], hR = height[right]
            let h = hL < hR ? hL : hR
            maxV = max(maxV, h * (right - left))
            if hL < hR { left += 1 }
            else { right -= 1 }
        }
        return maxV
    }
}
// Time: O(n), Memory: O(1)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn max_area(height: Vec<i32>) -> i32 {
        let (mut max_v, mut left, mut right) = (0, 0, height.len() - 1);
        while left < right {
            let h_l = height[left];
            let h_r = height[right];
            let h = if h_l < h_r { h_l } else { h_r };
            max_v = max_v.max(h * (right - left) as i32);
            if h_l < h_r { 
                left += 1; 
            } else { 
                right -= 1; 
            }
        }
        max_v
    }
}
// Time: O(n), Memory: O(1)
```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} height
# @return {Integer}
def max_area(height)
    max_v, left, right = 0, 0, height.length - 1
    while left < right
        h_l, h_r = height[left], height[right]
        h = h_l < h_r ? h_l : h_r
        area = h * (right - left)
        max_v = area if area > max_v
        if h_l < h_r then left += 1 else right -= 1 end
    end
    max_v
end
# Time: O(n), Memory: O(1)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[] $height
     * @return Integer
     */
    function maxArea($height) {
        $maxV = 0;
        $left = 0;
        $right = count($height) - 1;
        while ($left < $right) {
            $hL = $height[$left];
            $hR = $height[$right];
            $h = $hL < $hR ? $hL : $hR;
            $area = $h * ($right - $left);
            if ($area > $maxV) $maxV = $area;
            if ($hL < $hR) $left++;
            else $right--;
        }
        return $maxV;
    }
}
// Time: O(n), Memory: O(1)
```

# dart

## Sweet Spot

```dart
class Solution {
  int maxArea(List<int> height) {
    int maxV = 0, left = 0, right = height.length - 1;
    while (left < right) {
      int hL = height[left], hR = height[right];
      int h = hL < hR ? hL : hR;
      int area = h * (right - left);
      if (area > maxV) maxV = area;
      if (hL < hR) left++;
      else right--;
    }
    return maxV;
  }
}
// Time: O(n), Memory: O(1)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def maxArea(height: Array[Int]): Int = {
        var maxV = 0
        var left = 0
        var right = height.length - 1
        while (left < right) {
            val hL = height(left)
            val hR = height(right)
            val h = if (hL < hR) hL else hR
            val area = h * (right - left)
            if (area > maxV) maxV = area
            if (hL < hR) left += 1 else right -= 1
        }
        maxV
    }
}
// Time: O(n), Memory: O(1)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec max_area(height :: [integer]) :: integer
  def max_area(height) do
    vec = List.to_tuple(height)
    solve(vec, 0, tuple_size(vec) - 1, 0)
  end

  defp solve(_vec, left, right, max_v) when left >= right, do: max_v
  defp solve(vec, left, right, max_v) do
    h_l = elem(vec, left)
    h_r = elem(vec, right)
    h = if h_l < h_r, do: h_l, else: h_r
    new_max = max(max_v, h * (right - left))
    if h_l < h_r do
      solve(vec, left + 1, right, new_max)
    else
      solve(vec, left, right - 1, new_max)
    end
  end
end
# Time: O(n), Memory: O(n)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec max_area(Height :: [integer()]) -> integer().
max_area(Height) ->
    Vec = list_to_tuple(Height),
    solve(Vec, 0, tuple_size(Vec) - 1, 0).

solve(_Vec, Left, Right, MaxV) when Left >= Right ->
    MaxV;
solve(Vec, Left, Right, MaxV) ->
    HL = element(Left + 1, Vec),
    HR = element(Right + 1, Vec),
    H = if HL < HR -> HL; true -> HR end,
    Area = H * (Right - Left),
    NewMax = if Area > MaxV -> Area; true -> MaxV end,
    if HL < HR -> solve(Vec, Left + 1, Right, NewMax);
       true -> solve(Vec, Left, Right - 1, NewMax)
    end.
% Time: O(n), Memory: O(n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (max-area height)
  (-> (listof exact-integer?) exact-integer?)
  (let* ([vec (list->vector height)]
         [n (vector-length vec)])
    (let loop ([left 0] [right (- n 1)] [max-v 0])
      (if (>= left right)
          max-v
          (let* ([h-l (vector-ref vec left)]
                 [h-r (vector-ref vec right)]
                 [h (if (< h-l h-r) h-l h-r)]
                 [area (* h (- right left))]
                 [new-max (if (> area max-v) area max-v)])
            (if (< h-l h-r)
                (loop (+ left 1) right new-max)
                (loop left (- right 1) new-max)))))))
; Time: O(n), Memory: O(n)

```