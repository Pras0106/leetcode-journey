# cpp

## Sweet Spot

```cpp
class Solution {
public:
    bool isMatch(string s, string p) {
        int m = s.length(), n = p.length();
        vector<vector<bool>> dp(m + 1, vector<bool>(n + 1, false));
        dp[0][0] = true;
        for (int j = 2; j <= n; j++) {
            if (p[j - 1] == '*') dp[0][j] = dp[0][j - 2];
        }
        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (p[j - 1] == '*') {
                    dp[i][j] = dp[i][j - 2] || (dp[i - 1][j] && (s[i - 1] == p[j - 2] || p[j - 2] == '.'));
                } else {
                    dp[i][j] = dp[i - 1][j - 1] && (s[i - 1] == p[j - 1] || p[j - 1] == '.');
                }
            }
        }
        return dp[m][n];
    }
};
/* Time Complexity: O(m * n), Memory Complexity: O(m * n) */

```

# java

## Sweet Spot

```java
class Solution {
    public boolean isMatch(String s, String p) {
        int m = s.length(), n = p.length();
        boolean[][] dp = new boolean[m + 1][n + 1];
        dp[0][0] = true;
        for (int j = 2; j <= n; j++) {
            if (p.charAt(j - 1) == '*') dp[0][j] = dp[0][j - 2];
        }
        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (p.charAt(j - 1) == '*') {
                    dp[i][j] = dp[i][j - 2] || (dp[i - 1][j] && (s.charAt(i - 1) == p.charAt(j - 2) || p.charAt(j - 2) == '.'));
                } else {
                    dp[i][j] = dp[i - 1][j - 1] && (s.charAt(i - 1) == p.charAt(j - 1) || p.charAt(j - 1) == '.');
                }
            }
        }
        return dp[m][n];
    }
}
/* Time Complexity: O(m * n), Memory Complexity: O(m * n) */

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def isMatch(self, s: str, p: str) -> bool:
        m, n = len(s), len(p)
        dp = [[False] * (n + 1) for _ in range(m + 1)]
        dp[0][0] = True
        for j in range(2, n + 1):
            if p[j-1] == '*':
                dp[0][j] = dp[0][j-2]
        for i in range(1, m + 1):
            for j in range(1, n + 1):
                if p[j-1] == '*':
                    dp[i][j] = dp[i][j-2] or (dp[i-1][j] and (s[i-1] == p[j-2] or p[j-2] == '.'))
                else:
                    dp[i][j] = dp[i-1][j-1] and (s[i-1] == p[j-1] or p[j-1] == '.')
        return dp[m][n]
# Time Complexity: O(m * n), Memory Complexity: O(m * n)

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
        m, n = len(s), len(p)
        dp = [[False] * (n + 1) for _ in range(m + 1)]
        dp[0][0] = True
        for j in range(2, n + 1):
            if p[j-1] == '*':
                dp[0][j] = dp[0][j-2]
        for i in range(1, m + 1):
            for j in range(1, n + 1):
                if p[j-1] == '*':
                    dp[i][j] = dp[i][j-2] or (dp[i-1][j] and (s[i-1] == p[j-2] or p[j-2] == '.'))
                else:
                    dp[i][j] = dp[i-1][j-1] and (s[i-1] == p[j-1] or p[j-1] == '.')
        return dp[m][n]
# Time Complexity: O(m * n), Memory Complexity: O(m * n)

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
    const m = s.length, n = p.length;
    const dp = Array.from({ length: m + 1 }, () => Array(n + 1).fill(false));
    dp[0][0] = true;
    for (let j = 2; j <= n; j++) {
        if (p[j - 1] === '*') dp[0][j] = dp[0][j - 2];
    }
    for (let i = 1; i <= m; i++) {
        for (let j = 1; j <= n; j++) {
            if (p[j - 1] === '*') {
                dp[i][j] = dp[i][j - 2] || (dp[i - 1][j] && (s[i - 1] === p[j - 2] || p[j - 2] === '.'));
            } else {
                dp[i][j] = dp[i - 1][j - 1] && (s[i - 1] === p[j - 1] || p[j - 1] === '.');
            }
        }
    }
    return dp[m][n];
};
/* Time Complexity: O(m * n), Memory Complexity: O(m * n) */

```

# Typescript

## Sweet Spot

