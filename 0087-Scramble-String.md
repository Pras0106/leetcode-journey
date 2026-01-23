# C++

## Sweet Spot

```cpp
#include <string>
#include <vector>
#include <unordered_map>

using namespace std;

class Solution {
    unordered_map<string, bool> memo;
public:
    bool isScramble(string s1, string s2) {
        // Time Complexity: O(n^4)
        // Memory Complexity: O(n^4)
        if (s1 == s2) return true;
        if (s1.length() != s2.length()) return false;
        string key = s1 + "#" + s2;
        if (memo.count(key)) return memo[key];

        int n = s1.length();
        vector<int> count(26, 0);
        for (int i = 0; i < n; i++) {
            count[s1[i] - 'a']++;
            count[s2[i] - 'a']--;
        }
        for (int i = 0; i < 26; i++) {
            if (count[i] != 0) return memo[key] = false;
        }

        for (int i = 1; i < n; i++) {
            if ((isScramble(s1.substr(0, i), s2.substr(0, i)) && isScramble(s1.substr(i), s2.substr(i))) ||
                (isScramble(s1.substr(0, i), s2.substr(n - i)) && isScramble(s1.substr(i), s2.substr(0, n - i)))) {
                return memo[key] = true;
            }
        }
        return memo[key] = false;
    }
};

```

# java

## Sweet Spot

```java
import java.util.HashMap;
import java.util.Map;

class Solution {
    Map<String, Boolean> memo = new HashMap<>();

    public boolean isScramble(String s1, String s2) {
        // Time Complexity: O(n^4)
        // Memory Complexity: O(n^4)
        if (s1.equals(s2)) return true;
        String key = s1 + "#" + s2;
        if (memo.containsKey(key)) return memo.get(key);

        int n = s1.length();
        int[] count = new int[26];
        for (int i = 0; i < n; i++) {
            count[s1.charAt(i) - 'a']++;
            count[s2.charAt(i) - 'a']--;
        }
        for (int c : count) {
            if (c != 0) {
                memo.put(key, false);
                return false;
            }
        }

        for (int i = 1; i < n; i++) {
            if ((isScramble(s1.substring(0, i), s2.substring(0, i)) && isScramble(s1.substring(i), s2.substring(i))) ||
                (isScramble(s1.substring(0, i), s2.substring(n - i)) && isScramble(s1.substring(i), s2.substring(0, n - i)))) {
                memo.put(key, true);
                return true;
            }
        }
        memo.put(key, false);
        return false;
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def __init__(self):
        self.memo = {}

    def isScramble(self, s1: str, s2: str) -> bool:
        # Time Complexity: O(n^4)
        # Memory Complexity: O(n^4)
        if s1 == s2:
            return True
        key = (s1, s2)
        if key in self.memo:
            return self.memo[key]
        
        if sorted(s1) != sorted(s2):
            self.memo[key] = False
            return False
        
        n = len(s1)
        for i in range(1, n):
            if (self.isScramble(s1[:i], s2[:i]) and self.isScramble(s1[i:], s2[i:])) or \
               (self.isScramble(s1[:i], s2[n-i:]) and self.isScramble(s1[i:], s2[:n-i])):
                self.memo[key] = True
                return True
        
        self.memo[key] = False
        return False

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def __init__(self):
        self.memo = {}

    def isScramble(self, s1, s2):
        # Time Complexity: O(n^4)
        # Memory Complexity: O(n^4)
        if s1 == s2:
            return True
        key = s1 + "#" + s2
        if key in self.memo:
            return self.memo[key]
        
        if sorted(s1) != sorted(s2):
            self.memo[key] = False
            return False
            
        n = len(s1)
        for i in range(1, n):
            if (self.isScramble(s1[:i], s2[:i]) and self.isScramble(s1[i:], s2[i:])) or \
               (self.isScramble(s1[:i], s2[n-i:]) and self.isScramble(s1[i:], s2[:n-i])):
                self.memo[key] = True
                return True
        
        self.memo[key] = False
        return False

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {string} s1
 * @param {string} s2
 * @return {boolean}
 */
var isScramble = function(s1, s2, memo = {}) {
    // Time Complexity: O(n^4)
    // Memory Complexity: O(n^4)
    if (s1 === s2) return true;
    const key = s1 + "#" + s2;
    if (memo[key] !== undefined) return memo[key];

    const n = s1.length;
    const count = new Array(26).fill(0);
    for (let i = 0; i < n; i++) {
        count[s1.charCodeAt(i) - 97]++;
        count[s2.charCodeAt(i) - 97]--;
    }
    for (let i = 0; i < 26; i++) {
        if (count[i] !== 0) return memo[key] = false;
    }

    for (let i = 1; i < n; i++) {
        if ((isScramble(s1.substring(0, i), s2.substring(0, i), memo) && isScramble(s1.substring(i), s2.substring(i), memo)) ||
            (isScramble(s1.substring(0, i), s2.substring(n - i), memo) && isScramble(s1.substring(i), s2.substring(0, n - i), memo))) {
            return memo[key] = true;
        }
    }
    return memo[key] = false;
};

```

