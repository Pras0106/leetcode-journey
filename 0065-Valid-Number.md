# cpp

## Sweet Spot

```cpp
class Solution {
public:
    bool isNumber(string s) {
        bool seenDigit = false;
        bool seenDot = false;
        bool seenExponent = false;
        for (int i = 0; i < s.length(); ++i) {
            char c = s[i];
            if (isdigit(c)) {
                seenDigit = true;
            } else if (c == '+' || c == '-') {
                if (i > 0 && s[i - 1] != 'e' && s[i - 1] != 'E') return false;
            } else if (c == '.') {
                if (seenDot || seenExponent) return false;
                seenDot = true;
            } else if (c == 'e' || c == 'E') {
                if (seenExponent || !seenDigit) return false;
                seenExponent = true;
                seenDigit = false;
            } else {
                return false;
            }
        }
        return seenDigit;
    }
};
// Time: O(n), Memory: O(1)

```

# java

## Sweet Spot

```java
class Solution {
    public boolean isNumber(String s) {
        boolean seenDigit = false;
        boolean seenDot = false;
        boolean seenExponent = false;
        for (int i = 0; i < s.length(); i++) {
            char c = s.charAt(i);
            if (Character.isDigit(c)) {
                seenDigit = true;
            } else if (c == '+' || c == '-') {
                if (i > 0 && s.charAt(i - 1) != 'e' && s.charAt(i - 1) != 'E') return false;
            } else if (c == '.') {
                if (seenDot || seenExponent) return false;
                seenDot = true;
            } else if (c == 'e' || c == 'E') {
                if (seenExponent || !seenDigit) return false;
                seenExponent = true;
                seenDigit = false;
            } else {
                return false;
            }
        }
        return seenDigit;
    }
}
// Time: O(n), Memory: O(1)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def isNumber(self, s: str) -> bool:
        seen_digit = seen_dot = seen_exponent = False
        for i, char in enumerate(s):
            if char.isdigit():
                seen_digit = True
            elif char in "+-":
                if i > 0 and s[i-1] not in "eE":
                    return False
            elif char == ".":
                if seen_dot or seen_exponent:
                    return False
                seen_dot = True
            elif char in "eE":
                if seen_exponent or not seen_digit:
                    return False
                seen_exponent = True
                seen_digit = False
            else:
                return False
        return seen_digit
# Time: O(n), Memory: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def isNumber(self, s):
        """
        :type s: str
        :rtype: bool
        """
        seen_digit = seen_dot = seen_exponent = False
        for i in range(len(s)):
            char = s[i]
            if char.isdigit():
                seen_digit = True
            elif char in "+-":
                if i > 0 and s[i-1] not in "eE":
                    return False
            elif char == ".":
                if seen_dot or seen_exponent:
                    return False
                seen_dot = True
            elif char in "eE":
                if seen_exponent or not seen_digit:
                    return False
                seen_exponent = True
                seen_digit = False
            else:
                return False
        return seen_digit
# Time: O(n), Memory: O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {string} s
 * @return {boolean}
 */
var isNumber = function(s) {
    let seenDigit = false;
    let seenDot = false;
    let seenExponent = false;
    for (let i = 0; i < s.length; i++) {
        let char = s[i];
        if (char >= '0' && char <= '9') {
            seenDigit = true;
        } else if (char === '+' || char === '-') {
            if (i > 0 && s[i - 1] !== 'e' && s[i - 1] !== 'E') return false;
        } else if (char === '.') {
            if (seenDot || seenExponent) return false;
            seenDot = true;
        } else if (char === 'e' || char === 'E') {
            if (seenExponent || !seenDigit) return false;
            seenExponent = true;
            seenDigit = false;
        } else {
            return false;
        }
    }
    return seenDigit;
};
// Time: O(n), Memory: O(1)

```

# Typescript

## Sweet Spot

