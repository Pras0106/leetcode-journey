# cpp

## Sweet Spot

```cpp
class Solution {
public:
    double myPow(double x, int n) {
        long long N = n;
        if (N < 0) {
            x = 1 / x;
            N = -N;
        }
        double ans = 1;
        double current_product = x;
        for (long long i = N; i > 0; i /= 2) {
            if ((i % 2) == 1) {
                ans = ans * current_product;
            }
            current_product = current_product * current_product;
        }
        return ans;
    }
};
// Time Complexity: O(log n)
// Memory Complexity: O(1)

```

# java

## Sweet Spot

```java
class Solution {
    public double myPow(double x, int n) {
        long N = n;
        if (N < 0) {
            x = 1 / x;
            N = -N;
        }
        double ans = 1;
        double current_product = x;
        for (long i = N; i > 0; i /= 2) {
            if ((i % 2) == 1) {
                ans = ans * current_product;
            }
            current_product = current_product * current_product;
        }
        return ans;
    }
}
// Time Complexity: O(log n)
// Memory Complexity: O(1)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def myPow(self, x: float, n: int) -> float:
        if n < 0:
            x = 1 / x
            n = -n
        ans = 1.0
        current_product = x
        while n > 0:
            if n % 2 == 1:
                ans *= current_product
            current_product *= current_product
            n //= 2
        return ans
# Time Complexity: O(log n)
# Memory Complexity: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def myPow(self, x, n):
        """
        :type x: float
        :type n: int
        :rtype: float
        """
        if n < 0:
            x = 1.0 / x
            n = -n
        ans = 1.0
        current_product = x
        while n > 0:
            if n % 2 == 1:
                ans *= current_product
            current_product *= current_product
            n //= 2
        return ans
# Time Complexity: O(log n)
# Memory Complexity: O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number} x
 * @param {number} n
 * @return {number}
 */
var myPow = function(x, n) {
    let N = n;
    if (N < 0) {
        x = 1 / x;
        N = -N;
    }
    let ans = 1;
    let current_product = x;
    while (N > 0) {
        if (N % 2 === 1) {
            ans = ans * current_product;
        }
        current_product = current_product * current_product;
        N = Math.floor(N / 2);
    }
    return ans;
};
// Time Complexity: O(log n)
// Memory Complexity: O(1)

```

# Typescript

## Sweet Spot

```typescript
function myPow(x: number, n: number): number {
    let N: number = n;
    if (N < 0) {
        x = 1 / x;
        N = -N;
    }
    let ans: number = 1;
    let currentProduct: number = x;
    while (N > 0) {
        if (N % 2 === 1) {
            ans = ans * currentProduct;
        }
        currentProduct = currentProduct * currentProduct;
        N = Math.floor(N / 2);
    }
    return ans;
};
// Time Complexity: O(log n)
// Memory Complexity: O(1)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public double MyPow(double x, int n) {
        long N = n;
        if (N < 0) {
            x = 1 / x;
            N = -N;
        }
        double ans = 1;
        double currentProduct = x;
        for (long i = N; i > 0; i /= 2) {
            if ((i % 2) == 1) {
                ans = ans * currentProduct;
            }
            currentProduct = currentProduct * currentProduct;
        }
        return ans;
    }
}
// Time Complexity: O(log n)
// Memory Complexity: O(1)

```

# C

## Sweet Spot

```c
double myPow(double x, int n) {
    long long N = n;
    if (N < 0) {
        x = 1 / x;
        N = -N;
    }
    double ans = 1.0;
    double current_product = x;
    for (long long i = N; i > 0; i /= 2) {
        if ((i % 2) == 1) {
            ans = ans * current_product;
        }
        current_product = current_product * current_product;
    }
    return ans;
}
/* Time Complexity: O(log n) */
/* Memory Complexity: O(1) */

```

# Go

## Sweet Spot

```go
func myPow(x float64, n int) float64 {
    N := int64(n)
    if N < 0 {
        x = 1 / x
        N = -N
    }
    ans := 1.0
    currentProduct := x
    for i := N; i > 0; i /= 2 {
        if i%2 == 1 {
            ans *= currentProduct
        }
        currentProduct *= currentProduct
    }
    return ans
}
// Time Complexity: O(log n)
// Memory Complexity: O(1)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun myPow(x: Double, n: Int): Double {
        var N = n.toLong()
        var base = x
        if (N < 0) {
            base = 1 / base
            N = -N
        }
        var ans = 1.0
        var currentProduct = base
        var i = N
        while (i > 0) {
            if (i % 2 == 1L) {
                ans *= currentProduct
            }
            currentProduct *= currentProduct
            i /= 2
        }
        return ans
    }
}
// Time Complexity: O(log n)
// Memory Complexity: O(1)

```

# swift

## Sweet Spot

