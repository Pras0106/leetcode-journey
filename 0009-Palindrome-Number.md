# cpp

## Sweet Spot

```cpp
class Solution {
public:
    bool isPalindrome(int x) {
        if (x < 0 || (x % 10 == 0 && x != 0)) {
            return false;
        }
        int revertedNumber = 0;
        while (x > revertedNumber) {
            revertedNumber = revertedNumber * 10 + x % 10;
            x /= 10;
        }
        return x == revertedNumber || x == revertedNumber / 10;
        // Time Complexity: O(log10(n))
        // Memory Complexity: O(1)
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public boolean isPalindrome(int x) {
        if (x < 0 || (x % 10 == 0 && x != 0)) {
            return false;
        }
        int revertedNumber = 0;
        while (x > revertedNumber) {
            revertedNumber = revertedNumber * 10 + x % 10;
            x /= 10;
        }
        return x == revertedNumber || x == revertedNumber / 10;
        // Time Complexity: O(log10(n))
        // Memory Complexity: O(1)
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def isPalindrome(self, x: int) -> bool:
        if x < 0 or (x % 10 == 0 and x != 0):
            return False
        revertedNumber = 0
        while x > revertedNumber:
            revertedNumber = revertedNumber * 10 + x % 10
            x //= 10
        return x == revertedNumber or x == revertedNumber // 10
        # Time Complexity: O(log10(n))
        # Memory Complexity: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def isPalindrome(self, x):
        """
        :type x: int
        :rtype: bool
        """
        if x < 0 or (x % 10 == 0 and x != 0):
            return False
        revertedNumber = 0
        while x > revertedNumber:
            revertedNumber = revertedNumber * 10 + x % 10
            x /= 10
        return x == revertedNumber or x == revertedNumber / 10
        # Time Complexity: O(log10(n))
        # Memory Complexity: O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number} x
 * @return {boolean}
 */
var isPalindrome = function(x) {
    if (x < 0 || (x % 10 === 0 && x !== 0)) {
        return false;
    }
    let revertedNumber = 0;
    while (x > revertedNumber) {
        revertedNumber = revertedNumber * 10 + x % 10;
        x = Math.floor(x / 10);
    }
    return x === revertedNumber || x === Math.floor(revertedNumber / 10);
    // Time Complexity: O(log10(n))
    // Memory Complexity: O(1)
};

```

# Typescript

## Sweet Spot

```typescript
function isPalindrome(x: number): boolean {
    if (x < 0 || (x % 10 === 0 && x !== 0)) {
        return false;
    }
    let revertedNumber: number = 0;
    while (x > revertedNumber) {
        revertedNumber = revertedNumber * 10 + (x % 10);
        x = Math.floor(x / 10);
    }
    return x === revertedNumber || x === Math.floor(revertedNumber / 10);
    // Time Complexity: O(log10(n))
    // Memory Complexity: O(1)
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public bool IsPalindrome(int x) {
        if (x < 0 || (x % 10 == 0 && x != 0)) {
            return false;
        }
        int revertedNumber = 0;
        while (x > revertedNumber) {
            revertedNumber = revertedNumber * 10 + x % 10;
            x /= 10;
        }
        return x == revertedNumber || x == revertedNumber / 10;
        // Time Complexity: O(log10(n))
        // Memory Complexity: O(1)
    }
}

```

# C

## Sweet Spot

```c
bool isPalindrome(int x) {
    if (x < 0 || (x % 10 == 0 && x != 0)) {
        return false;
    }
    int revertedNumber = 0;
    while (x > revertedNumber) {
        revertedNumber = revertedNumber * 10 + x % 10;
        x /= 10;
    }
    return x == revertedNumber || x == revertedNumber / 10;
    /* Time Complexity: O(log10(n)) */
    /* Memory Complexity: O(1) */
}

```

# Go

## Sweet Spot