```typescript
function isNumber(s: string): boolean {
    let seenDigit = false;
    let seenDot = false;
    let seenExponent = false;
    for (let i = 0; i < s.length; i++) {
        let char = s[i];
        if (char >= '0' && char <= '9') {
            seenDigit = true;
        } else if (char === '+' || char === '-') {
            if (i > 0 && s[i - 1] !== 'e' && s[i - 1] !== 'E') return false;
        } else if (char === '.') {
            if (seenDot || seenExponent) return false;
            seenDot = true;
        } else if (char === 'e' || char === 'E') {
            if (seenExponent || !seenDigit) return false;
            seenExponent = true;
            seenDigit = false;
        } else {
            return false;
        }
    }
    return seenDigit;
};
// Time: O(n), Memory: O(1)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public bool IsNumber(string s) {
        bool seenDigit = false;
        bool seenDot = false;
        bool seenExponent = false;
        for (int i = 0; i < s.Length; i++) {
            char c = s[i];
            if (char.IsDigit(c)) {
                seenDigit = true;
            } else if (c == '+' || c == '-') {
                if (i > 0 && s[i - 1] != 'e' && s[i - 1] != 'E') return false;
            } else if (c == '.') {
                if (seenDot || seenExponent) return false;
                seenDot = true;
            } else if (c == 'e' || c == 'E') {
                if (seenExponent || !seenDigit) return false;
                seenExponent = true;
                seenDigit = false;
            } else {
                return false;
            }
        }
        return seenDigit;
    }
}
// Time: O(n), Memory: O(1)

```

# C

## Sweet Spot

```c
bool isNumber(char* s) {
    bool seenDigit = false;
    bool seenDot = false;
    bool seenExponent = false;
    int len = strlen(s);
    for (int i = 0; i < len; i++) {
        char c = s[i];
        if (c >= '0' && c <= '9') {
            seenDigit = true;
        } else if (c == '+' || c == '-') {
            if (i > 0 && s[i - 1] != 'e' && s[i - 1] != 'E') return false;
        } else if (c == '.') {
            if (seenDot || seenExponent) return false;
            seenDot = true;
        } else if (c == 'e' || c == 'E') {
            if (seenExponent || !seenDigit) return false;
            seenExponent = true;
            seenDigit = false;
        } else {
            return false;
        }
    }
    return seenDigit;
}
// Time: O(n), Memory: O(1)

```

# Go

## Sweet Spot

```go
func isNumber(s string) bool {
    seenDigit := false
    seenDot := false
    seenExponent := false
    for i := 0; i < len(s); i++ {
        c := s[i]
        if c >= '0' && c <= '9' {
            seenDigit = true
        } else if c == '+' || c == '-' {
            if i > 0 && s[i-1] != 'e' && s[i-1] != 'E' {
                return false
            }
        } else if c == '.' {
            if seenDot || seenExponent {
                return false
            }
            seenDot = true
        } else if c == 'e' || c == 'E' {
            if seenExponent || !seenDigit {
                return false
            }
            seenExponent = true
            seenDigit = false
        } else {
            return false
        }
    }
    return seenDigit
}
// Time: O(n), Memory: O(1)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun isNumber(s: String): Boolean {
        var seenDigit = false
        var seenDot = false
        var seenExponent = false
        for (i in s.indices) {
            val c = s[i]
            if (c.isDigit()) {
                seenDigit = true
            } else if (c == '+' || c == '-') {
                if (i > 0 && s[i - 1] != 'e' && s[i - 1] != 'E') return false
            } else if (c == '.') {
                if (seenDot || seenExponent) return false
                seenDot = true
            } else if (c == 'e' || c == 'E') {
                if (seenExponent || !seenDigit) return false
                seenExponent = true
                seenDigit = false
            } else {
                return false
            }
        }
        return seenDigit
    }
}
// Time: O(n), Memory: O(1)

```

# swift

## Sweet Spot

