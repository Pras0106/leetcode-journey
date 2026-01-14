# cpp

## Sweet Spot

```cpp
class Solution {
public:
    string countAndSay(int n) {
        if (n == 1) return "1";
        string curr = "1";
        for (int i = 2; i <= n; ++i) {
            string next = "";
            int len = curr.length();
            for (int j = 0; j < len; ++j) {
                int count = 1;
                while (j + 1 < len && curr[j] == curr[j + 1]) {
                    count++;
                    j++;
                }
                next += to_string(count) + curr[j];
            }
            curr = next;
        }
        return curr;
    }
};
// Time Complexity: O(2^n), Space Complexity: O(2^n)

```

# java

## Sweet Spot

```java
class Solution {
    public String countAndSay(int n) {
        if (n == 1) return "1";
        String curr = "1";
        for (int i = 2; i <= n; i++) {
            StringBuilder next = new StringBuilder();
            int len = curr.length();
            for (int j = 0; j < len; j++) {
                int count = 1;
                while (j + 1 < len && curr.charAt(j) == curr.charAt(j + 1)) {
                    count++;
                    j++;
                }
                next.append(count).append(curr.charAt(j));
            }
            curr = next.toString();
        }
        return curr;
    }
}
// Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def countAndSay(self, n: int) -> str:
        curr = "1"
        for _ in range(n - 1):
            next_val = []
            i = 0
            while i < len(curr):
                count = 1
                while i + 1 < len(curr) and curr[i] == curr[i+1]:
                    count += 1
                    i += 1
                next_val.append(str(count))
                next_val.append(curr[i])
                i += 1
            curr = "".join(next_val)
        return curr
# Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def countAndSay(self, n):
        """
        :type n: int
        :rtype: str
        """
        curr = "1"
        for _ in range(n - 1):
            next_val = []
            i = 0
            while i < len(curr):
                count = 1
                while i + 1 < len(curr) and curr[i] == curr[i+1]:
                    count += 1
                    i += 1
                next_val.append(str(count))
                next_val.append(curr[i])
                i += 1
            curr = "".join(next_val)
        return curr
# Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number} n
 * @return {string}
 */
var countAndSay = function(n) {
    let curr = "1";
    for (let i = 2; i <= n; i++) {
        let next = "";
        let j = 0;
        while (j < curr.length) {
            let count = 1;
            while (j + 1 < curr.length && curr[j] === curr[j + 1]) {
                count++;
                j++;
            }
            next += count.toString() + curr[j];
            j++;
        }
        curr = next;
    }
    return curr;
};
// Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# Typescript

## Sweet Spot

```typescript
function countAndSay(n: number): string {
    let curr: string = "1";
    for (let i = 2; i <= n; i++) {
        let next: string = "";
        let j: number = 0;
        while (j < curr.length) {
            let count: number = 1;
            while (j + 1 < curr.length && curr[j] === curr[j + 1]) {
                count++;
                j++;
            }
            next += count.toString() + curr[j];
            j++;
        }
        curr = next;
    }
    return curr;
};
// Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# C#

## Sweet Spot

```c#
using System.Text;

public class Solution {
    public string CountAndSay(int n) {
        if (n == 1) return "1";
        string curr = "1";
        for (int i = 2; i <= n; i++) {
            StringBuilder next = new StringBuilder();
            for (int j = 0; j < curr.Length; j++) {
                int count = 1;
                while (j + 1 < curr.Length && curr[j] == curr[j + 1]) {
                    count++;
                    j++;
                }
                next.Append(count).Append(curr[j]);
            }
            curr = next.ToString();
        }
        return curr;
    }
}
// Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# C

## Sweet Spot

```c
#include <stdlib.h>
#include <string.h>
#include <stdio.h>

char* countAndSay(int n) {
    if (n == 1) return strdup("1");
    char* curr = strdup("1");
    for (int i = 2; i <= n; i++) {
        int len = strlen(curr);
        char* next = (char*)malloc(len * 3 + 1);
        int next_idx = 0;
        for (int j = 0; j < len; j++) {
            int count = 1;
            while (j + 1 < len && curr[j] == curr[j + 1]) {
                count++;
                j++;
            }
            next_idx += sprintf(&next[next_idx], "%d%c", count, curr[j]);
        }
        free(curr);
        curr = next;
    }
    return curr;
}
// Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# Go

## Sweet Spot

