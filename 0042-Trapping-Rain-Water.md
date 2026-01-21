# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int trap(vector<int>& height) {
        // Time O(n), Memory O(1)
        int left = 0, right = height.size() - 1;
        int ans = 0;
        int left_max = 0, right_max = 0;
        while (left < right) {
            if (height[left] < height[right]) {
                height[left] >= left_max ? (left_max = height[left]) : ans += (left_max - height[left]);
                ++left;
            } else {
                height[right] >= right_max ? (right_max = height[right]) : ans += (right_max - height[right]);
                --right;
            }
        }
        return ans;
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public int trap(int[] height) {
        // Time O(n), Memory O(1)
        int left = 0, right = height.length - 1;
        int ans = 0;
        int left_max = 0, right_max = 0;
        while (left < right) {
            if (height[left] < height[right]) {
                if (height[left] >= left_max) {
                    left_max = height[left];
                } else {
                    ans += (left_max - height[left]);
                }
                left++;
            } else {
                if (height[right] >= right_max) {
                    right_max = height[right];
                } else {
                    ans += (right_max - height[right]);
                }
                right--;
            }
        }
        return ans;
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def trap(self, height: List[int]) -> int:
        # Time O(n), Memory O(1)
        if not height:
            return 0
        left, right = 0, len(height) - 1
        left_max, right_max = 0, 0
        ans = 0
        while left < right:
            if height[left] < height[right]:
                if height[left] >= left_max:
                    left_max = height[left]
                else:
                    ans += (left_max - height[left])
                left += 1
            else:
                if height[right] >= right_max:
                    right_max = height[right]
                else:
                    ans += (right_max - height[right])
                right -= 1
        return ans

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def trap(self, height):
        """
        :type height: List[int]
        :rtype: int
        """
        # Time O(n), Memory O(1)
        if not height:
            return 0
        left, right = 0, len(height) - 1
        left_max, right_max = 0, 0
        ans = 0
        while left < right:
            if height[left] < height[right]:
                if height[left] >= left_max:
                    left_max = height[left]
                else:
                    ans += (left_max - height[left])
                left += 1
            else:
                if height[right] >= right_max:
                    right_max = height[right]
                else:
                    ans += (right_max - height[right])
                right -= 1
        return ans

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} height
 * @return {number}
 */
var trap = function(height) {
    // Time O(n), Memory O(1)
    let left = 0, right = height.length - 1;
    let ans = 0;
    let left_max = 0, right_max = 0;
    while (left < right) {
        if (height[left] < height[right]) {
            height[left] >= left_max ? (left_max = height[left]) : ans += (left_max - height[left]);
            left++;
        } else {
            height[right] >= right_max ? (right_max = height[right]) : ans += (right_max - height[right]);
            right--;
        }
    }
    return ans;
};

```

# Typescript

## Sweet Spot

```typescript
function trap(height: number[]): number {
    // Time O(n), Memory O(1)
    let left = 0, right = height.length - 1;
    let ans = 0;
    let left_max = 0, right_max = 0;
    while (left < right) {
        if (height[left] < height[right]) {
            height[left] >= left_max ? (left_max = height[left]) : ans += (left_max - height[left]);
            left++;
        } else {
            height[right] >= right_max ? (right_max = height[right]) : ans += (right_max - height[right]);
            right--;
        }
    }
    return ans;
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int Trap(int[] height) {
        // Time O(n), Memory O(1)
        int left = 0, right = height.Length - 1;
        int ans = 0;
        int left_max = 0, right_max = 0;
        while (left < right) {
            if (height[left] < height[right]) {
                if (height[left] >= left_max) left_max = height[left];
                else ans += (left_max - height[left]);
                left++;
            } else {
                if (height[right] >= right_max) right_max = height[right];
                else ans += (right_max - height[right]);
                right--;
            }
        }
        return ans;
    }
}

```

# C

## Sweet Spot

```c
int trap(int* height, int heightSize) {
    // Time O(n), Memory O(1)
    int left = 0, right = heightSize - 1;
    int ans = 0;
    int left_max = 0, right_max = 0;
    while (left < right) {
        if (height[left] < height[right]) {
            if (height[left] >= left_max) left_max = height[left];
            else ans += (left_max - height[left]);
            left++;
        } else {
            if (height[right] >= right_max) right_max = height[right];
            else ans += (right_max - height[right]);
            right--;
        }
    }
    return ans;
}

