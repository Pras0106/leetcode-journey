# cpp

## Sweet Spot

```cpp
class Solution {
public:
    vector<string> fullJustify(vector<string>& words, int maxWidth) {
        vector<string> res;
        int n = words.size();
        int i = 0;
        while (i < n) {
            int len = words[i].length();
            int j = i + 1;
            while (j < n && len + 1 + words[j].length() <= maxWidth) {
                len += 1 + words[j].length();
                j++;
            }
            string line = "";
            int numWords = j - i;
            int numSpaces = maxWidth - (len - (numWords - 1));
            if (j == n || numWords == 1) {
                for (int k = i; k < j; k++) {
                    line += words[k];
                    if (line.length() < maxWidth) line += ' ';
                }
                while (line.length() < maxWidth) line += ' ';
            } else {
                int baseSpaces = numSpaces / (numWords - 1);
                int extraSpaces = numSpaces % (numWords - 1);
                for (int k = i; k < j - 1; k++) {
                    line += words[k];
                    int spacesToApply = baseSpaces + (k - i < extraSpaces ? 1 : 0);
                    line.append(spacesToApply, ' ');
                }
                line += words[j - 1];
            }
            res.push_back(line);
            i = j;
        }
        return res;
    }
};
// Time Complexity: O(n * maxWidth)
// Memory Complexity: O(n * maxWidth)

```

# java

## Sweet Spot

```java
class Solution {
    public List<String> fullJustify(String[] words, int maxWidth) {
        List<String> res = new ArrayList<>();
        int n = words.length;
        int i = 0;
        while (i < n) {
            int len = words[i].length();
            int j = i + 1;
            while (j < n && len + 1 + words[j].length() <= maxWidth) {
                len += 1 + words[j].length();
                j++;
            }
            StringBuilder sb = new StringBuilder();
            int numWords = j - i;
            if (j == n || numWords == 1) {
                for (int k = i; k < j; k++) {
                    sb.append(words[k]);
                    if (sb.length() < maxWidth) sb.append(" ");
                }
                while (sb.length() < maxWidth) sb.append(" ");
            } else {
                int totalSpaces = maxWidth - (len - (numWords - 1));
                int baseSpaces = totalSpaces / (numWords - 1);
                int extraSpaces = totalSpaces % (numWords - 1);
                for (int k = i; k < j - 1; k++) {
                    sb.append(words[k]);
                    int spaces = baseSpaces + (k - i < extraSpaces ? 1 : 0);
                    for (int s = 0; s < spaces; s++) sb.append(" ");
                }
                sb.append(words[j - 1]);
            }
            res.add(sb.toString());
            i = j;
        }
        return res;
    }
}
// Time Complexity: O(n * maxWidth)
// Memory Complexity: O(n * maxWidth)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def fullJustify(self, words: List[str], maxWidth: int) -> List[str]:
        res, cur, cur_len = [], [], 0
        for w in words:
            if cur_len + len(w) + len(cur) > maxWidth:
                for i in range(maxWidth - cur_len):
                    cur[i % (len(cur) - 1 or 1)] += ' '
                res.append("".join(cur))
                cur, cur_len = [], 0
            cur.append(w)
            cur_len += len(w)
        res.append(" ".join(cur).ljust(maxWidth))
        return res
# Time Complexity: O(n * maxWidth)
# Memory Complexity: O(n * maxWidth)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def fullJustify(self, words, maxWidth):
        """
        :type words: List[str]
        :type maxWidth: int
        :rtype: List[str]
        """
        res, cur, cur_len = [], [], 0
        for w in words:
            if cur_len + len(w) + len(cur) > maxWidth:
                for i in range(maxWidth - cur_len):
                    cur[i % (len(cur) - 1 or 1)] += ' '
                res.append("".join(cur))
                cur, cur_len = [], 0
            cur.append(w)
            cur_len += len(w)
        res.append(" ".join(cur).ljust(maxWidth))
        return res
# Time Complexity: O(n * maxWidth)
# Memory Complexity: O(n * maxWidth)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {string[]} words
 * @param {number} maxWidth
 * @return {string[]}
 */
var fullJustify = function(words, maxWidth) {
    let res = [];
    let i = 0;
    while (i < words.length) {
        let j = i + 1;
        let lineLen = words[i].length;
        while (j < words.length && lineLen + 1 + words[j].length <= maxWidth) {
            lineLen += 1 + words[j].length;
            j++;
        }
        let line = "";
        let numWords = j - i;
        if (j === words.length || numWords === 1) {
            for (let k = i; k < j; k++) {
                line += words[k] + (k < j - 1 ? " " : "");
            }
            line += " ".repeat(maxWidth - line.length);
        } else {
            let totalSpaces = maxWidth - (lineLen - (numWords - 1));
            let baseSpaces = Math.floor(totalSpaces / (numWords - 1));
            let extraSpaces = totalSpaces % (numWords - 1);
            for (let k = i; k < j - 1; k++) {
                line += words[k] + " ".repeat(baseSpaces + (k - i < extraSpaces ? 1 : 0));
            }
            line += words[j - 1];
        }
        res.push(line);
        i = j;
    }
    return res;
};
// Time Complexity: O(n * maxWidth)
// Memory Complexity: O(n * maxWidth)

```

