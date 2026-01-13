# cpp

## Sweet Spot

```cpp
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
        if (strs.empty()) return "";
        string prefix = strs[0];
        for (int i = 1; i < strs.size(); i++) {
            while (strs[i].find(prefix) != 0) {
                prefix = prefix.substr(0, prefix.length() - 1);
                if (prefix.empty()) return "";
            }
        }
        return prefix;
    }
};
// Time Complexity: O(S), where S is the sum of all characters in all strings.
// Memory Complexity: O(1) beyond the output string.

```

# java

## Sweet Spot

```java
class Solution {
    public String longestCommonPrefix(String[] strs) {
        if (strs == null || strs.length == 0) return "";
        String prefix = strs[0];
        for (int i = 1; i < strs.length; i++) {
            while (strs[i].indexOf(prefix) != 0) {
                prefix = prefix.substring(0, prefix.length() - 1);
                if (prefix.isEmpty()) return "";
            }
        }
        return prefix;
    }
}
// Time Complexity: O(S)
// Memory Complexity: O(1)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str:
        if not strs:
            return ""
        prefix = strs[0]
        for i in range(1, len(strs)):
            while not strs[i].startswith(prefix):
                prefix = prefix[:-1]
                if not prefix:
                    return ""
        return prefix
# Time Complexity: O(S)
# Memory Complexity: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def longestCommonPrefix(self, strs):
        """
        :type strs: List[str]
        :rtype: str
        """
        if not strs:
            return ""
        prefix = strs[0]
        for i in range(1, len(strs)):
            while not strs[i].startswith(prefix):
                prefix = prefix[:-1]
                if not prefix:
                    return ""
        return prefix
# Time Complexity: O(S)
# Memory Complexity: O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {string[]} strs
 * @return {string}
 */
var longestCommonPrefix = function(strs) {
    if (!strs.length) return "";
    let prefix = strs[0];
    for (let i = 1; i < strs.length; i++) {
        while (strs[i].indexOf(prefix) !== 0) {
            prefix = prefix.substring(0, prefix.length - 1);
            if (prefix === "") return "";
        }
    }
    return prefix;
};
// Time Complexity: O(S)
// Memory Complexity: O(1)

```

# Typescript

## Sweet Spot

```typescript
function longestCommonPrefix(strs: string[]): string {
    if (strs.length === 0) return "";
    let prefix: string = strs[0];
    for (let i = 1; i < strs.length; i++) {
        while (strs[i].indexOf(prefix) !== 0) {
            prefix = prefix.substring(0, prefix.length - 1);
            if (prefix === "") return "";
        }
    }
    return prefix;
};
// Time Complexity: O(S)
// Memory Complexity: O(1)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public string LongestCommonPrefix(string[] strs) {
        if (strs == null || strs.Length == 0) return "";
        string prefix = strs[0];
        for (int i = 1; i < strs.Length; i++) {
            while (strs[i].IndexOf(prefix) != 0) {
                prefix = prefix.Substring(0, prefix.Length - 1);
                if (prefix == "") return "";
            }
        }
        return prefix;
    }
}
// Time Complexity: O(S)
// Memory Complexity: O(1)

```

# C

## Sweet Spot

```c
char* longestCommonPrefix(char** strs, int strsSize) {
    if (strsSize == 0) return "";
    char* prefix = strs[0];
    for (int i = 1; i < strsSize; i++) {
        int j = 0;
        while (prefix[j] && strs[i][j] && prefix[j] == strs[i][j]) {
            j++;
        }
        prefix[j] = '\0';
        if (prefix[0] == '\0') return "";
    }
    return prefix;
}
// Time Complexity: O(S)
// Memory Complexity: O(1)

```

# Go

## Sweet Spot

```go
func longestCommonPrefix(strs []string) string {
    if len(strs) == 0 {
        return ""
    }
    prefix := strs[0]
    for i := 1; i < len(strs); i++ {
        for len(prefix) > 0 {
            if len(strs[i]) >= len(prefix) && strs[i][:len(prefix)] == prefix {
                break
            }
            prefix = prefix[:len(prefix)-1]
        }
        if prefix == "" {
            return ""
        }
    }
    return prefix
}
// Time Complexity: O(S)
// Memory Complexity: O(1)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun longestCommonPrefix(strs: Array<String>): String {
        if (strs.isEmpty()) return ""
        var prefix = strs[0]
        for (i in 1 until strs.size) {
            while (strs[i].indexOf(prefix) != 0) {
                prefix = prefix.substring(0, prefix.length - 1)
                if (prefix.isEmpty()) return ""
            }
        }
        return prefix
    }
}
// Time Complexity: O(S)
// Memory Complexity: O(1)

```

