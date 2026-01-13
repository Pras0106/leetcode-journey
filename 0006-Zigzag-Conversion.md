# cpp

## Sweet Spot

```cpp
class Solution {
public:
    string convert(string s, int numRows) {
        if (numRows == 1 || s.length() <= numRows) return s;
        string result;
        int n = s.length();
        int cycleLen = 2 * numRows - 2;
        for (int i = 0; i < numRows; i++) {
            for (int j = 0; j + i < n; j += cycleLen) {
                result += s[j + i];
                if (i != 0 && i != numRows - 1 && j + cycleLen - i < n) {
                    result += s[j + cycleLen - i];
                }
            }
        }
        return result;
    }
};
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# java

## Sweet Spot

```java
class Solution {
    public String convert(String s, int numRows) {
        if (numRows == 1 || s.length() <= numRows) return s;
        StringBuilder result = new StringBuilder();
        int n = s.length();
        int cycleLen = 2 * numRows - 2;
        for (int i = 0; i < numRows; i++) {
            for (int j = 0; j + i < n; j += cycleLen) {
                result.append(s.charAt(j + i));
                if (i != 0 && i != numRows - 1 && j + cycleLen - i < n) {
                    result.append(s.charAt(j + cycleLen - i));
                }
            }
        }
        return result.toString();
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def convert(self, s: str, numRows: int) -> str:
        if numRows == 1 or numRows >= len(s):
            return s
        res = []
        cycle = 2 * numRows - 2
        for i in range(numRows):
            for j in range(0, len(s) - i, cycle):
                res.append(s[j + i])
                if 0 < i < numRows - 1 and j + cycle - i < len(s):
                    res.append(s[j + cycle - i])
        return "".join(res)
# Time Complexity: O(n)
# Memory Complexity: O(n)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def convert(self, s, numRows):
        """
        :type s: str
        :type numRows: int
        :rtype: str
        """
        if numRows == 1 or numRows >= len(s):
            return s
        res = []
        cycle = 2 * numRows - 2
        for i in range(numRows):
            for j in range(0, len(s) - i, cycle):
                res.append(s[j + i])
                if 0 < i < numRows - 1 and j + cycle - i < len(s):
                    res.append(s[j + cycle - i])
        return "".join(res)
# Time Complexity: O(n)
# Memory Complexity: O(n)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {string} s
 * @param {number} numRows
 * @return {string}
 */
var convert = function(s, numRows) {
    if (numRows === 1 || s.length <= numRows) return s;
    let res = "";
    const n = s.length;
    const cycleLen = 2 * numRows - 2;
    for (let i = 0; i < numRows; i++) {
        for (let j = 0; j + i < n; j += cycleLen) {
            res += s[j + i];
            if (i !== 0 && i !== numRows - 1 && j + cycleLen - i < n) {
                res += s[j + cycleLen - i];
            }
        }
    }
    return res;
};
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# Typescript

## Sweet Spot

```typescript
function convert(s: string, numRows: number): string {
    if (numRows === 1 || s.length <= numRows) return s;
    let res: string[] = [];
    const n = s.length;
    const cycleLen = 2 * numRows - 2;
    for (let i = 0; i < numRows; i++) {
        for (let j = 0; j + i < n; j += cycleLen) {
            res.push(s[j + i]);
            if (i !== 0 && i !== numRows - 1 && j + cycleLen - i < n) {
                res.push(s[j + cycleLen - i]);
            }
        }
    }
    return res.join("");
};
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public string Convert(string s, int numRows) {
        if (numRows == 1 || s.Length <= numRows) return s;
        System.Text.StringBuilder res = new System.Text.StringBuilder();
        int n = s.Length;
        int cycleLen = 2 * numRows - 2;
        for (int i = 0; i < numRows; i++) {
            for (int j = 0; j + i < n; j += cycleLen) {
                res.Append(s[j + i]);
                if (i != 0 && i != numRows - 1 && j + cycleLen - i < n) {
                    res.Append(s[j + cycleLen - i]);
                }
            }
        }
        return res.ToString();
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# C

## Sweet Spot

```c
char* convert(char* s, int numRows) {
    int n = strlen(s);
    if (numRows == 1 || n <= numRows) return s;
    char* res = (char*)malloc((n + 1) * sizeof(char));
    int cycleLen = 2 * numRows - 2;
    int k = 0;
    for (int i = 0; i < numRows; i++) {
        for (int j = 0; j + i < n; j += cycleLen) {
            res[k++] = s[j + i];
            if (i != 0 && i != numRows - 1 && j + cycleLen - i < n) {
                res[k++] = s[j + cycleLen - i];
            }
        }
    }
    res[k] = '\0';
    return res;
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# Go

## Sweet Spot

```go
func convert(s string, numRows int) string {
    if numRows == 1 || len(s) <= numRows {
        return s
    }
    res := make([]byte, 0, len(s))
    cycleLen := 2*numRows - 2
    for i := 0; i < numRows; i++ {
        for j := 0; j+i < len(s); j += cycleLen {
            res = append(res, s[j+i])
            if i != 0 && i != numRows-1 && j+cycleLen-i < len(s) {
                res = append(res, s[j+cycleLen-i])
            }
        }
    }
    return string(res)
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun convert(s: String, numRows: Int): String {
        if (numRows == 1 || s.length <= numRows) return s
        val res = StringBuilder()
        val cycleLen = 2 * numRows - 2
        for (i in 0 until numRows) {
            for (j in 0 until s.length - i step cycleLen) {
                res.append(s[j + i])
                if (i != 0 && i != numRows - 1 && j + cycleLen - i < s.length) {
                    res.append(s[j + cycleLen - i])
                }
            }
        }
        return res.toString()
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# swift

## Sweet Spot

```swift
class Solution {
    func convert(_ s: String, _ numRows: Int) -> String {
        if numRows == 1 || s.count <= numRows { return s }
        var res = ""
        let characters = Array(s)
        let n = characters.count
        let cycleLen = 2 * numRows - 2
        for i in 0..<numRows {
            for j in stride(from: 0, to: n - i, by: cycleLen) {
                res.append(characters[j + i])
                if i != 0 && i != numRows - 1 && j + cycleLen - i < n {
                    res.append(characters[j + cycleLen - i])
                }
            }
        }
        return res
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn convert(s: String, num_rows: i32) -> String {
        if num_rows <= 1 || s.len() <= num_rows as usize {
            return s;
        }

        let mut rows: Vec<String> = vec![String::new(); num_rows as usize];
        let mut current_row = 0;
        let mut going_down = false;

        for c in s.chars() {
            rows[current_row].push(c);
            if current_row == 0 || current_row == num_rows as usize - 1 {
                going_down = !going_down;
            }
            current_row = if going_down {
                current_row + 1
            } else {
                current_row - 1
            };
        }

        rows.concat()
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(n)
```

# ruby

## Sweet Spot

```ruby
# @param {String} s
# @param {Integer} num_rows
# @return {String}
def convert(s, num_rows)
    return s if num_rows == 1 || s.length <= num_rows
    res = ""
    cycle_len = 2 * num_rows - 2
    (0...num_rows).each do |i|
        (0...(s.length - i)).step(cycle_len) do |j|
            res << s[j + i]
            if i != 0 && i != num_rows - 1 && j + cycle_len - i < s.length
                res << s[j + cycle_len - i]
            end
        end
    end
    res
end
# Time Complexity: O(n)
# Memory Complexity: O(n)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param String $s
     * @param Integer $numRows
     * @return String
     */
    function convert($s, $numRows) {
        if ($numRows == 1 || strlen($s) <= $numRows) return $s;
        $res = "";
        $n = strlen($s);
        $cycleLen = 2 * $numRows - 2;
        for ($i = 0; $i < $numRows; $i++) {
            for ($j = 0; $j + $i < $n; $j += $cycleLen) {
                $res .= $s[$j + $i];
                if ($i != 0 && $i != $numRows - 1 && $j + $cycleLen - $i < $n) {
                    $res .= $s[$j + $cycleLen - $i];
                }
            }
        }
        return $res;
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# dart

## Sweet Spot

```dart
class Solution {
  String convert(String s, int numRows) {
    if (numRows == 1 || s.length <= numRows) return s;
    StringBuffer res = StringBuffer();
    int cycleLen = 2 * numRows - 2;
    for (int i = 0; i < numRows; i++) {
      for (int j = 0; j + i < s.length; j += cycleLen) {
        res.write(s[j + i]);
        if (i != 0 && i != numRows - 1 && j + cycleLen - i < s.length) {
          res.write(s[j + cycleLen - i]);
        }
      }
    }
    return res.toString();
  }
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def convert(s: String, numRows: Int): String = {
        if (numRows == 1 || s.length <= numRows) return s
        val res = new StringBuilder()
        val cycleLen = 2 * numRows - 2
        for (i <- 0 until numRows) {
            for (j <- 0 until (s.length - i) by cycleLen) {
                res.append(s(j + i))
                if (i != 0 && i != numRows - 1 && j + cycleLen - i < s.length) {
                    res.append(s(j + cycleLen - i))
                }
            }
        }
        res.toString()
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec convert(s :: String.t, num_rows :: integer) :: String.t
  def convert(s, num_rows) when num_rows == 1, do: s
  def convert(s, num_rows) do
    len = String.length(s)
    if len <= num_rows do
      s
    else
      chars = String.to_charlist(s) |> List.to_tuple()
      cycle = 2 * num_rows - 2
      Enum.map_join(0..(num_rows - 1), fn i ->
        Enum.map_join(Enum.take_while(Stream.iterate(0, &(&1 + cycle)), &(&1 + i < len)), fn j ->
          first = elem(chars, j + i)
          second = if i != 0 and i != num_rows - 1 and j + cycle - i < len do
            [elem(chars, j + cycle - i)]
          else
            []
          end
          [first | second] |> List.to_string()
        end)
      end)
    end
  end
end
# Time Complexity: O(n)
# Memory Complexity: O(n)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec convert(S :: unicode:unicode_binary(), NumRows :: integer()) -> unicode:unicode_binary().
convert(S, 1) -> S;
convert(S, NumRows) ->
    Len = byte_size(S),
    if Len =< NumRows -> S;
       true ->
           CycleLen = 2 * NumRows - 2,
           Rows = [ 
               [ 
                 begin
                   Idx1 = J + I,
                   Idx2 = J + CycleLen - I,
                   Char1 = if Idx1 < Len -> [binary_part(S, Idx1, 1)]; true -> [] end,
                   Char2 = if (I > 0) and (I < NumRows - 1) and (Idx2 < Len) -> [binary_part(S, Idx2, 1)]; true -> [] end,
                   [Char1, Char2]
                 end
                 || J <- lists:seq(0, Len, CycleLen)
               ] 
               || I <- lists:seq(0, NumRows - 1) 
           ],
           unicode:characters_to_binary(Rows)
    end.
% Time Complexity: O(n)
% Memory Complexity: O(n)
```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (convert s numRows)
  (-> string? exact-integer? string?)
  (let ([n (string-length s)])
    (if (or (<= numRows 1) (<= n numRows))
        s
        (let* ([cycle-len (- (* 2 numRows) 2)]
               [res (open-output-string)])
          (for ([i (in-range numRows)])
            (for ([j (in-range 0 (- n i) cycle-len)])
              (write-char (string-ref s (+ j i)) res)
              (when (and (> i 0) (< i (- numRows 1)) (< (+ j cycle-len (- i)) n))
                (write-char (string-ref s (+ j cycle-len (- i))) res))))
          (get-output-string res)))))
; Time Complexity: O(n)
; Memory Complexity: O(n)

```