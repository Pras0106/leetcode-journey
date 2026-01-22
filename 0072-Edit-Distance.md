# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int minDistance(string word1, string word2) {
        int m = word1.length(), n = word2.length();
        if (m < n) return minDistance(word2, word1);
        vector<int> dp(n + 1);
        for (int j = 0; j <= n; ++j) dp[j] = j;
        for (int i = 1; i <= m; ++i) {
            int prev = dp[0];
            dp[0] = i;
            for (int j = 1; j <= n; ++j) {
                int temp = dp[j];
                if (word1[i - 1] == word2[j - 1]) dp[j] = prev;
                else dp[j] = 1 + min({prev, dp[j - 1], dp[j]});
                prev = temp;
            }
        }
        return dp[n];
    }
};
// Time Complexity: O(m * n)
// Memory Complexity: O(min(m, n))

```

# java

## Sweet Spot

```java
class Solution {
    public int minDistance(String word1, String word2) {
        int m = word1.length(), n = word2.length();
        if (m < n) return minDistance(word2, word1);
        int[] dp = new int[n + 1];
        for (int j = 0; j <= n; j++) dp[j] = j;
        for (int i = 1; i <= m; i++) {
            int prev = dp[0];
            dp[0] = i;
            for (int j = 1; j <= n; j++) {
                int temp = dp[j];
                if (word1.charAt(i - 1) == word2.charAt(j - 1)) dp[j] = prev;
                else dp[j] = 1 + Math.min(prev, Math.min(dp[j - 1], dp[j]));
                prev = temp;
            }
        }
        return dp[n];
    }
}
// Time Complexity: O(m * n)
// Memory Complexity: O(min(m, n))

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def minDistance(self, word1: str, word2: str) -> int:
        if len(word1) < len(word2):
            word1, word2 = word2, word1
        m, n = len(word1), len(word2)
        dp = list(range(n + 1))
        for i in range(1, m + 1):
            prev = dp[0]
            dp[0] = i
            for j in range(1, n + 1):
                temp = dp[j]
                if word1[i - 1] == word2[j - 1]:
                    dp[j] = prev
                else:
                    dp[j] = 1 + min(prev, dp[j - 1], dp[j])
                prev = temp
        return dp[n]
# Time Complexity: O(m * n)
# Memory Complexity: O(min(m, n))

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def minDistance(self, word1, word2):
        """
        :type word1: str
        :type word2: str
        :rtype: int
        """
        if len(word1) < len(word2):
            word1, word2 = word2, word1
        m, n = len(word1), len(word2)
        dp = range(n + 1)
        for i in range(1, m + 1):
            prev = dp[0]
            dp[0] = i
            for j in range(1, n + 1):
                temp = dp[j]
                if word1[i - 1] == word2[j - 1]:
                    dp[j] = prev
                else:
                    dp[j] = 1 + min(prev, dp[j - 1], dp[j])
                prev = temp
        return dp[n]
# Time Complexity: O(m * n)
# Memory Complexity: O(min(m, n))

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {string} word1
 * @param {string} word2
 * @return {number}
 */
var minDistance = function(word1, word2) {
    if (word1.length < word2.length) [word1, word2] = [word2, word1];
    let m = word1.length, n = word2.length;
    let dp = Array.from({ length: n + 1 }, (_, i) => i);
    for (let i = 1; i <= m; i++) {
        let prev = dp[0];
        dp[0] = i;
        for (let j = 1; j <= n; j++) {
            let temp = dp[j];
            if (word1[i - 1] === word2[j - 1]) dp[j] = prev;
            else dp[j] = 1 + Math.min(prev, dp[j - 1], dp[j]);
            prev = temp;
        }
    }
    return dp[n];
};
// Time Complexity: O(m * n)
// Memory Complexity: O(min(m, n))

