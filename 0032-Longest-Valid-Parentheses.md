# cpp

## Sweet Spot | memory O(1) and time O(n)

```cpp
class Solution {
public:
    int longestValidParentheses(string s) {
        int left = 0, right = 0, maxlength = 0;
        for (int i = 0; i < s.length(); i++) {
            if (s[i] == '(') left++;
            else right++;
            if (left == right) maxlength = max(maxlength, 2 * right);
            else if (right > left) left = right = 0;
        }
        left = right = 0;
        for (int i = s.length() - 1; i >= 0; i--) {
            if (s[i] == '(') left++;
            else right++;
            if (left == right) maxlength = max(maxlength, 2 * left);
            else if (left > right) left = right = 0;
        }
        return maxlength;
    }
};
/* Time Complexity: O(n), Memory Complexity: O(1) */

```

# java

## Sweet Spot | memory O(1) and time O(n)

```java
class Solution {
    public int longestValidParentheses(String s) {
        int left = 0, right = 0, maxlength = 0;
        for (int i = 0; i < s.length(); i++) {
            if (s.charAt(i) == '(') left++;
            else right++;
            if (left == right) maxlength = Math.max(maxlength, 2 * right);
            else if (right > left) left = right = 0;
        }
        left = right = 0;
        for (int i = s.length() - 1; i >= 0; i--) {
            if (s.charAt(i) == '(') left++;
            else right++;
            if (left == right) maxlength = Math.max(maxlength, 2 * left);
            else if (left > right) left = right = 0;
        }
        return maxlength;
    }
}
/* Time Complexity: O(n), Memory Complexity: O(1) */

```

# python 3.14

## Sweet Spot | memory O(1) and time O(n)

```python 3.14
class Solution:
    def longestValidParentheses(self, s: str) -> int:
        left = right = maxlength = 0
        for char in s:
            if char == '(': left += 1
            else: right += 1
            if left == right: maxlength = max(maxlength, 2 * right)
            elif right > left: left = right = 0
        left = right = 0
        for char in reversed(s):
            if char == '(': left += 1
            else: right += 1
            if left == right: maxlength = max(maxlength, 2 * left)
            elif left > right: left = right = 0
        return maxlength
# Time Complexity: O(n), Memory Complexity: O(1)

```

# python 2.7.11

## Sweet Spot | memory O(1) and time O(n)

```python 2.7.11
class Solution(object):
    def longestValidParentheses(self, s):
        """
        :type s: str
        :rtype: int
        """
        left = right = maxlength = 0
        for char in s:
            if char == '(': left += 1
            else: right += 1
            if left == right: maxlength = max(maxlength, 2 * right)
            elif right > left: left = right = 0
        left = right = 0
        for char in reversed(s):
            if char == '(': left += 1
            else: right += 1
            if left == right: maxlength = max(maxlength, 2 * left)
            elif left > right: left = right = 0
        return maxlength
# Time Complexity: O(n), Memory Complexity: O(1)

```

# JavaScript

## Sweet Spot | memory O(1) and time O(n)

```javascript
/**
 * @param {string} s
 * @return {number}
 */
var longestValidParentheses = function(s) {
    let left = 0, right = 0, maxlength = 0;
    for (let i = 0; i < s.length; i++) {
        if (s[i] === '(') left++;
        else right++;
        if (left === right) maxlength = Math.max(maxlength, 2 * right);
        else if (right > left) left = right = 0;
    }
    left = right = 0;
    for (let i = s.length - 1; i >= 0; i--) {
        if (s[i] === '(') left++;
        else right++;
        if (left === right) maxlength = Math.max(maxlength, 2 * left);
        else if (left > right) left = right = 0;
    }
    return maxlength;
};
/* Time Complexity: O(n), Memory Complexity: O(1) */

```

# Typescript

## Sweet Spot | memory O(1) and time O(n)

