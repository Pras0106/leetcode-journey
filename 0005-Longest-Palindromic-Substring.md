# cpp

## memory O(1) | Sweet Spot

```cpp
class Solution {
public:
    string longestPalindrome(string s) {
        if (s.length() < 1) return "";
        int start = 0, end = 0;
        for (int i = 0; i < s.length(); i++) {
            int len1 = expandAroundCenter(s, i, i);
            int len2 = expandAroundCenter(s, i, i + 1);
            int len = max(len1, len2);
            if (len > end - start) {
                start = i - (len - 1) / 2;
                end = i + len / 2;
            }
        }
        return s.substr(start, end - start + 1);
    }

private:
    int expandAroundCenter(string s, int left, int right) {
        int L = left, R = right;
        while (L >= 0 && R < s.length() && s[L] == s[R]) {
            L--;
            R++;
        }
        return R - L - 1;
    }
};
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# java

## memory O(1) | Sweet Spot

```java
class Solution {
    public String longestPalindrome(String s) {
        if (s == null || s.length() < 1) return "";
        int start = 0, end = 0;
        for (int i = 0; i < s.length(); i++) {
            int len1 = expandAroundCenter(s, i, i);
            int len2 = expandAroundCenter(s, i, i + 1);
            int len = Math.max(len1, len2);
            if (len > end - start) {
                start = i - (len - 1) / 2;
                end = i + len / 2;
            }
        }
        return s.substring(start, end + 1);
    }