```

# Typescript

## Sweet Spot

```typescript
function minDistance(word1: string, word2: string): number {
    if (word1.length < word2.length) [word1, word2] = [word2, word1];
    const m = word1.length, n = word2.length;
    const dp: number[] = Array.from({ length: n + 1 }, (_, i) => i);
    for (let i = 1; i <= m; i++) {
        let prev = dp[0];
        dp[0] = i;
        for (let j = 1; j <= n; j++) {
            let temp = dp[j];
            if (word1[i - 1] === word2[j - 1]) dp[j] = prev;
            else dp[j] = 1 + Math.min(prev, dp[j - 1], dp[j]);
            prev = temp;
        }
    }
    return dp[n];
};
// Time Complexity: O(m * n)
// Memory Complexity: O(min(m, n))

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int MinDistance(string word1, string word2) {
        if (word1.Length < word2.Length) {
            string temp = word1; word1 = word2; word2 = temp;
        }
        int m = word1.Length, n = word2.Length;
        int[] dp = new int[n + 1];
        for (int j = 0; j <= n; j++) dp[j] = j;
        for (int i = 1; i <= m; i++) {
            int prev = dp[0];
            dp[0] = i;
            for (int j = 1; j <= n; j++) {
                int tempVal = dp[j];
                if (word1[i - 1] == word2[j - 1]) dp[j] = prev;
                else dp[j] = 1 + Math.Min(prev, Math.Min(dp[j - 1], dp[j]));
                prev = tempVal;
            }
        }
        return dp[n];
    }
}
// Time Complexity: O(m * n)
// Memory Complexity: O(min(m, n))

```

# C

## Sweet Spot

```c
int minDistance(char* word1, char* word2) {
    int m = strlen(word1), n = strlen(word2);
    if (m < n) return minDistance(word2, word1);
    int* dp = (int*)malloc((n + 1) * sizeof(int));
    for (int j = 0; j <= n; j++) dp[j] = j;
    for (int i = 1; i <= m; i++) {
        int prev = dp[0];
        dp[0] = i;
        for (int j = 1; j <= n; j++) {
            int temp = dp[j];
            if (word1[i - 1] == word2[j - 1]) dp[j] = prev;
            else {
                int min_val = prev < dp[j - 1] ? prev : dp[j - 1];
                dp[j] = 1 + (min_val < dp[j] ? min_val : dp[j]);
            }
            prev = temp;
        }
    }
    int res = dp[n];
    free(dp);
    return res;
}
// Time Complexity: O(m * n)
// Memory Complexity: O(min(m, n))

```

# Go

## Sweet Spot

```go
func minDistance(word1 string, word2 string) int {
    if len(word1) < len(word2) {
        word1, word2 = word2, word1
    }
    m, n := len(word1), len(word2)
    dp := make([]int, n+1)
    for j := 0; j <= n; j++ {
        dp[j] = j
    }
    for i := 1; i <= m; i++ {
        prev := dp[0]
        dp[0] = i
        for j := 1; j <= n; j++ {
            temp := dp[j]
            if word1[i-1] == word2[j-1] {
                dp[j] = prev
            } else {
                min := prev
                if dp[j-1] < min { min = dp[j-1] }
                if dp[j] < min { min = dp[j] }
                dp[j] = 1 + min
            }
            prev = temp
        }
    }
    return dp[n]
}
// Time Complexity: O(m * n)
// Memory Complexity: O(min(m, n))

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun minDistance(word1: String, word2: String): Int {
        val (w1, w2) = if (word1.length < word2.length) word2 to word1 else word1 to word2
        val m = w1.length
        val n = w2.length
        val dp = IntArray(n + 1) { it }
        for (i in 1..m) {
            var prev = dp[0]
            dp[0] = i
            for (j in 1..n) {
                val temp = dp[j]
                if (w1[i - 1] == w2[j - 1]) dp[j] = prev
                else dp[j] = 1 + minOf(prev, minOf(dp[j - 1], dp[j]))
                prev = temp
            }
        }
        return dp[n]
    }
}
// Time Complexity: O(m * n)
// Memory Complexity: O(min(m, n))

