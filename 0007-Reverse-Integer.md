# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int reverse(int x) {
        int rev = 0;
        while (x != 0) {
            int pop = x % 10;
            x /= 10;
            if (rev > 2147483647 / 10 || (rev == 2147483647 / 10 && pop > 7)) return 0;
            if (rev < -2147483648 / 10 || (rev == -2147483648 / 10 && pop < -8)) return 0;
            rev = rev * 10 + pop;
        }
        return rev;
    }
};
// Time Complexity: O(log(x))
// Memory Complexity: O(1)

```

# java

## Sweet Spot

```java
class Solution {
    public int reverse(int x) {
        int rev = 0;
        while (x != 0) {
            int pop = x % 10;
            x /= 10;
            if (rev > Integer.MAX_VALUE / 10 || (rev == Integer.MAX_VALUE / 10 && pop > 7)) return 0;
            if (rev < Integer.MIN_VALUE / 10 || (rev == Integer.MIN_VALUE / 10 && pop < -8)) return 0;
            rev = rev * 10 + pop;
        }
        return rev;
    }
}
// Time Complexity: O(log(x))
// Memory Complexity: O(1)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def reverse(self, x: int) -> int:
        res = 0
        sign = 1 if x >= 0 else -1
        x = abs(x)
        while x:
            res = res * 10 + x % 10
            x //= 10
        res *= sign
        if res < -2**31 or res > 2**31 - 1:
            return 0
        return res
# Time Complexity: O(log(x))
# Memory Complexity: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def reverse(self, x):
        """
        :type x: int
        :rtype: int
        """
        res = 0
        sign = 1 if x >= 0 else -1
        x = abs(x)
        while x != 0:
            res = res * 10 + x % 10
            x /= 10
        res *= sign
        if res < -2147483648 or res > 2147483647:
            return 0
        return res
# Time Complexity: O(log(x))
# Memory Complexity: O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number} x
 * @return {number}
 */
var reverse = function(x) {
    let rev = 0;
    while (x !== 0) {
        const pop = x % 10;
        x = (x / 10) | 0;
        if (rev > 214748364 || (rev === 214748364 && pop > 7)) return 0;
        if (rev < -214748364 || (rev === -214748364 && pop < -8)) return 0;
        rev = rev * 10 + pop;
    }
    return rev;
};
// Time Complexity: O(log(x))
// Memory Complexity: O(1)

```

# Typescript

## Sweet Spot

```typescript
function reverse(x: number): number {
    let rev = 0;
    while (x !== 0) {
        const pop = x % 10;
        x = (x / 10) | 0;
        if (rev > 214748364 || (rev === 214748364 && pop > 7)) return 0;
        if (rev < -214748364 || (rev === -214748364 && pop < -8)) return 0;
        rev = rev * 10 + pop;
    }
    return rev;
};
// Time Complexity: O(log(x))
// Memory Complexity: O(1)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int Reverse(int x) {
        int rev = 0;
        while (x != 0) {
            int pop = x % 10;
            x /= 10;
            if (rev > int.MaxValue / 10 || (rev == int.MaxValue / 10 && pop > 7)) return 0;
            if (rev < int.MinValue / 10 || (rev == int.MinValue / 10 && pop < -8)) return 0;
            rev = rev * 10 + pop;
        }
        return rev;
    }
}
// Time Complexity: O(log(x))
// Memory Complexity: O(1)

```

# C

## Sweet Spot

```c
int reverse(int x){
    int rev = 0;
    while (x != 0) {
        int pop = x % 10;
        x /= 10;
        if (rev > 2147483647 / 10 || (rev == 2147483647 / 10 && pop > 7)) return 0;
        if (rev < -2147483648 / 10 || (rev == -2147483648 / 10 && pop < -8)) return 0;
        rev = rev * 10 + pop;
    }
    return rev;
}
// Time Complexity: O(log(x))
// Memory Complexity: O(1)