```typescript
function longestValidParentheses(s: string): number {
    let left = 0, right = 0, maxlength = 0;
    for (let i = 0; i < s.length; i++) {
        if (s[i] === '(') left++;
        else right++;
        if (left === right) maxlength = Math.max(maxlength, 2 * right);
        else if (right > left) left = right = 0;
    }
    left = right = 0;
    for (let i = s.length - 1; i >= 0; i--) {
        if (s[i] === '(') left++;
        else right++;
        if (left === right) maxlength = Math.max(maxlength, 2 * left);
        else if (left > right) left = right = 0;
    }
    return maxlength;
};
/* Time Complexity: O(n), Memory Complexity: O(1) */

```

# C#

## Sweet Spot | memory O(1) and time O(n)

```c#
public class Solution {
    public int LongestValidParentheses(string s) {
        int left = 0, right = 0, maxlength = 0;
        for (int i = 0; i < s.Length; i++) {
            if (s[i] == '(') left++;
            else right++;
            if (left == right) maxlength = Math.Max(maxlength, 2 * right);
            else if (right > left) left = right = 0;
        }
        left = right = 0;
        for (int i = s.Length - 1; i >= 0; i--) {
            if (s[i] == '(') left++;
            else right++;
            if (left == right) maxlength = Math.Max(maxlength, 2 * left);
            else if (left > right) left = right = 0;
        }
        return maxlength;
    }
}
/* Time Complexity: O(n), Memory Complexity: O(1) */

```

# C

## Sweet Spot | memory O(1) and time O(n)

```c
int longestValidParentheses(char* s) {
    int left = 0, right = 0, maxlength = 0;
    int n = 0;
    while(s[n] != '\0') n++;
    for (int i = 0; i < n; i++) {
        if (s[i] == '(') left++;
        else right++;
        if (left == right) maxlength = maxlength > 2 * right ? maxlength : 2 * right;
        else if (right > left) left = right = 0;
    }
    left = right = 0;
    for (int i = n - 1; i >= 0; i--) {
        if (s[i] == '(') left++;
        else right++;
        if (left == right) maxlength = maxlength > 2 * left ? maxlength : 2 * left;
        else if (left > right) left = right = 0;
    }
    return maxlength;
}
/* Time Complexity: O(n), Memory Complexity: O(1) */

```

# Go

## Sweet Spot | memory O(1) and time O(n)

```go
func longestValidParentheses(s string) int {
    left, right, maxlength := 0, 0, 0
    for i := 0; i < len(s); i++ {
        if s[i] == '(' {
            left++
        } else {
            right++
        }
        if left == right {
            if 2 * right > maxlength {
                maxlength = 2 * right
            }
        } else if right > left {
            left, right = 0, 0
        }
    }
    left, right = 0, 0
    for i := len(s) - 1; i >= 0; i-- {
        if s[i] == '(' {
            left++
        } else {
            right++
        }
        if left == right {
            if 2 * left > maxlength {
                maxlength = 2 * left
            }
        } else if left > right {
            left, right = 0, 0
        }
    }
    return maxlength
}
/* Time Complexity: O(n), Memory Complexity: O(1) */

```

# Kotlin

## Sweet Spot | memory O(1) and time O(n)

```kotlin
class Solution {
    fun longestValidParentheses(s: String): Int {
        var left = 0
        var right = 0
        var maxlength = 0
        for (i in 0 until s.length) {
            if (s[i] == '(') left++
            else right++
            if (left == right) maxlength = maxOf(maxlength, 2 * right)
            else if (right > left) {
                left = 0
                right = 0
            }
        }
        left = 0
        right = 0
        for (i in s.length - 1 downTo 0) {
            if (s[i] == '(') left++
            else right++
            if (left == right) maxlength = maxOf(maxlength, 2 * left)
            else if (left > right) {
                left = 0
                right = 0
            }
        }
        return maxlength
    }
}
/* Time Complexity: O(n), Memory Complexity: O(1) */

```

# swift

## Sweet Spot | memory O(1) and time O(n)

