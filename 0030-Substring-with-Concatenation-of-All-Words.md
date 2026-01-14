# cpp

## Sweet Spot

```cpp
class Solution {
public:
    vector<int> findSubstring(string s, vector<string>& words) {
        vector<int> res;
        int n = s.length(), m = words.size(), k = words[0].length();
        if (n < m * k) return res;
        unordered_map<string, int> counts;
        for (const string& word : words) counts[word]++;
        for (int i = 0; i < k; ++i) {
            int left = i, count = 0;
            unordered_map<string, int> seen;
            for (int j = i; j <= n - k; j += k) {
                string word = s.substr(j, k);
                if (counts.count(word)) {
                    seen[word]++;
                    count++;
                    while (seen[word] > counts[word]) {
                        seen[s.substr(left, k)]--;
                        count--;
                        left += k;
                    }
                    if (count == m) res.push_back(left);
                } else {
                    seen.clear();
                    count = 0;
                    left = j + k;
                }
            }
        }
        return res;
    }
};
/* Time Complexity: O(n * k), Memory Complexity: O(m * k) */

```

# java

## Sweet Spot

```java
class Solution {
    public List<Integer> findSubstring(String s, String[] words) {
        List<Integer> res = new ArrayList<>();
        int n = s.length(), m = words.length, k = words[0].length();
        if (n < m * k) return res;
        Map<String, Integer> counts = new HashMap<>();
        for (String word : words) counts.put(word, counts.getOrDefault(word, 0) + 1);
        for (int i = 0; i < k; i++) {
            Map<String, Integer> seen = new HashMap<>();
            int left = i, count = 0;
            for (int j = i; j <= n - k; j += k) {
                String word = s.substring(j, j + k);
                if (counts.containsKey(word)) {
                    seen.put(word, seen.getOrDefault(word, 0) + 1);
                    count++;
                    while (seen.get(word) > counts.get(word)) {
                        String leftWord = s.substring(left, left + k);
                        seen.put(leftWord, seen.get(leftWord) - 1);
                        count--;
                        left += k;
                    }
                    if (count == m) res.add(left);
                } else {
                    seen.clear();
                    count = 0;
                    left = j + k;
                }
            }
        }
        return res;
    }
}
/* Time Complexity: O(n * k), Memory Complexity: O(m * k) */

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def findSubstring(self, s: str, words: List[str]) -> List[int]:
        if not s or not words: return []
        k = len(words[0])
        m = len(words)
        n = len(s)
        counts = {}
        for w in words:
            counts[w] = counts.get(w, 0) + 1
        res = []
        for i in range(k):
            left = i
            seen = {}
            count = 0
            for j in range(i, n - k + 1, k):
                word = s[j:j+k]
                if word in counts:
                    seen[word] = seen.get(word, 0) + 1
                    count += 1
                    while seen[word] > counts[word]:
                        left_word = s[left:left+k]
                        seen[left_word] -= 1
                        count -= 1
                        left += k
                    if count == m:
                        res.append(left)
                else:
                    seen = {}
                    count = 0
                    left = j + k
        return res
# Time Complexity: O(n * k), Memory Complexity: O(m * k)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def findSubstring(self, s, words):
        """
        :type s: str
        :type words: List[str]
        :rtype: List[int]
        """
        if not s or not words: return []
        k = len(words[0])
        m = len(words)
        n = len(s)
        counts = {}
        for w in words:
            counts[w] = counts.get(w, 0) + 1
        res = []
        for i in range(k):
            left = i
            seen = {}
            count = 0
            for j in range(i, n - k + 1, k):
                word = s[j:j+k]
                if word in counts:
                    seen[word] = seen.get(word, 0) + 1
                    count += 1
                    while seen[word] > counts[word]:
                        left_word = s[left:left+k]
                        seen[left_word] -= 1
                        count -= 1
                        left += k
                    if count == m:
                        res.append(left)
                else:
                    seen = {}
                    count = 0
                    left = j + k
        return res
# Time Complexity: O(n * k), Memory Complexity: O(m * k)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {string} s
 * @param {string[]} words
 * @return {number[]}
 */
var findSubstring = function(s, words) {
    const res = [];
    const n = s.length, m = words.length, k = words[0].length;
    if (n < m * k) return res;
    const counts = {};
    for (const w of words) counts[w] = (counts[w] || 0) + 1;
    for (let i = 0; i < k; i++) {
        let left = i, count = 0;
        const seen = {};
        for (let j = i; j <= n - k; j += k) {
            const word = s.substring(j, j + k);
            if (counts[word]) {
                seen[word] = (seen[word] || 0) + 1;
                count++;
                while (seen[word] > counts[word]) {
                    const leftWord = s.substring(left, left + k);
                    seen[leftWord]--;
                    count--;
                    left += k;
                }
                if (count === m) res.push(left);
            } else {
                for (let key in seen) delete seen[key];
                count = 0;
                left = j + k;
            }
        }
    }
    return res;
};
// Time Complexity: O(n * k), Memory Complexity: O(m * k)

```

