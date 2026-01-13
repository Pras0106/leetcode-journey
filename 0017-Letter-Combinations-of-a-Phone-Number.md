# cpp

## Sweet Spot

```cpp
class Solution {
public:
    vector<string> letterCombinations(string digits) {
        if (digits.empty()) return {};
        vector<string> mapping = {"", "", "abc", "def", "ghi", "jkl", "mno", "pqrs", "tuv", "wxyz"};
        vector<string> result = {""};
        for (char digit : digits) {
            vector<string> temp;
            for (string combo : result) {
                for (char letter : mapping[digit - '0']) {
                    temp.push_back(combo + letter);
                }
            }
            result = temp;
        }
        return result;
    }
};
// Time Complexity: O(4^n * n)
// Memory Complexity: O(4^n * n)

```

# java

## Sweet Spot

```java
class Solution {
    public List<String> letterCombinations(String digits) {
        if (digits.isEmpty()) return new ArrayList<>();
        String[] mapping = {"", "", "abc", "def", "ghi", "jkl", "mno", "pqrs", "tuv", "wxyz"};
        List<String> result = new ArrayList<>();
        result.add("");
        for (char digit : digits.toCharArray()) {
            List<String> next = new ArrayList<>();
            for (String s : result) {
                for (char c : mapping[digit - '0'].toCharArray()) {
                    next.add(s + c);
                }
            }
            result = next;
        }
        return result;
    }
}
// Time Complexity: O(4^n * n)
// Memory Complexity: O(4^n * n)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def letterCombinations(self, digits: str) -> List[str]:
        if not digits: return []
        mapping = {"2": "abc", "3": "def", "4": "ghi", "5": "jkl", "6": "mno", "7": "pqrs", "8": "tuv", "9": "wxyz"}
        res = [""]
        for d in digits:
            res = [prev + char for prev in res for char in mapping[d]]
        return res
# Time Complexity: O(4^n * n)
# Memory Complexity: O(4^n * n)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def letterCombinations(self, digits):
        """
        :type digits: str
        :rtype: List[str]
        """
        if not digits: return []
        mapping = {"2": "abc", "3": "def", "4": "ghi", "5": "jkl", "6": "mno", "7": "pqrs", "8": "tuv", "9": "wxyz"}
        res = [""]
        for d in digits:
            res = [prev + char for prev in res for char in mapping[d]]
        return res
# Time Complexity: O(4^n * n)
# Memory Complexity: O(4^n * n)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {string} digits
 * @return {string[]}
 */
var letterCombinations = function(digits) {
    if (!digits.length) return [];
    const mapping = ["", "", "abc", "def", "ghi", "jkl", "mno", "pqrs", "tuv", "wxyz"];
    let res = [""];
    for (let digit of digits) {
        let next = [];
        for (let prev of res) {
            for (let char of mapping[digit]) {
                next.push(prev + char);
            }
        }
        res = next;
    }
    return res;
};
// Time Complexity: O(4^n * n)
// Memory Complexity: O(4^n * n)

```

# Typescript

## Sweet Spot

```typescript
function letterCombinations(digits: string): string[] {
    if (digits.length === 0) return [];
    const mapping: string[] = ["", "", "abc", "def", "ghi", "jkl", "mno", "pqrs", "tuv", "wxyz"];
    let res: string[] = [""];
    for (const digit of digits) {
        const next: string[] = [];
        for (const prev of res) {
            for (const char of mapping[Number(digit)]) {
                next.push(prev + char);
            }
        }
        res = next;
    }
    return res;
};
// Time Complexity: O(4^n * n)
// Memory Complexity: O(4^n * n)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public IList<string> LetterCombinations(string digits) {
        if (string.IsNullOrEmpty(digits)) return new List<string>();
        string[] mapping = {"", "", "abc", "def", "ghi", "jkl", "mno", "pqrs", "tuv", "wxyz"};
        List<string> result = new List<string> {""};
        foreach (char digit in digits) {
            List<string> next = new List<string>();
            foreach (string s in result) {
                foreach (char c in mapping[digit - '0']) {
                    next.Add(s + c);
                }
            }
            result = next;
        }
        return result;
    }
}
// Time Complexity: O(4^n * n)
// Memory Complexity: O(4^n * n)

```

# C

## Sweet Spot