```typescript
function isMatch(s: string, p: string): boolean {
    const m = s.length, n = p.length;
    const dp: boolean[][] = Array.from({ length: m + 1 }, () => Array(n + 1).fill(false));
    dp[0][0] = true;
    for (let j = 2; j <= n; j++) {
        if (p[j - 1] === '*') dp[0][j] = dp[0][j - 2];
    }
    for (let i = 1; i <= m; i++) {
        for (let j = 1; j <= n; j++) {
            if (p[j - 1] === '*') {
                dp[i][j] = dp[i][j - 2] || (dp[i - 1][j] && (s[i - 1] === p[j - 2] || p[j - 2] === '.'));
            } else {
                dp[i][j] = dp[i - 1][j - 1] && (s[i - 1] === p[j - 1] || p[j - 1] === '.');
            }
        }
    }
    return dp[m][n];
};
/* Time Complexity: O(m * n), Memory Complexity: O(m * n) */

```

# C#

## Sweet Spot

```c#
public class Solution {
    public bool IsMatch(string s, string p) {
        int m = s.Length, n = p.Length;
        bool[,] dp = new bool[m + 1, n + 1];
        dp[0, 0] = true;
        for (int j = 2; j <= n; j++) {
            if (p[j - 1] == '*') dp[0, j] = dp[0, j - 2];
        }
        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (p[j - 1] == '*') {
                    dp[i, j] = dp[i, j - 2] || (dp[i - 1, j] && (s[i - 1] == p[j - 2] || p[j - 2] == '.'));
                } else {
                    dp[i, j] = dp[i - 1, j - 1] && (s[i - 1] == p[j - 1] || p[j - 1] == '.');
                }
            }
        }
        return dp[m, n];
    }
}
/* Time Complexity: O(m * n), Memory Complexity: O(m * n) */

```

# C

## Sweet Spot

```c
bool isMatch(char* s, char* p) {
    int m = strlen(s), n = strlen(p);
    bool dp[m + 1][n + 1];
    memset(dp, 0, sizeof(dp));
    dp[0][0] = true;
    for (int j = 2; j <= n; j++) {
        if (p[j - 1] == '*') dp[0][j] = dp[0][j - 2];
    }
    for (int i = 1; i <= m; i++) {
        for (int j = 1; j <= n; j++) {
            if (p[j - 1] == '*') {
                dp[i][j] = dp[i][j - 2] || (dp[i - 1][j] && (s[i - 1] == p[j - 2] || p[j - 2] == '.'));
            } else {
                dp[i][j] = dp[i - 1][j - 1] && (s[i - 1] == p[j - 1] || p[j - 1] == '.');
            }
        }
    }
    return dp[m][n];
}
/* Time Complexity: O(m * n), Memory Complexity: O(m * n) */

```

# Go

## Sweet Spot

```go
func isMatch(s string, p string) bool {
    m, n := len(s), len(p)
    dp := make([][]bool, m+1)
    for i := range dp {
        dp[i] = make([]bool, n+1)
    }
    dp[0][0] = true
    for j := 2; j <= n; j++ {
        if p[j-1] == '*' {
            dp[0][j] = dp[0][j-2]
        }
    }
    for i := 1; i <= m; i++ {
        for j := 1; j <= n; j++ {
            if p[j-1] == '*' {
                dp[i][j] = dp[i][j-2] || (dp[i-1][j] && (s[i-1] == p[j-2] || p[j-2] == '.'))
            } else {
                dp[i][j] = dp[i-1][j-1] && (s[i-1] == p[j-1] || p[j-1] == '.')
            }
        }
    }
    return dp[m][n]
}
/* Time Complexity: O(m * n), Memory Complexity: O(m * n) */

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun isMatch(s: String, p: String): Boolean {
        val m = s.length
        val n = p.length
        val dp = Array(m + 1) { BooleanArray(n + 1) }
        dp[0][0] = true
        for (j in 2..n) {
            if (p[j - 1] == '*') dp[0][j] = dp[0][j - 2]
        }
        for (i in 1..m) {
            for (j in 1..n) {
                if (p[j - 1] == '*') {
                    dp[i][j] = dp[i][j - 2] || (dp[i - 1][j] && (s[i - 1] == p[j - 2] || p[j - 2] == '.'))
                } else {
                    dp[i][j] = dp[i - 1][j - 1] && (s[i - 1] == p[j - 1] || p[j - 1] == '.')
                }
            }
        }
        return dp[m][n]
    }
}
/* Time Complexity: O(m * n), Memory Complexity: O(m * n) */

```

# swift

## Sweet Spot

