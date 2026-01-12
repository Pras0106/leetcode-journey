# cpp

## Memory O(1) | Sweet Spot

```cpp
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        ios_base::sync_with_stdio(false);
        cin.tie(NULL);
        int last_pos[128];
        for (int i = 0; i < 128; i++) last_pos[i] = -1;
        int max_len = 0, start = 0;
        for (int i = 0; i < s.length(); i++) {
            if (last_pos[(int)s[i]] >= start) {
                start = last_pos[(int)s[i]] + 1;
            }
            last_pos[(int)s[i]] = i;
            max_len = max(max_len, i - start + 1);
        }
        return max_len;
    }
};
// Time: O(n), Memory: O(1)

```

# java

## Memory O(1) | Sweet Spot

```java
class Solution {
    public int lengthOfLongestSubstring(String s) {
        int[] lastPos = new int[128];
        for (int i = 0; i < 128; i++) lastPos[i] = -1;
        int maxLen = 0, start = 0;
        int n = s.length();
        for (int i = 0; i < n; i++) {
            char c = s.charAt(i);
            if (lastPos[c] >= start) {
                start = lastPos[c] + 1;
            }
            lastPos[c] = i;
            maxLen = Math.max(maxLen, i - start + 1);
        }
        return maxLen;
    }
}
// Time: O(n), Memory: O(1)

```

# python 3.14

## Memory O(1) | Sweet Spot

```python 3.14
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        last_pos = {}
        max_len = start = 0
        for i, char in enumerate(s):
            if char in last_pos and last_pos[char] >= start:
                start = last_pos[char] + 1
            last_pos[char] = i
            max_len = max(max_len, i - start + 1)
        return max_len
# Time: O(n), Memory: O(1)

```

# python 2.7.11

## Memory O(1) | Sweet Spot

```python 2.7.11
class Solution(object):
    def lengthOfLongestSubstring(self, s):
        """
        :type s: str
        :rtype: int
        """
        last_pos = {}
        max_len = start = 0
        for i in xrange(len(s)):
            char = s[i]
            if char in last_pos and last_pos[char] >= start:
                start = last_pos[char] + 1
            last_pos[char] = i
            length = i - start + 1
            if length > max_len:
                max_len = length
        return max_len
# Time: O(n), Memory: O(1)

```

# JavaScript

## Memory O(1) | Sweet Spot

```javascript
/**
 * @param {string} s
 * @return {number}
 */
var lengthOfLongestSubstring = function(s) {
    let lastPos = new Int32Array(128).fill(-1);
    let maxLen = 0, start = 0;
    for (let i = 0; i < s.length; i++) {
        let code = s.charCodeAt(i);
        if (lastPos[code] >= start) {
            start = lastPos[code] + 1;
        }
        lastPos[code] = i;
        maxLen = Math.max(maxLen, i - start + 1);
    }
    return maxLen;
};
// Time: O(n), Memory: O(1)

```

# Typescript

## Memory O(1) | Sweet Spot

```typescript
function lengthOfLongestSubstring(s: string): number {
    const lastPos: number[] = new Array(128).fill(-1);
    let maxLen: number = 0;
    let start: number = 0;
    for (let i = 0; i < s.length; i++) {
        const charCode = s.charCodeAt(i);
        if (lastPos[charCode] >= start) {
            start = lastPos[charCode] + 1;
        }
        lastPos[charCode] = i;
        maxLen = Math.max(maxLen, i - start + 1);
    }
    return maxLen;
};
// Time: O(n), Memory: O(1)

```

# C#

## Memory O(1) | Sweet Spot

```c#
public class Solution {
    public int LengthOfLongestSubstring(string s) {
        int[] lastPos = new int[128];
        for (int i = 0; i < 128; i++) lastPos[i] = -1;
        int maxLen = 0, start = 0;
        for (int i = 0; i < s.Length; i++) {
            if (lastPos[s[i]] >= start) {
                start = lastPos[s[i]] + 1;
            }
            lastPos[s[i]] = i;
            int currentLen = i - start + 1;
            if (currentLen > maxLen) maxLen = currentLen;
        }
        return maxLen;
    }
}
// Time: O(n), Memory: O(1)

```