# Typescript

## Sweet Spot

```typescript
function isScramble(s1: string, s2: string, memo: Map<string, boolean> = new Map()): boolean {
    // Time Complexity: O(n^4)
    // Memory Complexity: O(n^4)
    if (s1 === s2) return true;
    const key = s1 + "#" + s2;
    if (memo.has(key)) return memo.get(key)!;

    const n = s1.length;
    const count = new Array(26).fill(0);
    for (let i = 0; i < n; i++) {
        count[s1.charCodeAt(i) - 97]++;
        count[s2.charCodeAt(i) - 97]--;
    }
    if (count.some(c => c !== 0)) {
        memo.set(key, false);
        return false;
    }

    for (let i = 1; i < n; i++) {
        if ((isScramble(s1.substring(0, i), s2.substring(0, i), memo) && isScramble(s1.substring(i), s2.substring(i), memo)) ||
            (isScramble(s1.substring(0, i), s2.substring(n - i), memo) && isScramble(s1.substring(i), s2.substring(0, n - i), memo))) {
            memo.set(key, true);
            return true;
        }
    }
    memo.set(key, false);
    return false;
};

```

# C#

## Sweet Spot

```c#
using System;
using System.Collections.Generic;

public class Solution {
    private Dictionary<string, bool> memo = new Dictionary<string, bool>();

    public bool IsScramble(string s1, string s2) {
        // Time Complexity: O(n^4)
        // Memory Complexity: O(n^4)
        if (s1 == s2) return true;
        string key = s1 + "#" + s2;
        if (memo.ContainsKey(key)) return memo[key];

        int n = s1.Length;
        int[] count = new int[26];
        for (int i = 0; i < n; i++) {
            count[s1[i] - 'a']++;
            count[s2[i] - 'a']--;
        }
        for (int i = 0; i < 26; i++) {
            if (count[i] != 0) return memo[key] = false;
        }

        for (int i = 1; i < n; i++) {
            if ((IsScramble(s1.Substring(0, i), s2.Substring(0, i)) && IsScramble(s1.Substring(i), s2.Substring(i))) ||
                (IsScramble(s1.Substring(0, i), s2.Substring(n - i)) && IsScramble(s1.Substring(i), s2.Substring(0, n - i)))) {
                return memo[key] = true;
            }
        }
        return memo[key] = false;
    }
}

```

# C

## Sweet Spot

```c
#include <stdbool.h>
#include <string.h>

bool isScramble(char* s1, char* s2) {
    // Time Complexity: O(n^4)
    // Memory Complexity: O(n^4)
    int n = strlen(s1);
    bool dp[n + 1][n][n];
    memset(dp, 0, sizeof(dp));

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            if (s1[i] == s2[j]) dp[1][i][j] = true;
        }
    }

    for (int len = 2; len <= n; len++) {
        for (int i = 0; i <= n - len; i++) {
            for (int j = 0; j <= n - len; j++) {
                for (int k = 1; k < len; k++) {
                    if ((dp[k][i][j] && dp[len - k][i + k][j + k]) ||
                        (dp[k][i][j + len - k] && dp[len - k][i + k][j])) {
                        dp[len][i][j] = true;
                        break;
                    }
                }
            }
        }
    }
    return dp[n][0][0];
}

```

# Go

## Sweet Spot