```

# swift

## Sweet Spot

```swift
class Solution {
    func minDistance(_ word1: String, _ word2: String) -> Int {
        let s1 = Array(word1), s2 = Array(word2)
        if s1.count < s2.count { 
            return minDistance(word2, word1) 
        }
        let m = s1.count, n = s2.count
        if n == 0 { return m }
        
        var dp = Array(0...n)
        for i in 1...m {
            var prev = dp[0]
            dp[0] = i
            for j in 1...n {
                let temp = dp[j]
                if s1[i - 1] == s2[j - 1] {
                    dp[j] = prev
                } else {
                    dp[j] = 1 + min(prev, min(dp[j - 1], dp[j]))
                }
                prev = temp
            }
        }
        return dp[n]
    }
}
// Time Complexity: O(m * n)
// Memory Complexity: O(min(m, n))
```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn min_distance(word1: String, word2: String) -> i32 {
        let (w1, w2) = if word1.len() < word2.len() {
            (word2.as_bytes(), word1.as_bytes())
        } else {
            (word1.as_bytes(), word2.as_bytes())
        };
        let (m, n) = (w1.len(), w2.len());
        let mut dp: Vec<i32> = (0..=(n as i32)).collect();
        for i in 1..=m {
            let mut prev = dp[0];
            dp[0] = i as i32;
            for j in 1..=n {
                let temp = dp[j];
                if w1[i - 1] == w2[j - 1] {
                    dp[j] = prev;
                } else {
                    dp[j] = 1 + prev.min(dp[j - 1].min(dp[j]));
                }
                prev = temp;
            }
        }
        dp[n]
    }
}
// Time Complexity: O(m * n)
// Memory Complexity: O(min(m, n))

```

# ruby

## Sweet Spot

```ruby
# @param {String} word1
# @param {String} word2
# @return {Integer}
def min_distance(word1, word2)
    word1, word2 = word2, word1 if word1.length < word2.length
    m, n = word1.length, word2.length
    dp = (0..n).to_a
    (1..m).each do |i|
        prev = dp[0]
        dp[0] = i
        (1..n).each do |j|
            temp = dp[j]
            if word1[i-1] == word2[j-1]
                dp[j] = prev
            else
                dp[j] = 1 + [prev, dp[j-1], dp[j]].min
            end
            prev = temp
        end
    end
    dp[n]
end
# Time Complexity: O(m * n)
# Memory Complexity: O(min(m, n))

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param String $word1
     * @param String $word2
     * @return Integer
     */
    function minDistance($word1, $word2) {
        if (strlen($word1) < strlen($word2)) {
            $temp = $word1; $word1 = $word2; $word2 = $temp;
        }
        $m = strlen($word1); $n = strlen($word2);
        $dp = range(0, $n);
        for ($i = 1; $i <= $m; $i++) {
            $prev = $dp[0];
            $dp[0] = $i;
            for ($j = 1; $j <= $n; $j++) {
                $temp = $dp[$j];
                if ($word1[$i-1] == $word2[$j-1]) {
                    $dp[$j] = $prev;
                } else {
                    $dp[$j] = 1 + min($prev, $dp[$j-1], $dp[$j]);
                }
                $prev = $temp;
            }
        }
        return $dp[$n];
    }
}
// Time Complexity: O(m * n)
// Memory Complexity: O(min(m, n))

```

# dart

## Sweet Spot