# Typescript

## Sweet Spot

```typescript
function fullJustify(words: string[], maxWidth: number): string[] {
    let res: string[] = [];
    let i = 0;
    while (i < words.length) {
        let j = i + 1;
        let lineLen = words[i].length;
        while (j < words.length && lineLen + 1 + words[j].length <= maxWidth) {
            lineLen += 1 + words[j].length;
            j++;
        }
        let line = "";
        let numWords = j - i;
        if (j === words.length || numWords === 1) {
            for (let k = i; k < j; k++) {
                line += words[k] + (k < j - 1 ? " " : "");
            }
            line += " ".repeat(maxWidth - line.length);
        } else {
            let totalSpaces = maxWidth - (lineLen - (numWords - 1));
            let baseSpaces = Math.floor(totalSpaces / (numWords - 1));
            let extraSpaces = totalSpaces % (numWords - 1);
            for (let k = i; k < j - 1; k++) {
                line += words[k] + " ".repeat(baseSpaces + (k - i < extraSpaces ? 1 : 0));
            }
            line += words[j - 1];
        }
        res.push(line);
        i = j;
    }
    return res;
};
// Time Complexity: O(n * maxWidth)
// Memory Complexity: O(n * maxWidth)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public IList<string> FullJustify(string[] words, int maxWidth) {
        List<string> res = new List<string>();
        int i = 0;
        while (i < words.Length) {
            int j = i + 1;
            int lineLen = words[i].Length;
            while (j < words.Length && lineLen + 1 + words[j].Length <= maxWidth) {
                lineLen += 1 + words[j].Length;
                j++;
            }
            int numWords = j - i;
            StringBuilder sb = new StringBuilder();
            if (j == words.Length || numWords == 1) {
                for (int k = i; k < j; k++) {
                    sb.Append(words[k]);
                    if (k < j - 1) sb.Append(" ");
                }
                while (sb.Length < maxWidth) sb.Append(" ");
            } else {
                int totalSpaces = maxWidth - (lineLen - (numWords - 1));
                int baseSpaces = totalSpaces / (numWords - 1);
                int extraSpaces = totalSpaces % (numWords - 1);
                for (int k = i; k < j - 1; k++) {
                    sb.Append(words[k]);
                    sb.Append(' ', baseSpaces + (k - i < extraSpaces ? 1 : 0));
                }
                sb.Append(words[j - 1]);
            }
            res.Add(sb.ToString());
            i = j;
        }
        return res;
    }
}
// Time Complexity: O(n * maxWidth)
// Memory Complexity: O(n * maxWidth)

```

# C

## Sweet Spot