```go
func isScramble(s1 string, s2 string) bool {
    // Time Complexity: O(n^4)
    // Space Complexity: O(n^4)
    memo := make(map[string]bool)
    var solve func(string, string) bool
    solve = func(a, b string) bool {
        if a == b {
            return true
        }
        key := a + "#" + b
        if res, ok := memo[key]; ok {
            return res
        }

        count := make([]int, 26)
        for i := 0; i < len(a); i++ {
            count[a[i]-'a']++
            count[b[i]-'a']--
        }
        for _, v := range count {
            if v != 0 {
                memo[key] = false
                return false
            }
        }

        for i := 1; i < len(a); i++ {
            if (solve(a[:i], b[:i]) && solve(a[i:], b[i:])) ||
                (solve(a[:i], b[len(a)-i:]) && solve(a[i:], b[:len(a)-i])) {
                memo[key] = true
                return true
            }
        }
        memo[key] = false
        return false
    }
    return solve(s1, s2)
}
```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    private val memo = mutableMapOf<String, Boolean>()

    fun isScramble(s1: String, s2: String): Boolean {
        // Time Complexity: O(n^4)
        // Memory Complexity: O(n^4)
        if (s1 == s2) return true
        val key = "$s1#$s2"
        if (memo.containsKey(key)) return memo[key]!!

        val n = s1.length
        val count = IntArray(26)
        for (i in 0 until n) {
            count[s1[i] - 'a']++
            count[s2[i] - 'a']--
        }
        if (count.any { it != 0 }) {
            memo[key] = false
            return false
        }

        for (i in 1 until n) {
            if ((isScramble(s1.substring(0, i), s2.substring(0, i)) && isScramble(s1.substring(i), s2.substring(i))) ||
                (isScramble(s1.substring(0, i), s2.substring(n - i)) && isScramble(s1.substring(i), s2.substring(0, n - i)))) {
                memo[key] = true
                return true
            }
        }
        memo[key] = false
        return false
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    var memo = [String: Bool]()

    func isScramble(_ s1: String, _ s2: String) -> Bool {
        // Time Complexity: O(n^4)
        // Memory Complexity: O(n^4)
        if s1 == s2 { return true }
        let key = s1 + "#" + s2
        if let val = memo[key] { return val }

        let n = s1.count
        var count = Array(repeating: 0, count: 26)
        let a1 = Array(s1.utf8), a2 = Array(s2.utf8)
        
        for i in 0..<n {
            count[Int(a1[i]) - 97] += 1
            count[Int(a2[i]) - 97] -= 1
        }
        if count.contains(where: { $0 != 0 }) {
            memo[key] = false
            return false
        }

        for i in 1..<n {
            let s1_0_i = String(s1.prefix(i))
            let s1_i_n = String(s1.suffix(n - i))
            let s2_0_i = String(s2.prefix(i))
            let s2_i_n = String(s2.suffix(n - i))
            let s2_0_ni = String(s2.prefix(n - i))
            let s2_ni_n = String(s2.suffix(i))

            if (isScramble(s1_0_i, s2_0_i) && isScramble(s1_i_n, s2_i_n)) ||
               (isScramble(s1_0_i, s2_ni_n) && isScramble(s1_i_n, s2_0_ni)) {
                memo[key] = true
                return true
            }
        }
        memo[key] = false
        return false
    }
}

```

# rust

## Sweet Spot

```rust
use std::collections::HashMap;

impl Solution {
    pub fn is_scramble(s1: String, s2: String) -> bool {
        // Time Complexity: O(n^4)
        // Memory Complexity: O(n^4)
        let mut memo = HashMap::new();
        Self::solve(&s1, &s2, &mut memo)
    }

