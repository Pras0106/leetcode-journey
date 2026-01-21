# cpp

## Sweet Spot

```cpp
class Solution {
public:
    vector<vector<string>> groupAnagrams(vector<string>& strs) {
        unordered_map<string, vector<string>> groups;
        for (const string& s : strs) {
            string key = s;
            sort(key.begin(), key.end());
            groups[key].push_back(s);
        }
        vector<vector<string>> result;
        for (auto& pair : groups) {
            result.push_back(move(pair.second));
        }
        return result;
        // Time Complexity: O(n * k log k), Memory Complexity: O(n * k)
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public List<List<String>> groupAnagrams(String[] strs) {
        Map<String, List<String>> map = new HashMap<>();
        for (String s : strs) {
            char[] chars = s.toCharArray();
            Arrays.sort(chars);
            String key = new String(chars);
            if (!map.containsKey(key)) map.put(key, new ArrayList<>());
            map.get(key).add(s);
        }
        return new ArrayList<>(map.values());
        // Time Complexity: O(n * k log k), Memory Complexity: O(n * k)
    }
}

```

# python 3.14

## Sweet Spot

```python
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        groups = collections.defaultdict(list)
        for s in strs:
            groups["".join(sorted(s))].append(s)
        return list(groups.values())
        # Time Complexity: O(n * k log k), Memory Complexity: O(n * k)

```

# python 2.7.11

## Sweet Spot

```python
class Solution(object):
    def groupAnagrams(self, strs):
        """
        :type strs: List[str]
        :rtype: List[List[str]]
        """
        groups = {}
        for s in strs:
            key = "".join(sorted(s))
            if key not in groups:
                groups[key] = []
            groups[key].append(s)
        return groups.values()
        # Time Complexity: O(n * k log k), Memory Complexity: O(n * k)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {string[]} strs
 * @return {string[][]}
 */
var groupAnagrams = function(strs) {
    const map = new Map();
    for (const s of strs) {
        const key = s.split('').sort().join('');
        if (!map.has(key)) map.set(key, []);
        map.get(key).push(s);
    }
    return Array.from(map.values());
    // Time Complexity: O(n * k log k), Memory Complexity: O(n * k)
};

```

# Typescript

## Sweet Spot

```typescript
function groupAnagrams(strs: string[]): string[][] {
    const map = new Map<string, string[]>();
    for (const s of strs) {
        const key = s.split('').sort().join('');
        if (!map.has(key)) map.set(key, []);
        map.get(key)!.push(s);
    }
    return Array.from(map.values());
    // Time Complexity: O(n * k log k), Memory Complexity: O(n * k)
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public IList<IList<string>> GroupAnagrams(string[] strs) {
        var groups = new Dictionary<string, IList<string>>();
        foreach (var s in strs) {
            char[] chars = s.ToCharArray();
            Array.Sort(chars);
            string key = new string(chars);
            if (!groups.ContainsKey(key)) groups[key] = new List<string>();
            groups[key].Add(s);
        }
        return new List<IList<string>>(groups.Values);
        // Time Complexity: O(n * k log k), Memory Complexity: O(n * k)
    }
}

```

# C

## Sweet Spot

```c
/**
 * Return an array of arrays of size *returnSize.
 * The sizes of the arrays are returned as *returnColumnSizes array.
 * Note: Both returned array and *columnSizes array must be malloced, assume caller calls free().
 */
typedef struct {
    char *sorted;
    char *original;
} Entry;

int compareChars(const void *a, const void *b) {
    return (*(char *)a - *(char *)b);
}

int compareEntries(const void *a, const void *b) {
    return strcmp(((Entry *)a)->sorted, ((Entry *)b)->sorted);
}

char*** groupAnagrams(char** strs, int strsSize, int* returnSize, int** returnColumnSizes) {
    Entry *entries = malloc(strsSize * sizeof(Entry));
    for (int i = 0; i < strsSize; i++) {
        entries[i].original = strs[i];
        entries[i].sorted = strdup(strs[i]);
        qsort(entries[i].sorted, strlen(entries[i].sorted), sizeof(char), compareChars);
    }
    qsort(entries, strsSize, sizeof(Entry), compareEntries);
    char ***res = malloc(strsSize * sizeof(char **));
    *returnColumnSizes = malloc(strsSize * sizeof(int));
    int groupCount = 0;
    for (int i = 0; i < strsSize; ) {
        int j = i;
        while (j < strsSize && strcmp(entries[i].sorted, entries[j].sorted) == 0) j++;
        int size = j - i;
        res[groupCount] = malloc(size * sizeof(char *));
        (*returnColumnSizes)[groupCount] = size;
        for (int k = 0; k < size; k++) res[groupCount][k] = entries[i + k].original;
        groupCount++;
        i = j;
    }
    for (int i = 0; i < strsSize; i++) free(entries[i].sorted);
    free(entries);
    *returnSize = groupCount;
    return res;
    /* Time Complexity: O(n * k log k + n log n), Memory Complexity: O(n * k) */
}

```