# Typescript

## Sweet Spot

```typescript
function findSubstring(s: string, words: string[]): number[] {
    const res: number[] = [];
    const n = s.length, m = words.length, k = words[0].length;
    if (n < m * k) return res;
    const counts: Map<string, number> = new Map();
    for (const w of words) counts.set(w, (counts.get(w) || 0) + 1);
    for (let i = 0; i < k; i++) {
        let left = i, count = 0;
        const seen: Map<string, number> = new Map();
        for (let j = i; j <= n - k; j += k) {
            const word = s.substring(j, j + k);
            if (counts.has(word)) {
                seen.set(word, (seen.get(word) || 0) + 1);
                count++;
                while ((seen.get(word) || 0) > (counts.get(word) || 0)) {
                    const leftWord = s.substring(left, left + k);
                    seen.set(leftWord, (seen.get(leftWord) || 0) - 1);
                    count--;
                    left += k;
                }
                if (count === m) res.push(left);
            } else {
                seen.clear();
                count = 0;
                left = j + k;
            }
        }
    }
    return res;
};
// Time Complexity: O(n * k), Memory Complexity: O(m * k)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public IList<int> FindSubstring(string s, string[] words) {
        var res = new List<int>();
        int n = s.Length, m = words.Length, k = words[0].Length;
        if (n < m * k) return res;
        var counts = new Dictionary<string, int>();
        foreach (var w in words) {
            if (counts.ContainsKey(w)) counts[w]++;
            else counts[w] = 1;
        }
        for (int i = 0; i < k; i++) {
            var seen = new Dictionary<string, int>();
            int left = i, count = 0;
            for (int j = i; j <= n - k; j += k) {
                string word = s.Substring(j, k);
                if (counts.ContainsKey(word)) {
                    if (seen.ContainsKey(word)) seen[word]++;
                    else seen[word] = 1;
                    count++;
                    while (seen[word] > counts[word]) {
                        string leftWord = s.Substring(left, k);
                        seen[leftWord]--;
                        count--;
                        left += k;
                    }
                    if (count == m) res.Add(left);
                } else {
                    seen.Clear();
                    count = 0;
                    left = j + k;
                }
            }
        }
        return res;
    }
}
/* Time Complexity: O(n * k), Memory Complexity: O(m * k) */

```

# C

## Sweet Spot