# C

## Memory O(1) | Sweet Spot

```c
int lengthOfLongestSubstring(char* s) {
    int lastPos[128];
    for (int i = 0; i < 128; i++) lastPos[i] = -1;
    int maxLen = 0, start = 0, i = 0;
    while (s[i] != '\0') {
        unsigned char c = (unsigned char)s[i];
        if (lastPos[c] >= start) {
            start = lastPos[c] + 1;
        }
        lastPos[c] = i;
        int currentLen = i - start + 1;
        if (currentLen > maxLen) maxLen = currentLen;
        i++;
    }
    return maxLen;
}
// Time: O(n), Memory: O(1)

```

# Go

## Memory O(1) | Sweet Spot

```go
func lengthOfLongestSubstring(s string) int {
    lastPos := [128]int{}
    for i := range lastPos {
        lastPos[i] = -1
    }
    maxLen, start := 0, 0
    for i := 0; i < len(s); i++ {
        char := s[i]
        if lastPos[char] >= start {
            start = lastPos[char] + 1
        }
        lastPos[char] = i
        if i-start+1 > maxLen {
            maxLen = i - start + 1
        }
    }
    return maxLen
}
// Time: O(n), Memory: O(1)

```

# Kotlin

## Memory O(1) | Sweet Spot

```kotlin
class Solution {
    fun lengthOfLongestSubstring(s: String): Int {
        val lastPos = IntArray(128) { -1 }
        var maxLen = 0
        var start = 0
        for (i in s.indices) {
            val charCode = s[i].toInt()
            if (lastPos[charCode] >= start) {
                start = lastPos[charCode] + 1
            }
            lastPos[charCode] = i
            maxLen = maxOf(maxLen, i - start + 1)
        }
        return maxLen
    }
}
// Time: O(n), Memory: O(1)

```

# swift

## Memory O(1) | Sweet Spot

```swift
class Solution {
    func lengthOfLongestSubstring(_ s: String) -> Int {
        var lastPos = [Int](repeating: -1, count: 128)
        var maxLen = 0
        var start = 0
        let chars = Array(s.utf8)
        for i in 0..<chars.count {
            let char = Int(chars[i])
            if lastPos[char] >= start {
                start = lastPos[char] + 1
            }
            lastPos[char] = i
            maxLen = max(maxLen, i - start + 1)
        }
        return maxLen
    }
}
// Time: O(n), Memory: O(1)

```

# rust

## Memory O(1) | Sweet Spot

```rust
impl Solution {
    pub fn length_of_longest_substring(s: String) -> i32 {
        let mut last_pos = [-1; 128];
        let mut max_len = 0;
        let mut start = 0;
        for (i, &byte) in s.as_bytes().iter().enumerate() {
            let char_idx = byte as usize;
            if last_pos[char_idx] >= start {
                start = last_pos[char_idx] + 1;
            }
            last_pos[char_idx] = i as i32;
            max_len = max_len.max(i as i32 - start + 1);
        }
        max_len
    }
}
// Time: O(n), Memory: O(1)

```

# ruby

## Memory O(1) | Sweet Spot

```ruby
# @param {String} s
# @return {Integer}
def length_of_longest_substring(s)
    last_pos = Array.new(128, -1)
    max_len = 0
    start = 0
    s.each_byte.with_index do |byte, i|
        if last_pos[byte] >= start
            start = last_pos[byte] + 1
        end
        last_pos[byte] = i
        current_len = i - start + 1
        max_len = current_len if current_len > max_len
    end
    max_len
end
# Time: O(n), Memory: O(1)

```

# php

## Memory O(1) | Sweet Spot