```swift
class Solution {
    func isNumber(_ s: String) -> Bool {
        var seenDigit = false
        var seenDot = false
        var seenExponent = false
        let chars = Array(s)
        for i in 0..<chars.count {
            let c = chars[i]
            if c.isNumber {
                seenDigit = true
            } else if c == "+" || c == "-" {
                if i > 0 && chars[i-1] != "e" && chars[i-1] != "E" { return false }
            } else if c == "." {
                if seenDot || seenExponent { return false }
                seenDot = true
            } else if c == "e" || c == "E" {
                if seenExponent || !seenDigit { return false }
                seenExponent = true
                seenDigit = false
            } else {
                return false
            }
        }
        return seenDigit
    }
}
// Time: O(n), Memory: O(n) due to Array conversion, but O(1) auxiliary

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn is_number(s: String) -> bool {
        let mut seen_digit = false;
        let mut seen_dot = false;
        let mut seen_exponent = false;
        let chars: Vec<char> = s.chars().collect();
        for i in 0..chars.len() {
            let c = chars[i];
            if c.is_ascii_digit() {
                seen_digit = true;
            } else if c == '+' || c == '-' {
                if i > 0 && chars[i - 1] != 'e' && chars[i - 1] != 'E' {
                    return false;
                }
            } else if c == '.' {
                if seen_dot || seen_exponent {
                    return false;
                }
                seen_dot = true;
            } else if c == 'e' || c == 'E' {
                if seen_exponent || !seen_digit {
                    return false;
                }
                seen_exponent = true;
                seen_digit = false;
            } else {
                return false;
            }
        }
        seen_digit
    }
}
// Time: O(n), Memory: O(n)

```

# ruby

## Sweet Spot

```ruby
# @param {String} s
# @return {Boolean}
def is_number(s)
    seen_digit = false
    seen_dot = false
    seen_exponent = false
    s.chars.each_with_index do |c, i|
        if c >= '0' && c <= '9'
            seen_digit = true
        elsif c == '+' || c == '-'
            return false if i > 0 && s[i-1] != 'e' && s[i-1] != 'E'
        elsif c == '.'
            return false if seen_dot || seen_exponent
            seen_dot = true
        elsif c == 'e' || c == 'E'
            return false if seen_exponent || !seen_digit
            seen_exponent = true
            seen_digit = false
        else
            return false
        end
    end
    seen_digit
end
# Time: O(n), Memory: O(n)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param String $s
     * @return Boolean
     */
    function isNumber($s) {
        $seenDigit = false;
        $seenDot = false;
        $seenExponent = false;
        $len = strlen($s);
        for ($i = 0; $i < $len; $i++) {
            $c = $s[$i];
            if (is_numeric($c)) {
                $seenDigit = true;
            } else if ($c === '+' || $c === '-') {
                if ($i > 0 && $s[$i - 1] !== 'e' && $s[$i - 1] !== 'E') return false;
            } else if ($c === '.') {
                if ($seenDot || $seenExponent) return false;
                $seenDot = true;
            } else if ($c === 'e' || $c === 'E') {
                if ($seenExponent || !$seenDigit) return false;
                $seenExponent = true;
                $seenDigit = false;
            } else {
                return false;
            }
        }
        return $seenDigit;
    }
}
// Time: O(n), Memory: O(1)

```

# dart

## Sweet Spot