```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
char** fullJustify(char** words, int wordsSize, int maxWidth, int* returnSize) {
    char** res = malloc(wordsSize * sizeof(char*));
    int count = 0;
    int i = 0;
    while (i < wordsSize) {
        int j = i + 1;
        int lineLen = strlen(words[i]);
        while (j < wordsSize && lineLen + 1 + strlen(words[j]) <= maxWidth) {
            lineLen += 1 + strlen(words[j]);
            j++;
        }
        res[count] = malloc((maxWidth + 1) * sizeof(char));
        int numWords = j - i;
        int currPos = 0;
        if (j == wordsSize || numWords == 1) {
            for (int k = i; k < j; k++) {
                int wLen = strlen(words[k]);
                memcpy(res[count] + currPos, words[k], wLen);
                currPos += wLen;
                if (currPos < maxWidth) res[count][currPos++] = ' ';
            }
            while (currPos < maxWidth) res[count][currPos++] = ' ';
        } else {
            int totalSpaces = maxWidth - (lineLen - (numWords - 1));
            int baseSpaces = totalSpaces / (numWords - 1);
            int extraSpaces = totalSpaces % (numWords - 1);
            for (int k = i; k < j - 1; k++) {
                int wLen = strlen(words[k]);
                memcpy(res[count] + currPos, words[k], wLen);
                currPos += wLen;
                int spaces = baseSpaces + (k - i < extraSpaces ? 1 : 0);
                for (int s = 0; s < spaces; s++) res[count][currPos++] = ' ';
            }
            int wLen = strlen(words[j - 1]);
            memcpy(res[count] + currPos, words[j - 1], wLen);
            currPos += wLen;
        }
        res[count][maxWidth] = '\0';
        count++;
        i = j;
    }
    *returnSize = count;
    return res;
}
// Time Complexity: O(n * maxWidth)
// Memory Complexity: O(n * maxWidth)

```

# Go

## Sweet Spot

```go
func fullJustify(words []string, maxWidth int) []string {
    res := []string{}
    i := 0
    for i < len(words) {
        j := i + 1
        lineLen := len(words[i])
        for j < len(words) && lineLen + 1 + len(words[j]) <= maxWidth {
            lineLen += 1 + len(words[j])
            j++
        }
        numWords := j - i
        line := ""
        if j == len(words) || numWords == 1 {
            for k := i; k < j; k++ {
                line += words[k]
                if len(line) < maxWidth {
                    line += " "
                }
            }
            for len(line) < maxWidth {
                line += " "
            }
        } else {
            totalSpaces := maxWidth - (lineLen - (numWords - 1))
            baseSpaces := totalSpaces / (numWords - 1)
            extraSpaces := totalSpaces % (numWords - 1)
            for k := i; k < j - 1; k++ {
                line += words[k]
                spaces := baseSpaces
                if k-i < extraSpaces {
                    spaces++
                }
                for s := 0; s < spaces; s++ {
                    line += " "
                }
            }
            line += words[j-1]
        }
        res = append(res, line)
        i = j
    }
    return res
}
// Time Complexity: O(n * maxWidth)
// Memory Complexity: O(n * maxWidth)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun fullJustify(words: Array<String>, maxWidth: Int): List<String> {
        val res = mutableListOf<String>()
        var i = 0
        while (i < words.size) {
            var j = i + 1
            var lineLen = words[i].length
            while (j < words.size && lineLen + 1 + words[j].length <= maxWidth) {
                lineLen += 1 + words[j].length
                j++
            }
            val sb = StringBuilder()
            val numWords = j - i
            if (j == words.size || numWords == 1) {
                for (k in i until j) {
                    sb.append(words[k])
                    if (sb.length < maxWidth) sb.append(" ")
                }
                while (sb.length < maxWidth) sb.append(" ")
            } else {
                val totalSpaces = maxWidth - (lineLen - (numWords - 1))
                val baseSpaces = totalSpaces / (numWords - 1)
                val extraSpaces = totalSpaces % (numWords - 1)
                for (k in i until j - 1) {
                    sb.append(words[k])
                    val spaces = baseSpaces + if (k - i < extraSpaces) 1 else 0
                    repeat(spaces) { sb.append(" ") }
                }
                sb.append(words[j - 1])
            }
            res.add(sb.toString())
            i = j
        }
        return res
    }
}
// Time Complexity: O(n * maxWidth)
// Memory Complexity: O(n * maxWidth)

```

# swift

## Sweet Spot