```swift
class Solution {
    func longestValidParentheses(_ s: String) -> Int {
        var left = 0, right = 0, maxlength = 0
        let chars = Array(s)
        for i in 0..<chars.count {
            if chars[i] == "(" { left += 1 }
            else { right += 1 }
            if left == right { maxlength = max(maxlength, 2 * right) }
            else if right > left { left = 0; right = 0 }
        }
        left = 0; right = 0
        for i in (0..<chars.count).reversed() {
            if chars[i] == "(" { left += 1 }
            else { right += 1 }
            if left == right { maxlength = max(maxlength, 2 * left) }
            else if left > right { left = 0; right = 0 }
        }
        return maxlength
    }
}
/* Time Complexity: O(n), Memory Complexity: O(1) */

```

# rust

## Sweet Spot | memory O(1) and time O(n)

```rust
impl Solution {
    pub fn longest_valid_parentheses(s: String) -> i32 {
        let (mut left, mut right, mut maxlength) = (0, 0, 0);
        let bytes = s.as_bytes();
        for &b in bytes {
            if b == b'(' { left += 1; }
            else { right += 1; }
            if left == right { maxlength = maxlength.max(2 * right); }
            else if right > left { left = 0; right = 0; }
        }
        left = 0; right = 0;
        for &b in bytes.iter().rev() {
            if b == b'(' { left += 1; }
            else { right += 1; }
            if left == right { maxlength = maxlength.max(2 * left); }
            else if left > right { left = 0; right = 0; }
        }
        maxlength
    }
}
/* Time Complexity: O(n), Memory Complexity: O(1) */

```

# ruby

## Sweet Spot | memory O(1) and time O(n)

```ruby
# @param {String} s
# @return {Integer}
def longest_valid_parentheses(s)
    left = right = maxlength = 0
    s.each_char do |c|
        if c == '(' then left += 1 else right += 1 end
        if left == right
            maxlength = [maxlength, 2 * right].max
        elsif right > left
            left = right = 0
        end
    end
    left = right = 0
    s.reverse.each_char do |c|
        if c == '(' then left += 1 else right += 1 end
        if left == right
            maxlength = [maxlength, 2 * left].max
        elsif left > right
            left = right = 0
        end
    end
    maxlength
end
# Time Complexity: O(n), Memory Complexity: O(1)

```

# php

## Sweet Spot | memory O(1) and time O(n)

```php
class Solution {

    /**
     * @param String $s
     * @return Integer
     */
    function longestValidParentheses($s) {
        $left = $right = $maxlength = 0;
        $n = strlen($s);
        for ($i = 0; $i < $n; $i++) {
            if ($s[$i] == '(') $left++;
            else $right++;
            if ($left == $right) $maxlength = max($maxlength, 2 * $right);
            else if ($right > $left) $left = $right = 0;
        }
        $left = $right = 0;
        for ($i = $n - 1; $i >= 0; $i--) {
            if ($s[$i] == '(') $left++;
            else $right++;
            if ($left == $right) $maxlength = max($maxlength, 2 * $left);
            else if ($left > $right) $left = $right = 0;
        }
        return $maxlength;
    }
}
/* Time Complexity: O(n), Memory Complexity: O(1) */

```

# dart

## Sweet Spot | memory O(1) and time O(n)

```dart
import 'dart:math';

class Solution {
  int longestValidParentheses(String s) {
    int left = 0, right = 0, maxlength = 0;
    for (int i = 0; i < s.length; i++) {
      if (s[i] == '(') left++;
      else right++;
      if (left == right) maxlength = max(maxlength, 2 * right);
      else if (right > left) { left = 0; right = 0; }
    }
    left = 0; right = 0;
    for (int i = s.length - 1; i >= 0; i--) {
      if (s[i] == '(') left++;
      else right++;
      if (left == right) maxlength = max(maxlength, 2 * left);
      else if (left > right) { left = 0; right = 0; }
    }
    return maxlength;
  }
}
/* Time Complexity: O(n), Memory Complexity: O(1) */

```

# scala 3.3.1

## Sweet Spot | memory O(1) and time O(n)