```

# Go

## Sweet Spot

```go
func reverse(x int) int {
    rev := 0
    for x != 0 {
        pop := x % 10
        x /= 10
        if rev > 2147483647/10 || (rev == 2147483647/10 && pop > 7) {
            return 0
        }
        if rev < -2147483648/10 || (rev == -2147483648/10 && pop < -8) {
            return 0
        }
        rev = rev*10 + pop
    }
    return rev
}
// Time Complexity: O(log(x))
// Memory Complexity: O(1)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun reverse(x: Int): Int {
        var num = x
        var rev = 0
        while (num != 0) {
            val pop = num % 10
            num /= 10
            if (rev > Int.MAX_VALUE / 10 || (rev == Int.MAX_VALUE / 10 && pop > 7)) return 0
            if (rev < Int.MIN_VALUE / 10 || (rev == Int.MIN_VALUE / 10 && pop < -8)) return 0
            rev = rev * 10 + pop
        }
        return rev
    }
}
// Time Complexity: O(log(x))
// Memory Complexity: O(1)

```

# swift

## Sweet Spot

```swift
class Solution {
    func reverse(_ x: Int) -> Int {
        var num = x
        var rev = 0
        while num != 0 {
            let pop = num % 10
            num /= 10
            if rev > Int32.max / 10 || (rev == Int32.max / 10 && pop > 7) { return 0 }
            if rev < Int32.min / 10 || (rev == Int32.min / 10 && pop < -8) { return 0 }
            rev = rev * 10 + pop
        }
        return rev
    }
}
// Time Complexity: O(log(x))
// Memory Complexity: O(1)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn reverse(x: i32) -> i32 {
        let mut num = x;
        let mut rev: i32 = 0;
        while num != 0 {
            let pop = num % 10;
            num /= 10;
            if let Some(new_rev) = rev.checked_mul(10).and_then(|r| r.checked_add(pop)) {
                rev = new_rev;
            } else {
                return 0;
            }
        }
        rev
    }
}
// Time Complexity: O(log(x))
// Memory Complexity: O(1)

```

# ruby

## Sweet Spot

```ruby
# @param {Integer} x
# @return {Integer}
def reverse(x)
    sign = x < 0 ? -1 : 1
    res = x.abs.to_s.reverse.to_i * sign
    return 0 if res < -2147483648 || res > 2147483647
    res
end
# Time Complexity: O(log(x))
# Memory Complexity: O(log(x))

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer $x
     * @return Integer
     */
    function reverse($x) {
        $rev = 0;
        while ($x != 0) {
            $pop = $x % 10;
            $x = (int)($x / 10);
            if ($rev > 214748364 || ($rev == 214748364 && $pop > 7)) return 0;
            if ($rev < -214748364 || ($rev == -214748364 && $pop < -8)) return 0;
            $rev = $rev * 10 + $pop;
        }
        return $rev;
    }
}
// Time Complexity: O(log(x))
// Memory Complexity: O(1)

```

# dart

## Sweet Spot

```dart
class Solution {
  int reverse(int x) {
    int rev = 0;
    while (x != 0) {
      int pop = x % 10;
      x = x ~/ 10;
      if (rev > 214748364 || (rev == 214748364 && pop > 7)) return 0;
      if (rev < -214748364 || (rev == -214748364 && pop < -8)) return 0;
      rev = rev * 10 + pop;
    }
    return rev;
  }
}
// Time Complexity: O(log(x))
// Memory Complexity: O(1)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def reverse(x: Int): Int = {
        var rev = 0
        var temp = x
        while (temp != 0) {
            val pop = temp % 10
            temp /= 10
            if (rev > Int.MaxValue / 10 || (rev == Int.MaxValue / 10 && pop > 7)) return 0
            if (rev < Int.MinValue / 10 || (rev == Int.MinValue / 10 && pop < -8)) return 0
            rev = rev * 10 + pop
        }
        rev
    }
}
// Time Complexity: O(log(x))
// Memory Complexity: O(1)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec reverse(x :: integer) :: integer
  def reverse(x) do
    sign = if x < 0, do: -1, else: 1
    rev = x |> abs() |> Integer.to_string() |> String.reverse() |> String.to_integer()
    res = rev * sign
    if res < -2147483648 or res > 2147483647, do: 0, else: res
  end
end
# Time Complexity: O(log(x))
# Memory Complexity: O(log(x))

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec reverse(X :: integer()) -> integer().
reverse(X) ->
  Sign = if X < 0 -> -1; true -> 1 end,
  AbsX = abs(X),
  Rev = list_to_integer(lists:reverse(integer_to_list(AbsX))),
  Res = Rev * Sign,
  if Res < -2147483648 -> 0;
     Res > 2147483647 -> 0;
     true -> Res
  end.
% Time Complexity: O(log(x))
% Memory Complexity: O(log(x))

```