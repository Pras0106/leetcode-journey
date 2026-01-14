# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int strStr(string haystack, string needle) {
        if (needle.empty()) return 0;
        int n = haystack.size();
        int m = needle.size();
        if (n < m) return -1;
        for (int i = 0; i <= n - m; i++) {
            int j = 0;
            while (j < m && haystack[i + j] == needle[j]) {
                j++;
            }
            if (j == m) return i;
        }
        return -1;
        /* Time complexity: O(n * m) */
        /* Memory complexity: O(1) */
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public int strStr(String haystack, String needle) {
        if (needle.isEmpty()) return 0;
        int n = haystack.length();
        int m = needle.length();
        for (int i = 0; i <= n - m; i++) {
            int j = 0;
            while (j < m && haystack.charAt(i + j) == needle.charAt(j)) {
                j++;
            }
            if (j == m) return i;
        }
        return -1;
        /* Time complexity: O(n * m) */
        /* Memory complexity: O(1) */
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        return haystack.find(needle)
        # Time complexity: O(n * m)
        # Memory complexity: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def strStr(self, haystack, needle):
        """
        :type haystack: str
        :type needle: str
        :rtype: int
        """
        return haystack.find(needle)
        # Time complexity: O(n * m)
        # Memory complexity: O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {string} haystack
 * @param {string} needle
 * @return {number}
 */
var strStr = function(haystack, needle) {
    return haystack.indexOf(needle);
    /* Time complexity: O(n * m) */
    /* Memory complexity: O(1) */
};

```

# Typescript

## Sweet Spot

```typescript
function strStr(haystack: string, needle: string): number {
    return haystack.indexOf(needle);
    /* Time complexity: O(n * m) */
    /* Memory complexity: O(1) */
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int StrStr(string haystack, string needle) {
        if (string.IsNullOrEmpty(needle)) return 0;
        return haystack.IndexOf(needle);
        /* Time complexity: O(n * m) */
        /* Memory complexity: O(1) */
    }
}

```

# C

## Sweet Spot

```c
int strStr(char* haystack, char* needle) {
    if (!*needle) return 0;
    char *p1 = haystack;
    while (*p1) {
        char *p1_adv = p1;
        char *p2 = needle;
        while (*p1_adv && *p2 && *p1_adv == *p2) {
            p1_adv++;
            p2++;
        }
        if (!*p2) return (int)(p1 - haystack);
        p1++;
    }
    return -1;
    /* Time complexity: O(n * m) */
    /* Memory complexity: O(1) */
}

```

# Go

## Sweet Spot

```go
func strStr(haystack string, needle string) int {
    n := len(haystack)
    m := len(needle)
    if m == 0 {
        return 0
    }
    for i := 0; i <= n-m; i++ {
        if haystack[i:i+m] == needle {
            return i
        }
    }
    return -1
    /* Time complexity: O(n * m) */
    /* Memory complexity: O(1) */
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun strStr(haystack: String, needle: String): Int {
        return haystack.indexOf(needle)
        /* Time complexity: O(n * m) */
        /* Memory complexity: O(1) */
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func strStr(_ haystack: String, _ needle: String) -> Int {
        if let range = haystack.range(of: needle) {
            return haystack.distance(from: haystack.startIndex, to: range.lowerBound)
        }
        return -1
        /* Time complexity: O(n * m) */
        /* Memory complexity: O(1) */
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn str_str(haystack: String, needle: String) -> i32 {
        match haystack.find(&needle) {
            Some(i) => i as i32,
            None => -1,
        }
        /* Time complexity: O(n * m) */
        /* Memory complexity: O(1) */
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {String} haystack
# @param {String} needle
# @return {Integer}
def str_str(haystack, needle)
    haystack.index(needle) || -1
    # Time complexity: O(n * m)
    # Memory complexity: O(1)
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param String $haystack
     * @param String $needle
     * @return Integer
     */
    function strStr($haystack, $needle) {
        $pos = strpos($haystack, $needle);
        return ($pos === false) ? -1 : $pos;
        /* Time complexity: O(n * m) */
        /* Memory complexity: O(1) */
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  int strStr(String haystack, String needle) {
    return haystack.indexOf(needle);
    /* Time complexity: O(n * m) */
    /* Memory complexity: O(1) */
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def strStr(haystack: String, needle: String): Int = {
        haystack.indexOf(needle)
        /* Time complexity: O(n * m) */
        /* Memory complexity: O(1) */
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  # Time complexity: O(n * m)
  # Memory complexity: O(1)
  @spec str_str(haystack :: String.t, needle :: String.t) :: integer
  def str_str(haystack, needle) do
    case :binary.match(haystack, needle) do
      {start, _length} -> start
      :nomatch -> -1
    end
  end
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
% Time complexity: O(n * m)
% Memory complexity: O(1)
-spec str_str(Haystack :: unicode:unicode_binary(), Needle :: unicode:unicode_binary()) -> integer().
str_str(Haystack, Needle) ->
  case binary:match(Haystack, Needle) of
    {Start, _Length} -> Start;
    nomatch -> -1
  end.

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
; Time complexity: O(n * m)
; Memory complexity: O(1)
(define/contract (str-str haystack needle)
  (-> string? string? exact-integer?)
  (let ([match (regexp-match-positions (regexp-quote needle) haystack)])
    (if match
        (caar match)
        -1)))

```