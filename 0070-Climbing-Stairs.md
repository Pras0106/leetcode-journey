# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int climbStairs(int n) {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        if (n <= 2) return n;
        int first = 1;
        int second = 2;
        for (int i = 3; i <= n; i++) {
            int third = first + second;
            first = second;
            second = third;
        }
        return second;
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public int climbStairs(int n) {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        if (n <= 2) return n;
        int first = 1;
        int second = 2;
        for (int i = 3; i <= n; i++) {
            int third = first + second;
            first = second;
            second = third;
        }
        return second;
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def climbStairs(self, n: int) -> int:
        # Time Complexity: O(n)
        # Memory Complexity: O(1)
        if n <= 2:
            return n
        first, second = 1, 2
        for _ in range(3, n + 1):
            first, second = second, first + second
        return second

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def climbStairs(self, n):
        """
        :type n: int
        :rtype: int
        """
        # Time Complexity: O(n)
        # Memory Complexity: O(1)
        if n <= 2:
            return n
        first = 1
        second = 2
        for i in xrange(3, n + 1):
            third = first + second
            first = second
            second = third
        return second

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number} n
 * @return {number}
 */
var climbStairs = function(n) {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    if (n <= 2) return n;
    let first = 1;
    let second = 2;
    for (let i = 3; i <= n; i++) {
        let third = first + second;
        first = second;
        second = third;
    }
    return second;
};

```

# Typescript

## Sweet Spot

```typescript
function climbStairs(n: number): number {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    if (n <= 2) return n;
    let first: number = 1;
    let second: number = 2;
    for (let i: number = 3; i <= n; i++) {
        let third: number = first + second;
        first = second;
        second = third;
    }
    return second;
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int ClimbStairs(int n) {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        if (n <= 2) return n;
        int first = 1;
        int second = 2;
        for (int i = 3; i <= n; i++) {
            int third = first + second;
            first = second;
            second = third;
        }
        return second;
    }
}

```

# C

## Sweet Spot

```c
int climbStairs(int n) {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    if (n <= 2) return n;
    int first = 1;
    int second = 2;
    for (int i = 3; i <= n; i++) {
        int third = first + second;
        first = second;
        second = third;
    }
    return second;
}

```

# Go

## Sweet Spot

```go
func climbStairs(n int) int {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    if n <= 2 {
        return n
    }
    first := 1
    second := 2
    for i := 3; i <= n; i++ {
        third := first + second
        first = second
        second = third
    }
    return second
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun climbStairs(n: Int): Int {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        if (n <= 2) return n
        var first = 1
        var second = 2
        for (i in 3..n) {
            val third = first + second
            first = second
            second = third
        }
        return second
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func climbStairs(_ n: Int) -> Int {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        if n <= 2 {
            return n
        }
        var first = 1
        var second = 2
        for _ in 3...n {
            let third = first + second
            first = second
            second = third
        }
        return second
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn climb_stairs(n: i32) -> i32 {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        if n <= 2 {
            return n;
        }
        let mut first = 1;
        let mut second = 2;
        for _ in 3..=n {
            let third = first + second;
            first = second;
            second = third;
        }
        second
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer} n
# @return {Integer}
def climb_stairs(n)
    # Time Complexity: O(n)
    # Memory Complexity: O(1)
    return n if n <= 2
    first = 1
    second = 2
    (3..n).each do
        third = first + second
        first = second
        second = third
    end
    second
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer $n
     * @return Integer
     */
    function climbStairs($n) {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        if ($n <= 2) return $n;
        $first = 1;
        $second = 2;
        for ($i = 3; $i <= $n; $i++) {
            $third = $first + $second;
            $first = $second;
            $second = $third;
        }
        return $second;
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  int climbStairs(int n) {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    if (n <= 2) return n;
    int first = 1;
    int second = 2;
    for (int i = 3; i <= n; i++) {
      int third = first + second;
      first = second;
      second = third;
    }
    return second;
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def climbStairs(n: Int): Int = {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        if (n <= 2) return n
        var first = 1
        var second = 2
        var i = 3
        while (i <= n) {
            val third = first + second
            first = second
            second = third
            i += 1
        }
        second
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec climb_stairs(n :: integer) :: integer
  def climb_stairs(n) do
    # Time Complexity: O(n)
    # Memory Complexity: O(1)
    cond do
      n <= 2 -> n
      true -> iterate(3, n, 1, 2)
    end
  end

  defp iterate(current, target, first, second) when current > target do
    second
  end

  defp iterate(current, target, first, second) do
    iterate(current + 1, target, second, first + second)
  end
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec climb_stairs(N :: integer()) -> integer().
climb_stairs(N) ->
  % Time Complexity: O(N)
  % Memory Complexity: O(1)
  if
    N =< 2 -> N;
    true -> climb_stairs_iter(3, N, 1, 2)
  end.

climb_stairs_iter(Current, Target, First, Second) when Current > Target ->
  Second;
climb_stairs_iter(Current, Target, First, Second) ->
  climb_stairs_iter(Current + 1, Target, Second, First + Second).

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (climb-stairs n)
  (-> exact-integer? exact-integer?)
  ; Time Complexity: O(n)
  ; Memory Complexity: O(1)
  (let loop ([current 3]
             [first 1]
             [second 2])
    (cond
      [(<= n 2) n]
      [(> current n) second]
      [else (loop (+ current 1) second (+ first second))])))

```