```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
typedef struct {
    char key[31];
    int val;
    UT_hash_handle hh;
} HashEntry;

int* findSubstring(char* s, char** words, int wordsSize, int* returnSize) {
    int n = strlen(s), m = wordsSize, k = strlen(words[0]);
    *returnSize = 0;
    if (n < m * k) return NULL;
    int* res = (int*)malloc(n * sizeof(int));
    HashEntry *counts = NULL, *curr, *tmp;
    for (int i = 0; i < m; i++) {
        HASH_FIND_STR(counts, words[i], curr);
        if (curr) curr->val++;
        else {
            curr = (HashEntry*)malloc(sizeof(HashEntry));
            strcpy(curr->key, words[i]);
            curr->val = 1;
            HASH_ADD_STR(counts, key, curr);
        }
    }
    for (int i = 0; i < k; i++) {
        HashEntry *seen = NULL, *s_entry;
        int left = i, count = 0;
        for (int j = i; j <= n - k; j += k) {
            char sub[31];
            strncpy(sub, s + j, k);
            sub[k] = '\0';
            HASH_FIND_STR(counts, sub, curr);
            if (curr) {
                HASH_FIND_STR(seen, sub, s_entry);
                if (s_entry) s_entry->val++;
                else {
                    s_entry = (HashEntry*)malloc(sizeof(HashEntry));
                    strcpy(s_entry->key, sub);
                    s_entry->val = 1;
                    HASH_ADD_STR(seen, key, s_entry);
                }
                count++;
                while (s_entry->val > curr->val) {
                    char l_sub[31];
                    strncpy(l_sub, s + left, k);
                    l_sub[k] = '\0';
                    HashEntry *l_entry;
                    HASH_FIND_STR(seen, l_sub, l_entry);
                    l_entry->val--;
                    count--;
                    left += k;
                }
                if (count == m) res[(*returnSize)++] = left;
            } else {
                HASH_ITER(hh, seen, s_entry, tmp) {
                    HASH_DEL(seen, s_entry);
                    free(s_entry);
                }
                count = 0;
                left = j + k;
            }
        }
        HASH_ITER(hh, seen, curr, tmp) {
            HASH_DEL(seen, curr);
            free(curr);
        }
    }
    HASH_ITER(hh, counts, curr, tmp) {
        HASH_DEL(counts, curr);
        free(curr);
    }
    /* Time Complexity: O(n * k), Memory Complexity: O(m * k) */
    return res;
}
```

# Go

## Sweet Spot

```go
func findSubstring(s string, words []string) []int {
    res := []int{}
    n := len(s)
    m := len(words)
    if m == 0 { return res }
    k := len(words[0])
    if n < m*k { return res }
    counts := make(map[string]int)
    for _, w := range words {
        counts[w]++
    }
    for i := 0; i < k; i++ {
        seen := make(map[string]int)
        left, count := i, 0
        for j := i; j <= n-k; j += k {
            word := s[j : j+k]
            if c, ok := counts[word]; ok {
                seen[word]++
                count++
                for seen[word] > c {
                    leftWord := s[left : left+k]
                    seen[leftWord]--
                    count--
                    left += k
                }
                if count == m {
                    res = append(res, left)
                }
            } else {
                seen = make(map[string]int)
                count = 0
                left = j + k
            }
        }
    }
    return res
}
// Time Complexity: O(n * k), Memory Complexity: O(m * k)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun findSubstring(s: String, words: Array<String>): List<Int> {
        val res = mutableListOf<Int>()
        val n = s.length
        val m = words.size
        if (m == 0) return res
        val k = words[0].length
        if (n < m * k) return res
        val counts = HashMap<String, Int>()
        for (w in words) counts[w] = counts.getOrDefault(w, 0) + 1
        for (i in 0 until k) {
            val seen = HashMap<String, Int>()
            var left = i
            var count = 0
            for (j in i..n - k step k) {
                val word = s.substring(j, j + k)
                if (counts.containsKey(word)) {
                    seen[word] = seen.getOrDefault(word, 0) + 1
                    count++
                    while (seen[word]!! > counts[word]!!) {
                        val leftWord = s.substring(left, left + k)
                        seen[leftWord] = seen[leftWord]!! - 1
                        count--
                        left += k
                    }
                    if (count == m) res.add(left)
                } else {
                    seen.clear()
                    count = 0
                    left = j + k
                }
            }
        }
        return res
    }
}
/* Time Complexity: O(n * k), Memory Complexity: O(m * k) */

```