```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
char** letterCombinations(char* digits, int* returnSize) {
    int len = strlen(digits);
    if (len == 0) {
        *returnSize = 0;
        return NULL;
    }
    char* map[] = {"", "", "abc", "def", "ghi", "jkl", "mno", "pqrs", "tuv", "wxyz"};
    int counts[] = {0, 0, 3, 3, 3, 3, 3, 4, 3, 4};
    int total = 1;
    for (int i = 0; i < len; i++) total *= counts[digits[i] - '0'];
    *returnSize = total;
    char** res = (char**)malloc(total * sizeof(char*));
    for (int i = 0; i < total; i++) {
        res[i] = (char*)malloc((len + 1) * sizeof(char));
        res[i][len] = '\0';
    }
    for (int i = 0; i < total; i++) {
        int temp = i;
        for (int j = len - 1; j >= 0; j--) {
            int d = digits[j] - '0';
            res[i][j] = map[d][temp % counts[d]];
            temp /= counts[d];
        }
    }
    return res;
}
// Time Complexity: O(4^n * n)
// Memory Complexity: O(4^n * n)

```

# Go

## Sweet Spot

```go
func letterCombinations(digits string) []string {
    if len(digits) == 0 {
        return []string{}
    }
    mapping := []string{"", "", "abc", "def", "ghi", "jkl", "mno", "pqrs", "tuv", "wxyz"}
    res := []string{""}
    for _, digit := range digits {
        var next []string
        letters := mapping[digit-'0']
        for _, prev := range res {
            for _, char := range letters {
                next = append(next, prev+string(char))
            }
        }
        res = next
    }
    return res
}
// Time Complexity: O(4^n * n)
// Memory Complexity: O(4^n * n)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun letterCombinations(digits: String): List<String> {
        if (digits.isEmpty()) return listOf()
        val mapping = arrayOf("", "", "abc", "def", "ghi", "jkl", "mno", "pqrs", "tuv", "wxyz")
        var result = listOf("")
        for (digit in digits) {
            val next = mutableListOf<String>()
            for (s in result) {
                for (c in mapping[digit - '0']) {
                    next.add(s + c)
                }
            }
            result = next
        }
        return result
    }
}
// Time Complexity: O(4^n * n)
// Memory Complexity: O(4^n * n)

```

# swift

## Sweet Spot

```swift
class Solution {
    func letterCombinations(_ digits: String) -> [String] {
        if digits.isEmpty { return [] }
        let mapping = ["", "", "abc", "def", "ghi", "jkl", "mno", "pqrs", "tuv", "wxyz"]
        var res = [""]
        for char in digits {
            let digit = Int(String(char))!
            let letters = mapping[digit]
            var next = [String]()
            for s in res {
                for l in letters {
                    next.append(s + String(l))
                }
            }
            res = next
        }
        return res
    }
}
// Time Complexity: O(4^n * n)
// Memory Complexity: O(4^n * n)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn letter_combinations(digits: String) -> Vec<String> {
        if digits.is_empty() { return vec![]; }
        let mapping = vec!["", "", "abc", "def", "ghi", "jkl", "mno", "pqrs", "tuv", "wxyz"];
        let mut res = vec!["".to_string()];
        for digit in digits.chars() {
            let mut next = Vec::new();
            let d = digit.to_digit(10).unwrap() as usize;
            for prev in &res {
                for c in mapping[d].chars() {
                    next.push(format!("{}{}", prev, c));
                }
            }
            res = next;
        }
        res
    }
}
// Time Complexity: O(4^n * n)
// Memory Complexity: O(4^n * n)

```

# ruby

## Sweet Spot

```ruby
# @param {String} digits
# @return {String[]}
def letter_combinations(digits)
  return [] if digits.empty?
  mapping = ["", "", "abc", "def", "ghi", "jkl", "mno", "pqrs", "tuv", "wxyz"]
  res = [""]
  digits.each_char do |d|
    next_res = []
    res.each do |prev|
      mapping[d.to_i].each_char do |char|
        next_res << prev + char
      end
    end
    res = next_res
  end
  res
end
# Time Complexity: O(4^n * n)
# Memory Complexity: O(4^n * n)

```

# php

## Sweet Spot

