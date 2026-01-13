# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int myAtoi(string s) {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        int i = 0, n = s.length();
        while (i < n && s[i] == ' ') i++;
        if (i == n) return 0;
        int sign = 1;
        if (s[i] == '+' || s[i] == '-') {
            if (s[i] == '-') sign = -1;
            i++;
        }
        long result = 0;
        while (i < n && isdigit(s[i])) {
            result = result * 10 + (s[i] - '0');
            if (sign == 1 && result > INT_MAX) return INT_MAX;
            if (sign == -1 && -result < INT_MIN) return INT_MIN;
            i++;
        }
        return (int)(result * sign);
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public int myAtoi(String s) {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        if (s == null || s.length() == 0) return 0;
        int i = 0, n = s.length();
        while (i < n && s.charAt(i) == ' ') i++;
        if (i == n) return 0;
        int sign = 1;
        if (s.charAt(i) == '+' || s.charAt(i) == '-') {
            sign = (s.charAt(i) == '-') ? -1 : 1;
            i++;
        }
        long res = 0;
        while (i < n && Character.isDigit(s.charAt(i))) {
            res = res * 10 + (s.charAt(i) - '0');
            if (sign == 1 && res > Integer.MAX_VALUE) return Integer.MAX_VALUE;
            if (sign == -1 && -res < Integer.MIN_VALUE) return Integer.MIN_VALUE;
            i++;
        }
        return (int)(res * sign);
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def myAtoi(self, s: str) -> int:
        # Time Complexity: O(n)
        # Memory Complexity: O(1)
        s = s.lstrip()
        if not s:
            return 0
        sign = 1
        if s[0] == '-':
            sign = -1
            s = s[1:]
        elif s[0] == '+':
            s = s[1:]
        res = 0
        for char in s:
            if char.isdigit():
                res = res * 10 + int(char)
            else:
                break
        res *= sign
        if res > 2147483647:
            return 2147483647
        if res < -2147483648:
            return -2147483648
        return res

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def myAtoi(self, s):
        """
        :type s: str
        :rtype: int
        """
        # Time Complexity: O(n)
        # Memory Complexity: O(1)
        s = s.lstrip()
        if not s:
            return 0
        sign = 1
        if s[0] == '-':
            sign = -1
            s = s[1:]
        elif s[0] == '+':
            s = s[1:]
        res = 0
        for char in s:
            if char.isdigit():
                res = res * 10 + int(char)
            else:
                break
        res *= sign
        if res > 2147483647:
            return 2147483647
        if res < -2147483648:
            return -2147483648
        return res

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {string} s
 * @return {number}
 */
var myAtoi = function(s) {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    let i = 0;
    while (i < s.length && s[i] === ' ') i++;
    if (i === s.length) return 0;
    let sign = 1;
    if (s[i] === '-' || s[i] === '+') {
        sign = s[i] === '-' ? -1 : 1;
        i++;
    }
    let res = 0;
    const INT_MAX = 2147483647;
    const INT_MIN = -2147483648;
    while (i < s.length && s[i] >= '0' && s[i] <= '9') {
        res = res * 10 + (s[i] - '0');
        if (sign === 1 && res > INT_MAX) return INT_MAX;
        if (sign === -1 && -res < INT_MIN) return INT_MIN;
        i++;
    }
    return res * sign;
};

```

# Typescript

## Sweet Spot

```typescript
function myAtoi(s: string): number {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    let i = 0;
    const n = s.length;
    while (i < n && s[i] === ' ') i++;
    if (i === n) return 0;
    let sign = 1;
    if (s[i] === '-' || s[i] === '+') {
        sign = s[i] === '-' ? -1 : 1;
        i++;
    }
    let res = 0;
    const INT_MAX = 2147483647;
    const INT_MIN = -2147483648;
    while (i < n && s[i] >= '0' && s[i] <= '9') {
        res = res * 10 + (Number(s[i]));
        if (sign === 1 && res > INT_MAX) return INT_MAX;
        if (sign === -1 && -res < INT_MIN) return INT_MIN;
        i++;
    }
    return res * sign;
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int MyAtoi(string s) {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        if (string.IsNullOrEmpty(s)) return 0;
        int i = 0, n = s.Length;
        while (i < n && s[i] == ' ') i++;
        if (i == n) return 0;
        int sign = 1;
        if (s[i] == '+' || s[i] == '-') {
            sign = (s[i] == '-') ? -1 : 1;
            i++;
        }
        long res = 0;
        while (i < n && char.IsDigit(s[i])) {
            res = res * 10 + (s[i] - '0');
            if (sign == 1 && res > int.MaxValue) return int.MaxValue;
            if (sign == -1 && -res < int.MinValue) return int.MinValue;
            i++;
        }
        return (int)(res * sign);
    }
}

```

# C

## Sweet Spot

```c
#include <limits.h>
#include <ctype.h>

int myAtoi(char* s) {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    int i = 0;
    while (s[i] == ' ') i++;
    int sign = 1;
    if (s[i] == '+' || s[i] == '-') {
        if (s[i] == '-') sign = -1;
        i++;
    }
    long result = 0;
    while (isdigit(s[i])) {
        result = result * 10 + (s[i] - '0');
        if (sign == 1 && result > INT_MAX) return INT_MAX;
        if (sign == -1 && -result < INT_MIN) return INT_MIN;
        i++;
    }
    return (int)(result * sign);
}

```

# Go

## Sweet Spot

```go
import "math"

func myAtoi(s string) int {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    i, n := 0, len(s)
    for i < n && s[i] == ' ' {
        i++
    }
    if i == n {
        return 0
    }
    sign := 1
    if s[i] == '-' {
        sign = -1
        i++
    } else if s[i] == '+' {
        i++
    }
    res := 0
    for i < n && s[i] >= '0' && s[i] <= '9' {
        digit := int(s[i] - '0')
        if res > (math.MaxInt32-digit)/10 {
            if sign == 1 {
                return math.MaxInt32
            }
            return math.MinInt32
        }
        res = res*10 + digit
        i++
    }
    return res * sign
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun myAtoi(s: String): Int {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        var i = 0
        val n = s.length
        while (i < n && s[i] == ' ') i++
        if (i == n) return 0
        var sign = 1
        if (s[i] == '-' || s[i] == '+') {
            if (s[i] == '-') sign = -1
            i++
        }
        var res = 0L
        while (i < n && s[i].isDigit()) {
            res = res * 10 + (s[i] - '0')
            if (sign == 1 && res > Int.MAX_VALUE) return Int.MAX_VALUE
            if (sign == -1 && -res < Int.MIN_VALUE) return Int.MIN_VALUE
            i++
        }
        return (res * sign).toInt()
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func myAtoi(_ s: String) -> Int {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        let chars = Array(s)
        var i = 0
        let n = chars.count
        while i < n && chars[i] == " " { i += 1 }
        if i == n { return 0 }
        var sign = 1
        if chars[i] == "-" {
            sign = -1
            i += 1
        } else if chars[i] == "+" {
            i += 1
        }
        var res: Int64 = 0
        while i < n, let digit = Int64(String(chars[i])) {
            res = res * 10 + digit
            if sign == 1 && res > Int32.max { return Int(Int32.max) }
            if sign == -1 && -res < Int32.min { return Int(Int32.min) }
            i += 1
        }
        return Int(res) * sign
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn my_atoi(s: String) -> i32 {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        let s = s.trim_start();
        if s.is_empty() { return 0; }
        let mut chars = s.chars().peekable();
        let sign = match chars.peek() {
            Some(&'-') => { chars.next(); -1 },
            Some(&'+') => { chars.next(); 1 },
            _ => 1,
        };
        let mut res: i64 = 0;
        for c in chars {
            if let Some(digit) = c.to_digit(10) {
                res = res * 10 + digit as i64;
                if sign == 1 && res > i32::MAX as i64 { return i32::MAX; }
                if sign == -1 && -res < i32::MIN as i64 { return i32::MIN; }
            } else {
                break;
            }
        }
        (res * sign as i64) as i32
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {String} s
# @return {Integer}
def my_atoi(s)
    # Time Complexity: O(n)
    # Memory Complexity: O(1)
    s = s.lstrip
    return 0 if s.empty?
    sign = 1
    if s[0] == '-'
        sign = -1
        s = s[1..-1]
    elsif s[0] == '+'
        s = s[1..-1]
    end
    res = 0
    s.each_char do |c|
        if c =~ /[0-9]/
            res = res * 10 + c.to_i
            if sign == 1 && res > 2147483647
                return 2147483647
            elsif sign == -1 && -res < -2147483648
                return -2147483648
            end
        else
            break
        end
    end
    res * sign
end

```

# php

## Sweet Spot

```php
class Solution {
    /**
     * @param String $s
     * @return Integer
     */
    function myAtoi($s) {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        $s = ltrim($s);
        if ($s === "") return 0;
        $sign = 1;
        $i = 0;
        if ($s[0] === '-') {
            $sign = -1;
            $i = 1;
        } elseif ($s[0] === '+') {
            $i = 1;
        }
        $res = 0;
        $max = 2147483647;
        $min = -2147483648;
        for (; $i < strlen($s); $i++) {
            if (is_numeric($s[$i])) {
                $res = $res * 10 + intval($s[$i]);
                if ($sign === 1 && $res > $max) return $max;
                if ($sign === -1 && -$res < $min) return $min;
            } else {
                break;
            }
        }
        return $res * $sign;
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  int myAtoi(String s) {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    s = s.trimLeft();
    if (s.isEmpty) return 0;
    int sign = 1;
    int i = 0;
    if (s[0] == '-') {
      sign = -1;
      i = 1;
    } else if (s[0] == '+') {
      i = 1;
    }
    int res = 0;
    int maxInt = 2147483647;
    int minInt = -2147483648;
    while (i < s.length && RegExp(r'[0-9]').hasMatch(s[i])) {
      res = res * 10 + int.parse(s[i]);
      if (sign == 1 && res > maxInt) return maxInt;
      if (sign == -1 && -res < minInt) return minInt;
      i++;
    }
    return res * sign;
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def myAtoi(s: String): Int = {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        val trimmed = s.trim
        if (trimmed.isEmpty) return 0
        var sign = 1
        var i = 0
        if (trimmed(0) == '-') {
            sign = -1
            i = 1
        } else if (trimmed(0) == '+') {
            i = 1
        }
        var res: Long = 0
        val maxInt = Int.MaxValue
        val minInt = Int.MinValue
        while (i < trimmed.length && trimmed(i).isDigit) {
            res = res * 10 + (trimmed(i) - '0')
            if (sign == 1 && res > maxInt) return maxInt
            if (sign == -1 && -res < minInt) return minInt
            i += 1
        }
        (res * sign).toInt
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec my_atoi(s :: String.t) :: integer
  def my_atoi(s) do
    # Time Complexity: O(n)
    # Space Complexity: O(n)
    s
    |> String.trim_leading()
    |> parse_sign()
    |> process_conversion()
  end

  defp parse_sign("-" <> rest), do: {-1, rest}
  defp parse_sign("+" <> rest), do: {1, rest}
  defp parse_sign(rest), do: {1, rest}

  defp process_conversion({sign, rest}) do
    digits = extract_digits(rest, [])
    
    case digits do
      [] -> 0
      _ ->
        num = Enum.reduce(digits, 0, fn d, acc -> 
          new_val = acc * 10 + d
          if new_val > 2147483648, do: 2147483648, else: new_val
        end)
        
        clamp(sign * num)
    end
  end

  defp extract_digits(<<char, rest::binary>>, acc) when char in ?0..?9 do
    extract_digits(rest, acc ++ [char - ?0])
  end
  defp extract_digits(_, acc), do: acc

  defp clamp(n) do
    cond do
      n > 2147483647 -> 2147483647
      n < -2147483648 -> -2147483648
      true -> n
    end
  end
end
```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec my_atoi(S :: unicode:unicode_binary()) -> integer().
my_atoi(S) ->
  % Time Complexity: O(n)
  % Memory Complexity: O(n)
  Trimmed = string:trim(S, leading),
  {Sign, Rest} = case Trimmed of
    <<"-", R/binary>> -> {-1, R};
    <<"+", R/binary>> -> {1, R};
    _ -> {1, Trimmed}
  end,
  Val = parse_digits(Rest, 0),
  SignedVal = Sign * Val,
  if
    SignedVal > 2147483647 -> 2147483647;
    SignedVal < -2147483648 -> -2147483648;
    true -> SignedVal
  end.

parse_digits(<<C, Rest/binary>>, Acc) when C >= $0, C =< $9 ->
  NewAcc = Acc * 10 + (C - $0),
  if NewAcc > 2147483648 -> NewAcc;
     true -> parse_digits(Rest, NewAcc)
  end;
parse_digits(_, Acc) -> Acc.

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (my-atoi s)
  (-> string? exact-integer?)
  ; Time Complexity: O(n)
  ; Memory Complexity: O(n)
  (let* ([trimmed (string-trim s #:left? #t #:right? #f)]
         [n (string-length trimmed)])
    (if (zero? n)
        0
        (let-values ([(sign start) 
                      (cond [(char=? (string-ref trimmed 0) #\-) (values -1 1)]
                            [(char=? (string-ref trimmed 0) #\+) (values 1 1)]
                            [else (values 1 0)])])
          (let loop ([i start] [acc 0])
            (if (or (>= i n) (not (char-numeric? (string-ref trimmed i))))
                (let ([res (* sign acc)])
                  (cond [(> res 2147483647) 2147483647]
                        [(< res -2147483648) -2147483648]
                        [else res]))
                (let ([new-acc (+ (* acc 10) (- (char->integer (string-ref trimmed i)) (char->integer #\0)))])
                  (if (> new-acc 2147483648)
                      (loop n new-acc)
                      (loop (+ i 1) new-acc)))))))))

```