# Go

## Sweet Spot

```go
func groupAnagrams(strs []string) [][]string {
    groups := make(map[string][]string)
    for _, s := range strs {
        bytes := []byte(s)
        sort.Slice(bytes, func(i, j int) bool { return bytes[i] < bytes[j] })
        key := string(bytes)
        groups[key] = append(groups[key], s)
    }
    res := make([][]string, 0, len(groups))
    for _, val := range groups {
        res = append(res, val)
    }
    return res
    // Time Complexity: O(n * k log k), Memory Complexity: O(n * k)
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun groupAnagrams(strs: Array<String>): List<List<String>> {
        val groups = HashMap<String, MutableList<String>>()
        for (s in strs) {
            val key = s.toCharArray().sortedArray().joinToString("")
            groups.getOrPut(key) { mutableListOf() }.add(s)
        }
        return groups.values.toList()
        // Time Complexity: O(n * k log k), Memory Complexity: O(n * k)
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func groupAnagrams(_ strs: [String]) -> [[String]] {
        var groups = [String: [String]]()
        for s in strs {
            let key = String(s.sorted())
            groups[key, default: []].append(s)
        }
        return Array(groups.values)
        // Time Complexity: O(n * k log k), Memory Complexity: O(n * k)
    }
}

```

# rust

## Sweet Spot

```rust
use std::collections::HashMap;
impl Solution {
    pub fn group_anagrams(strs: Vec<String>) -> Vec<Vec<String>> {
        let mut groups: HashMap<String, Vec<String>> = HashMap::new();
        for s in strs {
            let mut chars: Vec<char> = s.chars().collect();
            chars.sort_unstable();
            let key: String = chars.into_iter().collect();
            groups.entry(key).or_insert(Vec::new()).push(s);
        }
        groups.into_values().collect()
        // Time Complexity: O(n * k log k), Memory Complexity: O(n * k)
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {String[]} strs
# @return {String[][]}
def group_anagrams(strs)
    groups = {}
    strs.each do |s|
        key = s.chars.sort.join
        groups[key] ||= []
        groups[key] << s
    end
    groups.values
    # Time Complexity: O(n * k log k), Memory Complexity: O(n * k)
end

```

# php

## Sweet Spot

```php
class Solution {
    /**
     * @param String[] $strs
     * @return String[][]
     */
    function groupAnagrams($strs) {
        $groups = [];
        foreach ($strs as $s) {
            $chars = str_split($s);
            sort($chars);
            $key = implode('', $chars);
            $groups[$key][] = $s;
        }
        return array_values($groups);
        // Time Complexity: O(n * k log k), Memory Complexity: O(n * k)
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  List<List<String>> groupAnagrams(List<String> strs) {
    Map<String, List<String>> groups = {};
    for (var s in strs) {
      List<String> chars = s.split('');
      chars.sort();
      String key = chars.join('');
      groups.putIfAbsent(key, () => []).add(s);
    }
    return groups.values.toList();
    // Time Complexity: O(n * k log k), Memory Complexity: O(n * k)
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala
import scala.collection.mutable

object Solution {
    def groupAnagrams(strs: Array[String]): List[List[String]] = {
        strs.groupBy(_.sorted).values.map(_.toList).toList
        // Time Complexity: O(n * k log k), Memory Complexity: O(n * k)
    }
}
```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir
defmodule Solution do
  @spec group_anagrams(strs :: [String.t]) :: [[String.t]]
  def group_anagrams(strs) do
    strs
    |> Enum.group_by(fn s -> s |> String.codepoints() |> Enum.sort() |> Enum.join() end)
    |> Map.values()
    # Time Complexity: O(n * k log k), Memory Complexity: O(n * k)
  end
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang
-spec group_anagrams(Strs :: [unicode:unicode_binary()]) -> [[unicode:unicode_binary()]].
group_anagrams(Strs) ->
    Dict = lists:foldl(fun(S, Acc) ->
        Sorted = lists:sort(binary_to_list(S)),
        orddict:append(Sorted, S, Acc)
    end, orddict:new(), Strs),
    [V || {_, V} <- orddict:to_list(Dict)].
    % Time Complexity: O(n * k log k), Memory Complexity: O(n * k)

```

# Racket CS v8.15

## Sweet Spot

```racket
(define/contract (group-anagrams strs)
  (-> (listof string?) (listof (listof string?)))
  (let ([ht (make-hash)])
    (for ([s strs])
      (let ([key (list->string (sort (string->list s) char<?))])
        (hash-set! ht key (cons s (hash-ref ht key '())))))
    (hash-values ht))
    ; Time Complexity: O(n * k log k), Memory Complexity: O(n * k)
)

```