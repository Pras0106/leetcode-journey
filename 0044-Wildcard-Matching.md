# cpp

## Sweet Spot

```cpp
class Solution {
public:
    bool isMatch(string s, string p) {
        int sLen = s.length(), pLen = p.length();
        int sIdx = 0, pIdx = 0, lastWildcardIdx = -1, sBacktrackIdx = -1;
        while (sIdx < sLen) {
            if (pIdx < pLen && (p[pIdx] == '?' || p[pIdx] == s[sIdx])) {
                sIdx++;
                pIdx++;
            } else if (pIdx < pLen && p[pIdx] == '*') {
                lastWildcardIdx = pIdx;
                sBacktrackIdx = sIdx;
                pIdx++;
            } else if (lastWildcardIdx != -1) {
                pIdx = lastWildcardIdx + 1;
                sBacktrackIdx++;
                sIdx = sBacktrackIdx;
            } else {
                return false;
            }
        }
        while (pIdx < pLen && p[pIdx] == '*') {
            pIdx++;
        }
        return pIdx == pLen;
    }
    // Time Complexity: O(N * M) worst case, O(N + M) average
    // Memory Complexity: O(1)
};

```

# java

## Sweet Spot

```java
class Solution {
    public boolean isMatch(String s, String p) {
        int sLen = s.length(), pLen = p.length();
        int sIdx = 0, pIdx = 0, lastWildcardIdx = -1, sBacktrackIdx = -1;
        while (sIdx < sLen) {
            if (pIdx < pLen && (p.charAt(pIdx) == '?' || p.charAt(pIdx) == s.charAt(sIdx))) {
                sIdx++;
                pIdx++;
            } else if (pIdx < pLen && p.charAt(pIdx) == '*') {
                lastWildcardIdx = pIdx;
                sBacktrackIdx = sIdx;
                pIdx++;
            } else if (lastWildcardIdx != -1) {
                pIdx = lastWildcardIdx + 1;
                sBacktrackIdx++;
                sIdx = sBacktrackIdx;
            } else {
                return false;
            }
        }
        while (pIdx < pLen && p.charAt(pIdx) == '*') {
            pIdx++;
        }
        return pIdx == pLen;
    }
    // Time Complexity: O(N * M) worst case, O(N + M) average
    // Memory Complexity: O(1)
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def isMatch(self, s: str, p: str) -> bool:
        s_len, p_len = len(s), len(p)
        s_idx = p_idx = 0
        last_wildcard = -1
        s_backtrack = -1
        while s_idx < s_len:
            if p_idx < p_len and (p[p_idx] == '?' or p[p_idx] == s[s_idx]):
                s_idx += 1
                p_idx += 1
            elif p_idx < p_len and p[p_idx] == '*':
                last_wildcard = p_idx
                s_backtrack = s_idx
                p_idx += 1
            elif last_wildcard != -1:
                p_idx = last_wildcard + 1
                s_backtrack += 1
                s_idx = s_backtrack
            else:
                return False
        return all(x == '*' for x in p[p_idx:])
        # Time Complexity: O(N * M) worst case, O(N + M) average
        # Memory Complexity: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def isMatch(self, s, p):
        """
        :type s: str
        :type p: str
        :rtype: bool
        """
        s_len, p_len = len(s), len(p)
        s_idx = p_idx = 0
        last_wildcard = -1
        s_backtrack = -1
        while s_idx < s_len:
            if p_idx < p_len and (p[p_idx] == '?' or p[p_idx] == s[s_idx]):
                s_idx += 1
                p_idx += 1
            elif p_idx < p_len and p[p_idx] == '*':
                last_wildcard = p_idx
                s_backtrack = s_idx
                p_idx += 1
            elif last_wildcard != -1:
                p_idx = last_wildcard + 1
                s_backtrack += 1
                s_idx = s_backtrack
            else:
                return False
        while p_idx < p_len and p[p_idx] == '*':
            p_idx += 1
        return p_idx == p_len
        # Time Complexity: O(N * M) worst case, O(N + M) average
        # Memory Complexity: O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {string} s
 * @param {string} p
 * @return {boolean}
 */
var isMatch = function(s, p) {
    let sLen = s.length, pLen = p.length;
    let sIdx = 0, pIdx = 0, lastWildcardIdx = -1, sBacktrackIdx = -1;
    while (sIdx < sLen) {
        if (pIdx < pLen && (p[pIdx] === '?' || p[pIdx] === s[sIdx])) {
            sIdx++;
            pIdx++;
        } else if (pIdx < pLen && p[pIdx] === '*') {
            lastWildcardIdx = pIdx;
            sBacktrackIdx = sIdx;
            pIdx++;
        } else if (lastWildcardIdx !== -1) {
            pIdx = lastWildcardIdx + 1;
            sBacktrackIdx++;
            sIdx = sBacktrackIdx;
        } else {
            return false;
        }
    }
    while (pIdx < pLen && p[pIdx] === '*') {
        pIdx++;
    }
    return pIdx === pLen;
    // Time Complexity: O(N * M) worst case, O(N + M) average
    // Memory Complexity: O(1)
};

```

