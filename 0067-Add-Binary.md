# cpp

## Sweet Spot

```cpp
class Solution {
public:
    string addBinary(string a, string b) {
        // Time Complexity: O(max(N, M))
        // Memory Complexity: O(max(N, M))
        string result = "";
        int i = a.length() - 1;
        int j = b.length() - 1;
        int carry = 0;
        while (i >= 0 || j >= 0 || carry) {
            int sum = carry;
            if (i >= 0) sum += a[i--] - '0';
            if (j >= 0) sum += b[j--] - '0';
            result += (sum % 2) + '0';
            carry = sum / 2;
        }
        reverse(result.begin(), result.end());
        return result;
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public String addBinary(String a, String b) {
        // Time Complexity: O(max(N, M))
        // Memory Complexity: O(max(N, M))
        StringBuilder sb = new StringBuilder();
        int i = a.length() - 1, j = b.length() - 1, carry = 0;
        while (i >= 0 || j >= 0 || carry > 0) {
            int sum = carry;
            if (i >= 0) sum += a.charAt(i--) - '0';
            if (j >= 0) sum += b.charAt(j--) - '0';
            sb.append(sum % 2);
            carry = sum / 2;
        }
        return sb.reverse().toString();
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def addBinary(self, a: str, b: str) -> str:
        # Time Complexity: O(max(N, M))
        # Memory Complexity: O(max(N, M))
        return bin(int(a, 2) + int(b, 2))[2:]

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def addBinary(self, a, b):
        """
        :type a: str
        :type b: str
        :rtype: str
        """
        # Time Complexity: O(max(N, M))
        # Memory Complexity: O(max(N, M))
        return bin(int(a, 2) + int(b, 2))[2:]

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {string} a
 * @param {string} b
 * @return {string}
 */
var addBinary = function(a, b) {
    // Time Complexity: O(max(N, M))
    // Memory Complexity: O(max(N, M))
    let res = "";
    let i = a.length - 1;
    let j = b.length - 1;
    let carry = 0;
    while (i >= 0 || j >= 0 || carry) {
        let sum = carry + (i >= 0 ? Number(a[i--]) : 0) + (j >= 0 ? Number(b[j--]) : 0);
        res = (sum % 2) + res;
        carry = Math.floor(sum / 2);
    }
    return res;
};

```

# Typescript

## Sweet Spot

```typescript
function addBinary(a: string, b: string): string {
    // Time Complexity: O(max(N, M))
    // Memory Complexity: O(max(N, M))
    let result = "";
    let i = a.length - 1;
    let j = b.length - 1;
    let carry = 0;
    while (i >= 0 || j >= 0 || carry) {
        let sum = carry;
        if (i >= 0) sum += parseInt(a[i--]);
        if (j >= 0) sum += parseInt(b[j--]);
        result = (sum % 2).toString() + result;
        carry = Math.floor(sum / 2);
    }
    return result;
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public string AddBinary(string a, string b) {
        // Time Complexity: O(max(N, M))
        // Memory Complexity: O(max(N, M))
        var sb = new System.Text.StringBuilder();
        int i = a.Length - 1, j = b.Length - 1, carry = 0;
        while (i >= 0 || j >= 0 || carry > 0) {
            int sum = carry;
            if (i >= 0) sum += a[i--] - '0';
            if (j >= 0) sum += b[j--] - '0';
            sb.Append(sum % 2);
            carry = sum / 2;
        }
        char[] charArray = sb.ToString().ToCharArray();
        System.Array.Reverse(charArray);
        return new string(charArray);
    }
}

```

# C

## Sweet Spot

```c
char* addBinary(char* a, char* b) {
    // Time Complexity: O(max(N, M))
    // Memory Complexity: O(max(N, M))
    int len1 = strlen(a);
    int len2 = strlen(b);
    int maxLen = len1 > len2 ? len1 : len2;
    char* res = (char*)malloc(maxLen + 2);
    
    int i = len1 - 1;
    int j = len2 - 1;
    int k = 0;
    int carry = 0;

    while (i >= 0 || j >= 0 || carry) {
        int sum = carry;
        if (i >= 0) sum += a[i--] - '0';
        if (j >= 0) sum += b[j--] - '0';
        res[k++] = (sum % 2) + '0';
        carry = sum / 2;
    }
    res[k] = '\0';

    for (int start = 0, end = k - 1; start < end; start++, end--) {
        char temp = res[start];
        res[start] = res[end];
        res[end] = temp;
    }

    return res;
}
```

# Go

## Sweet Spot