    private int expandAroundCenter(String s, int left, int right) {
        int L = left, R = right;
        while (L >= 0 && R < s.length() && s.charAt(L) == s.charAt(R)) {
            L--;
            R++;
        }
        return R - L - 1;
    }
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# python 3.14

## memory O(1) | Sweet Spot

```python 3.14
class Solution:
    def longestPalindrome(self, s: str) -> str:
        if not s:
            return ""
        start = 0
        end = 0
        for i in range(len(s)):
            len1 = self._expand(s, i, i)
            len2 = self._expand(s, i, i + 1)
            length = max(len1, len2)
            if length > end - start:
                start = i - (length - 1) // 2
                end = i + length // 2
        return s[start : end + 1]

    def _expand(self, s: str, left: int, right: int) -> int:
        while left >= 0 and right < len(s) and s[left] == s[right]:
            left -= 1
            right += 1
        return right - left - 1
# Time Complexity: O(n^2)
# Memory Complexity: O(1)

```

# python 2.7.11

## memory O(1) | Sweet Spot

```python 2.7.11
class Solution(object):
    def longestPalindrome(self, s):
        """
        :type s: str
        :rtype: str
        """
        if not s:
            return ""
        start = 0
        end = 0
        for i in range(len(s)):
            len1 = self._expand(s, i, i)
            len2 = self._expand(s, i, i + 1)
            max_len = max(len1, len2)
            if max_len > end - start:
                start = i - (max_len - 1) / 2
                end = i + max_len / 2
        return s[start : end + 1]

    def _expand(self, s, left, right):
        while left >= 0 and right < len(s) and s[left] == s[right]:
            left -= 1
            right += 1
        return right - left - 1
# Time Complexity: O(n^2)
# Memory Complexity: O(1)

```

# JavaScript

## memory O(1) | Sweet Spot

```javascript
/**
 * @param {string} s
 * @return {string}
 */
var longestPalindrome = function(s) {
    if (!s || s.length < 1) return "";
    let start = 0, end = 0;
    for (let i = 0; i < s.length; i++) {
        let len1 = expandAroundCenter(s, i, i);
        let len2 = expandAroundCenter(s, i, i + 1);
        let len = Math.max(len1, len2);
        if (len > end - start) {
            start = i - Math.floor((len - 1) / 2);
            end = i + Math.floor(len / 2);
        }
    }
    return s.substring(start, end + 1);
};

function expandAroundCenter(s, left, right) {
    while (left >= 0 && right < s.length && s[left] === s[right]) {
        left--;
        right++;
    }
    return right - left - 1;
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# Typescript

## memory O(1) | Sweet Spot

```typescript
function longestPalindrome(s: string): string {
    if (!s || s.length < 1) return "";
    let start = 0, end = 0;
    for (let i = 0; i < s.length; i++) {
        const len1 = expandAroundCenter(s, i, i);
        const len2 = expandAroundCenter(s, i, i + 1);
        const len = Math.max(len1, len2);
        if (len > end - start) {
            start = i - Math.floor((len - 1) / 2);
            end = i + Math.floor(len / 2);
        }
    }
    return s.substring(start, end + 1);
};

function expandAroundCenter(s: string, left: number, right: number): number {
    while (left >= 0 && right < s.length && s[left] === s[right]) {
        left--;
        right++;
    }
    return right - left - 1;
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# C#

## memory O(1) | Sweet Spot

```c#
public class Solution {
    public string LongestPalindrome(string s) {
        if (string.IsNullOrEmpty(s)) return "";
        int start = 0, end = 0;
        for (int i = 0; i < s.Length; i++) {
            int len1 = ExpandAroundCenter(s, i, i);
            int len2 = ExpandAroundCenter(s, i, i + 1);
            int len = Math.Max(len1, len2);
            if (len > end - start) {
                start = i - (len - 1) / 2;
                end = i + len / 2;
            }
        }
        return s.Substring(start, end - start + 1);
    }

    private int ExpandAroundCenter(string s, int left, int right) {
        int L = left, R = right;
        while (L >= 0 && R < s.Length && s[L] == s[R]) {
            L--;
            R++;
        }
        return R - L - 1;
    }
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# C

## memory O(1) | Sweet Spot

```c
char* longestPalindrome(char* s) {
    int n = strlen(s);
    if (n < 1) return "";
    int start = 0, maxLen = 1;
    for (int i = 0; i < n; i++) {
        int l = i, r = i;
        while (l >= 0 && r < n && s[l] == s[r]) {
            if (r - l + 1 > maxLen) {
                start = l;
                maxLen = r - l + 1;
            }
            l--; r++;
        }
        l = i, r = i + 1;
        while (l >= 0 && r < n && s[l] == s[r]) {
            if (r - l + 1 > maxLen) {
                start = l;
                maxLen = r - l + 1;
            }
            l--; r++;
        }
    }
    char* result = (char*)malloc((maxLen + 1) * sizeof(char));
    strncpy(result, s + start, maxLen);
    result[maxLen] = '\0';
    return result;
}
// Time Complexity: O(n^2)
// Memory Complexity: O(n) for result string allocation

```

# Go

## memory O(1) | Sweet Spot

```go
func longestPalindrome(s string) string {
    if len(s) < 1 {
        return ""
    }
    start, end := 0, 0
    for i := 0; i < len(s); i++ {
        len1 := expandAroundCenter(s, i, i)
        len2 := expandAroundCenter(s, i, i+1)
        length := len1
        if len2 > len1 {
            length = len2
        }
        if length > end-start {
            start = i - (length-1)/2
            end = i + length/2
        }
    }
    return s[start : end+1]
}

func expandAroundCenter(s string, left, right int) int {
    L, R := left, right
    for L >= 0 && R < len(s) && s[L] == s[R] {
        L--
        R++
    }
    return R - L - 1
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# Kotlin

## memory O(1) | Sweet Spot

```kotlin
class Solution {
    fun longestPalindrome(s: String): String {
        if (s.isEmpty()) return ""
        var start = 0
        var end = 0
        for (i in s.indices) {
            val len1 = expandAroundCenter(s, i, i)
            val len2 = expandAroundCenter(s, i, i + 1)
            val len = maxOf(len1, len2)
            if (len > end - start) {
                start = i - (len - 1) / 2
                end = i + len / 2
            }
        }
        return s.substring(start, end + 1)
    }

    private fun expandAroundCenter(s: String, left: Int, right: Int): Int {
        var l = left
        var r = right
        while (l >= 0 && r < s.length && s[l] == s[r]) {
            l--
            r++
        }
        return r - l - 1
    }
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# swift

## memory O(1) | Sweet Spot

```swift
class Solution {
    func longestPalindrome(_ s: String) -> String {
        if s.count < 1 { return "" }
        let chars = Array(s)
        var start = 0
        var maxLen = 0
        
        for i in 0..<chars.count {
            let len1 = expandAroundCenter(chars, i, i)
            let len2 = expandAroundCenter(chars, i, i + 1)
            let len = max(len1, len2)
            if len > maxLen {
                start = i - (len - 1) / 2
                maxLen = len
            }
        }
        
        let startIndex = s.index(s.startIndex, offsetBy: start)
        let endIndex = s.index(startIndex, offsetBy: maxLen)
        return String(s[startIndex..<endIndex])
    }
    
    private func expandAroundCenter(_ chars: [Character], _ left: Int, _ right: Int) -> Int {
        var l = left
        var r = right
        while l >= 0 && r < chars.count && chars[l] == chars[r] {
            l -= 1
            r += 1
        }
        return r - l - 1
    }
}
// Time Complexity: O(n^2)
// Memory Complexity: O(n) due to String to Array conversion for O(1) access

```

# rust

## memory O(1) | Sweet Spot

```rust
impl Solution {
    pub fn longest_palindrome(s: String) -> String {
        let chars: Vec<char> = s.chars().collect();
        let n = chars.len();
        if n == 0 { return "".to_string(); }
        let mut start = 0;
        let mut max_len = 0;

        for i in 0..n {
            let len1 = Self::expand(&chars, i as i32, i as i32);
            let len2 = Self::expand(&chars, i as i32, i as i32 + 1);
            let len = len1.max(len2);
            if len > max_len {
                start = i - (len - 1) as usize / 2;
                max_len = len;
            }
        }
        chars[start..start + max_len].iter().collect()
    }

    fn expand(chars: &[char], mut left: i32, mut right: i32) -> usize {
        while left >= 0 && right < chars.len() as i32 && chars[left as usize] == chars[right as usize] {
            left -= 1;
            right += 1;
        }
        (right - left - 1) as usize
    }
}
// Time Complexity: O(n^2)
// Memory Complexity: O(n)

```

# ruby

## memory O(1) | Sweet Spot

```ruby
# @param {String} s
# @return {String}
def longest_palindrome(s)
    return "" if s.length == 0
    start_idx = 0
    max_len = 0
    
    (0...s.length).each do |i|
        len1 = expand_around_center(s, i, i)
        len2 = expand_around_center(s, i, i + 1)
        len = [len1, len2].max
        if len > max_len
            start_idx = i - (len - 1) / 2
            max_len = len
        end
    end
    s[start_idx, max_len]
end

def expand_around_center(s, left, right)
    while left >= 0 && right < s.length && s[left] == s[right]
        left -= 1
        right += 1
    end
    right - left - 1
end
# Time Complexity: O(n^2)
# Memory Complexity: O(1)

```

# php

## memory O(1) | Sweet Spot

```php
class Solution {

    /**
     * @param String $s
     * @return String
     */
    function longestPalindrome($s) {
        $n = strlen($s);
        if ($n < 1) return "";
        $start = 0;
        $maxLen = 0;
        for ($i = 0; $i < $n; $i++) {
            $len1 = $this->expand($s, $i, $i);
            $len2 = $this->expand($s, $i, $i + 1);
            $len = max($len1, $len2);
            if ($len > $maxLen) {
                $start = $i - floor(($len - 1) / 2);
                $maxLen = $len;
            }
        }
        return substr($s, $start, $maxLen);
    }

    private function expand($s, $l, $r) {
        while ($l >= 0 && $r < strlen($s) && $s[$l] == $s[$r]) {
            $l--;
            $r++;
        }
        return $r - $l - 1;
    }
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# dart

## memory O(1) | Sweet Spot

```dart
class Solution {
  String longestPalindrome(String s) {
    if (s.isEmpty) return "";
    int start = 0;
    int end = 0;
    for (int i = 0; i < s.length; i++) {
      int len1 = _expand(s, i, i);
      int len2 = _expand(s, i, i + 1);
      int len = len1 > len2 ? len1 : len2;
      if (len > end - start) {
        start = i - (len - 1) ~/ 2;
        end = i + len ~/ 2;
      }
    }
    return s.substring(start, end + 1);
  }

  int _expand(String s, int left, int right) {
    while (left >= 0 && right < s.length && s[left] == s[right]) {
      left--;
      right++;
    }
    return right - left - 1;
  }
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# scala 3.3.1

## memory O(1) | Sweet Spot

```scala 3.3.1
object Solution {
    def longestPalindrome(s: String): String = {
        if (s == null || s.length < 1) return ""
        var start = 0
        var end = 0
        for (i <- 0 until s.length) {
            val len1 = expand(s, i, i)
            val len2 = expand(s, i, i + 1)
            val len = Math.max(len1, len2)
            if (len > end - start) {
                start = i - (len - 1) / 2
                end = i + len / 2
            }
        }
        s.substring(start, end + 1)
    }

    private def expand(s: String, left: Int, right: Int): Int = {
        var l = left
        var r = right
        while (l >= 0 && r < s.length && s.charAt(l) == s.charAt(r)) {
            l -= 1
            r += 1
        }
        r - l - 1
    }
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# Elixir 1.17 with Erlang/OTP 26

## memory O(n) | Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec longest_palindrome(s :: String.t) :: String.t
  def longest_palindrome(s) do
    chars = String.to_charlist(s) |> List.to_tuple()
    n = tuple_size(chars)
    if n == 0 do
      ""
    else
      {start, len} = Enum.reduce(0..(n - 1), {0, 0}, fn i, acc ->
        l1 = expand(chars, i, i, n)
        l2 = expand(chars, i, i + 1, n)
        curr_max = max(l1, l2)
        if curr_max > elem(acc, 1) do
          {i - div(curr_max - 1, 2), curr_max}
        else
          acc
        end
      end)
      String.slice(s, start, len)
    end
  end

  defp expand(_, l, r, n) when l < 0 or r >= n, do: r - l - 1
  defp expand(chars, l, r, n) do
    if elem(chars, l) == elem(chars, r) do
      expand(chars, l - 1, r + 1, n)
    else
      r - l - 1
    end
  end
end
# Time Complexity: O(n^2)
# Memory Complexity: O(n)

```

# Erlang/OTP 26

## memory O(n) | Sweet Spot

```erlang/otp 26
-spec longest_palindrome(S :: unicode:unicode_binary()) -> unicode:unicode_binary().
longest_palindrome(S) ->
    Chars = list_to_tuple(binary_to_list(S)),
    N = tuple_size(Chars),
    if N == 0 -> <<>>;
       true ->
           {Start, Len} = lists:foldl(fun(I, {BestStart, BestLen}) ->
               L1 = expand(Chars, I-1, I-1, N),
               L2 = expand(Chars, I-1, I, N),
               Max = if L1 > L2 -> L1; true -> L2 end,
               if Max > BestLen -> {I - 1 - (Max - 1) div 2, Max};
                  true -> {BestStart, BestLen}
               end
           end, {0, 0}, lists:seq(1, N)),
           binary:part(S, Start, Len)
    end.

expand(_, L, R, N) when L < 0; R >= N -> R - L - 1;
expand(Chars, L, R, N) ->
    case element(L + 1, Chars) == element(R + 1, Chars) of
        true -> expand(Chars, L - 1, R + 1, N);
        false -> R - L - 1
    end.
% Time Complexity: O(n^2)
% Memory Complexity: O(n)

```

# Racket CS v8.15

## memory O(n) | Sweet Spot

```racket CS v8.15
(define/contract (longest-palindrome s)
  (-> string? string?)
  (let* ([vec (list->vector (string->list s))]
         [n (vector-length vec)])
    (if (= n 0)
        ""
        (let loop ([i 0] [best-start 0] [best-len 0])
          (if (= i n)
              (substring s best-start (+ best-start best-len))
              (let* ([l1 (expand vec i i n)]
                     [l2 (expand vec i (+ i 1) n)]
                     [curr-max (max l1 l2)])
                (if (> curr-max best-len)
                    (loop (+ i 1) (- i (quotient (- curr-max 1) 2)) curr-max)
                    (loop (+ i 1) best-start best-len))))))))

(define (expand vec l r n)
  (if (and (>= l 0) (< r n) (char=? (vector-ref vec l) (vector-ref vec r)))
      (expand vec (- l 1) (+ r 1) n)
      (- r l 1)))
; Time Complexity: O(n^2)
; Memory Complexity: O(n)

```