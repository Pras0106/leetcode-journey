# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int divide(int dividend, int divisor) {
        // Time Complexity: O(log^2 N)
        // Memory Complexity: O(1)
        if (dividend == INT_MIN && divisor == -1) return INT_MAX;
        long long a = abs((long long)dividend);
        long long b = abs((long long)divisor);
        long long res = 0;
        while (a >= b) {
            long long temp = b, mul = 1;
            while (a >= (temp << 1)) {
                temp <<= 1;
                mul <<= 1;
            }
            a -= temp;
            res += mul;
        }
        return (dividend > 0) == (divisor > 0) ? res : -res;
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public int divide(int dividend, int divisor) {
        // Time Complexity: O(log^2 N)
        // Memory Complexity: O(1)
        if (dividend == Integer.MIN_VALUE && divisor == -1) return Integer.MAX_VALUE;
        long a = Math.abs((long) dividend);
        long b = Math.abs((long) divisor);
        int res = 0;
        while (a >= b) {
            long temp = b, mul = 1;
            while (a >= (temp << 1)) {
                temp <<= 1;
                mul <<= 1;
            }
            a -= temp;
            res += mul;
        }
        return (dividend > 0) == (divisor > 0) ? res : -res;
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def divide(self, dividend: int, divisor: int) -> int:
        # Time Complexity: O(log^2 N)
        # Memory Complexity: O(1)
        if dividend == -2147483648 and divisor == -1:
            return 2147483647
        a, b = abs(dividend), abs(divisor)
        res = 0
        while a >= b:
            temp, mul = b, 1
            while a >= (temp << 1):
                temp <<= 1
                mul <<= 1
            a -= temp
            res += mul
        res = res if (dividend > 0) == (divisor > 0) else -res
        return min(max(-2147483648, res), 2147483647)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def divide(self, dividend, divisor):
        """
        :type dividend: int
        :type divisor: int
        :rtype: int
        """
        # Time Complexity: O(log^2 N)
        # Memory Complexity: O(1)
        if dividend == -2147483648 and divisor == -1:
            return 2147483647
        a, b = abs(long(dividend)), abs(long(divisor))
        res = 0
        while a >= b:
            temp, mul = b, 1
            while a >= (temp << 1):
                temp <<= 1
                mul <<= 1
            a -= temp
            res += mul
        res = res if (dividend > 0) == (divisor > 0) else -res
        return min(max(-2147483648, res), 2147483647)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number} dividend
 * @param {number} divisor
 * @return {number}
 */
var divide = function(dividend, divisor) {
    // Time Complexity: O(log^2 N)
    // Memory Complexity: O(1)
    if (dividend === -2147483648 && divisor === -1) return 2147483647;
    let a = Math.abs(dividend);
    let b = Math.abs(divisor);
    let res = 0;
    while (a >= b) {
        let temp = b, mul = 1;
        while (a >= temp * 2) {
            temp *= 2;
            mul *= 2;
        }
        a -= temp;
        res += mul;
    }
    return (dividend > 0) === (divisor > 0) ? res : -res;
};

```

# Typescript

## Sweet Spot

```typescript
function divide(dividend: number, divisor: number): number {
    // Time Complexity: O(log^2 N)
    // Memory Complexity: O(1)
    if (dividend === -2147483648 && divisor === -1) return 2147483647;
    let a: number = Math.abs(dividend);
    let b: number = Math.abs(divisor);
    let res: number = 0;
    while (a >= b) {
        let temp: number = b;
        let mul: number = 1;
        while (a >= temp * 2) {
            temp *= 2;
            mul *= 2;
        }
        a -= temp;
        res += mul;
    }
    return (dividend > 0) === (divisor > 0) ? res : -res;
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int Divide(int dividend, int divisor) {
        // Time Complexity: O(log^2 N)
        // Memory Complexity: O(1)
        if (dividend == int.MinValue && divisor == -1) return int.MaxValue;
        long a = Math.Abs((long)dividend);
        long b = Math.Abs((long)divisor);
        long res = 0;
        while (a >= b) {
            long temp = b, mul = 1;
            while (a >= (temp << 1)) {
                temp <<= 1;
                mul <<= 1;
            }
            a -= temp;
            res += mul;
        }
        return (dividend > 0) == (divisor > 0) ? (int)res : (int)-res;
    }
}