```scala 3.3.1
object Solution {
    def longestValidParentheses(s: String): Int = {
        var left = 0
        var right = 0
        var maxlength = 0
        for (i <- 0 until s.length) {
            if (s(i) == '(') left += 1
            else right += 1
            if (left == right) maxlength = math.max(maxlength, 2 * right)
            else if (right > left) { left = 0; right = 0 }
        }
        left = 0; right = 0
        for (i <- (s.length - 1) to 0 by -1) {
            if (s(i) == '(') left += 1
            else right += 1
            if (left == right) maxlength = math.max(maxlength, 2 * left)
            else if (left > right) { left = 0; right = 0 }
        }
        maxlength
    }
}
/* Time Complexity: O(n), Memory Complexity: O(1) */

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot | memory O(n) and time O(n)

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec longest_valid_parentheses(s :: String.t) :: integer
  def longest_valid_parentheses(s) do
    chars = String.to_charlist(s)
    
    forward = solve(chars, 0, 0, 0, ?()
    backward = solve(Enum.reverse(chars), 0, 0, 0, ?))
    
    max(forward, backward)
  end

  defp solve([], _left, _right, max_len, _open_char), do: max_len
  
  defp solve([char | rest], left, right, max_len, open_char) do
    {nl, nr} = if char == open_char, do: {left + 1, right}, else: {left, right + 1}
    
    cond do
      nl == nr ->
        solve(rest, nl, nr, max(max_len, 2 * nl), open_char)
      nr > nl ->
        solve(rest, 0, 0, max_len, open_char)
      true ->
        solve(rest, nl, nr, max_len, open_char)
    end
  end
  # Time Complexity: O(n), Memory Complexity: O(n)
end
```

# Erlang/OTP 26

## Sweet Spot | memory O(n) and time O(n)

```erlang/otp 26
-spec longest_valid_parentheses(S :: unicode:unicode_binary()) -> integer().
longest_valid_parentheses(S) ->
    Chars = binary_to_list(S),
    F = solve(Chars, 0, 0, 0, forward),
    B = solve(lists:reverse(Chars), 0, 0, 0, backward),
    if F > B -> F; true -> B end.

solve([], _, _, Max, _) -> Max;
solve([C|Rest], L, R, Max, Dir) ->
    {NL, NR} = case {Dir, C} of
        {forward, $(} -> {L+1, R};
        {forward, $)} -> {L, R+1};
        {backward, $)} -> {L, R+1};
        {backward, $(} -> {L+1, R}
    end,
    if
        NL == NR -> solve(Rest, NL, NR, erlang:max(Max, 2 * NL), Dir);
        (Dir == forward) and (NR > NL) -> solve(Rest, 0, 0, Max, Dir);
        (Dir == backward) and (NL > NR) -> solve(Rest, 0, 0, Max, Dir);
        true -> solve(Rest, NL, NR, Max, Dir)
    end.
% Time Complexity: O(n), Memory Complexity: O(n)

```

# Racket CS v8.15

## Sweet Spot | memory O(n) and time O(n)

```racket CS v8.15
(define/contract (longest-valid-parentheses s)
  (-> string? exact-integer?)
  (let ([chars (string->list s)])
    (define (solve lst l r m dir)
      (if (null? lst) m
          (let* ([c (car lst)]
                 [nl (if (char=? c #\() (+ l 1) l)]
                 [nr (if (char=? c #\)) (+ r 1) r)])
            (cond
              [(= nl nr) (solve (cdr lst) nl nr (max m (* 2 nl)) dir)]
              [(and (eq? dir 'f) (> nr nl)) (solve (cdr lst) 0 0 m dir)]
              [(and (eq? dir 'b) (> nl nr)) (solve (cdr lst) 0 0 m dir)]
              [else (solve (cdr lst) nl nr m dir)]))))
    (max (solve chars 0 0 0 'f)
         (solve (reverse chars) 0 0 0 'b))))
; Time Complexity: O(n), Memory Complexity: O(n)

```