```swift
class Solution {
    func fullJustify(_ words: [String], _ maxWidth: Int) -> [String] {
        var res = [String]()
        var i = 0
        while i < words.count {
            var j = i + 1
            var lineLen = words[i].count
            while j < words.count && lineLen + 1 + words[j].count <= maxWidth {
                lineLen += 1 + words[j].count
                j += 1
            }
            var line = ""
            let numWords = j - i
            if j == words.count || numWords == 1 {
                for k in i..<j {
                    line += words[k]
                    if line.count < maxWidth { line += " " }
                }
                line += String(repeating: " ", count: maxWidth - line.count)
            } else {
                let totalSpaces = maxWidth - (lineLen - (numWords - 1))
                let baseSpaces = totalSpaces / (numWords - 1)
                let extraSpaces = totalSpaces % (numWords - 1)
                for k in i..<j-1 {
                    line += words[k]
                    let spaces = baseSpaces + (k - i < extraSpaces ? 1 : 0)
                    line += String(repeating: " ", count: spaces)
                }
                line += words[j - 1]
            }
            res.append(line)
            i = j
        }
        return res
    }
}
// Time Complexity: O(n * maxWidth)
// Memory Complexity: O(n * maxWidth)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn full_justify(words: Vec<String>, max_width: i32) -> Vec<String> {
        let max_width = max_width as usize;
        let mut res = Vec::new();
        let mut i = 0;
        while i < words.len() {
            let mut j = i + 1;
            let mut line_len = words[i].len();
            while j < words.len() && line_len + 1 + words[j].len() <= max_width {
                line_len += 1 + words[j].len();
                j += 1;
            }
            let mut line = String::new();
            let num_words = j - i;
            if j == words.len() || num_words == 1 {
                for k in i..j {
                    line.push_str(&words[k]);
                    if line.len() < max_width { line.push(' '); }
                }
                while line.len() < max_width { line.push(' '); }
            } else {
                let total_spaces = max_width - (line_len - (num_words - 1));
                let base_spaces = total_spaces / (num_words - 1);
                let extra_spaces = total_spaces % (num_words - 1);
                for k in i..j-1 {
                    line.push_str(&words[k]);
                    let spaces = base_spaces + if k - i < extra_spaces { 1 } else { 0 };
                    line.push_str(&" ".repeat(spaces));
                }
                line.push_str(&words[j-1]);
            }
            res.push(line);
            i = j;
        }
        res
    }
}
// Time Complexity: O(n * maxWidth)
// Memory Complexity: O(n * maxWidth)

```

# ruby

## Sweet Spot

```ruby
# @param {String[]} words
# @param {Integer} max_width
# @return {String[]}
def full_justify(words, max_width)
    res = []
    i = 0
    while i < words.length
        j = i + 1
        line_len = words[i].length
        while j < words.length && line_len + 1 + words[j].length <= max_width
            line_len += 1 + words[j].length
            j += 1
        end
        num_words = j - i
        if j == words.length || num_words == 1
            line = words[i...j].join(" ")
            line += " " * (max_width - line.length)
        else
            total_spaces = max_width - (line_len - (num_words - 1))
            base_spaces = total_spaces / (num_words - 1)
            extra_spaces = total_spaces % (num_words - 1)
            line = ""
            (i...j-1).each_with_index do |k, idx|
                line += words[k]
                line += " " * (base_spaces + (idx < extra_spaces ? 1 : 0))
            end
            line += words[j-1]
        end
        res << line
        i = j
    end
    res
end
# Time Complexity: O(n * maxWidth)
# Memory Complexity: O(n * maxWidth)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param String[] $words
     * @param Integer $maxWidth
     * @return String[]
     */
    function fullJustify($words, $maxWidth) {
        $res = [];
        $i = 0;
        $n = count($words);
        
        while ($i < $n) {
            $j = $i + 1;
            $lineLen = strlen($words[$i]);
            
            while ($j < $n && $lineLen + 1 + strlen($words[$j]) <= $maxWidth) {
                $lineLen += 1 + strlen($words[$j]);
                $j++;
            }
            
            $numWords = $j - $i;
            $line = "";
            
            if ($j == $n || $numWords == 1) {
                $line = implode(" ", array_slice($words, $i, $numWords));
                $line = str_pad($line, $maxWidth);
            } else {
                $totalSpaces = $maxWidth - ($lineLen - ($numWords - 1));
                $baseSpaces = intdiv($totalSpaces, ($numWords - 1));
                $extraSpaces = $totalSpaces % ($numWords - 1);
                
                for ($k = $i; $k < $j - 1; $k++) {
                    $spacesToApply = $baseSpaces + ($k - $i < $extraSpaces ? 1 : 0);
                    $line .= $words[$k] . str_repeat(" ", $spacesToApply);
                }
                $line .= $words[$j - 1];
            }
            
            $res[] = $line;
            $i = $j;
        }
        
        return $res;
    }
}
// Time Complexity: O(n * maxWidth)
// Memory Complexity: O(n * maxWidth)
```

# dart

## Sweet Spot