```go
func isPalindrome(x int) bool {
    if x < 0 || (x % 10 == 0 && x != 0) {
        return false
    }
    revertedNumber := 0
    for x > revertedNumber {
        revertedNumber = revertedNumber * 10 + x % 10
        x /= 10
    }
    return x == revertedNumber || x == revertedNumber / 10
    // Time Complexity: O(log10(n))
    // Memory Complexity: O(1)
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun isPalindrome(x: Int): Boolean {
        if (x < 0 || (x % 10 == 0 && x != 0)) {
            return false
        }
        var num = x
        var revertedNumber = 0
        while (num > revertedNumber) {
            revertedNumber = revertedNumber * 10 + num % 10
            num /= 10
        }
        return num == revertedNumber || num == revertedNumber / 10
        // Time Complexity: O(log10(n))
        // Memory Complexity: O(1)
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func isPalindrome(_ x: Int) -> Bool {
        if x < 0 || (x % 10 == 0 && x != 0) {
            return false
        }
        var num = x
        var revertedNumber = 0
        while num > revertedNumber {
            revertedNumber = revertedNumber * 10 + num % 10
            num /= 10
        }
        return num == revertedNumber || num == revertedNumber / 10
        // Time Complexity: O(log10(n))
        // Memory Complexity: O(1)
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn is_palindrome(x: i32) -> bool {
        if x < 0 || (x % 10 == 0 && x != 0) {
            return false;
        }
        let mut num = x;
        let mut reverted_number = 0;
        while num > reverted_number {
            reverted_number = reverted_number * 10 + num % 10;
            num /= 10;
        }
        num == reverted_number || num == reverted_number / 10
        // Time Complexity: O(log10(n))
        // Memory Complexity: O(1)
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer} x
# @return {Boolean}
def is_palindrome(x)
    return false if x < 0 || (x % 10 == 0 && x != 0)
    reverted_number = 0
    while x > reverted_number
        reverted_number = reverted_number * 10 + x % 10
        x /= 10
    end
    x == reverted_number || x == reverted_number / 10
    # Time Complexity: O(log10(n))
    # Memory Complexity: O(1)
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer $x
     * @return Boolean
     */
    function isPalindrome($x) {
        if ($x < 0 || ($x % 10 == 0 && $x != 0)) {
            return false;
        }
        $revertedNumber = 0;
        while ($x > $revertedNumber) {
            $revertedNumber = $revertedNumber * 10 + $x % 10;
            $x = (int)($x / 10);
        }
        return $x == $revertedNumber || $x == (int)($revertedNumber / 10);
        // Time Complexity: O(log10(n))
        // Memory Complexity: O(1)
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  bool isPalindrome(int x) {
    if (x < 0 || (x % 10 == 0 && x != 0)) {
      return false;
    }
    int revertedNumber = 0;
    while (x > revertedNumber) {
      revertedNumber = revertedNumber * 10 + (x % 10);
      x ~/= 10;
    }
    return x == revertedNumber || x == revertedNumber ~/ 10;
    // Time Complexity: O(log10(n))
    // Memory Complexity: O(1)
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def isPalindrome(x: Int): Boolean = {
        if (x < 0 || (x % 10 == 0 && x != 0)) {
            false
        } else {
            var tempX = x
            var revertedNumber = 0
            while (tempX > revertedNumber) {
                revertedNumber = revertedNumber * 10 + tempX % 10
                tempX /= 10
            }
            tempX == revertedNumber || tempX == revertedNumber / 10
        }
        // Time Complexity: O(log10(n))
        // Memory Complexity: O(1)
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec is_palindrome(x :: integer) :: boolean
  def is_palindrome(x) do
    cond do
      x < 0 -> false
      x != 0 and rem(x, 10) == 0 -> false
      true -> 
        {final_x, reverted} = reverse_half(x, 0)
        final_x == reverted or final_x == div(reverted, 10)
    end
  end

  defp reverse_half(x, reverted) when x > reverted do
    reverse_half(div(x, 10), reverted * 10 + rem(x, 10))
  end
  defp reverse_half(x, reverted), do: {x, reverted}
  # Time Complexity: O(log10(n))
  # Memory Complexity: O(log10(n)) due to recursion stack
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec is_palindrome(X :: integer()) -> boolean().
is_palindrome(X) ->
  if
    X < 0 -> false;
    (X /= 0) and (X rem 10 =:= 0) -> false;
    true ->
      {FinalX, Reverted} = reverse_half(X, 0),
      (FinalX =:= Reverted) orelse (FinalX =:= Reverted div 10)
  end.

reverse_half(X, Reverted) when X > Reverted ->
  reverse_half(X div 10, Reverted * 10 + (X rem 10));
reverse_half(X, Reverted) ->
  {X, Reverted}.
% Time Complexity: O(log10(n))
% Memory Complexity: O(log10(n))

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (is-palindrome x)
  (-> exact-integer? boolean?)
  (cond
    [(or (< x 0) (and (not (zero? x)) (zero? (remainder x 10)))) #f]
    [else
     (let loop ([curr-x x] [reverted 0])
       (if (> curr-x reverted)
           (loop (quotient curr-x 10) (+ (* reverted 10) (remainder curr-x 10)))
           (or (= curr-x reverted) (= curr-x (quotient reverted 10)))))]))
; Time Complexity: O(log10(n))
; Memory Complexity: O(1) with tail-call optimization

```