```swift
class Solution {
    func myPow(_ x: Double, _ n: Int) -> Double {
        var N = Int64(n)
        var base = x
        if N < 0 {
            base = 1 / base
            N = -N
        }
        var ans: Double = 1.0
        var currentProduct = base
        var i = N
        while i > 0 {
            if i % 2 == 1 {
                ans *= currentProduct
            }
            currentProduct *= currentProduct
            i /= 2
        }
        return ans
    }
}
// Time Complexity: O(log n)
// Memory Complexity: O(1)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn my_pow(x: f64, n: i32) -> f64 {
        let mut n_long = n as i64;
        let mut base = x;
        if n_long < 0 {
            base = 1.0 / base;
            n_long = -n_long;
        }
        let mut ans = 1.0;
        let mut current_product = base;
        let mut i = n_long;
        while i > 0 {
            if i % 2 == 1 {
                ans *= current_product;
            }
            current_product *= current_product;
            i /= 2;
        }
        ans
    }
}
// Time Complexity: O(log n)
// Memory Complexity: O(1)

```

# ruby

## Sweet Spot

```ruby
# @param {Float} x
# @param {Integer} n
# @return {Float}
def my_pow(x, n)
    if n < 0
        x = 1.0 / x
        n = -n
    end
    ans = 1.0
    current_product = x
    while n > 0
        if n % 2 == 1
            ans *= current_product
        end
        current_product *= current_product
        n /= 2
    end
    ans
end
# Time Complexity: O(log n)
# Memory Complexity: O(1)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Float $x
     * @param Integer $n
     * @return Float
     */
    function myPow($x, $n) {
        $N = (float)$n;
        if ($N < 0) {
            $x = 1 / $x;
            $N = -$N;
        }
        $ans = 1.0;
        $current_product = $x;
        while ($N > 0) {
            if (fmod($N, 2) == 1) {
                $ans *= $current_product;
            }
            $current_product *= $current_product;
            $N = floor($N / 2);
        }
        return $ans;
    }
}
// Time Complexity: O(log n)
// Memory Complexity: O(1)

```

# dart

## Sweet Spot

```dart
class Solution {
  double myPow(double x, int n) {
    int N = n;
    if (N < 0) {
      x = 1 / x;
      N = -N;
    }
    double ans = 1.0;
    double currentProduct = x;
    for (int i = N; i > 0; i = i ~/ 2) {
      if (i % 2 == 1) {
        ans *= currentProduct;
      }
      currentProduct *= currentProduct;
    }
    return ans;
  }
}
// Time Complexity: O(log n)
// Memory Complexity: O(1)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def myPow(x: Double, n: Int): Double = {
        var N: Long = n.toLong
        var base = x
        if (N < 0) {
            base = 1.0 / base
            N = -N
        }
        var ans = 1.0
        var currentProduct = base
        var i = N
        while (i > 0) {
            if (i % 2 == 1) {
                ans *= currentProduct
            }
            currentProduct *= currentProduct
            i /= 2
        }
        ans
    }
}
// Time Complexity: O(log n)
// Memory Complexity: O(1)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec my_pow(x :: float, n :: integer) :: float
  def my_pow(x, n) do
    cond do
      n == 0 -> 1.0
      n < 0 -> pow_iter(1.0 / x, -n, 1.0)
      true -> pow_iter(x, n, 1.0)
    end
  end

  defp pow_iter(_base, 0, acc), do: acc
  defp pow_iter(base, n, acc) do
    new_acc = if rem(n, 2) == 1, do: acc * base, else: acc
    pow_iter(base * base, div(n, 2), new_acc)
  end
end
# Time Complexity: O(log n)
# Memory Complexity: O(log n) due to tail call recursion optimization in some environments, but technically stack-safe

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec my_pow(X :: float(), N :: integer()) -> float().
my_pow(X, 0) -> 1.0;
my_pow(X, N) when N < 0 -> pow_iter(1.0 / X, -N, 1.0);
my_pow(X, N) -> pow_iter(X, N, 1.0).

pow_iter(_Base, 0, Acc) -> Acc;
pow_iter(Base, N, Acc) ->
    NewAcc = case N rem 2 of
        1 -> Acc * Base;
        0 -> Acc
    end,
    pow_iter(Base * Base, N div 2, NewAcc).
% Time Complexity: O(log n)
% Memory Complexity: O(log n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (my-pow x n)
  (-> flonum? exact-integer? flonum?)
  (let ([N (if (< n 0) (- n) n)]
        [base (if (< n 0) (/ 1.0 x) x)])
    (let loop ([i N] [curr base] [ans 1.0])
      (if (zero? i)
          ans
          (loop (quotient i 2)
                (* curr curr)
                (if (odd? i) (* ans curr) ans))))))
; Time Complexity: O(log n)
; Memory Complexity: O(log n)

```