```dart
class Solution {
  List<String> fullJustify(List<String> words, int maxWidth) {
    List<String> res = [];
    int i = 0;
    while (i < words.length) {
      int j = i + 1;
      int lineLen = words[i].length;
      while (j < words.length && lineLen + 1 + words[j].length <= maxWidth) {
        lineLen += 1 + words[j].length;
        j++;
      }
      int numWords = j - i;
      String line = "";
      if (j == words.length || numWords == 1) {
        line = words.sublist(i, j).join(" ");
        line = line.padRight(maxWidth);
      } else {
        int totalSpaces = maxWidth - (lineLen - (numWords - 1));
        int baseSpaces = totalSpaces ~/ (numWords - 1);
        int extraSpaces = totalSpaces % (numWords - 1);
        for (int k = i; k < j - 1; k++) {
          line += words[k] + " " * (baseSpaces + (k - i < extraSpaces ? 1 : 0));
        }
        line += words[j - 1];
      }
      res.add(line);
      i = j;
    }
    return res;
  }
}
// Time Complexity: O(n * maxWidth)
// Memory Complexity: O(n * maxWidth)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def fullJustify(words: Array[String], maxWidth: Int): List[String] = {
        var res = List[String]()
        var i = 0
        while (i < words.length) {
            var j = i + 1
            var lineLen = words(i).length
            while (j < words.length && lineLen + 1 + words(j).length <= maxWidth) {
                lineLen += 1 + words(j).length
                j += 1
            }
            val numWords = j - i
            val line = if (j == words.length || numWords == 1) {
                val s = words.slice(i, j).mkString(" ")
                s + " " * (maxWidth - s.length)
            } else {
                val totalSpaces = maxWidth - (lineLen - (numWords - 1))
                val baseSpaces = totalSpaces / (numWords - 1)
                val extraSpaces = totalSpaces % (numWords - 1)
                val sb = new StringBuilder()
                for (k <- i until j - 1) {
                    sb.append(words(k))
                    sb.append(" " * (baseSpaces + (if (k - i < extraSpaces) 1 else 0)))
                }
                sb.append(words(j - 1))
                sb.toString()
            }
            res = res :+ line
            i = j
        }
        res
    }
}
// Time Complexity: O(n * maxWidth)
// Memory Complexity: O(n * maxWidth)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec full_justify(words :: [String.t()], max_width :: integer) :: [String.t()]
  def full_justify(words, max_width) do
    do_justify(words, max_width, [])
  end

  defp do_justify([], _max_width, acc), do: Enum.reverse(acc)

  defp do_justify(words, max_width, acc) do
    {line_words, rest} = take_line(words, max_width, 0, [])
    is_last = rest == []
    formatted = format_line(line_words, max_width, is_last)
    do_justify(rest, max_width, [formatted | acc])
  end

  defp take_line([], _max_width, _cur_len, acc), do: {Enum.reverse(acc), []}

  defp take_line([w | rest] = words, max_width, cur_len, acc) do
    w_len = String.length(w)
    # If acc is empty, we only need w_len. Otherwise, we need 1 (space) + w_len.
    needed = if acc == [], do: w_len, else: cur_len + 1 + w_len

    if needed <= max_width do
      take_line(rest, max_width, needed, [w | acc])
    else
      {Enum.reverse(acc), words}
    end
  end

  defp format_line(words, max_width, true) do
    words
    |> Enum.join(" ")
    |> String.pad_trailing(max_width)
  end

  defp format_line([w], max_width, _is_last) do
    String.pad_trailing(w, max_width)
  end

  defp format_line(words, max_width, false) do
    num_words = length(words)
    total_chars = words |> Enum.map(&String.length/1) |> Enum.sum()
    total_spaces = max_width - total_chars
    
    # gaps = number of slots between words
    gaps = num_words - 1
    base_spaces = div(total_spaces, gaps)
    extra_spaces = rem(total_spaces, gaps)

    words
    |> Enum.with_index()
    |> Enum.map_join(fn {word, i} ->
      cond do
        # Last word in the line gets no trailing spaces
        i == gaps -> 
          word
        # Left-most slots get one extra space if extra_spaces > 0
        i < extra_spaces -> 
          word <> String.duplicate(" ", base_spaces + 1)
        # Normal slots
        true -> 
          word <> String.duplicate(" ", base_spaces)
      end
    end)
  end
end
# Time Complexity: O(n * maxWidth)
# Memory Complexity: O(n * maxWidth)
```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec full_justify(Words :: [unicode:unicode_binary()], MaxWidth :: integer()) -> [unicode:unicode_binary()].
full_justify(Words, MaxWidth) ->
    justify(Words, MaxWidth, []).

