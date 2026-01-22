# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int uniquePaths(int m, int n) {
        long long res = 1;
        int r = (m < n) ? m - 1 : n - 1;
        int total = m + n - 2;
        for (int i = 1; i <= r; ++i) {
            res = res * (total - i + 1) / i;
        }
        return (int)res;
    }
};
// Time Complexity: O(min(m, n))
// Memory Complexity: O(1)

```

# java

## Sweet Spot

```java
class Solution {
    public int uniquePaths(int m, int n) {
        long res = 1;
        int r = Math.min(m - 1, n - 1);
        int total = m + n - 2;
        for (int i = 1; i <= r; i++) {
            res = res * (total - i + 1) / i;
        }
        return (int) res;
    }
}
// Time Complexity: O(min(m, n))
// Memory Complexity: O(1)

```

# python 3.14

## Sweet Spot

```python 3.14
import math

class Solution:
    def uniquePaths(self, m: int, n: int) -> int:
        return math.comb(m + n - 2, min(m - 1, n - 1))
# Time Complexity: O(min(m, n))
# Memory Complexity: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def uniquePaths(self, m, n):
        """
        :type m: int
        :type n: int
        :rtype: int
        """
        if m == 1 or n == 1:
            return 1
        r = min(m - 1, n - 1)
        total = m + n - 2
        res = 1
        for i in range(1, r + 1):
            res = res * (total - i + 1) / i
        return int(res)
# Time Complexity: O(min(m, n))
# Memory Complexity: O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number} m
 * @param {number} n
 * @return {number}
 */
var uniquePaths = function(m, n) {
    let res = 1;
    let r = Math.min(m - 1, n - 1);
    let total = m + n - 2;
    for (let i = 1; i <= r; i++) {
        res = res * (total - i + 1) / i;
    }
    return Math.round(res);
};
// Time Complexity: O(min(m, n))
// Memory Complexity: O(1)

```

# Typescript

## Sweet Spot

```typescript
function uniquePaths(m: number, n: number): number {
    let res: number = 1;
    let r: number = Math.min(m - 1, n - 1);
    let total: number = m + n - 2;
    for (let i: number = 1; i <= r; i++) {
        res = res * (total - i + 1) / i;
    }
    return Math.round(res);
};
// Time Complexity: O(min(m, n))
// Memory Complexity: O(1)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int UniquePaths(int m, int n) {
        long res = 1;
        int r = Math.Min(m - 1, n - 1);
        int total = m + n - 2;
        for (int i = 1; i <= r; i++) {
            res = res * (total - i + 1) / i;
        }
        return (int)res;
    }
}
// Time Complexity: O(min(m, n))
// Memory Complexity: O(1)

```

# C

## Sweet Spot

```c
int uniquePaths(int m, int n) {
    long long res = 1;
    int r = (m < n) ? m - 1 : n - 1;
    int total = m + n - 2;
    for (int i = 1; i <= r; i++) {
        res = res * (total - i + 1) / i;
    }
    return (int)res;
}
// Time Complexity: O(min(m, n))
// Memory Complexity: O(1)

```

# Go

## Sweet Spot

```go
func uniquePaths(m int, n int) int {
    res := 1
    r := m - 1
    if n - 1 < r {
        r = n - 1
    }
    total := m + n - 2
    for i := 1; i <= r; i++ {
        res = res * (total - i + 1) / i
    }
    return res
}
// Time Complexity: O(min(m, n))
// Memory Complexity: O(1)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun uniquePaths(m: Int, n: Int): Int {
        var res: Long = 1
        val r = if (m < n) m - 1 else n - 1
        val total = m + n - 2
        for (i in 1..r) {
            res = res * (total - i + 1) / i
        }
        return res.toInt()
    }
}
// Time Complexity: O(min(m, n))
// Memory Complexity: O(1)

