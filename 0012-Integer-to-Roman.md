# cpp

## memory O(1) and time O(1) | Sweet Spot

```cpp
class Solution {
public:
    string intToRoman(int num) {
        // Time Complexity: O(1)
        // Memory Complexity: O(1)
        string thousands[] = {"", "M", "MM", "MMM"};
        string hundreds[] = {"", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"};
        string tens[] = {"", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"};
        string units[] = {"", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"};
        return thousands[num / 1000] + hundreds[(num % 1000) / 100] + tens[(num % 100) / 10] + units[num % 10];
    }
};

```

# java

## memory O(1) and time O(1) | Sweet Spot

```java
class Solution {
    public String intToRoman(int num) {
        // Time Complexity: O(1)
        // Memory Complexity: O(1)
        String[] thousands = {"", "M", "MM", "MMM"};
        String[] hundreds = {"", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"};
        String[] tens = {"", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"};
        String[] units = {"", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"};
        return thousands[num / 1000] + hundreds[(num % 1000) / 100] + tens[(num % 100) / 10] + units[num % 10];
    }
}

```

# python 3.14

## memory O(1) and time O(1) | Sweet Spot

```python 3.14
class Solution:
    def intToRoman(self, num: int) -> str:
        # Time Complexity: O(1)
        # Memory Complexity: O(1)
        thousands = ["", "M", "MM", "MMM"]
        hundreds = ["", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"]
        tens = ["", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"]
        units = ["", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"]
        return thousands[num // 1000] + hundreds[(num % 1000) // 100] + tens[(num % 100) // 10] + units[num % 10]

```

# python 2.7.11

## memory O(1) and time O(1) | Sweet Spot

```python 2.7.11
class Solution(object):
    def intToRoman(self, num):
        """
        :type num: int
        :rtype: str
        """
        # Time Complexity: O(1)
        # Memory Complexity: O(1)
        thousands = ["", "M", "MM", "MMM"]
        hundreds = ["", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"]
        tens = ["", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"]
        units = ["", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"]
        return thousands[num / 1000] + hundreds[(num % 1000) / 100] + tens[(num % 100) / 10] + units[num % 10]

```

# JavaScript

## memory O(1) and time O(1) | Sweet Spot

```javascript
/**
 * @param {number} num
 * @return {string}
 */
var intToRoman = function(num) {
    // Time Complexity: O(1)
    // Memory Complexity: O(1)
    const thousands = ["", "M", "MM", "MMM"];
    const hundreds = ["", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"];
    const tens = ["", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"];
    const units = ["", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"];
    return thousands[Math.floor(num / 1000)] + 
           hundreds[Math.floor((num % 1000) / 100)] + 
           tens[Math.floor((num % 100) / 10)] + 
           units[num % 10];
};

```

# Typescript

## memory O(1) and time O(1) | Sweet Spot

```typescript
function intToRoman(num: number): string {
    // Time Complexity: O(1)
    // Memory Complexity: O(1)
    const thousands: string[] = ["", "M", "MM", "MMM"];
    const hundreds: string[] = ["", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"];
    const tens: string[] = ["", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"];
    const units: string[] = ["", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"];
    return thousands[Math.floor(num / 1000)] + 
           hundreds[Math.floor((num % 1000) / 100)] + 
           tens[Math.floor((num % 100) / 10)] + 
           units[num % 10];
};

```

# C#

## memory O(1) and time O(1) | Sweet Spot

```c#
public class Solution {
    public string IntToRoman(int num) {
        // Time Complexity: O(1)
        // Memory Complexity: O(1)
        string[] thousands = {"", "M", "MM", "MMM"};
        string[] hundreds = {"", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"};
        string[] tens = {"", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"};
        string[] units = {"", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"};
        return thousands[num / 1000] + hundreds[(num % 1000) / 100] + tens[(num % 100) / 10] + units[num % 10];
    }
}

```

# C

## memory O(1) and time O(1) | Sweet Spot

```c
char* intToRoman(int num) {
    // Time Complexity: O(1)
    // Memory Complexity: O(1)
    static char result[16];
    result[0] = '\0';
    char* thousands[] = {"", "M", "MM", "MMM"};
    char* hundreds[] = {"", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"};
    char* tens[] = {"", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"};
    char* units[] = {"", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"};
    strcat(result, thousands[num / 1000]);
    strcat(result, hundreds[(num % 1000) / 100]);
    strcat(result, tens[(num % 100) / 10]);
    strcat(result, units[num % 10]);
    return result;
}

```

# Go

## memory O(1) and time O(1) | Sweet Spot

```go
func intToRoman(num int) string {
    // Time Complexity: O(1)
    // Memory Complexity: O(1)
    thousands := []string{"", "M", "MM", "MMM"}
    hundreds := []string{"", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"}
    tens := []string{"", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"}
    units := []string{"", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"}
    return thousands[num/1000] + hundreds[(num%1000)/100] + tens[(num%100)/10] + units[num%10]
}

```

# Kotlin

## memory O(1) and time O(1) | Sweet Spot

```kotlin
class Solution {
    fun intToRoman(num: Int): String {
        // Time Complexity: O(1)
        // Memory Complexity: O(1)
        val thousands = arrayOf("", "M", "MM", "MMM")
        val hundreds = arrayOf("", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM")
        val tens = arrayOf("", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC")
        val units = arrayOf("", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX")
        return thousands[num / 1000] + hundreds[(num % 1000) / 100] + tens[(num % 100) / 10] + units[num % 10]
    }
}

```

# swift

