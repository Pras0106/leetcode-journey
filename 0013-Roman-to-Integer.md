# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int romanToInt(string s) {
        int total = 0;
        int prevValue = 0;
        for (int i = s.length() - 1; i >= 0; i--) {
            int current = 0;
            switch (s[i]) {
                case 'I': current = 1; break;
                case 'V': current = 5; break;
                case 'X': current = 10; break;
                case 'L': current = 50; break;
                case 'C': current = 100; break;
                case 'D': current = 500; break;
                case 'M': current = 1000; break;
            }
            if (current < prevValue) {
                total -= current;
            } else {
                total += current;
            }
            prevValue = current;
        }
        return total;
    }
};
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# java

## Sweet Spot

```java
class Solution {
    public int romanToInt(String s) {
        int total = 0;
        int prevValue = 0;
        for (int i = s.length() - 1; i >= 0; i--) {
            int current = 0;
            switch (s.charAt(i)) {
                case 'I': current = 1; break;
                case 'V': current = 5; break;
                case 'X': current = 10; break;
                case 'L': current = 50; break;
                case 'C': current = 100; break;
                case 'D': current = 500; break;
                case 'M': current = 1000; break;
            }
            if (current < prevValue) {
                total -= current;
            } else {
                total += current;
            }
            prevValue = current;
        }
        return total;
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def romanToInt(self, s: str) -> int:
        roman = {'I': 1, 'V': 5, 'X': 10, 'L': 50, 'C': 100, 'D': 500, 'M': 1000}
        total = 0
        prev_value = 0
        for char in reversed(s):
            curr_value = roman[char]
            if curr_value < prev_value:
                total -= curr_value
            else:
                total += curr_value
            prev_value = curr_value
        return total
# Time Complexity: O(n)
# Memory Complexity: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def romanToInt(self, s):
        """
        :type s: str
        :rtype: int
        """
        roman = {'I': 1, 'V': 5, 'X': 10, 'L': 50, 'C': 100, 'D': 500, 'M': 1000}
        total = 0
        prev_value = 0
        for i in range(len(s) - 1, -1, -1):
            curr_value = roman[s[i]]
            if curr_value < prev_value:
                total -= curr_value
            else:
                total += curr_value
            prev_value = curr_value
        return total
# Time Complexity: O(n)
# Memory Complexity: O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {string} s
 * @return {number}
 */
var romanToInt = function(s) {
    const roman = {
        'I': 1, 'V': 5, 'X': 10, 'L': 50, 'C': 100, 'D': 500, 'M': 1000
    };
    let total = 0;
    let prevValue = 0;
    for (let i = s.length - 1; i >= 0; i--) {
        let currValue = roman[s[i]];
        if (currValue < prevValue) {
            total -= currValue;
        } else {
            total += currValue;
        }
        prevValue = currValue;
    }
    return total;
};
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# Typescript

## Sweet Spot

```typescript
function romanToInt(s: string): number {
    const roman: { [key: string]: number } = {
        'I': 1, 'V': 5, 'X': 10, 'L': 50, 'C': 100, 'D': 500, 'M': 1000
    };
    let total = 0;
    let prevValue = 0;
    for (let i = s.length - 1; i >= 0; i--) {
        const currValue = roman[s[i]];
        if (currValue < prevValue) {
            total -= currValue;
        } else {
            total += currValue;
        }
        prevValue = currValue;
    }
    return total;
};
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int RomanToInt(string s) {
        int total = 0;
        int prevValue = 0;
        for (int i = s.Length - 1; i >= 0; i--) {
            int current = s[i] switch {
                'I' => 1,
                'V' => 5,
                'X' => 10,
                'L' => 50,
                'C' => 100,
                'D' => 500,
                'M' => 1000,
                _ => 0
            };
            if (current < prevValue) {
                total -= current;
            } else {
                total += current;
            }
            prevValue = current;
        }
        return total;
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# C

## Sweet Spot

```c
int romanToInt(char* s) {
    int total = 0;
    int prevValue = 0;
    int n = strlen(s);
    for (int i = n - 1; i >= 0; i--) {
        int current = 0;
        switch (s[i]) {
            case 'I': current = 1; break;
            case 'V': current = 5; break;
            case 'X': current = 10; break;
            case 'L': current = 50; break;
            case 'C': current = 100; break;
            case 'D': current = 500; break;
            case 'M': current = 1000; break;
        }
        if (current < prevValue) {
            total -= current;
        } else {
            total += current;
        }
        prevValue = current;
    }
    return total;
}
/* Time Complexity: O(n) */
/* Memory Complexity: O(1) */

```

# Go

## Sweet Spot

```go
func romanToInt(s string) int {
    roman := map[byte]int{
        'I': 1, 'V': 5, 'X': 10, 'L': 50, 'C': 100, 'D': 500, 'M': 1000,
    }
    total := 0
    prevValue := 0
    for i := len(s) - 1; i >= 0; i-- {
        currValue := roman[s[i]]
        if currValue < prevValue {
            total -= currValue
        } else {
            total += currValue
        }
        prevValue = currValue
    }
    return total
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun romanToInt(s: String): Int {
        val roman = mapOf('I' to 1, 'V' to 5, 'X' to 10, 'L' to 50, 'C' to 100, 'D' to 500, 'M' to 1000)
        var total = 0
        var prevValue = 0
        for (i in s.length - 1 downTo 0) {
            val currValue = roman[s[i]] ?: 0
            if (currValue < prevValue) {
                total -= currValue
            } else {
                total += currValue
            }
            prevValue = currValue
        }
        return total
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# swift

## Sweet Spot

```swift
class Solution {
    func romanToInt(_ s: String) -> Int {
        let roman: [Character: Int] = ["I": 1, "V": 5, "X": 10, "L": 50, "C": 100, "D": 500, "M": 1000]
        var total = 0
        var prevValue = 0
        let chars = Array(s)
        for i in (0..<chars.count).reversed() {
            let currValue = roman[chars[i]] ?? 0
            if currValue < prevValue {
                total -= currValue
            } else {
                total += currValue
            }
            prevValue = currValue
        }
        return total
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(n) due to Array(s) for fast indexing

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn roman_to_int(s: String) -> i32 {
        let mut total = 0;
        let mut prev_value = 0;
        for c in s.chars().rev() {
            let curr_value = match c {
                'I' => 1,
                'V' => 5,
                'X' => 10,
                'L' => 50,
                'C' => 100,
                'D' => 500,
                'M' => 1000,
                _ => 0,
            };
            if curr_value < prev_value {
                total -= curr_value;
            } else {
                total += curr_value;
            }
            prev_value = curr_value;
        }
        total
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# ruby

## Sweet Spot

```ruby
# @param {String} s
# @return {Integer}
def roman_to_int(s)
    roman = { 'I' => 1, 'V' => 5, 'X' => 10, 'L' => 50, 'C' => 100, 'D' => 500, 'M' => 1000 }
    total = 0
    prev_value = 0
    s.reverse.each_char do |char|
        curr_value = roman[char]
        if curr_value < prev_value
            total -= curr_value
        else
            total += curr_value
        end
        prev_value = curr_value
    end
    total
end
# Time Complexity: O(n)
# Memory Complexity: O(1)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param String $s
     * @return Integer
     */
    function romanToInt($s) {
        $roman = [
            'I' => 1,
            'V' => 5,
            'X' => 10,
            'L' => 50,
            'C' => 100,
            'D' => 500,
            'M' => 1000
        ];
        
        $total = 0;
        $prevValue = 0;
        $length = strlen($s);

        for ($i = $length - 1; $i >= 0; $i--) {
            $currValue = $roman[$s[$i]];
            
            if ($currValue < $prevValue) {
                $total -= $currValue;
            } else {
                $total += $currValue;
            }
            
            $prevValue = $currValue;
        }

        return $total;
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)
```

# dart

## Sweet Spot

```dart
class Solution {
  int romanToInt(String s) {
    Map<String, int> roman = {
      'I': 1, 'V': 5, 'X': 10, 'L': 50, 'C': 100, 'D': 500, 'M': 1000
    };
    int total = 0;
    int prevValue = 0;
    for (int i = s.length - 1; i >= 0; i--) {
      int currValue = roman[s[i]]!;
      if (currValue < prevValue) {
        total -= currValue;
      } else {
        total += currValue;
      }
      prevValue = currValue;
    }
    return total;
  }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def romanToInt(s: String): Int = {
        val roman = Map('I' -> 1, 'V' -> 5, 'X' -> 10, 'L' -> 50, 'C' -> 100, 'D' -> 500, 'M' -> 1000)
        var total = 0
        var prevValue = 0
        for (i <- s.length - 1 to 0 by -1) {
            val currValue = roman(s(i))
            if (currValue < prevValue) {
                total -= currValue
            } else {
                total += currValue
            }
            prevValue = currValue
        }
        total
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec roman_to_int(s :: String.t) :: integer
  def roman_to_int(s) do
    roman = %{"I" => 1, "V" => 5, "X" => 10, "L" => 50, "C" => 100, "D" => 500, "M" => 1000}
    s
    |> String.graphemes()
    |> Enum.reverse()
    |> Enum.reduce({0, 0}, fn char, {total, prev} ->
      curr = Map.get(roman, char)
      if curr < prev do
        {total - curr, curr}
      else
        {total + curr, curr}
      end
    end)
    |> elem(0)
  end
end
# Time Complexity: O(n)
# Memory Complexity: O(n)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec roman_to_int(S :: unicode:unicode_binary()) -> integer().
roman_to_int(S) ->
    Roman = fun(73) -> 1; (86) -> 5; (88) -> 10; (76) -> 50; (67) -> 100; (68) -> 500; (77) -> 1000 end,
    Chars = lists:reverse(binary_to_list(S)),
    {Total, _} = lists:foldl(fun(C, {Acc, Prev}) ->
        Curr = Roman(C),
        if Curr < Prev -> {Acc - Curr, Curr};
           true -> {Acc + Curr, Curr}
        end
    end, {0, 0}, Chars),
    Total.
% Time Complexity: O(n)
% Memory Complexity: O(n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (roman-to-int s)
  (-> string? exact-integer?)
  (let ([roman (hash #\I 1 #\V 5 #\X 10 #\L 50 #\C 100 #\D 500 #\M 1000)]
        [chars (reverse (string->list s))])
    (for/fold ([total 0]
               [prev 0]
               #:result total)
              ([c chars])
      (let ([curr (hash-ref roman c)])
        (if (< curr prev)
            (values (- total curr) curr)
            (values (+ total curr) curr))))))
; Time Complexity: O(n)
; Memory Complexity: O(n)

```