# Typescript

## Sweet Spot

```typescript
function isMatch(s: string, p: string): boolean {
    let sLen = s.length, pLen = p.length;
    let sIdx = 0, pIdx = 0, lastWildcardIdx = -1, sBacktrackIdx = -1;
    while (sIdx < sLen) {
        if (pIdx < pLen && (p[pIdx] === '?' || p[pIdx] === s[sIdx])) {
            sIdx++;
            pIdx++;
        } else if (pIdx < pLen && p[pIdx] === '*') {
            lastWildcardIdx = pIdx;
            sBacktrackIdx = sIdx;
            pIdx++;
        } else if (lastWildcardIdx !== -1) {
            pIdx = lastWildcardIdx + 1;
            sBacktrackIdx++;
            sIdx = sBacktrackIdx;
        } else {
            return false;
        }
    }
    while (pIdx < pLen && p[pIdx] === '*') {
        pIdx++;
    }
    return pIdx === pLen;
    // Time Complexity: O(N * M) worst case, O(N + M) average
    // Memory Complexity: O(1)
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public bool IsMatch(string s, string p) {
        int sLen = s.Length, pLen = p.Length;
        int sIdx = 0, pIdx = 0, lastWildcardIdx = -1, sBacktrackIdx = -1;
        while (sIdx < sLen) {
            if (pIdx < pLen && (p[pIdx] == '?' || p[pIdx] == s[sIdx])) {
                sIdx++;
                pIdx++;
            } else if (pIdx < pLen && p[pIdx] == '*') {
                lastWildcardIdx = pIdx;
                sBacktrackIdx = sIdx;
                pIdx++;
            } else if (lastWildcardIdx != -1) {
                pIdx = lastWildcardIdx + 1;
                sBacktrackIdx++;
                sIdx = sBacktrackIdx;
            } else {
                return false;
            }
        }
        while (pIdx < pLen && p[pIdx] == '*') {
            pIdx++;
        }
        return pIdx == pLen;
    }
    // Time Complexity: O(N * M) worst case, O(N + M) average
    // Memory Complexity: O(1)
}

```

# C

## Sweet Spot

```c
bool isMatch(char* s, char* p) {
    int sIdx = 0, pIdx = 0, lastWildcardIdx = -1, sBacktrackIdx = -1;
    while (s[sIdx] != '\0') {
        if (p[pIdx] != '\0' && (p[pIdx] == '?' || p[pIdx] == s[sIdx])) {
            sIdx++;
            pIdx++;
        } else if (p[pIdx] == '*') {
            lastWildcardIdx = pIdx;
            sBacktrackIdx = sIdx;
            pIdx++;
        } else if (lastWildcardIdx != -1) {
            pIdx = lastWildcardIdx + 1;
            sBacktrackIdx++;
            sIdx = sBacktrackIdx;
        } else {
            return false;
        }
    }
    while (p[pIdx] == '*') {
        pIdx++;
    }
    return p[pIdx] == '\0';
    /* Time Complexity: O(N * M) worst case, O(N + M) average */
    /* Memory Complexity: O(1) */
}

```

# Go

## Sweet Spot