# swift

## Sweet Spot

```swift
class Solution {
    func findSubstring(_ s: String, _ words: [String]) -> [Int] {
        var res = [Int]()
        let n = s.count, m = words.count
        if m == 0 { return res }
        let k = words[0].count
        if n < m * k { return res }
        var counts = [String: Int]()
        for w in words { counts[w, default: 0] += 1 }
        let sArr = Array(s)
        for i in 0..<k {
            var seen = [String: Int]()
            var left = i, count = 0
            for j in stride(from: i, through: n - k, by: k) {
                let word = String(sArr[j..<j+k])
                if let targetCount = counts[word] {
                    seen[word, default: 0] += 1
                    count += 1
                    while seen[word]! > targetCount {
                        let leftWord = String(sArr[left..<left+k])
                        seen[leftWord]! -= 1
                        count -= 1
                        left += k
                    }
                    if count == m { res.append(left) }
                } else {
                    seen.removeAll()
                    count = 0
                    left = j + k
                }
            }
        }
        return res
    }
}
/* Time Complexity: O(n * k), Memory Complexity: O(m * k) */

```

# rust

## Sweet Spot

```rust
use std::collections::HashMap;
impl Solution {
    pub fn find_substring(s: String, words: Vec<String>) -> Vec<i32> {
        let mut res = Vec::new();
        let n = s.len();
        let m = words.len();
        if m == 0 { return res; }
        let k = words[0].len();
        if n < m * k { return res; }
        let mut counts = HashMap::new();
        for w in &words { *counts.entry(w.as_str()).or_insert(0) += 1; }
        for i in 0..k {
            let mut seen = HashMap::new();
            let (mut left, mut count) = (i, 0);
            for j in (i..=n - k).step_by(k) {
                let word = &s[j..j + k];
                if let Some(&c) = counts.get(word) {
                    *seen.entry(word).or_insert(0) += 1;
                    count += 1;
                    while seen[word] > c {
                        let left_word = &s[left..left + k];
                        *seen.get_mut(left_word).unwrap() -= 1;
                        count -= 1;
                        left += k;
                    }
                    if count == m { res.push(left as i32); }
                } else {
                    seen.clear();
                    count = 0;
                    left = j + k;
                }
            }
        }
        res
    }
}
/* Time Complexity: O(n * k), Memory Complexity: O(m * k) */

```

# ruby

## Sweet Spot

```ruby
# @param {String} s
# @param {String[]} words
# @return {Integer[]}
def find_substring(s, words)
    res = []
    n = s.length
    m = words.length
    return res if m == 0
    k = words[0].length
    return res if n < m * k
    counts = Hash.new(0)
    words.each { |w| counts[w] += 1 }
    (0...k).each do |i|
        seen = Hash.new(0)
        left = i
        count = 0
        (i..n-k).step(k) do |j|
            word = s[j, k]
            if counts.key?(word)
                seen[word] += 1
                count += 1
                while seen[word] > counts[word]
                    left_word = s[left, k]
                    seen[left_word] -= 1
                    count -= 1
                    left += k
                end
                res << left if count == m
            else
                seen.clear
                count = 0
                left = j + k
            end
        end
    end
    res
end
# Time Complexity: O(n * k), Memory Complexity: O(m * k)

```

# php

## Sweet Spot