```

# C

## Sweet Spot

```c
int divide(int dividend, int divisor) {
    // Time Complexity: O(log^2 N)
    // Memory Complexity: O(1)
    if (dividend == -2147483648 && divisor == -1) return 2147483647;
    long long a = llabs((long long)dividend);
    long long b = llabs((long long)divisor);
    long long res = 0;
    while (a >= b) {
        long long temp = b, mul = 1;
        while (a >= (temp << 1)) {
            temp <<= 1;
            mul <<= 1;
        }
        a -= temp;
        res += mul;
    }
    return (dividend > 0) == (divisor > 0) ? (int)res : (int)-res;
}

```

# Go

## Sweet Spot

```go
func divide(dividend int, divisor int) int {
    // Time Complexity: O(log^2 N)
    // Memory Complexity: O(1)
    if dividend == -2147483648 && divisor == -1 {
        return 2147483647
    }
    a := int64(dividend)
    if a < 0 { a = -a }
    b := int64(divisor)
    if b < 0 { b = -b }
    var res int64 = 0
    for a >= b {
        temp, mul := b, int64(1)
        for a >= (temp << 1) {
            temp <<= 1
            mul <<= 1
        }
        a -= temp
        res += mul
    }
    if (dividend > 0) != (divisor > 0) {
        res = -res
    }
    return int(res)
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun divide(dividend: Int, divisor: Int): Int {
        // Time Complexity: O(log^2 N)
        // Memory Complexity: O(1)
        if (dividend == Int.MIN_VALUE && divisor == -1) return Int.MAX_VALUE
        var a = Math.abs(dividend.toLong())
        val b = Math.abs(divisor.toLong())
        var res = 0L
        while (a >= b) {
            var temp = b
            var mul = 1L
            while (a >= (temp shl 1)) {
                temp = temp shl 1
                mul = mul shl 1
            }
            a -= temp
            res += mul
        }
        return if ((dividend > 0) == (divisor > 0)) res.toInt() else (-res).toInt()
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func divide(_ dividend: Int, _ divisor: Int) -> Int {
        // Time Complexity: O(log^2 N)
        // Memory Complexity: O(1)
        if dividend == -2147483648 && divisor == -1 { return 2147483647 }
        var a = abs(Int64(dividend))
        let b = abs(Int64(divisor))
        var res: Int64 = 0
        while a >= b {
            var temp = b
            var mul: Int64 = 1
            while a >= (temp << 1) {
                temp <<= 1
                mul <<= 1
            }
            a -= temp
            res += mul
        }
        return (dividend > 0) == (divisor > 0) ? Int(res) : Int(-res)
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn divide(dividend: i32, divisor: i32) -> i32 {
        // Time Complexity: O(log^2 N)
        // Memory Complexity: O(1)
        if dividend == i32::MIN && divisor == -1 { return i32::MAX; }
        let mut a = (dividend as i64).abs();
        let b = (divisor as i64).abs();
        let mut res = 0i64;
        while a >= b {
            let mut temp = b;
            let mut mul = 1i64;
            while a >= (temp << 1) {
                temp <<= 1;
                mul <<= 1;
            }
            a -= temp;
            res += mul;
        }
        if (dividend > 0) == (divisor > 0) { res as i32 } else { -res as i32 }
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer} dividend
# @param {Integer} divisor
# @return {Integer}
def divide(dividend, divisor)
    # Time Complexity: O(log^2 N)
    # Memory Complexity: O(1)
    if dividend == -2147483648 && divisor == -1
        return 2147483647
    end
    a, b = dividend.abs, divisor.abs
    res = 0
    while a >= b
        temp, mul = b, 1
        while a >= (temp << 1)
            temp <<= 1
            mul <<= 1
        end
        a -= temp
        res += mul
    end
    res = (dividend > 0) == (divisor > 0) ? res : -res
    [[-2147483648, res].max, 2147483647].min
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer $dividend
     * @param Integer $divisor
     * @return Integer
     */
    function divide($dividend, $divisor) {
        // Time Complexity: O(log^2 N)
        // Memory Complexity: O(1)
        if ($dividend == -2147483648 && $divisor == -1) return 2147483647;
        $a = abs($dividend);
        $b = abs($divisor);
        $res = 0;
        while ($a >= $b) {
            $temp = $b;
            $mul = 1;
            while ($a >= ($temp << 1)) {
                $temp <<= 1;
                $mul <<= 1;
            }
            $a -= $temp;
            $res += $mul;
        }
        return ($dividend > 0) == ($divisor > 0) ? $res : -$res;
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  int divide(int dividend, int divisor) {
    // Time Complexity: O(log^2 N)
    // Memory Complexity: O(1)
    if (dividend == -2147483648 && divisor == -1) return 2147483647;
    int a = dividend.abs();
    int b = divisor.abs();
    int res = 0;
    while (a >= b) {
      int temp = b;
      int mul = 1;
      while (a >= (temp << 1)) {
        temp <<= 1;
        mul <<= 1;
      }
      a -= temp;
      res += mul;
    }
    int ans = (dividend > 0) == (divisor > 0) ? res : -res;
    return ans.clamp(-2147483648, 2147483647);
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def divide(dividend: Int, divisor: Int): Int = {
        // Time Complexity: O(log^2 N)
        // Memory Complexity: O(1)
        if (dividend == Int.MinValue && divisor == -1) return Int.MaxValue
        var a: Long = Math.abs(dividend.toLong)
        val b: Long = Math.abs(divisor.toLong)
        var res: Long = 0
        while (a >= b) {
            var temp = b
            var mul = 1L
            while (a >= (temp << 1)) {
                temp <<= 1
                mul <<= 1
            }
            a -= temp
            res += mul
        }
        if ((dividend > 0) == (divisor > 0)) res.toInt else (-res).toInt
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  import Bitwise

  @spec divide(dividend :: integer, divisor :: integer) :: integer
  def divide(dividend, divisor) do
    # Time Complexity: O(log^2 N)
    # Memory Complexity: O(log N)
    if dividend == -2147483648 and divisor == -1 do
      2147483647
    else
      a = abs(dividend)
      b = abs(divisor)
      res = do_divide(a, b, 0)
      if (dividend > 0) == (divisor > 0), do: res, else: -res
    end
  end

  defp do_divide(a, b, res) when a < b, do: res
  defp do_divide(a, b, res) do
    {temp, mul} = find_max_sub(a, b, 1)
    do_divide(a - temp, b, res + mul)
  end

  defp find_max_sub(a, b, mul) when b <<< 1 <= a and b <<< 1 > 0 do
    find_max_sub(a, b <<< 1, mul <<< 1)
  end
  defp find_max_sub(_a, b, mul), do: {b, mul}
end
```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec divide(Dividend :: integer(), Divisor :: integer()) -> integer().
divide(Dividend, Divisor) ->
  % Time Complexity: O(log^2 N)
  % Memory Complexity: O(1)
  if
    Dividend == -2147483648, Divisor == -1 -> 2147483647;
    true ->
      A = abs(Dividend),
      B = abs(Divisor),
      Res = calc_divide(A, B, 0),
      case (Dividend > 0) == (Divisor > 0) of
        true -> Res;
        false -> -Res
      end
  end.

calc_divide(A, B, Acc) when A >= B ->
  {Temp, Mul} = find_max(A, B, 1),
  calc_divide(A - Temp, B, Acc + Mul);
calc_divide(_, _, Acc) -> Acc.

find_max(A, B, Mul) when A >= (B bsl 1) -> find_max(A, (B bsl 1), (Mul bsl 1));
find_max(_, B, Mul) -> {B, Mul}.

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (divide dividend divisor)
  (-> exact-integer? exact-integer? exact-integer?)
  ; Time Complexity: O(log^2 N)
  ; Memory Complexity: O(1)
  (if (and (= dividend -2147483648) (= divisor -1))
      2147483647
      (let* ([a (abs dividend)]
             [b (abs divisor)]
             [res (let loop ([curr_a a] [acc 0])
                    (if (< curr_a b)
                        acc
                        (let-values ([(temp mul) 
                                      (let find ([t b] [m 1])
                                        (if (>= curr_a (arithmetic-shift t 1))
                                            (find (arithmetic-shift t 1) (arithmetic-shift m 1))
                                            (values t m)))])
                          (loop (- curr_a temp) (+ acc mul)))))])
        (if (eq? (> dividend 0) (> divisor 0))
            res
            (- res)))))

```