```dart
import 'dart:math';

class Solution {
  int minDistance(String word1, String word2) {
    if (word1.length < word2.length) {
      String t = word1; word1 = word2; word2 = t;
    }
    int m = word1.length;
    int n = word2.length;
    List<int> dp = List.generate(n + 1, (i) => i);
    for (int i = 1; i <= m; i++) {
      int prev = dp[0];
      dp[0] = i;
      for (int j = 1; j <= n; j++) {
        int temp = dp[j];
        if (word1[i - 1] == word2[j - 1]) {
          dp[j] = prev;
        } else {
          dp[j] = 1 + min(prev, min(dp[j - 1], dp[j]));
        }
        prev = temp;
      }
    }
    return dp[n];
  }
}
// Time Complexity: O(m * n)
// Memory Complexity: O(min(m, n))

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def minDistance(word1: String, word2: String): Int = {
        val (w1, w2) = if (word1.length < word2.length) (word2, word1) else (word1, word2)
        val m = w1.length
        val n = w2.length
        val dp = Array.tabulate(n + 1)(identity)
        for (i <- 1 to m) {
            var prev = dp(0)
            dp(0) = i
            for (j <- 1 to n) {
                val temp = dp(j)
                if (w1(i - 1) == w2(j - 1)) dp(j) = prev
                else dp(j) = 1 + Math.min(prev, Math.min(dp(j - 1), dp(j)))
                prev = temp
            }
        }
        dp(n)
    }
}
// Time Complexity: O(m * n)
// Memory Complexity: O(min(m, n))

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec min_distance(word1 :: String.t, word2 :: String.t) :: integer
  def min_distance(word1, word2) do
    n = String.length(word1)
    m = String.length(word2)

    cond do
      n == 0 -> m
      m == 0 -> n
      true ->
        t1 = List.to_tuple(String.to_charlist(word1))
        t2 = List.to_tuple(String.to_charlist(word2))
        
        initial_row = Enum.to_list(0..m)

        final_row = Enum.reduce(0..(n - 1), initial_row, fn i, prev_row ->
          char1 = elem(t1, i)
          
          # current_row_acc starts with the base case for word1[0..i] -> ""
          {new_row, _} = Enum.reduce(0..(m - 1), {[i + 1], i}, fn j, {acc, diag} ->
            char2 = elem(t2, j)
            top = Enum.at(prev_row, j + 1)
            left = hd(acc)

            cost = if char1 == char2 do
              diag
            else
              1 + min(diag, min(top, left))
            end

            {[cost | acc], top}
          end)

          Enum.reverse(new_row)
        end)

        List.last(final_row)
    end
  end
end
# Time Complexity: O(n * m)
# Memory Complexity: O(m)
```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-export([min_distance/2]).

-spec min_distance(Word1 :: unicode:unicode_binary(), Word2 :: unicode:unicode_binary()) -> integer().
min_distance(Word1, Word2) ->
    Len1 = byte_size(Word1),
    Len2 = byte_size(Word2),
    {W1, W2, M, N} = if 
        Len1 < Len2 -> {Word2, Word1, Len2, Len1}; 
        true -> {Word1, Word2, Len1, Len2} 
    end,
    InitialDP = list_to_tuple(lists:seq(0, N)),
    FinalDP = lists:foldl(fun(I, AccDP) ->
        Char1 = binary:at(W1, I - 1),
        {RowDP, _} = lists:foldl(fun(J, {InnerDP, PrevDiag}) ->
            CurrentAbove = element(J + 1, InnerDP),
            Char2 = binary:at(W2, J - 1),
            NewVal = if 
                Char1 == Char2 -> PrevDiag;
                true -> 1 + min(PrevDiag, min(element(J, InnerDP), CurrentAbove))
            end,
            {setelement(J + 1, InnerDP, NewVal), CurrentAbove}
        end, {setelement(1, AccDP, I), element(1, AccDP)}, lists:seq(1, N)),
        RowDP
    end, InitialDP, lists:seq(1, M)),
    element(N + 1, FinalDP).

% Time Complexity: O(M * N)
% Memory Complexity: O(min(M, N))
```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (min-distance word1 word2)
  (-> string? string? exact-integer?)
  (let* ([m (string-length word1)]
         [n (string-length word2)]
         [s1 (if (< m n) word2 word1)]
         [s2 (if (< m n) word1 word2)]
         [M (string-length s1)]
         [N (string-length s2)]
         [dp (make-vector (+ N 1))])
    (for ([j (in-range (+ N 1))])
      (vector-set! dp j j))
    (for ([i (in-range 1 (+ M 1))])
      (let ([prev (vector-ref dp 0)])
        (vector-set! dp 0 i)
        (for ([j (in-range 1 (+ N 1))])
          (let ([temp (vector-ref dp j)])
            (if (char=? (string-ref s1 (- i 1)) (string-ref s2 (- j 1)))
                (vector-set! dp j prev)
                (vector-set! dp j (+ 1 (min prev (vector-ref dp (- j 1)) temp))))
            (set! prev temp)))))
    (vector-ref dp N)))
; Time Complexity: O(m * n)
; Memory Complexity: O(min(m, n))

```