```dart
class Solution {
  bool isNumber(String s) {
    bool seenDigit = false;
    bool seenDot = false;
    bool seenExponent = false;
    for (int i = 0; i < s.length; i++) {
      String c = s[i];
      if (RegExp(r'[0-9]').hasMatch(c)) {
        seenDigit = true;
      } else if (c == '+' || c == '-') {
        if (i > 0 && s[i - 1] != 'e' && s[i - 1] != 'E') return false;
      } else if (c == '.') {
        if (seenDot || seenExponent) return false;
        seenDot = true;
      } else if (c == 'e' || c == 'E') {
        if (seenExponent || !seenDigit) return false;
        seenExponent = true;
        seenDigit = false;
      } else {
        return false;
      }
    }
    return seenDigit;
  }
}
// Time: O(n), Memory: O(1)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def isNumber(s: String): Boolean = {
        var seenDigit = false
        var seenDot = false
        var seenExponent = false
        
        var i = 0
        var isValid = true
        
        while (i < s.length && isValid) {
            val c = s(i)
            if (c.isDigit) {
                seenDigit = true
            } else if (c == '+' || c == '-') {
                if (i > 0 && s(i - 1) != 'e' && s(i - 1) != 'E') isValid = false
            } else if (c == '.') {
                if (seenDot || seenExponent) isValid = false
                seenDot = true
            } else if (c == 'e' || c == 'E') {
                if (seenExponent || !seenDigit) isValid = false
                seenExponent = true
                seenDigit = false
            } else {
                isValid = false
            }
            i += 1
        }
        
        isValid && seenDigit
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)
```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec is_number(s :: String.t) :: boolean
  def is_number(s) do
    s
    |> String.to_charlist()
    |> validate(false, false, false)
  end

  defp validate([], seen_digit, _seen_dot, _seen_e), do: seen_digit

  defp validate([char | rest], seen_digit, seen_dot, seen_e) when char in ?0..?9 do
    validate(rest, true, seen_dot, seen_e)
  end

  defp validate([char | rest], seen_digit, seen_dot, seen_e) when char in [?+, ?-] do
    if seen_digit or seen_dot do
      false
    else
      validate_after_sign(rest, seen_digit, seen_dot, seen_e)
    end
  end

  defp validate([?. | rest], seen_digit, false, false) do
    validate(rest, seen_digit, true, false)
  end

  defp validate([char | rest], true, seen_dot, false) when char in [?e, ?E] do
    validate_exponent(rest, false)
  end

  defp validate(_, _, _, _), do: false

  defp validate_after_sign([?. | rest], seen_digit, false, false) do
    validate(rest, seen_digit, true, false)
  end
  defp validate_after_sign([char | rest], seen_digit, seen_dot, seen_e) when char in ?0..?9 do
    validate(rest, true, seen_dot, seen_e)
  end
  defp validate_after_sign(_, _, _, _), do: false

  defp validate_exponent([char | rest], false) when char in [?+, ?-] do
    validate_exponent_digits(rest, false)
  end
  defp validate_exponent(list, false), do: validate_exponent_digits(list, false)

  defp validate_exponent_digits([], seen_digit), do: seen_digit
  defp validate_exponent_digits([char | rest], _) when char in ?0..?9 do
    validate_exponent_digits(rest, true)
  end
  defp validate_exponent_digits(_, _), do: false
end
# Time: O(n), Memory: O(n)
```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec is_number(S :: unicode:unicode_binary()) -> boolean().
is_number(S) ->
    L = binary_to_list(S),
    case L of
        [H|T] when H == $+; H == $- -> check_mantissa(T, false, false);
        _ -> check_mantissa(L, false, false)
    end.

% Time: O(n)
% Memory: O(n)

check_mantissa([], SeenDigit, _SeenDot) ->
    SeenDigit;
check_mantissa([H|T], SeenDigit, SeenDot) when H >= $0, H =< $9 ->
    check_mantissa(T, true, SeenDot);
check_mantissa([$.|T], SeenDigit, false) ->
    check_mantissa(T, SeenDigit, true);
check_mantissa([H|T], SeenDigit, _SeenDot) when H == $e; H == $E ->
    SeenDigit andalso check_exponent(T);
check_mantissa(_, _, _) ->
    false.

check_exponent([H|T]) when H == $+; H == $- ->
    check_exp_digits(T, false);
check_exponent(L) ->
    check_exp_digits(L, false).

check_exp_digits([], SeenDigit) ->
    SeenDigit;
check_exp_digits([H|T], _) when H >= $0, H =< $9 ->
    check_exp_digits(T, true);
check_exp_digits(_, _) ->
    false.
```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (is-number s)
  (-> string? boolean?)
  (let ([chars (string->list s)])
    (let loop ([lst chars] [digit? #f] [dot? #f] [exp? #f] [prev #f])
      (if (null? lst)
          digit?
          (let ([curr (car lst)])
            (cond
              [(char-numeric? curr)
               (loop (cdr lst) #t dot? exp? curr)]
              [(or (char=? curr #\+) (char=? curr #\-))
               (if (or (not prev) (equal? prev #\e) (equal? prev #\E))
                   (loop (cdr lst) digit? dot? exp? curr)
                   #f)]
              [(char=? curr #\.)
               (if (or dot? exp?)
                   #f
                   (loop (cdr lst) digit? #t exp? curr))]
              [(or (char=? curr #\e) (char=? curr #\E))
               (if (or (not digit?) exp?)
                   #f
                   (loop (cdr lst) #f dot? #t curr))]
              [else #f]))))))
; Time: O(n)
; Memory: O(n)
```