```swift
class Solution {
    func isMatch(_ s: String, _ p: String) -> Bool {
        let sArr = Array(s), pArr = Array(p)
        let m = sArr.count, n = pArr.count
        var dp = Array(repeating: Array(repeating: false, count: n + 1), count: m + 1)
        dp[0][0] = true
        for j in 1...n {
            if pArr[j-1] == "*" {
                dp[0][j] = dp[0][j-2]
            }
        }
        if m > 0 {
            for i in 1...m {
                for j in 1...n {
                    if pArr[j-1] == "*" {
                        dp[i][j] = dp[i][j-2] || (dp[i-1][j] && (sArr[i-1] == pArr[j-2] || pArr[j-2] == "."))
                    } else {
                        dp[i][j] = dp[i-1][j-1] && (sArr[i-1] == pArr[j-1] || pArr[j-1] == ".")
                    }
                }
            }
        }
        return dp[m][n]
    }
}
/* Time Complexity: O(m * n), Memory Complexity: O(m * n) */

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn is_match(s: String, p: String) -> bool {
        let s_bytes = s.as_bytes();
        let p_bytes = p.as_bytes();
        let m = s_bytes.len();
        let n = p_bytes.len();
        let mut dp = vec![vec![false; n + 1]; m + 1];
        dp[0][0] = true;
        for j in 2..=n {
            if p_bytes[j - 1] == b'*' {
                dp[0][j] = dp[0][j - 2];
            }
        }
        for i in 1..=m {
            for j in 1..=n {
                if p_bytes[j - 1] == b'*' {
                    dp[i][j] = dp[i][j - 2] || (dp[i - 1][j] && (s_bytes[i - 1] == p_bytes[j - 2] || p_bytes[j - 2] == b'.'));
                } else {
                    dp[i][j] = dp[i - 1][j - 1] && (s_bytes[i - 1] == p_bytes[j - 1] || p_bytes[j - 1] == b'.');
                }
            }
        }
        dp[m][n]
    }
}
/* Time Complexity: O(m * n), Memory Complexity: O(m * n) */

```

# ruby

## Sweet Spot

```ruby
# @param {String} s
# @param {String} p
# @return {Boolean}
def is_match(s, p)
    m, n = s.length, p.length
    dp = Array.new(m + 1) { Array.new(n + 1, false) }
    dp[0][0] = true
    (2..n).each do |j|
        dp[0][j] = dp[0][j - 2] if p[j - 1] == '*'
    end
    (1..m).each do |i|
        (1..n).each do |j|
            if p[j - 1] == '*'
                dp[i][j] = dp[i][j - 2] || (dp[i - 1][j] && (s[i - 1] == p[j - 2] || p[j - 2] == '.'))
            else
                dp[i][j] = dp[i - 1][j - 1] && (s[i - 1] == p[j - 1] || p[j - 1] == '.')
            end
        end
    end
    dp[m][n]
end
# Time Complexity: O(m * n), Memory Complexity: O(m * n)

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
        $m = strlen($s);
        $n = strlen($p);
        $dp = array_fill(0, $m + 1, array_fill(0, $n + 1, false));
        $dp[0][0] = true;
        for ($j = 2; $j <= $n; $j++) {
            if ($p[$j - 1] == '*') $dp[0][$j] = $dp[0][$j - 2];
        }
        for ($i = 1; $i <= $m; $i++) {
            for ($j = 1; $j <= $n; $j++) {
                if ($p[$j - 1] == '*') {
                    $dp[$i][$j] = $dp[$i][$j - 2] || ($dp[$i - 1][$j] && ($s[$i - 1] == $p[$j - 2] || $p[$j - 2] == '.'));
                } else {
                    $dp[$i][$j] = $dp[$i - 1][$j - 1] && ($s[$i - 1] == $p[$j - 1] || $p[$j - 1] == '.');
                }
            }
        }
        return $dp[$m][$n];
    }
}
/* Time Complexity: O(m * n), Memory Complexity: O(m * n) */

```

# dart

## Sweet Spot

