# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int lengthOfLastWord(string s) {
        int length = 0;
        int i = s.length() - 1;
        while (i >= 0 && s[i] == ' ') {
            i--;
        }
        while (i >= 0 && s[i] != ' ') {
            length++;
            i--;
        }
        return length;
    }
};
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# java

## Sweet Spot

```java
class Solution {
    public int lengthOfLastWord(String s) {
        int length = 0;
        int i = s.length() - 1;
        while (i >= 0 && s.charAt(i) == ' ') {
            i--;
        }
        while (i >= 0 && s.charAt(i) != ' ') {
            length++;
            i--;
        }
        return length;
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def lengthOfLastWord(self, s: str) -> int:
        length = 0
        i = len(s) - 1
        while i >= 0 and s[i] == ' ':
            i -= 1
        while i >= 0 and s[i] != ' ':
            length += 1
            i -= 1
        return length
# Time Complexity: O(n)
# Memory Complexity: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def lengthOfLastWord(self, s):
        """
        :type s: str
        :rtype: int
        """
        length = 0
        i = len(s) - 1
        while i >= 0 and s[i] == ' ':
            i -= 1
        while i >= 0 and s[i] != ' ':
            length += 1
            i -= 1
        return length
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
var lengthOfLastWord = function(s) {
    let length = 0;
    let i = s.length - 1;
    while (i >= 0 && s[i] === ' ') {
        i--;
    }
    while (i >= 0 && s[i] !== ' ') {
        length++;
        i--;
    }
    return length;
};
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# Typescript

## Sweet Spot

```typescript
function lengthOfLastWord(s: string): number {
    let length: number = 0;
    let i: number = s.length - 1;
    while (i >= 0 && s[i] === ' ') {
        i--;
    }
    while (i >= 0 && s[i] !== ' ') {
        length++;
        i--;
    }
    return length;
};
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int LengthOfLastWord(string s) {
        int length = 0;
        int i = s.Length - 1;
        while (i >= 0 && s[i] == ' ') {
            i--;
        }
        while (i >= 0 && s[i] != ' ') {
            length++;
            i--;
        }
        return length;
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# C

## Sweet Spot

```c
int lengthOfLastWord(char* s) {
    int length = 0;
    int i = strlen(s) - 1;
    while (i >= 0 && s[i] == ' ') {
        i--;
    }
    while (i >= 0 && s[i] != ' ') {
        length++;
        i--;
    }
    return length;
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# Go

## Sweet Spot

```go
func lengthOfLastWord(s string) int {
    length := 0
    i := len(s) - 1
    for i >= 0 && s[i] == ' ' {
        i--
    }
    for i >= 0 && s[i] != ' ' {
        length++
        i--
    }
    return length
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun lengthOfLastWord(s: String): Int {
        var length = 0
        var i = s.length - 1
        while (i >= 0 && s[i] == ' ') {
            i--
        }
        while (i >= 0 && s[i] != ' ') {
            length++
            i--
        }
        return length
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# swift

## Sweet Spot

```swift
class Solution {
    func lengthOfLastWord(_ s: String) -> Int {
        let chars = Array(s)
        var length = 0
        var i = chars.count - 1
        while i >= 0 && chars[i] == " " {
            i -= 1
        }
        while i >= 0 && chars[i] != " " {
            length += 1
            i -= 1
        }
        return length
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn length_of_last_word(s: String) -> i32 {
        let bytes = s.as_bytes();
        let mut length = 0;
        let mut i = (bytes.len() as i32) - 1;
        while i >= 0 && bytes[i as usize] == b' ' {
            i -= 1;
        }
        while i >= 0 && bytes[i as usize] != b' ' {
            length += 1;
            i -= 1;
        }
        length
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
def length_of_last_word(s)
    length = 0
    i = s.length - 1
    while i >= 0 && s[i] == ' '
        i -= 1
    end
    while i >= 0 && s[i] != ' '
        length += 1
        i -= 1
    end
    length
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
    function lengthOfLastWord($s) {
        $length = 0;
        $i = strlen($s) - 1;
        while ($i >= 0 && $s[$i] == ' ') {
            $i--;
        }
        while ($i >= 0 && $s[$i] != ' ') {
            $length++;
            $i--;
        }
        return $length;
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# dart

## Sweet Spot

```dart
class Solution {
  int lengthOfLastWord(String s) {
    int length = 0;
    int i = s.length - 1;
    while (i >= 0 && s[i] == ' ') {
      i--;
    }
    while (i >= 0 && s[i] != ' ') {
      length++;
      i--;
    }
    return length;
  }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def lengthOfLastWord(s: String): Int = {
        var length = 0
        var i = s.length - 1
        while (i >= 0 && s(i) == ' ') {
            i -= 1
        }
        while (i >= 0 && s(i) != ' ') {
            length += 1
            i -= 1
        }
        length
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec length_of_last_word(s :: String.t) :: integer
  def length_of_last_word(s) do
    s
    |> String.trim_trailing()
    |> String.split(" ")
    |> List.last()
    |> String.length()
  end
end
# Time Complexity: O(n)
# Memory Complexity: O(n)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec length_of_last_word(S :: unicode:unicode_binary()) -> integer().
length_of_last_word(S) ->
    Trimmed = string:trim(S, trailing),
    Words = string:lexemes(Trimmed, " "),
    LastWord = lists:last(Words),
    string:length(LastWord).
% Time Complexity: O(n)
% Memory Complexity: O(n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (length-of-last-word s)
  (-> string? exact-integer?)
  (let* ([trimmed (string-trim s #:left? #f)]
         [words (string-split trimmed " ")])
    (string-length (last words))))
; Time Complexity: O(n)
; Memory Complexity: O(n)

```