    fn solve(s1: &str, s2: &str, memo: &mut HashMap<(String, String), bool>) -> bool {
        if s1 == s2 { return true; }
        if let Some(&res) = memo.get(&(s1.to_string(), s2.to_string())) { return res; }

        let n = s1.len();
        let mut count = [0; 26];
        for (b1, b2) in s1.bytes().zip(s2.bytes()) {
            count[(b1 - b'a') as usize] += 1;
            count[(b2 - b'a') as usize] -= 1;
        }

        if count.iter().any(|&c| c != 0) {
            memo.insert((s1.to_string(), s2.to_string()), false);
            return false;
        }

        for i in 1..n {
            if (Self::solve(&s1[..i], &s2[..i], memo) && Self::solve(&s1[i..], &s2[i..], memo)) ||
               (Self::solve(&s1[..i], &s2[n-i..], memo) && Self::solve(&s1[i..], &s2[..n-i], memo)) {
                memo.insert((s1.to_string(), s2.to_string()), true);
                return true;
            }
        }
        memo.insert((s1.to_string(), s2.to_string()), false);
        false
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {String} s1
# @param {String} s2
# @return {Boolean}
def is_scramble(s1, s2, memo = {})
    # Time Complexity: O(n^4)
    # Memory Complexity: O(n^4)
    return true if s1 == s2
    key = s1 + "#" + s2
    return memo[key] if memo.key?(key)

    return memo[key] = false if s1.chars.sort != s2.chars.sort

    n = s1.length
    (1...n).each do |i|
        if (is_scramble(s1[0...i], s2[0...i], memo) && is_scramble(s1[i..-1], s2[i..-1], memo)) ||
           (is_scramble(s1[0...i], s2[n-i..-1], memo) && is_scramble(s1[i..-1], s2[0...n-i], memo))
            return memo[key] = true
        end
    end
    memo[key] = false
end

```

# php

## Sweet Spot

```php
class Solution {
    private $memo = [];

    /**
     * @param String $s1
     * @param String $s2
     * @return Boolean
     */
    function isScramble($s1, $s2) {
        // Time Complexity: O(n^4)
        // Memory Complexity: O(n^4)
        if ($s1 === $s2) return true;
        $key = $s1 . "#" . $s2;
        if (isset($this->memo[$key])) return $this->memo[$key];

        $n = strlen($s1);
        $count = array_fill(0, 26, 0);
        for ($i = 0; $i < $n; $i++) {
            $count[ord($s1[$i]) - 97]++;
            $count[ord($s2[$i]) - 97]--;
        }
        for ($i = 0; $i < 26; $i++) {
            if ($count[$i] !== 0) return $this->memo[$key] = false;
        }

        for ($i = 1; $i < $n; $i++) {
            if (($this->isScramble(substr($s1, 0, $i), substr($s2, 0, $i)) && $this->isScramble(substr($s1, $i), substr($s2, $i))) ||
                ($this->isScramble(substr($s1, 0, $i), substr($s2, $n - $i)) && $this->isScramble(substr($s1, $i), substr($s2, 0, $n - $i)))) {
                return $this->memo[$key] = true;
            }
        }
        return $this->memo[$key] = false;
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  Map<String, bool> memo = {};

  bool isScramble(String s1, String s2) {
    // Time Complexity: O(n^4)
    // Memory Complexity: O(n^4)
    if (s1 == s2) return true;
    String key = s1 + "#" + s2;
    if (memo.containsKey(key)) return memo[key]!;

    int n = s1.length;
    List<int> count = List.filled(26, 0);
    for (int i = 0; i < n; i++) {
      count[s1.codeUnitAt(i) - 97]++;
      count[s2.codeUnitAt(i) - 97]--;
    }
    if (count.any((c) => c != 0)) {
      memo[key] = false;
      return false;
    }

    for (int i = 1; i < n; i++) {
      if ((isScramble(s1.substring(0, i), s2.substring(0, i)) && isScramble(s1.substring(i), s2.substring(i))) ||
          (isScramble(s1.substring(0, i), s2.substring(n - i)) && isScramble(s1.substring(i), s2.substring(0, n - i)))) {
        memo[key] = true;
        return true;
      }
    }
    memo[key] = false;
    return false;
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
import scala.collection.mutable
import scala.util.boundary, boundary.break

object Solution {
    val memo = mutable.Map[String, Boolean]()

    def isScramble(s1: String, s2: String): Boolean = {
        // Time Complexity: O(n^4)
        // Memory Complexity: O(n^4)
        boundary {
            if (s1 == s2) break(true)
            val key = s1 + "#" + s2
            if (memo.contains(key)) break(memo(key))

            val n = s1.length
            if (s1.sorted != s2.sorted) {
                memo(key) = false
                break(false)
            }

            for (i <- 1 until n) {
                if ((isScramble(s1.substring(0, i), s2.substring(0, i)) && isScramble(s1.substring(i), s2.substring(i))) ||
                    (isScramble(s1.substring(0, i), s2.substring(n - i)) && isScramble(s1.substring(i), s2.substring(0, n - i)))) {
                    memo(key) = true
                    break(true)
                }
            }
            memo(key) = false
            false
        }
    }
}
```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec is_scramble(s1 :: String.t, s2 :: String.t) :: boolean
  def is_scramble(s1, s2) do
    # Time Complexity: O(n^4)
    # Memory Complexity: O(n^4)
    Process.put(:memo, %{})
    solve(s1, s2)
  end

  defp solve(s1, s2) do
    memo = Process.get(:memo)
    cond do
      s1 == s2 -> true
      Map.has_key?(memo, {s1, s2}) -> Map.get(memo, {s1, s2})
      String.length(s1) != String.length(s2) -> false
      Enum.sort(String.to_charlist(s1)) != Enum.sort(String.to_charlist(s2)) -> 
        Process.put(:memo, Map.put(memo, {s1, s2}, false))
        false
      true ->
        n = String.length(s1)
        res = Enum.any?(1..(n-1), fn i ->
          (solve(String.slice(s1, 0, i), String.slice(s2, 0, i)) and solve(String.slice(s1, i..-1), String.slice(s2, i..-1))) or
          (solve(String.slice(s1, 0, i), String.slice(s2, (n-i)..-1)) and solve(String.slice(s1, i..-1), String.slice(s2, 0, n-i)))
        end)
        Process.put(:memo, Map.put(Process.get(:memo), {s1, s2}, res))
        res
    end
  end
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec is_scramble(S1 :: unicode:unicode_binary(), S2 :: unicode:unicode_binary()) -> boolean().
is_scramble(S1, S2) ->
  % Time Complexity: O(n^4)
  % Memory Complexity: O(n^4)
  put(memo, #{}),
  solve(S1, S2).

solve(S1, S2) ->
  Memo = get(memo),
  case maps:find({S1, S2}, Memo) of
    {ok, Res} -> Res;
    error ->
      Result = if
        S1 =:= S2 -> true;
        true ->
          L1 = binary_to_list(S1),
          L2 = binary_to_list(S2),
          case lists:sort(L1) =:= lists:sort(L2) of
            false -> false;
            true ->
              N = byte_size(S1),
              check_splits(S1, S2, 1, N)
          end
      end,
      put(memo, maps:put({S1, S2}, Result, get(memo))),
      Result
  end.

check_splits(_S1, _S2, N, N) -> false;
check_splits(S1, S2, I, N) ->
  S1L = binary:part(S1, 0, I),
  S1R = binary:part(S1, I, N - I),
  S2L = binary:part(S2, 0, I),
  S2R = binary:part(S2, I, N - I),
  S2RL = binary:part(S2, 0, N - I),
  S2RR = binary:part(S2, N - I, I),
  case (solve(S1L, S2L) andalso solve(S1R, S2R)) orelse (solve(S1L, S2RR) andalso solve(S1R, S2RL)) of
    true -> true;
    false -> check_splits(S1, S2, I + 1, N)
  end.

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (is-scramble s1 s2)
  (-> string? string? boolean?)
  ; Time Complexity: O(n^4)
  ; Memory Complexity: O(n^4)
  (define memo (make-hash))
  (define (solve a b)
    (cond
      [(equal? a b) #t]
      [(hash-has-key? memo (cons a b)) (hash-ref memo (cons a b))]
      [(not (equal? (sort (string->list a) char<?) (sort (string->list b) char<?)))
       (hash-set! memo (cons a b) #f) #f]
      [else
       (let ([n (string-length a)])
         (define res
           (for/or ([i (in-range 1 n)])
             (or (and (solve (substring a 0 i) (substring b 0 i))
                      (solve (substring a i n) (substring b i n)))
                 (and (solve (substring a 0 i) (substring b (- n i) n))
                      (solve (substring a i n) (substring b 0 (- n i)))))))
         (hash-set! memo (cons a b) res)
         res)]))
  (solve s1 s2))

```