```go
func isMatch(s string, p string) bool {
    sIdx, pIdx, lastWildcardIdx, sBacktrackIdx := 0, 0, -1, -1
    sLen, pLen := len(s), len(p)
    for sIdx < sLen {
        if pIdx < pLen && (p[pIdx] == '?' || p[pIdx] == s[sIdx]) {
            sIdx++
            pIdx++
        } else if pIdx < pLen && p[pIdx] == '*' {
            lastWildcardIdx = pIdx
            sBacktrackIdx = sIdx
            pIdx++
        } else if lastWildcardIdx != -1 {
            pIdx = lastWildcardIdx + 1
            sBacktrackIdx++
            sIdx = sBacktrackIdx
        } else {
            return false
        }
    }
    for pIdx < pLen && p[pIdx] == '*' {
        pIdx++
    }
    return pIdx == pLen
    // Time Complexity: O(N * M) worst case, O(N + M) average
    // Memory Complexity: O(1)
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun isMatch(s: String, p: String): Boolean {
        val sLen = s.length
        val pLen = p.length
        var sIdx = 0
        var pIdx = 0
        var lastWildcardIdx = -1
        var sBacktrackIdx = -1
        while (sIdx < sLen) {
            if (pIdx < pLen && (p[pIdx] == '?' || p[pIdx] == s[sIdx])) {
                sIdx++
                pIdx++
            } else if (pIdx < pLen && p[pIdx] == '*') {
                lastWildcardIdx = pIdx
                sBacktrackIdx = sIdx
                pIdx++
            } else if (lastWildcardIdx != -1) {
                pIdx = lastWildcardIdx + 1
                sBacktrackIdx++
                sIdx = sBacktrackIdx
            } else {
                return false
            }
        }
        var currentPIdx = pIdx
        while (currentPIdx < pLen && p[currentPIdx] == '*') {
            currentPIdx++
        }
        return currentPIdx == pLen
    }
    // Time Complexity: O(N * M) worst case, O(N + M) average
    // Memory Complexity: O(1)
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func isMatch(_ s: String, _ p: String) -> Bool {
        let sChars = Array(s)
        let pChars = Array(p)
        var sIdx = 0
        var pIdx = 0
        var lastWildcardIdx = -1
        var sBacktrackIdx = -1
        while sIdx < sChars.count {
            if pIdx < pChars.count && (pChars[pIdx] == "?" || pChars[pIdx] == sChars[sIdx]) {
                sIdx += 1
                pIdx += 1
            } else if pIdx < pChars.count && pChars[pIdx] == "*" {
                lastWildcardIdx = pIdx
                sBacktrackIdx = sIdx
                pIdx += 1
            } else if lastWildcardIdx != -1 {
                pIdx = lastWildcardIdx + 1
                sBacktrackIdx += 1
                sIdx = sBacktrackIdx
            } else {
                return false
            }
        }
        while pIdx < pChars.count && pChars[pIdx] == "*" {
            pIdx += 1
        }
        return pIdx == pChars.count
    }
    // Time Complexity: O(N * M) worst case, O(N + M) average
    // Memory Complexity: O(N + M) due to Array conversion in Swift string indexing
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn is_match(s: String, p: String) -> bool {
        let s_bytes = s.as_bytes();
        let p_bytes = p.as_bytes();
        let mut s_idx = 0;
        let mut p_idx = 0;
        let mut last_wildcard = -1;
        let mut s_backtrack = -1;
        while s_idx < s_bytes.len() {
            if p_idx < p_bytes.len() && (p_bytes[p_idx] == b'?' || p_bytes[p_idx] == s_bytes[s_idx]) {
                s_idx += 1;
                p_idx += 1;
            } else if p_idx < p_bytes.len() && p_bytes[p_idx] == b'*' {
                last_wildcard = p_idx as i32;
                s_backtrack = s_idx as i32;
                p_idx += 1;
            } else if last_wildcard != -1 {
                p_idx = (last_wildcard + 1) as usize;
                s_backtrack += 1;
                s_idx = s_backtrack as usize;
            } else {
                return false;
            }
        }
        while p_idx < p_bytes.len() && p_bytes[p_idx] == b'*' {
            p_idx += 1;
        }
        p_idx == p_bytes.len()
    }
    // Time Complexity: O(N * M) worst case, O(N + M) average
    // Memory Complexity: O(1)
}

```