```php
class Solution {
    /**
     * @param String $digits
     * @return String[]
     */
    function letterCombinations($digits) {
        if ($digits === "") return [];
        $mapping = ["", "", "abc", "def", "ghi", "jkl", "mno", "pqrs", "tuv", "wxyz"];
        $res = [""];
        for ($i = 0; $i < strlen($digits); $i++) {
            $next = [];
            $chars = str_split($mapping[$digits[$i]]);
            foreach ($res as $prev) {
                foreach ($chars as $char) {
                    $next[] = $prev . $char;
                }
            }
            $res = $next;
        }
        return $res;
    }
}
// Time Complexity: O(4^n * n)
// Memory Complexity: O(4^n * n)

```

# dart

## Sweet Spot

```dart
class Solution {
  List<String> letterCombinations(String digits) {
    if (digits.isEmpty) return [];
    List<String> mapping = ["", "", "abc", "def", "ghi", "jkl", "mno", "pqrs", "tuv", "wxyz"];
    List<String> res = [""];
    for (int i = 0; i < digits.length; i++) {
      List<String> next = [];
      String letters = mapping[int.parse(digits[i])];
      for (String prev in res) {
        for (int j = 0; j < letters.length; j++) {
          next.add(prev + letters[j]);
        }
      }
      res = next;
    }
    return res;
  }
}
// Time Complexity: O(4^n * n)
// Memory Complexity: O(4^n * n)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def letterCombinations(digits: String): List[String] = {
        if (digits.isEmpty) return Nil
        val mapping = Array("", "", "abc", "def", "ghi", "jkl", "mno", "pqrs", "tuv", "wxyz")
        digits.foldLeft(List("")) { (acc, digit) =>
            for {
                s <- acc
                c <- mapping(digit - '0')
            } yield s + c
        }
    }
}
// Time Complexity: O(4^n * n)
// Memory Complexity: O(4^n * n)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec letter_combinations(digits :: String.t) :: [String.t]
  def letter_combinations("") do
    []
  end

  def letter_combinations(digits) do
    map = %{
      ?2 => ["a", "b", "c"], ?3 => ["d", "e", "f"], ?4 => ["g", "h", "i"],
      ?5 => ["j", "k", "l"], ?6 => ["m", "n", "o"], ?7 => ["p", "q", "r", "s"],
      ?8 => ["t", "u", "v"], ?9 => ["w", "x", "y", "z"]
    }
    String.to_charlist(digits)
    |> Enum.reduce([""], fn d, acc ->
      for s <- acc, c <- Map.get(map, d), do: s <> c
    end)
  end
end
# Time Complexity: O(4^n * n)
# Memory Complexity: O(4^n * n)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec letter_combinations(Digits :: unicode:unicode_binary()) -> [unicode:unicode_binary()].
letter_combinations(<<>>) -> [];
letter_combinations(Digits) ->
    Map = #{ $2 => [<<"a">>, <<"b">>, <<"c">>], 
             $3 => [<<"d">>, <<"e">>, <<"f">>],
             $4 => [<<"g">>, <<"h">>, <<"i">>],
             $5 => [<<"j">>, <<"k">>, <<"l">>],
             $6 => [<<"m">>, <<"n">>, <<"o">>],
             $7 => [<<"p">>, <<"q">>, <<"r">>, <<"s">>],
             $8 => [<<"t">>, <<"u">>, <<"v">>],
             $9 => [<<"w">>, <<"x">>, <<"y">>, <<"z">>] },
    lists:foldl(fun(D, Acc) ->
        Letters = maps:get(D, Map),
        [ <<S/binary, L/binary>> || S <- Acc, L <- Letters ]
    end, [<<>>], binary_to_list(Digits)).
% Time Complexity: O(4^n * n)
% Memory Complexity: O(4^n * n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (letter-combinations digits)
  (-> string? (listof string?))
  (if (string=? digits "")
      '()
      (let ([mapping (vector "" "" "abc" "def" "ghi" "jkl" "mno" "pqrs" "tuv" "wxyz")])
        (foldl (lambda (d acc)
                 (let ([letters (string->list (vector-ref mapping (- (char->integer d) 48)))])
                   (for*/list ([s acc] [c letters])
                     (string-append s (string c)))))
               '("")
               (string->list digits)))))
; Time Complexity: O(4^n * n)
; Memory Complexity: O(4^n * n)

```