```php
class Solution {
    /**
     * @param String $s
     * @param String[] $words
     * @return Integer[]
     */
    function findSubstring($s, $words) {
        $res = [];
        $n = strlen($s);
        $m = count($words);
        if ($m == 0) return $res;
        $k = strlen($words[0]);
        if ($n < $m * $k) return $res;
        $counts = array_count_values($words);
        for ($i = 0; $i < $k; $i++) {
            $seen = [];
            $left = $i;
            $count = 0;
            for ($j = $i; $j <= $n - $k; $j += $k) {
                $word = substr($s, $j, $k);
                if (isset($counts[$word])) {
                    $seen[$word] = ($seen[$word] ?? 0) + 1;
                    $count++;
                    while ($seen[$word] > $counts[$word]) {
                        $leftWord = substr($s, $left, $k);
                        $seen[$leftWord]--;
                        $count--;
                        $left += $k;
                    }
                    if ($count == $m) $res[] = $left;
                } else {
                    $seen = [];
                    $count = 0;
                    $left = $j + $k;
                }
            }
        }
        return $res;
    }
}
/* Time Complexity: O(n * k), Memory Complexity: O(m * k) */

```

# dart

## Sweet Spot

```dart
class Solution {
  List<int> findSubstring(String s, List<String> words) {
    List<int> res = [];
    int n = s.length;
    int m = words.length;
    if (m == 0) return res;
    int k = words[0].length;
    if (n < m * k) return res;
    Map<String, int> counts = {};
    for (var w in words) counts[w] = (counts[w] ?? 0) + 1;
    for (int i = 0; i < k; i++) {
      Map<String, int> seen = {};
      int left = i, count = 0;
      for (int j = i; j <= n - k; j += k) {
        String word = s.substring(j, j + k);
        if (counts.containsKey(word)) {
          seen[word] = (seen[word] ?? 0) + 1;
          count++;
          while (seen[word]! > counts[word]!) {
            String leftWord = s.substring(left, left + k);
            seen[leftWord] = seen[leftWord]! - 1;
            count--;
            left += k;
          }
          if (count == m) res.add(left);
        } else {
          seen.clear();
          count = 0;
          left = j + k;
        }
      }
    }
    return res;
  }
}
/* Time Complexity: O(n * k), Memory Complexity: O(m * k) */

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def findSubstring(s: String, words: Array[String]): List[Int] = {
        if (words.isEmpty) return Nil
        val n = s.length
        val m = words.length
        val k = words(0).length
        if (n < m * k) return Nil
        val counts = words.groupBy(identity).view.mapValues(_.length).toMap
        val res = scala.collection.mutable.ListBuffer[Int]()
        for (i <- 0 until k) {
            var left = i
            var count = 0
            var seen = scala.collection.mutable.Map[String, Int]()
            for (j <- i to n - k by k) {
                val word = s.substring(j, j + k)
                if (counts.contains(word)) {
                    seen(word) = seen.getOrElse(word, 0) + 1
                    count += 1
                    while (seen(word) > counts(word)) {
                        val leftWord = s.substring(left, left + k)
                        seen(leftWord) -= 1
                        count -= 1
                        left += k
                    }
                    if (count == m) res += left
                } else {
                    seen.clear()
                    count = 0
                    left = j + k
                }
            }
        }
        res.toList
    }
}
/* Time Complexity: O(n), Memory Complexity: O(m * k) */
```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec find_substring(s :: String.t, words :: [String.t]) :: [integer]
  def find_substring(s, words) do
    if words == [] do
      []
    else
      n = byte_size(s)
      m = length(words)
      k = byte_size(hd(words))
      counts = Enum.frequencies(words)
      
      for i <- 0..(k - 1), reduce: [] do
        acc -> acc ++ process_offset(s, i, n, m, k, counts)
      end
    end
  end

  defp process_offset(s, i, n, m, k, counts) do
    sliding_window(s, i, i, 0, %{}, n, m, k, counts, [])
  end

  defp sliding_window(s, left, j, count, seen, n, m, k, counts, res) do
    if j > n - k do
      res
    else
      word = binary_part(s, j, k)
      if Map.has_key?(counts, word) do
        new_seen = Map.update(seen, word, 1, &(&1 + 1))
        new_count = count + 1
        {final_left, final_seen, final_count} = shrink(s, left, word, new_seen, new_count, k, counts)
        new_res = if final_count == m, do: [final_left | res], else: res
        sliding_window(s, final_left, j + k, final_count, final_seen, n, m, k, counts, new_res)
      else
        sliding_window(s, j + k, j + k, 0, %{}, n, m, k, counts, res)
      end
    end
  end

  defp shrink(s, left, word, seen, count, k, counts) do
    if Map.get(seen, word) > Map.get(counts, word) do
      left_word = binary_part(s, left, k)
      shrink(s, left + k, word, Map.update!(seen, left_word, &(&1 - 1)), count - 1, k, counts)
    else
      {left, seen, count}
    end
  end