# ruby

## Sweet Spot

```ruby
# @param {String} s
# @param {String} p
# @return {Boolean}
def is_match(s, p)
    s_len, p_len = s.length, p.length
    s_idx = p_idx = 0
    last_wildcard = -1
    s_backtrack = -1
    while s_idx < s_len
        if p_idx < p_len && (p[p_idx] == '?' || p[p_idx] == s[s_idx])
            s_idx += 1
            p_idx += 1
        elsif p_idx < p_len && p[p_idx] == '*'
            last_wildcard = p_idx
            s_backtrack = s_idx
            p_idx += 1
        elsif last_wildcard != -1
            p_idx = last_wildcard + 1
            s_backtrack += 1
            s_idx = s_backtrack
        else
            return false
        end
    end
    while p_idx < p_len && p[p_idx] == '*'
        p_idx += 1
    end
    p_idx == p_len
    # Time Complexity: O(N * M) worst case, O(N + M) average
    # Memory Complexity: O(1)
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param String $s
     * @param String $p
     * @return Boolean
     */
    function isMatch($s, $p) {
        $sLen = strlen($s);
        $pLen = strlen($p);
        $sIdx = 0;
        $pIdx = 0;
        $lastWildcardIdx = -1;
        $sBacktrackIdx = -1;
        while ($sIdx < $sLen) {
            if ($pIdx < $pLen && ($p[$pIdx] === '?' || $p[$pIdx] === $s[$sIdx])) {
                $sIdx++;
                $pIdx++;
            } else if ($pIdx < $pLen && $p[$pIdx] === '*') {
                $lastWildcardIdx = $pIdx;
                $sBacktrackIdx = $sIdx;
                $pIdx++;
            } else if ($lastWildcardIdx !== -1) {
                $pIdx = $lastWildcardIdx + 1;
                $sBacktrackIdx++;
                $sIdx = $sBacktrackIdx;
            } else {
                return false;
            }
        }
        while ($pIdx < $pLen && $p[$pIdx] === '*') {
            $pIdx++;
        }
        return $pIdx === $pLen;
    }
    // Time Complexity: O(N * M) worst case, O(N + M) average
    // Memory Complexity: O(1)
}

```

# dart

## Sweet Spot

```dart
class Solution {
  bool isMatch(String s, String p) {
    int sLen = s.length;
    int pLen = p.length;
    int sIdx = 0;
    int pIdx = 0;
    int lastWildcardIdx = -1;
    int sBacktrackIdx = -1;
    while (sIdx < sLen) {
      if (pIdx < pLen && (p[pIdx] == '?' || p[pIdx] == s[sIdx])) {
        sIdx++;
        pIdx++;
      } else if (pIdx < pLen && p[pIdx] == '*') {
        lastWildcardIdx = pIdx;
        sBacktrackIdx = sIdx;
        pIdx++;
      } else if (lastWildcardIdx != -1) {
        pIdx = lastWildcardIdx + 1;
        sBacktrackIdx++;
        sIdx = sBacktrackIdx;
      } else {
        return false;
      }
    }
    while (pIdx < pLen && p[pIdx] == '*') {
      pIdx++;
    }
    return pIdx == pLen;
  }
  // Time Complexity: O(N * M) worst case, O(N + M) average
  // Memory Complexity: O(1)
}

```