```go
func addBinary(a string, b string) string {
    // Time Complexity: O(max(N, M))
    // Memory Complexity: O(max(N, M))
    res := ""
    i, j, carry := len(a)-1, len(b)-1, 0
    for i >= 0 || j >= 0 || carry > 0 {
        sum := carry
        if i >= 0 {
            sum += int(a[i] - '0')
            i--
        }
        if j >= 0 {
            sum += int(b[j] - '0')
            j--
        }
        res = strconv.Itoa(sum%2) + res
        carry = sum / 2
    }
    return res
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun addBinary(a: String, b: String): String {
        // Time Complexity: O(max(N, M))
        // Memory Complexity: O(max(N, M))
        val sb = StringBuilder()
        var i = a.length - 1
        var j = b.length - 1
        var carry = 0
        while (i >= 0 || j >= 0 || carry > 0) {
            var sum = carry
            if (i >= 0) sum += a[i--] - '0'
            if (j >= 0) sum += b[j--] - '0'
            sb.append(sum % 2)
            carry = sum / 2
        }
        return sb.reverse().toString()
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func addBinary(_ a: String, _ b: String) -> String {
        // Time Complexity: O(max(N, M))
        // Memory Complexity: O(max(N, M))
        var res = ""
        let aArr = Array(a), bArr = Array(b)
        var i = aArr.count - 1, j = bArr.count - 1, carry = 0
        while i >= 0 || j >= 0 || carry > 0 {
            var sum = carry
            if i >= 0 { sum += Int(String(aArr[i]))!; i -= 1 }
            if j >= 0 { sum += Int(String(bArr[j]))!; j -= 1 }
            res = String(sum % 2) + res
            carry = sum / 2
        }
        return res
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn add_binary(a: String, b: String) -> String {
        // Time Complexity: O(max(N, M))
        // Memory Complexity: O(max(N, M))
        let mut res = String::new();
        let a_chars: Vec<char> = a.chars().collect();
        let b_chars: Vec<char> = b.chars().collect();
        let (mut i, mut j, mut carry) = (a_chars.len() as i32 - 1, b_chars.len() as i32 - 1, 0);
        while i >= 0 || j >= 0 || carry > 0 {
            let mut sum = carry;
            if i >= 0 { sum += a_chars[i as usize].to_digit(10).unwrap(); i -= 1; }
            if j >= 0 { sum += b_chars[j as usize].to_digit(10).unwrap(); j -= 1; }
            res.push_str(&(sum % 2).to_string());
            carry = sum / 2;
        }
        res.chars().rev().collect()
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {String} a
# @param {String} b
# @return {String}
def add_binary(a, b)
    # Time Complexity: O(max(N, M))
    # Memory Complexity: O(max(N, M))
    (a.to_i(2) + b.to_i(2)).to_s(2)
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param String $a
     * @param String $b
     * @return String
     */
    function addBinary($a, $b) {
        // Time Complexity: O(max(N, M))
        // Memory Complexity: O(max(N, M))
        $res = "";
        $i = strlen($a) - 1;
        $j = strlen($b) - 1;
        $carry = 0;
        while ($i >= 0 || $j >= 0 || $carry > 0) {
            $sum = $carry;
            if ($i >= 0) $sum += (int)$a[$i--];
            if ($j >= 0) $sum += (int)$b[$j--];
            $res = ($sum % 2) . $res;
            $carry = (int)($sum / 2);
        }
        return $res;
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  String addBinary(String a, String b) {
    // Time Complexity: O(max(N, M))
    // Memory Complexity: O(max(N, M))
    var res = StringBuffer();
    int i = a.length - 1, j = b.length - 1, carry = 0;
    while (i >= 0 || j >= 0 || carry > 0) {
      int sum = carry;
      if (i >= 0) sum += int.parse(a[i--]);
      if (j >= 0) sum += int.parse(b[j--]);
      res.write(sum % 2);
      carry = sum ~/ 2;
    }
    return res.toString().split('').reversed.join();
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def addBinary(a: String, b: String): String = {
        // Time Complexity: O(max(N, M))
        // Memory Complexity: O(max(N, M))
        BigInt(a, 2).+(BigInt(b, 2)).toString(2)
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec add_binary(a :: String.t, b :: String.t) :: String.t
  def add_binary(a, b) do
    # Time Complexity: O(max(N, M))
    # Memory Complexity: O(max(N, M))
    (String.to_integer(a, 2) + String.to_integer(b, 2)) |> Integer.to_string(2)
  end
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec add_binary(A :: unicode:unicode_binary(), B :: unicode:unicode_binary()) -> unicode:unicode_binary().
add_binary(A, B) ->
  % Time Complexity: O(max(N, M))
  % Memory Complexity: O(max(N, M))
  IntA = binary_to_integer(A, 2),
  IntB = binary_to_integer(B, 2),
  integer_to_binary(IntA + IntB, 2).

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (add-binary a b)
  (-> string? string? string?)
  ; Time Complexity: O(max(N, M))
  ; Memory Complexity: O(max(N, M))
  (number->string (+ (string->number a 2) (string->number b 2)) 2)
)

```