```

# swift

## Sweet Spot

```swift
class Solution {
    func uniquePaths(_ m: Int, _ n: Int) -> Int {
        var res = 1
        let r = min(m - 1, n - 1)
        if r == 0 { return 1 }
        let total = m + n - 2
        for i in 1...r {
            res = res * (total - i + 1) / i
        }
        return res
    }
}
// Time Complexity: O(min(m, n))
// Memory Complexity: O(1)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn unique_paths(m: i32, n: i32) -> i32 {
        let mut res: i64 = 1;
        let r = if m < n { m - 1 } else { n - 1 };
        let total = m + n - 2;
        for i in 1..=r {
            res = res * (total - i + 1) as i64 / i as i64;
        }
        res as i32
    }
}
// Time Complexity: O(min(m, n))
// Memory Complexity: O(1)

```

# ruby

## Sweet Spot

```ruby
# @param {Integer} m
# @param {Integer} n
# @return {Integer}
def unique_paths(m, n)
    r = [m - 1, n - 1].min
    total = m + n - 2
    res = 1
    (1..r).each do |i|
        res = res * (total - i + 1) / i
    end
    res
end
# Time Complexity: O(min(m, n))
# Memory Complexity: O(1)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer $m
     * @param Integer $n
     * @return Integer
     */
    function uniquePaths($m, $n) {
        $res = 1;
        $r = min($m - 1, $n - 1);
        $total = $m + $n - 2;
        for ($i = 1; $i <= $r; $i++) {
            $res = $res * ($total - $i + 1) / $i;
        }
        return (int)$res;
    }
}
// Time Complexity: O(min(m, n))
// Memory Complexity: O(1)

```

# dart

## Sweet Spot

```dart
class Solution {
  int uniquePaths(int m, int n) {
    int res = 1;
    int r = (m < n) ? m - 1 : n - 1;
    int total = m + n - 2;
    for (int i = 1; i <= r; i++) {
      res = res * (total - i + 1) ~/ i;
    }
    return res;
  }
}
// Time Complexity: O(min(m, n))
// Memory Complexity: O(1)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def uniquePaths(m: Int, n: Int): Int = {
        var res: Long = 1
        val r = if (m < n) m - 1 else n - 1
        val total = m + n - 2
        for (i <- 1 to r) {
            res = res * (total - i + 1) / i
        }
        res.toInt
    }
}
// Time Complexity: O(min(m, n))
// Memory Complexity: O(1)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec unique_paths(m :: integer, n :: integer) :: integer
  def unique_paths(m, n) do
    r = min(m - 1, n - 1)
    total = m + n - 2
    calculate_comb(total, r, 1, 1)
  end

  defp calculate_comb(_total, r, i, acc) when i > r, do: acc
  defp calculate_comb(total, r, i, acc) do
    calculate_comb(total, r, i + 1, div(acc * (total - i + 1), i))
  end
end
# Time Complexity: O(min(m, n))
# Memory Complexity: O(1)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec unique_paths(M :: integer(), N :: integer()) -> integer().
unique_paths(M, N) ->
    R = min(M - 1, N - 1),
    Total = M + N - 2,
    comb(Total, R, 1, 1).

comb(_Total, R, I, Acc) when I > R -> Acc;
comb(Total, R, I, Acc) ->
    comb(Total, R, I + 1, (Acc * (Total - I + 1)) div I).

min(A, B) when A < B -> A;
min(_, B) -> B.
% Time Complexity: O(min(m, n))
% Memory Complexity: O(1)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (unique-paths m n)
  (-> exact-integer? exact-integer? exact-integer?)
  (let* ([r (min (- m 1) (- n 1))]
         [total (- (+ m n) 2)])
    (let loop ([i 1] [res 1])
      (if (> i r)
          res
          (loop (+ i 1) (quotient (* res (- (+ total 1) i)) i))))))
; Time Complexity: O(min(m, n))
; Memory Complexity: O(1)

```