```

# Go

## Sweet Spot

```go
func trap(height []int) int {
    // Time O(n), Memory O(1)
    left, right := 0, len(height)-1
    ans := 0
    left_max, right_max := 0, 0
    for left < right {
        if height[left] < height[right] {
            if height[left] >= left_max {
                left_max = height[left]
            } else {
                ans += (left_max - height[left])
            }
            left++
        } else {
            if height[right] >= right_max {
                right_max = height[right]
            } else {
                ans += (right_max - height[right])
            }
            right--
        }
    }
    return ans
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun trap(height: IntArray): Int {
        // Time O(n), Memory O(1)
        var left = 0
        var right = height.size - 1
        var ans = 0
        var left_max = 0
        var right_max = 0
        while (left < right) {
            if (height[left] < height[right]) {
                if (height[left] >= left_max) left_max = height[left]
                else ans += (left_max - height[left])
                left++
            } else {
                if (height[right] >= right_max) right_max = height[right]
                else ans += (right_max - height[right])
                right--
            }
        }
        return ans
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func trap(_ height: [Int]) -> Int {
        // Time O(n), Memory O(1)
        var left = 0
        var right = height.count - 1
        var ans = 0
        var left_max = 0
        var right_max = 0
        while left < right {
            if height[left] < height[right] {
                if height[left] >= left_max {
                    left_max = height[left]
                } else {
                    ans += (left_max - height[left])
                }
                left += 1
            } else {
                if height[right] >= right_max {
                    right_max = height[right]
                } else {
                    ans += (right_max - height[right])
                }
                right -= 1
            }
        }
        return ans
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn trap(height: Vec<i32>) -> i32 {
        // Time O(n), Memory O(1)
        if height.is_empty() { return 0; }
        let (mut left, mut right) = (0, height.len() - 1);
        let (mut left_max, mut right_max) = (0, 0);
        let mut ans = 0;
        while left < right {
            if height[left] < height[right] {
                if height[left] >= left_max { left_max = height[left]; }
                else { ans += left_max - height[left]; }
                left += 1;
            } else {
                if height[right] >= right_max { right_max = height[right]; }
                else { ans += right_max - height[right]; }
                right -= 1;
            }
        }
        ans
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} height
# @return {Integer}
def trap(height)
    # Time O(n), Memory O(1)
    return 0 if height.empty?
    left, right = 0, height.length - 1
    left_max, right_max = 0, 0
    ans = 0
    while left < right
        if height[left] < height[right]
            height[left] >= left_max ? (left_max = height[left]) : (ans += left_max - height[left])
            left += 1
        else
            height[right] >= right_max ? (right_max = height[right]) : (ans += right_max - height[right])
            right -= 1
        end
    end
    ans
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[] $height
     * @return Integer
     */
    function trap($height) {
        // Time O(n), Memory O(1)
        $left = 0;
        $right = count($height) - 1;
        $ans = 0;
        $left_max = 0;
        $right_max = 0;
        while ($left < $right) {
            if ($height[$left] < $height[$right]) {
                $height[$left] >= $left_max ? ($left_max = $height[$left]) : ($ans += ($left_max - $height[$left]));
                $left++;
            } else {
                $height[$right] >= $right_max ? ($right_max = $height[$right]) : ($ans += ($right_max - $height[$right]));
                $right--;
            }
        }
        return $ans;
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  int trap(List<int> height) {
    // Time O(n), Memory O(1)
    int left = 0, right = height.length - 1;
    int ans = 0;
    int leftMax = 0, rightMax = 0;
    while (left < right) {
      if (height[left] < height[right]) {
        if (height[left] >= leftMax) {
          leftMax = height[left];
        } else {
          ans += (leftMax - height[left]);
        }
        left++;
      } else {
        if (height[right] >= rightMax) {
          rightMax = height[right];
        } else {
          ans += (rightMax - height[right]);
        }
        right--;
      }
    }
    return ans;
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def trap(height: Array[Int]): Int = {
        // Time O(n), Memory O(1)
        var left = 0
        var right = height.length - 1
        var ans = 0
        var leftMax = 0
        var rightMax = 0
        while (left < right) {
            if (height(left) < height(right)) {
                if (height(left) >= leftMax) leftMax = height(left)
                else ans += (leftMax - height(left))
                left += 1
            } else {
                if (height(right) >= rightMax) rightMax = height(right)
                else ans += (rightMax - height(right))
                right -= 1
            }
        }
        ans
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec trap(height :: [integer]) :: integer
  def trap(height) do
    # Time O(n), Memory O(n)
    h_vec = List.to_tuple(height)
    n = tuple_size(h_vec)
    solve(h_vec, 0, n - 1, 0, 0, 0)
  end

  defp solve(_h, left, right, _lm, _rm, ans) when left >= right, do: ans
  defp solve(h, left, right, lm, rm, ans) do
    hl = elem(h, left)
    hr = elem(h, right)
    if hl < hr do
      new_lm = max(lm, hl)
      solve(h, left + 1, right, new_lm, rm, ans + (new_lm - hl))
    else
      new_rm = max(rm, hr)
      solve(h, left, right - 1, lm, new_rm, ans + (new_rm - hr))
    end
  end
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec trap(Height :: [integer()]) -> integer().
trap(Height) ->
  % Time O(n), Memory O(n)
  H = list_to_tuple(Height),
  solve(H, 1, tuple_size(H), 0, 0, 0).

solve(_H, Left, Right, _LM, _RM, Ans) when Left >= Right -> Ans;
solve(H, Left, Right, LM, RM, Ans) ->
  HL = element(Left, H),
  HR = element(Right, H),
  if
    HL < HR ->
      NewLM = if HL > LM -> HL; true -> LM end,
      solve(H, Left + 1, Right, NewLM, RM, Ans + (NewLM - HL));
    true ->
      NewRM = if HR > RM -> HR; true -> RM end,
      solve(H, Left, Right - 1, LM, NewRM, Ans + (NewRM - HR))
  end.

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (trap height)
  (-> (listof exact-integer?) exact-integer?)
  ; Time O(n), Memory O(n)
  (let* ([h (list->vector height)]
         [n (vector-length h)])
    (let loop ([left 0] [right (sub1 n)] [lm 0] [rm 0] [ans 0])
      (if (>= left right)
          ans
          (let ([hl (vector-ref h left)]
                [hr (vector-ref h right)])
            (if (< hl hr)
                (let ([new-lm (max lm hl)])
                  (loop (add1 left) right new-lm rm (+ ans (- new-lm hl))))
                (let ([new-rm (max rm hr)])
                  (loop left (sub1 right) lm new-rm (+ ans (- new-rm hr))))))))))

```