justify([], _, Acc) -> 
    lists:reverse(Acc);
justify(Words, MaxWidth, Acc) ->
    {LineWords, Rest} = get_line(Words, MaxWidth, 0, []),
    IsLast = (Rest == []),
    Formatted = format_line(LineWords, MaxWidth, IsLast),
    justify(Rest, MaxWidth, [Formatted | Acc]).

get_line([], _, _, Acc) -> 
    {lists:reverse(Acc), []};
get_line([W | T], MaxWidth, CurLen, Acc) ->
    WLen = byte_size(W),
    Needed = case Acc of 
        [] -> WLen; 
        _ -> CurLen + 1 + WLen 
    end,
    if 
        Needed =< MaxWidth -> get_line(T, MaxWidth, Needed, [W | Acc]);
        true -> {lists:reverse(Acc), [W | T]}
    end.

format_line(Words, MaxWidth, true) ->
    S = str_join(Words, <<" ">>),
    pad_trailing(S, MaxWidth);
format_line([W], MaxWidth, _) -> 
    pad_trailing(W, MaxWidth);
format_line(Words, MaxWidth, false) ->
    NumWords = length(Words),
    CharsLen = lists:foldl(fun(W, Sum) -> byte_size(W) + Sum end, 0, Words),
    TotalSpaces = MaxWidth - CharsLen,
    Base = TotalSpaces div (NumWords - 1),
    Extra = TotalSpaces rem (NumWords - 1),
    build_line(Words, Base, Extra, 0, <<>>).

build_line([W], _, _, _, Acc) -> 
    <<Acc/binary, W/binary>>;
build_line([W | T], Base, Extra, I, Acc) ->
    Spaces = if 
        I < Extra -> Base + 1; 
        true -> Base 
    end,
    SBin = binary:copy(<<" ">>, Spaces),
    build_line(T, Base, Extra, I + 1, <<Acc/binary, W/binary, SBin/binary>>).

str_join([H|T], Sep) -> 
    lists:foldl(fun(W, Acc) -> <<Acc/binary, Sep/binary, W/binary>> end, H, T);
str_join([], _) -> 
    <<>>.

pad_trailing(B, Max) ->
    Len = byte_size(B),
    if 
        Len < Max -> <<B/binary, (binary:copy(<<" ">>, Max - Len))/binary>>;
        true -> B
    end.

% Time Complexity: O(n * maxWidth)
% Memory Complexity: O(n * maxWidth)
```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (full-justify words maxWidth)
  (-> (listof string?) exact-integer? (listof string?))
  (define (format-line line-words is-last)
    (let* ([num-words (length line-words)]
           [chars-len (apply + (map string-length line-words))])
      (if (or is-last (= num-words 1))
          (let* ([base (string-join line-words " ")]
                 [padding (make-string (- maxWidth (string-length base)) #\space)])
            (string-append base padding))
          (let* ([total-spaces (- maxWidth chars-len)]
                 [base-spaces (quotient total-spaces (- num-words 1))]
                 [extra-spaces (remainder total-spaces (- num-words 1))])
            (let loop ([ws line-words] [i 0] [acc ""])
              (cond
                [(null? (cdr ws)) (string-append acc (car ws))]
                [else (let ([s-count (+ base-spaces (if (< i extra-spaces) 1 0))])
                        (loop (cdr ws) (+ i 1) 
                              (string-append acc (car ws) (make-string s-count #\space))))]))))))
  (let loop ([ws words] [res '()])
    (if (null? ws)
        (reverse res)
        (let-values ([(line-ws rest) 
                      (let line-loop ([ws ws] [cur-len 0] [acc '()])
                        (if (null? ws)
                            (values (reverse acc) '())
                            (let* ([w (car ws)]
                                   [w-len (string-length w)]
                                   [needed (if (null? acc) w-len (+ cur-len 1 w-len))])
                              (if (<= needed maxWidth)
                                  (line-loop (cdr ws) needed (cons w acc))
                                  (values (reverse acc) ws)))))])
          (loop rest (cons (format-line line-ws (null? rest)) res))))))
; Time Complexity: O(n * maxWidth)
; Memory Complexity: O(n * maxWidth)

```