```php
class Solution {
    /**
     * @param String $s
     * @return Integer
     */
    function lengthOfLongestSubstring($s) {
        $lastPos = array_fill(0, 128, -1);
        $maxLen = 0;
        $start = 0;
        $len = strlen($s);
        for ($i = 0; $i < $len; $i++) {
            $char = ord($s[$i]);
            if ($lastPos[$char] >= $start) {
                $start = $lastPos[$char] + 1;
            }
            $lastPos[$char] = $i;
            $maxLen = max($maxLen, $i - $start + 1);
        }
        return $maxLen;
    }
}
// Time: O(n), Memory: O(1)

```

# dart

## Memory O(1) | Sweet Spot

```dart
import 'dart:math';

class Solution {
  int lengthOfLongestSubstring(String s) {
    List<int> lastPos = List.filled(128, -1);
    int maxLen = 0;
    int start = 0;
    for (int i = 0; i < s.length; i++) {
      int charCode = s.codeUnitAt(i);
      if (lastPos[charCode] >= start) {
        start = lastPos[charCode] + 1;
      }
      lastPos[charCode] = i;
      maxLen = max(maxLen, i - start + 1);
    }
    return maxLen;
  }
}
// Time: O(n), Memory: O(1)

```

# scala

## Memory O(1) | Sweet Spot

```scala
object Solution {
    def lengthOfLongestSubstring(s: String): Int = {
        val lastPos = Array.fill(128)(-1)
        var maxLen = 0
        var start = 0
        for (i <- 0 until s.length) {
            val charCode = s.charAt(i).toInt
            if (lastPos(charCode) >= start) {
                start = lastPos(charCode) + 1
            }
            lastPos(charCode) = i
            maxLen = Math.max(maxLen, i - start + 1)
        }
        maxLen
    }
}
// Time: O(n), Memory: O(1)

```

# elixir

## Memory O(1) | Sweet Spot

```elixir
defmodule Solution do
  @spec length_of_longest_substring(s :: String.t) :: integer
  def length_of_longest_substring(s) do
    s
    |> String.to_charlist()
    |> Enum.reduce({0, 0, %{}, 0}, fn char, {i, start, last_pos, max_len} ->
      new_start = if Map.has_key?(last_pos, char) and Map.get(last_pos, char) >= start do
        Map.get(last_pos, char) + 1
      else
        start
      end
      new_last_pos = Map.put(last_pos, char, i)
      new_max_len = max(max_len, i - new_start + 1)
      {i + 1, new_start, new_last_pos, new_max_len}
    end)
    |> elem(3)
  end
end
# Time: O(n), Memory: O(1)

```

# erlang

## Memory O(1) | Sweet Spot

```erlang
-spec length_of_longest_substring(S :: unicode:unicode_binary()) -> integer().
length_of_longest_substring(S) ->
    solve(binary_to_list(S), 0, 0, #{}, 0).

solve([], _I, _Start, _LastPos, MaxLen) -> MaxLen;
solve([Char | Rest], I, Start, LastPos, MaxLen) ->
    NewStart = case maps:find(Char, LastPos) of
        {ok, Pos} when Pos >= Start -> Pos + 1;
        _ -> Start
    end,
    NewMaxLen = erlang:max(MaxLen, I - NewStart + 1),
    solve(Rest, I + 1, NewStart, LastPos#{Char => I}, NewMaxLen).
% Time: O(n), Memory: O(1)

```

# Racket

## Memory O(1) | Sweet Spot

```racket
(define/contract (length-of-longest-substring s)
  (-> string? exact-integer?)
  (let ([last-pos (make-vector 256 -1)]
        [chars (string->list s)])
    (let loop ([lst chars] [i 0] [start 0] [max-len 0])
      (if (null? lst)
          max-len
          (let* ([char-code (char->integer (car lst))]
                 [prev-pos (vector-ref last-pos char-code)]
                 [new-start (if (>= prev-pos start) (+ prev-pos 1) start)]
                 [new-max (max max-len (+ (- i new-start) 1))])
            (vector-set! last-pos char-code i)
            (loop (cdr lst) (+ i 1) new-start new-max))))))
; Time: O(n), Memory: O(1)

```