```dart
class Solution {
  bool isMatch(String s, String p) {
    int m = s.length;
    int n = p.length;
    List<List<bool>> dp = List.generate(m + 1, (_) => List.filled(n + 1, false));
    dp[0][0] = true;
    for (int j = 2; j <= n; j++) {
      if (p[j - 1] == '*') dp[0][j] = dp[0][j - 2];
    }
    for (int i = 1; i <= m; i++) {
      for (int j = 1; j <= n; j++) {
        if (p[j - 1] == '*') {
          dp[i][j] = dp[i][j - 2] || (dp[i - 1][j] && (s[i - 1] == p[j - 2] || p[j - 2] == '.'));
        } else {
          dp[i][j] = dp[i - 1][j - 1] && (s[i - 1] == p[j - 1] || p[j - 1] == '.');
        }
      }
    }
    return dp[m][n];
  }
}
/* Time Complexity: O(m * n), Memory Complexity: O(m * n) */

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def isMatch(s: String, p: String): Boolean = {
        val m = s.length
        val n = p.length
        val dp = Array.ofDim[Boolean](m + 1, n + 1)
        dp(0)(0) = true
        for (j <- 2 to n) {
            if (p(j - 1) == '*') dp(0)(j) = dp(0)(j - 2)
        }
        for (i <- 1 to m; j <- 1 to n) {
            if (p(j - 1) == '*') {
                dp(i)(j) = dp(i)(j - 2) || (dp(i - 1)(j) && (s(i - 1) == p(j - 2) || p(j - 2) == '.'))
            } else {
                dp(i)(j) = dp(i - 1)(j - 1) && (s(i - 1) == p(j - 1) || p(j - 1) == '.')
            }
        }
        dp(m)(n)
    }
}
/* Time Complexity: O(m * n), Memory Complexity: O(m * n) */

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec is_match(s :: String.t, p :: String.t) :: boolean
  def is_match(s, p) do
    s_bytes = :unicode.characters_to_binary(s)
    p_bytes = :unicode.characters_to_binary(p)
    m = byte_size(s_bytes)
    n = byte_size(p_bytes)
    memo = %{}
    {res, _} = dp(0, 0, s_bytes, p_bytes, m, n, memo)
    res
  end

  defp dp(i, j, s, p, m, n, memo) do
    cond do
      Map.has_key?(memo, {i, j}) -> {memo[{i, j}], memo}
      j == n -> {i == m, memo}
      true ->
        first_match = i < m and (binary_part(s, i, 1) == binary_part(p, j, 1) or binary_part(p, j, 1) == ".")
        if j + 1 < n and binary_part(p, j + 1, 1) == "*" do
          {res1, memo} = dp(i, j + 2, s, p, m, n, memo)
          if res1 do
            {true, Map.put(memo, {i, j}, true)}
          else
            {res2, memo} = if first_match, do: dp(i + 1, j, s, p, m, n, memo), else: {false, memo}
            {res2, Map.put(memo, {i, j}, res2)}
          end
        else
          {res, memo} = if first_match, do: dp(i + 1, j + 1, s, p, m, n, memo), else: {false, memo}
          {res, Map.put(memo, {i, j}, res)}
        end
    end
  end
end
# Time Complexity: O(m * n), Memory Complexity: O(m * n)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec is_match(S :: unicode:unicode_binary(), P :: unicode:unicode_binary()) -> boolean().
is_match(S, P) ->
    M = byte_size(S),
    N = byte_size(P),
    {Res, _} = dp(0, 0, S, P, M, N, #{}),
    Res.

dp(I, J, S, P, M, N, Memo) ->
    case maps:find({I, J}, Memo) of
        {ok, Val} -> {Val, Memo};
        error ->
            if J == N -> {I == M, Memo};
               true ->
                   FirstMatch = (I < M) andalso 
                                ((binary:at(S, I) == binary:at(P, J)) orelse (binary:at(P, J) == $. )),
                   HasStar = (J + 1 < N) andalso (binary:at(P, J + 1) == $*),
                   if HasStar ->
                           {Res1, Memo1} = dp(I, J + 2, S, P, M, N, Memo),
                           case Res1 of
                               true -> {true, maps:put({I, J}, true, Memo1)};
                               false -> 
                                   {Res2, Memo2} = if FirstMatch -> dp(I + 1, J, S, P, M, N, Memo1);
                                                      true -> {false, Memo1}
                                                   end,
                                   {Res2, maps:put({I, J}, Res2, Memo2)}
                           end;
                      true ->
                           {Res3, Memo3} = if FirstMatch -> dp(I + 1, J + 1, S, P, M, N, Memo);
                                              true -> {false, Memo}
                                           end,
                           {Res3, maps:put({I, J}, Res3, Memo3)}
                   end
            end
    end.
% Time Complexity: O(M * N), Memory Complexity: O(M * N)
```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (is-match s p)
  (-> string? string? boolean?)
  (let* ([m (string-length s)]
         [n (string-length p)]
         [memo (make-hash)])
    (letrec ([dp (lambda (i j)
                   (hash-ref! memo (cons i j)
                              (lambda ()
                                (cond
                                  [(= j n) (= i m)]
                                  [else
                                   (let ([first-match (and (< i m)
                                                           (or (char=? (string-ref s i) (string-ref p j))
                                                               (char=? (string-ref p j) #\.)))])
                                     (if (and (< (+ j 1) n) (char=? (string-ref p (+ j 1)) #\*))
                                         (or (dp i (+ j 2))
                                             (and first-match (dp (+ i 1) j)))
                                         (and first-match (dp (+ i 1) (+ j 1)))))]))))])
      (dp 0 0))))
; Time Complexity: O(m * n), Memory Complexity: O(m * n)

```