end
# Time Complexity: O(n * k), Memory Complexity: O(m * k)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec find_substring(S :: unicode:unicode_binary(), Words :: [unicode:unicode_binary()]) -> [integer()].
find_substring(S, []) -> [];
find_substring(S, Words) ->
    N = byte_size(S),
    M = length(Words),
    K = byte_size(hd(Words)),
    Counts = lists:foldl(fun(W, Acc) -> maps:put(W, maps:get(W, Acc, 0) + 1, Acc) end, #{}, Words),
    lists:flatmap(fun(I) -> process_offset(S, I, N, M, K, Counts) end, lists:seq(0, K - 1)).

process_offset(S, I, N, M, K, Counts) ->
    sliding_window(S, I, I, 0, #{}, N, M, K, Counts, []).

sliding_window(S, Left, J, Count, Seen, N, M, K, Counts, Res) when J =< N - K ->
    Word = binary_part(S, J, K),
    case maps:is_key(Word, Counts) of
        true ->
            NewSeen = maps:put(Word, maps:get(Word, Seen, 0) + 1, Seen),
            {FinalLeft, FinalSeen, FinalCount} = shrink(S, Left, Word, NewSeen, Count + 1, K, Counts),
            NewRes = if FinalCount == M -> [FinalLeft | Res]; true -> Res end,
            sliding_window(S, FinalLeft, J + K, FinalCount, FinalSeen, N, M, K, Counts, NewRes);
        false ->
            sliding_window(S, J + K, J + K, 0, #{}, N, M, K, Counts, Res)
    end;
sliding_window(_, _, _, _, _, _, _, _, _, Res) -> Res.

shrink(S, Left, Word, Seen, Count, K, Counts) ->
    case maps:get(Word, Seen) > maps:get(Word, Counts) of
        true ->
            LeftWord = binary_part(S, Left, K),
            shrink(S, Left + K, Word, maps:put(LeftWord, maps:get(LeftWord, Seen) - 1, Seen), Count - 1, K, Counts);
        false -> {Left, Seen, Count}
    end.
% Time Complexity: O(n * k), Memory Complexity: O(m * k)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (find-substring s words)
  (-> string? (listof string?) (listof exact-integer?))
  (if (null? words) '()
      (let* ([n (string-length s)]
             [m (length words)]
             [k (string-length (car words))]
             [counts (make-hash)]
             [_ (for ([w words]) (hash-update! counts w add1 0))])
        (apply append
               (for/list ([i (in-range k)])
                 (let loop ([left i] [j i] [count 0] [seen (make-hash)] [res '()])
                   (if (> j (- n k)) res
                       (let ([word (substring s j (+ j k))])
                         (if (hash-has-key? counts word)
                             (begin
                               (hash-update! seen word add1 0)
                               (let shrink ([l left] [c (add1 count)])
                                 (if (> (hash-ref seen word) (hash-ref counts word))
                                     (let ([lw (substring s l (+ l k))])
                                       (hash-update! seen lw sub1)
                                       (shrink (+ l k) (sub1 c)))
                                     (loop l (+ j k) c seen (if (= c m) (cons l res) res)))))
                             (begin
                               (hash-clear! seen)
                               (loop (+ j k) (+ j k) 0 seen res))))))))))
; Time Complexity: O(n * k), Memory Complexity: O(m * k)

```