# scala  3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def isMatch(s: String, p: String): Boolean = {
        val sLen = s.length
        val pLen = p.length
        var sIdx = 0
        var pIdx = 0
        var lastWildcardIdx = -1
        var sBacktrackIdx = -1
        while (sIdx < sLen) {
            if (pIdx < pLen && (p(pIdx) == '?' || p(pIdx) == s(sIdx))) {
                sIdx += 1
                pIdx += 1
            } else if (pIdx < pLen && p(pIdx) == '*') {
                lastWildcardIdx = pIdx
                sBacktrackIdx = sIdx
                pIdx += 1
            } else if (lastWildcardIdx != -1) {
                pIdx = lastWildcardIdx + 1
                sBacktrackIdx += 1
                sIdx = sBacktrackIdx
            } else {
                return false
            }
        }
        var curP = pIdx
        while (curP < pLen && p(curP) == '*') {
            curP += 1
        }
        curP == pLen
    }
    // Time Complexity: O(N * M) worst case, O(N + M) average
    // Memory Complexity: O(1)
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec is_match(s :: String.t, p :: String.t) :: boolean
  def is_match(s, p) do
    s_vec = s |> String.to_charlist() |> List.to_tuple()
    p_vec = p |> String.to_charlist() |> List.to_tuple()
    match(s_vec, p_vec, 0, 0, -1, -1)
  end

  defp match(s, p, si, pi, lw, sb) when si < tuple_size(s) do
    cond do
      pi < tuple_size(p) and (elem(p, pi) == ?? or elem(p, pi) == elem(s, si)) ->
        match(s, p, si + 1, pi + 1, lw, sb)
      pi < tuple_size(p) and elem(p, pi) == ?* ->
        match(s, p, si, pi + 1, pi, si)
      lw != -1 ->
        match(s, p, sb + 1, lw + 1, lw, sb + 1)
      true ->
        false
    end
  end

  defp match(_s, p, _si, pi, _lw, _sb) do
    trailing_stars(p, pi)
  end

  defp trailing_stars(p, pi) when pi < tuple_size(p) do
    if elem(p, pi) == ?* do
      trailing_stars(p, pi + 1)
    else
      false
    end
  end
  defp trailing_stars(p, pi), do: pi == tuple_size(p)
  # Time Complexity: O(N * M)
  # Memory Complexity: O(N + M) for tuple conversion
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec is_match(S :: unicode:unicode_binary(), P :: unicode:unicode_binary()) -> boolean().
is_match(S, P) ->
    SList = binary_to_list(S),
    PList = binary_to_list(P),
    SV = list_to_tuple(SList),
    PV = list_to_tuple(PList),
    match(SV, PV, 0, 0, -1, -1).

match(S, P, SI, PI, LW, SB) when SI < tuple_size(S) ->
    if
        PI < tuple_size(P), (element(PI + 1, P) == $? orelse element(PI + 1, P) == element(SI + 1, S)) ->
            match(S, P, SI + 1, PI + 1, LW, SB);
        PI < tuple_size(P), element(PI + 1, P) == $* ->
            match(S, P, SI, PI + 1, PI, SI);
        LW /= -1 ->
            match(S, P, SB + 1, LW + 1, LW, SB + 1);
        true ->
            false
    end;
match(_, P, _, PI, _, _) ->
    check_stars(P, PI).

check_stars(P, PI) when PI < tuple_size(P) ->
    case element(PI + 1, P) of
        $* -> check_stars(P, PI + 1);
        _ -> false
    end;
check_stars(P, PI) -> PI == tuple_size(P).
% Time Complexity: O(N * M)
% Memory Complexity: O(N + M)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (is-match s p)
  (-> string? string? boolean?)
  (let* ([s-vec (list->vector (string->list s))]
         [p-vec (list->vector (string->list p))]
         [s-len (vector-length s-vec)]
         [p-len (vector-length p-vec)])
    (let loop ([si 0] [pi 0] [lw -1] [sb -1])
      (cond
        [(< si s-len)
         (cond
           [(and (< pi p-len) (or (char=? (vector-ref p-vec pi) #\?) 
                                  (char=? (vector-ref p-vec pi) (vector-ref s-vec si))))
            (loop (+ si 1) (+ pi 1) lw sb)]
           [(and (< pi p-len) (char=? (vector-ref p-vec pi) #\*))
            (loop si (+ pi 1) pi si)]
           [(not (= lw -1))
            (loop (+ sb 1) (+ lw 1) lw (+ sb 1))]
           [else #f])]
        [else
         (let tail ([curr-p pi])
           (if (and (< curr-p p-len) (char=? (vector-ref p-vec curr-p) #\*))
               (tail (+ curr-p 1))
               (= curr-p p-len)))])))
  ; Time Complexity: O(N * M)
  ; Memory Complexity: O(N + M)
  )

```