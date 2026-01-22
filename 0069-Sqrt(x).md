# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int mySqrt(int x) {
        if (x < 2) return x;
        int left = 2, right = x / 2, ans = 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (mid <= x / mid) {
                ans = mid;
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return ans;
        /* Time: O(log x), Memory: O(1) */
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public int mySqrt(int x) {
        if (x < 2) return x;
        int left = 2, right = x / 2, ans = 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (mid <= x / mid) {
                ans = mid;
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return ans;
        /* Time: O(log x), Memory: O(1) */
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def mySqrt(self, x: int) -> int:
        if x < 2:
            return x
        left, right = 2, x // 2
        ans = 1
        while left <= right:
            mid = left + (right - left) // 2
            if mid <= x // mid:
                ans = mid
                left = mid + 1
            else:
                right = mid - 1
        return ans
        # Time: O(log x), Memory: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def mySqrt(self, x):
        """
        :type x: int
        :rtype: int
        """
        if x < 2:
            return x
        left, right = 2, x / 2
        ans = 1
        while left <= right:
            mid = left + (right - left) / 2
            if mid <= x / mid:
                ans = mid
                left = mid + 1
            else:
                right = mid - 1
        return ans
        # Time: O(log x), Memory: O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number} x
 * @return {number}
 */
var mySqrt = function(x) {
    if (x < 2) return x;
    let left = 2, right = Math.floor(x / 2), ans = 1;
    while (left <= right) {
        let mid = Math.floor(left + (right - left) / 2);
        if (mid <= x / mid) {
            ans = mid;
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    return ans;
    /* Time: O(log x), Memory: O(1) */
};

```

# Typescript

## Sweet Spot

```typescript
function mySqrt(x: number): number {
    if (x < 2) return x;
    let left: number = 2, right: number = Math.floor(x / 2), ans: number = 1;
    while (left <= right) {
        let mid: number = Math.floor(left + (right - left) / 2);
        if (mid <= x / mid) {
            ans = mid;
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    return ans;
    /* Time: O(log x), Memory: O(1) */
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int MySqrt(int x) {
        if (x < 2) return x;
        int left = 2, right = x / 2, ans = 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (mid <= x / mid) {
                ans = mid;
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return ans;
        /* Time: O(log x), Memory: O(1) */
    }
}

```

# C

## Sweet Spot

```c
int mySqrt(int x) {
    if (x < 2) return x;
    int left = 2, right = x / 2, ans = 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (mid <= x / mid) {
            ans = mid;
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    return ans;
    /* Time: O(log x), Memory: O(1) */
}

```

# Go

## Sweet Spot

```go
func mySqrt(x int) int {
    if x < 2 {
        return x
    }
    left, right, ans := 2, x/2, 1
    for left <= right {
        mid := left + (right-left)/2
        if mid <= x/mid {
            ans = mid
            left = mid + 1
        } else {
            right = mid - 1
        }
    }
    return ans
    /* Time: O(log x), Memory: O(1) */
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun mySqrt(x: Int): Int {
        if (x < 2) return x
        var left = 2
        var right = x / 2
        var ans = 1
        while (left <= right) {
            val mid = left + (right - left) / 2
            if (mid <= x / mid) {
                ans = mid
                left = mid + 1
            } else {
                right = mid - 1
            }
        }
        return ans
        /* Time: O(log x), Memory: O(1) */
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func mySqrt(_ x: Int) -> Int {
        if x < 2 { return x }
        var left = 2
        var right = x / 2
        var ans = 1
        while left <= right {
            let mid = left + (right - left) / 2
            if mid <= x / mid {
                ans = mid
                left = mid + 1
            } else {
                right = mid - 1
            }
        }
        return ans
        /* Time: O(log x), Memory: O(1) */
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn my_sqrt(x: i32) -> i32 {
        if x < 2 { return x; }
        let mut left = 2;
        let mut right = x / 2;
        let mut ans = 1;
        while left <= right {
            let mid = left + (right - left) / 2;
            if mid <= x / mid {
                ans = mid;
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        ans
        /* Time: O(log x), Memory: O(1) */
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer} x
# @return {Integer}
def my_sqrt(x)
    return x if x < 2
    left, right, ans = 2, x / 2, 1
    while left <= right
        mid = left + (right - left) / 2
        if mid <= x / mid
            ans = mid
            left = mid + 1
        else
            right = mid - 1
        end
    end
    ans
    # Time: O(log x), Memory: O(1)
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer $x
     * @return Integer
     */
    function mySqrt($x) {
        if ($x < 2) return $x;
        $left = 2;
        $right = (int)($x / 2);
        $ans = 1;
        while ($left <= $right) {
            $mid = $left + (int)(($right - $left) / 2);
            if ($mid <= $x / $mid) {
                $ans = $mid;
                $left = $mid + 1;
            } else {
                $right = $mid - 1;
            }
        }
        return $ans;
        /* Time: O(log x), Memory: O(1) */
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  int mySqrt(int x) {
    if (x < 2) return x;
    int left = 2, right = x ~/ 2, ans = 1;
    while (left <= right) {
      int mid = left + (right - left) ~/ 2;
      if (mid <= x ~/ mid) {
        ans = mid;
        left = mid + 1;
      } else {
        right = mid - 1;
      }
    }
    return ans;
    /* Time: O(log x), Memory: O(1) */
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def mySqrt(x: Int): Int = {
        if (x < 2) return x
        var left = 2
        var right = x / 2
        var ans = 1
        while (left <= right) {
            val mid = left + (right - left) / 2
            if (mid <= x / mid) {
                ans = mid
                left = mid + 1
            } else {
                right = mid - 1
            }
        }
        ans
        /* Time: O(log x), Memory: O(1) */
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec my_sqrt(x :: integer) :: integer
  def my_sqrt(x) when x < 2, do: x
  def my_sqrt(x) do
    binary_search(2, div(x, 2), 1, x)
  end

  defp binary_search(left, right, ans, x) when left <= right do
    mid = left + div(right - left, 2)
    if mid <= div(x, mid) do
      binary_search(mid + 1, right, mid, x)
    else
      binary_search(left, mid - 1, ans, x)
    end
  end
  defp binary_search(_left, _right, ans, _x), do: ans
  # Time: O(log x), Memory: O(log x) due to recursion
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec my_sqrt(X :: integer()) -> integer().
my_sqrt(X) when X < 2 -> X;
my_sqrt(X) -> binary_search(2, X div 2, 1, X).

binary_search(Left, Right, Ans, X) when Left =< Right ->
    Mid = Left + (Right - Left) div 2,
    case Mid =< (X div Mid) of
        true -> binary_search(Mid + 1, Right, Mid, X);
        false -> binary_search(Left, Mid - 1, Ans, X)
    end;
binary_search(_, _, Ans, _) -> Ans.
% Time: O(log x), Memory: O(log x) due to tail recursion stack in some VMs, though optimized here

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (my-sqrt x)
  (-> exact-integer? exact-integer?)
  (if (< x 2)
      x
      (let loop ([left 2] [right (quotient x 2)] [ans 1])
        (if (<= left right)
            (let* ([mid (+ left (quotient (- right left) 2))]
                   [sq-check (<= mid (quotient x mid))])
              (if sq-check
                  (loop (+ mid 1) right mid)
                  (loop left (- mid 1) ans)))
            ans))))
; Time: O(log x), Memory: O(1)

```