```go
import (
    "strconv"
    "strings"
)

func countAndSay(n int) string {
    curr := "1"
    for i := 2; i <= n; i++ {
        var next strings.Builder
        for j := 0; j < len(curr); j++ {
            count := 1
            for j+1 < len(curr) && curr[j] == curr[j+1] {
                count++
                j++
            }
            next.WriteString(strconv.Itoa(count))
            next.WriteByte(curr[j])
        }
        curr = next.String()
    }
    return curr
}
// Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun countAndSay(n: Int): String {
        var curr = "1"
        for (i in 2..n) {
            val next = StringBuilder()
            var j = 0
            while (j < curr.length) {
                var count = 1
                while (j + 1 < curr.length && curr[j] == curr[j + 1]) {
                    count++
                    j++
                }
                next.append(count).append(curr[j])
                j++
            }
            curr = next.toString()
        }
        return curr
    }
}
// Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# swift

## Sweet Spot

```swift
class Solution {
    func countAndSay(_ n: Int) -> String {
        if n == 1 { return "1" }
        var curr = "1"
        for _ in 2...n {
            var next = ""
            let chars = Array(curr)
            var j = 0
            while j < chars.count {
                var count = 1
                while j + 1 < chars.count && chars[j] == chars[j + 1] {
                    count += 1
                    j += 1
                }
                next += String(count) + String(chars[j])
                j += 1
            }
            curr = next
        }
        return curr
    }
}
// Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn count_and_say(n: i32) -> String {
        let mut curr = String::from("1");
        for _ in 2..=n {
            let mut next = String::new();
            let mut chars = curr.chars().peekable();
            while let Some(c) = chars.next() {
                let mut count = 1;
                while let Some(&nc) = chars.peek() {
                    if nc == c {
                        count += 1;
                        chars.next();
                    } else {
                        break;
                    }
                }
                next.push_str(&count.to_string());
                next.push(c);
            }
            curr = next;
        }
        curr
    }
}
// Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# ruby

## Sweet Spot

```ruby
# @param {Integer} n
# @return {String}
def count_and_say(n)
    curr = "1"
    (n - 1).times do
        next_val = ""
        i = 0
        while i < curr.length
            count = 1
            while i + 1 < curr.length && curr[i] == curr[i+1]
                count += 1
                i += 1
            end
            next_val << count.to_s << curr[i]
            i += 1
        end
        curr = next_val
    end
    curr
end
# Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer $n
     * @return String
     */
    function countAndSay($n) {
        $curr = "1";
        for ($i = 2; $i <= $n; $i++) {
            $next = "";
            $len = strlen($curr);
            for ($j = 0; $j < $len; $j++) {
                $count = 1;
                while ($j + 1 < $len && $curr[$j] == $curr[$j+1]) {
                    $count++;
                    $j++;
                }
                $next .= $count . $curr[$j];
            }
            $curr = $next;
        }
        return $curr;
    }
}
// Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# dart

## Sweet Spot

```dart
class Solution {
  String countAndSay(int n) {
    String curr = "1";
    for (int i = 2; i <= n; i++) {
      StringBuffer next = StringBuffer();
      for (int j = 0; j < curr.length; j++) {
        int count = 1;
        while (j + 1 < curr.length && curr[j] == curr[j + 1]) {
          count++;
          j++;
        }
        next.write(count);
        next.write(curr[j]);
      }
      curr = next.toString();
    }
    return curr;
  }
}
// Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def countAndSay(n: Int): String = {
        var curr = "1"
        for (_ <- 2 to n) {
            val next = new StringBuilder()
            var j = 0
            while (j < curr.length) {
                var count = 1
                while (j + 1 < curr.length && curr(j) == curr(j + 1)) {
                    count += 1
                    j += 1
                }
                next.append(count).append(curr(j))
                j += 1
            }
            curr = next.toString()
        }
        curr
    }
}
// Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec count_and_say(n :: integer) :: String.t
  def count_and_say(1), do: "1"
  def count_and_say(n) do
    Enum.reduce(2..n, "1", fn _, acc ->
      acc
      |> String.to_charlist()
      |> Enum.chunk_by(& &1)
      |> Enum.map_join(fn chunk -> "#{length(chunk)}#{[hd(chunk)]}" end)
    end)
  end
end
# Time Complexity: O(2^n)
# Memory Complexity: O(2^n)
```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec count_and_say(N :: integer()) -> unicode:unicode_binary().
count_and_say(1) -> <<"1">>;
count_and_say(N) ->
    Prev = count_and_say(N - 1),
    rle(binary_to_list(Prev), []).

rle([], Acc) -> list_to_binary(lists:reverse(Acc));
rle([H|T], Acc) ->
    {Count, Rest} = count_run(T, H, 1),
    rle(Rest, [H, integer_to_list(Count) | Acc]).

count_run([H|T], H, Count) -> count_run(T, H, Count + 1);
count_run(Rest, _, Count) -> {Count, Rest}.
% Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (count-and-say n)
  (-> exact-integer? string?)
  (let loop ([i 1] [curr "1"])
    (if (= i n)
        curr
        (loop (+ i 1) (next-sequence curr)))))

(define (next-sequence s)
  (let ([chars (string->list s)])
    (let rle ([lst chars] [acc ""])
      (if (null? lst)
          acc
          (let-values ([(count rest) (count-run (cdr lst) (car lst) 1)])
            (rle rest (string-append acc (number->string count) (string (car lst)))))))))

(define (count-run lst char count)
  (if (and (not (null? lst)) (char=? (car lst) char))
      (count-run (cdr lst) char (+ count 1))
      (values count lst)))
; Time Complexity: O(2^n), Memory Complexity: O(2^n)

```