# swift

## Sweet Spot

```swift
class Solution {
    func longestCommonPrefix(_ strs: [String]) -> String {
        guard !strs.isEmpty else { return "" }
        var prefix = strs[0]
        for i in 1..<strs.count {
            while !strs[i].hasPrefix(prefix) {
                prefix.removeLast()
                if prefix.isEmpty { return "" }
            }
        }
        return prefix
    }
}
// Time Complexity: O(S)
// Memory Complexity: O(1)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn longest_common_prefix(strs: Vec<String>) -> String {
        if strs.is_empty() { return String::new(); }
        let mut prefix = strs[0].clone();
        for s in strs.iter().skip(1) {
            while !s.starts_with(&prefix) {
                prefix.pop();
                if prefix.is_empty() { return String::new(); }
            }
        }
        prefix
    }
}
// Time Complexity: O(S)
// Memory Complexity: O(1)

```

# ruby

## Sweet Spot

```ruby
# @param {String[]} strs
# @return {String}
def longest_common_prefix(strs)
    return "" if strs.empty?
    prefix = strs[0]
    strs[1..-1].each do |s|
        while s.index(prefix) != 0
            prefix = prefix[0...-1]
            return "" if prefix.empty?
        end
    end
    prefix
end
# Time Complexity: O(S)
# Memory Complexity: O(1)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param String[] $strs
     * @return String
     */
    function longestCommonPrefix($strs) {
        if (empty($strs)) return "";
        $prefix = $strs[0];
        for ($i = 1; $i < count($strs); $i++) {
            while (strpos($strs[$i], $prefix) !== 0) {
                $prefix = substr($prefix, 0, -1);
                if ($prefix === "") return "";
            }
        }
        return $prefix;
    }
}
// Time Complexity: O(S)
// Memory Complexity: O(1)

```

# dart

## Sweet Spot

```dart
class Solution {
  String longestCommonPrefix(List<String> strs) {
    if (strs.isEmpty) return "";
    String prefix = strs[0];
    for (int i = 1; i < strs.length; i++) {
      while (!strs[i].startsWith(prefix)) {
        prefix = prefix.substring(0, prefix.length - 1);
        if (prefix.isEmpty) return "";
      }
    }
    return prefix;
  }
}
// Time Complexity: O(S)
// Memory Complexity: O(1)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def longestCommonPrefix(strs: Array[String]): String = {
        if (strs.isEmpty) return ""
        var prefix = strs(0)
        var i = 1
        while (i < strs.length) {
            while (!strs(i).startsWith(prefix)) {
                prefix = prefix.substring(0, prefix.length - 1)
            }
            if (prefix.isEmpty) return ""
            i += 1
        }
        prefix
    }
}
// Time Complexity: O(S)
// Memory Complexity: O(1)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec longest_common_prefix(strs :: [String.t]) :: String.t
  def longest_common_prefix([]), do: ""
  def longest_common_prefix([first | rest]) do
    Enum.reduce(rest, first, fn s, acc ->
      find_prefix(acc, s)
    end)
  end

  defp find_prefix(p, s) do
    if String.starts_with?(s, p) do
      p
    else
      find_prefix(String.slice(p, 0..-2//1), s)
    end
  end
end
# Time Complexity: O(S)
# Memory Complexity: O(S)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec longest_common_prefix(Strs :: [unicode:unicode_binary()]) -> unicode:unicode_binary().
longest_common_prefix([]) -> <<>>;
longest_common_prefix([H | T]) ->
    lists:foldl(fun(S, Acc) -> common(Acc, S) end, H, T).

common(<<>>, _) -> <<>>;
common(Prefix, S) ->
    case S of
        <<Prefix:(byte_size(Prefix))/binary, _/binary>> -> Prefix;
        _ -> common(binary:part(Prefix, {0, byte_size(Prefix) - 1}), S)
    end.
% Time Complexity: O(S)
% Memory Complexity: O(S)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (longest-common-prefix strs)
  (-> (listof string?) string?)
  (if (empty? strs)
      ""
      (foldl (lambda (s acc)
               (let loop ([prefix acc])
                 (if (string-prefix? s prefix)
                     prefix
                     (if (string=? prefix "")
                         ""
                         (loop (substring prefix 0 (sub1 (string-length prefix))))))))
             (first strs)
             (rest strs))))
; Time Complexity: O(S)
; Memory Complexity: O(S)

```