## memory O(1) and time O(1) | Sweet Spot

```swift
class Solution {
    func intToRoman(_ num: Int) -> String {
        // Time Complexity: O(1)
        // Memory Complexity: O(1)
        let thousands = ["", "M", "MM", "MMM"]
        let hundreds = ["", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"]
        let tens = ["", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"]
        let units = ["", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"]
        return thousands[num / 1000] + hundreds[(num % 1000) / 100] + tens[(num % 100) / 10] + units[num % 10]
    }
}

```

# rust

## memory O(1) and time O(1) | Sweet Spot

```rust
impl Solution {
    pub fn int_to_roman(num: i32) -> String {
        // Time Complexity: O(1)
        // Memory Complexity: O(1)
        let thousands = ["", "M", "MM", "MMM"];
        let hundreds = ["", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"];
        let tens = ["", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"];
        let units = ["", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"];
        format!("{}{}{}{}", 
            thousands[(num / 1000) as usize], 
            hundreds[((num % 1000) / 100) as usize], 
            tens[((num % 100) / 10) as usize], 
            units[(num % 10) as usize])
    }
}

```

# ruby

## memory O(1) and time O(1) | Sweet Spot

```ruby
# @param {Integer} num
# @return {String}
def int_to_roman(num)
    # Time Complexity: O(1)
    # Memory Complexity: O(1)
    thousands = ["", "M", "MM", "MMM"]
    hundreds = ["", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"]
    tens = ["", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"]
    units = ["", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"]
    thousands[num / 1000] + hundreds[(num % 1000) / 100] + tens[(num % 100) / 10] + units[num % 10]
end

```

# php

## memory O(1) and time O(1) | Sweet Spot

```php
class Solution {

    /**
     * @param Integer $num
     * @return String
     */
    function intToRoman($num) {
        // Time Complexity: O(1)
        // Memory Complexity: O(1)
        $thousands = ["", "M", "MM", "MMM"];
        $hundreds = ["", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"];
        $tens = ["", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"];
        $units = ["", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"];
        return $thousands[(int)($num / 1000)] . $hundreds[(int)(($num % 1000) / 100)] . $tens[(int)(($num % 100) / 10)] . $units[$num % 10];
    }
}

```

# dart

## memory O(1) and time O(1) | Sweet Spot

```dart
class Solution {
  String intToRoman(int num) {
    // Time Complexity: O(1)
    // Memory Complexity: O(1)
    List<String> thousands = ["", "M", "MM", "MMM"];
    List<String> hundreds = ["", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"];
    List<String> tens = ["", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"];
    List<String> units = ["", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"];
    return thousands[num ~/ 1000] + hundreds[(num % 1000) ~/ 100] + tens[(num % 100) ~/ 10] + units[num % 10];
  }
}

```

# scala 3.3.1

## memory O(1) and time O(1) | Sweet Spot

```scala 3.3.1
object Solution {
    def intToRoman(num: Int): String = {
        // Time Complexity: O(1)
        // Memory Complexity: O(1)
        val thousands = Array("", "M", "MM", "MMM")
        val hundreds = Array("", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM")
        val tens = Array("", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC")
        val units = Array("", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX")
        thousands(num / 1000) + hundreds((num % 1000) / 100) + tens((num % 100) / 10) + units(num % 10)
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## memory O(1) and time O(1) | Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec int_to_roman(num :: integer) :: String.t
  def int_to_roman(num) do
    # Time Complexity: O(1)
    # Memory Complexity: O(1)
    thousands = {"", "M", "MM", "MMM"}
    hundreds = {"", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"}
    tens = {"", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"}
    units = {"", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"}
    
    elem(thousands, div(num, 1000)) <>
    elem(hundreds, div(rem(num, 1000), 100)) <>
    elem(tens, div(rem(num, 100), 10)) <>
    elem(units, rem(num, 10))
  end
end

```

# Erlang/OTP 26

## memory O(1) and time O(1) | Sweet Spot

```erlang/otp 26
-spec int_to_roman(Num :: integer()) -> unicode:unicode_binary().
int_to_roman(Num) ->
  % Time Complexity: O(1)
  % Memory Complexity: O(1)
  Thousands = {"", "M", "MM", "MMM"},
  Hundreds = {"", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"},
  Tens = {"", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"},
  Units = {"", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"},
  T = element(Num div 1000 + 1, Thousands),
  H = element((Num rem 1000) div 100 + 1, Hundreds),
  Te = element((Num rem 100) div 10 + 1, Tens),
  U = element(Num rem 10 + 1, Units),
  list_to_binary(T ++ H ++ Te ++ U).

```

# Racket CS v8.15

## memory O(1) and time O(1) | Sweet Spot

```racket CS v8.15
(define/contract (int-to-roman num)
  (-> exact-integer? string?)
  ; Time Complexity: O(1)
  ; Memory Complexity: O(1)
  (let ([thousands #("" "M" "MM" "MMM")]
        [hundreds #("" "C" "CC" "CCC" "CD" "D" "DC" "DCC" "DCCC" "CM")]
        [tens #("" "X" "XX" "XXX" "XL" "L" "LX" "LXX" "LXXX" "XC")]
        [units #("" "I" "II" "III" "IV" "V" "VI" "VII" "VIII" "IX")])
    (string-append
     (vector-ref thousands (quotient num 1000))
     (vector-ref hundreds (quotient (remainder num 1000) 100))
     (vector-ref tens (quotient (remainder num 100) 10))
     (vector-ref units (remainder num 10)))))

```