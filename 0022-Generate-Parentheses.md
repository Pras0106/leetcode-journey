# cpp

## Sweet Spot

```cpp
class Solution {
public:
    vector<string> generateParenthesis(int n) {
        vector<string> result;
        string current;
        backtrack(result, current, 0, 0, n);
        return result;
    }

private:
    // Time Complexity: O(4^n / sqrt(n))
    // Memory Complexity: O(n)
    void backtrack(vector<string>& result, string& current, int open, int close, int max) {
        if (current.length() == max * 2) {
            result.push_back(current);
            return;
        }
        if (open < max) {
            current.push_back('(');
            backtrack(result, current, open + 1, close, max);
            current.pop_back();
        }
        if (close < open) {
            current.push_back(')');
            backtrack(result, current, open, close + 1, max);
            current.pop_back();
        }
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public List<String> generateParenthesis(int n) {
        List<String> result = new ArrayList<>();
        backtrack(result, new StringBuilder(), 0, 0, n);
        return result;
    }

    // Time Complexity: O(4^n / sqrt(n))
    // Memory Complexity: O(n)
    private void backtrack(List<String> result, StringBuilder current, int open, int close, int max) {
        if (current.length() == max * 2) {
            result.add(current.toString());
            return;
        }
        if (open < max) {
            current.append("(");
            backtrack(result, current, open + 1, close, max);
            current.deleteCharAt(current.length() - 1);
        }
        if (close < open) {
            current.append(")");
            backtrack(result, current, open, close + 1, max);
            current.deleteCharAt(current.length() - 1);
        }
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def generateParenthesis(self, n: int) -> List[str]:
        # Time Complexity: O(4^n / sqrt(n))
        # Memory Complexity: O(n)
        res = []
        def backtrack(s=[], left=0, right=0):
            if len(s) == 2 * n:
                res.append("".join(s))
                return
            if left < n:
                s.append("(")
                backtrack(s, left + 1, right)
                s.pop()
            if right < left:
                s.append(")")
                backtrack(s, left, right + 1)
                s.pop()
        backtrack()
        return res

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def generateParenthesis(self, n):
        """
        :type n: int
        :rtype: List[str]
        """
        # Time Complexity: O(4^n / sqrt(n))
        # Memory Complexity: O(n)
        res = []
        def backtrack(s, left, right):
            if len(s) == 2 * n:
                res.append("".join(s))
                return
            if left < n:
                s.append("(")
                backtrack(s, left + 1, right)
                s.pop()
            if right < left:
                s.append(")")
                backtrack(s, left, right + 1)
                s.pop()
        backtrack([], 0, 0)
        return res

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number} n
 * @return {string[]}
 */
var generateParenthesis = function(n) {
    // Time Complexity: O(4^n / sqrt(n))
    // Memory Complexity: O(n)
    const res = [];
    const backtrack = (s, left, right) => {
        if (s.length === 2 * n) {
            res.push(s);
            return;
        }
        if (left < n) backtrack(s + "(", left + 1, right);
        if (right < left) backtrack(s + ")", left, right + 1);
    };
    backtrack("", 0, 0);
    return res;
};

```

# Typescript

## Sweet Spot

```typescript
function generateParenthesis(n: number): string[] {
    // Time Complexity: O(4^n / sqrt(n))
    // Memory Complexity: O(n)
    const res: string[] = [];
    const backtrack = (s: string, left: number, right: number): void => {
        if (s.length === 2 * n) {
            res.push(s);
            return;
        }
        if (left < n) backtrack(s + "(", left + 1, right);
        if (right < left) backtrack(s + ")", left, right + 1);
    };
    backtrack("", 0, 0);
    return res;
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public IList<string> GenerateParenthesis(int n) {
        // Time Complexity: O(4^n / sqrt(n))
        // Memory Complexity: O(n)
        var result = new List<string>();
        Backtrack(result, "", 0, 0, n);
        return result;
    }

    private void Backtrack(IList<string> result, string current, int open, int close, int max) {
        if (current.Length == max * 2) {
            result.Add(current);
            return;
        }
        if (open < max) Backtrack(result, current + "(", open + 1, close, max);
        if (close < open) Backtrack(result, current + ")", open, close + 1, max);
    }
}

```

# C

## Sweet Spot

```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
// Time Complexity: O(4^n / sqrt(n))
// Memory Complexity: O(n)
void backtrack(char** res, int* count, char* cur, int open, int close, int n, int pos) {
    if (pos == 2 * n) {
        cur[pos] = '\0';
        res[*count] = strdup(cur);
        (*count)++;
        return;
    }
    if (open < n) {
        cur[pos] = '(';
        backtrack(res, count, cur, open + 1, close, n, pos + 1);
    }
    if (close < open) {
        cur[pos] = ')';
        backtrack(res, count, cur, open, close + 1, n, pos + 1);
    }
}

char** generateParenthesis(int n, int* returnSize) {
    char** res = (char**)malloc(2000 * sizeof(char*));
    char* cur = (char*)malloc((2 * n + 1) * sizeof(char));
    *returnSize = 0;
    backtrack(res, returnSize, cur, 0, 0, n, 0);
    free(cur);
    return res;
}

```

# Go

## Sweet Spot

```go
func generateParenthesis(n int) []string {
    // Time Complexity: O(4^n / sqrt(n))
    // Memory Complexity: O(n)
    res := []string{}
    var backtrack func(string, int, int)
    backtrack = func(cur string, open int, close int) {
        if len(cur) == 2*n {
            res = append(res, cur)
            return
        }
        if open < n {
            backtrack(cur+"(", open+1, close)
        }
        if close < open {
            backtrack(cur+")", open, close+1)
        }
    }
    backtrack("", 0, 0)
    return res
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun generateParenthesis(n: Int): List<String> {
        // Time Complexity: O(4^n / sqrt(n))
        // Memory Complexity: O(n)
        val res = mutableListOf<String>()
        fun backtrack(cur: String, open: Int, close: Int) {
            if (cur.length == 2 * n) {
                res.add(cur)
                return
            }
            if (open < n) backtrack(cur + "(", open + 1, close)
            if (close < open) backtrack(cur + ")", open, close + 1)
        }
        backtrack("", 0, 0)
        return res
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func generateParenthesis(_ n: Int) -> [String] {
        // Time Complexity: O(4^n / sqrt(n))
        // Memory Complexity: O(n)
        var res = [String]()
        func backtrack(_ cur: String, _ open: Int, _ close: Int) {
            if cur.count == n * 2 {
                res.append(cur)
                return
            }
            if open < n {
                backtrack(cur + "(", open + 1, close)
            }
            if close < open {
                backtrack(cur + ")", open, close + 1)
            }
        }
        backtrack("", 0, 0)
        return res
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn generate_parenthesis(n: i32) -> Vec<String> {
        // Time Complexity: O(4^n / sqrt(n))
        // Memory Complexity: O(n)
        let mut res = Vec::new();
        let mut cur = String::new();
        Self::backtrack(&mut res, &mut cur, 0, 0, n);
        res
    }

    fn backtrack(res: &mut Vec<String>, cur: &mut String, open: i32, close: i32, n: i32) {
        if cur.len() == (n * 2) as usize {
            res.push(cur.clone());
            return;
        }
        if open < n {
            cur.push('(');
            Self::backtrack(res, cur, open + 1, close, n);
            cur.pop();
        }
        if close < open {
            cur.push(')');
            Self::backtrack(res, cur, open, close + 1, n);
            cur.pop();
        }
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer} n
# @return {String[]}
def generate_parenthesis(n)
  # Time Complexity: O(4^n / sqrt(n))
  # Memory Complexity: O(n)
  res = []
  backtrack = lambda do |cur, open, close|
    if cur.length == 2 * n
      res << cur
      return
    end
    backtrack.call(cur + "(", open + 1, close) if open < n
    backtrack.call(cur + ")", open, close + 1) if close < open
  end
  backtrack.call("", 0, 0)
  res
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer $n
     * @return String[]
     */
    function generateParenthesis($n) {
        // Time Complexity: O(4^n / sqrt(n))
        // Memory Complexity: O(n)
        $res = [];
        $this->backtrack($res, "", 0, 0, $n);
        return $res;
    }

    function backtrack(&$res, $cur, $open, $close, $n) {
        if (strlen($cur) == 2 * $n) {
            $res[] = $cur;
            return;
        }
        if ($open < $n) $this->backtrack($res, $cur . "(", $open + 1, $close, $n);
        if ($close < $open) $this->backtrack($res, $cur . ")", $open, $close + 1, $n);
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  List<String> generateParenthesis(int n) {
    // Time Complexity: O(4^n / sqrt(n))
    // Memory Complexity: O(n)
    List<String> res = [];
    void backtrack(String cur, int open, int close) {
      if (cur.length == 2 * n) {
        res.add(cur);
        return;
      }
      if (open < n) backtrack(cur + "(", open + 1, close);
      if (close < open) backtrack(cur + ")", open, close + 1);
    }
    backtrack("", 0, 0);
    return res;
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def generateParenthesis(n: Int): List[String] = {
        // Time Complexity: O(4^n / sqrt(n))
        // Memory Complexity: O(n)
        var res = List[String]()
        def backtrack(cur: String, open: Int, close: Int): Unit = {
            if (cur.length == 2 * n) {
                res = cur :: res
                return
            }
            if (open < n) backtrack(cur + "(", open + 1, close)
            if (close < open) backtrack(cur + ")", open, close + 1)
        }
        backtrack("", 0, 0)
        res.reverse
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec generate_parenthesis(n :: integer) :: [String.t]
  def generate_parenthesis(n) do
    # Time Complexity: O(4^n / sqrt(n))
    # Memory Complexity: O(n)
    backtrack("", 0, 0, n)
  end

  defp backtrack(cur, open, close, n) when byte_size(cur) == 2 * n do
    [cur]
  end

  defp backtrack(cur, open, close, n) do
    left = if open < n, do: backtrack(cur <> "(", open + 1, close, n), else: []
    right = if close < open, do: backtrack(cur <> ")", open, close + 1, n), else: []
    left ++ right
  end
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-export([generate_parenthesis/1]).

-spec generate_parenthesis(N :: integer()) -> [unicode:unicode_binary()].
generate_parenthesis(N) ->
    % Time Complexity: O(4^n / sqrt(n))
    % Memory Complexity: O(4^n / sqrt(n))
    backtrack(<<>>, 0, 0, N).

backtrack(Cur, Open, Close, N) when byte_size(Cur) =:= 2 * N ->
    [Cur];
backtrack(Cur, Open, Close, N) ->
    Res1 = if
        Open < N -> 
            backtrack(<<Cur/binary, "(">>, Open + 1, Close, N);
        true -> 
            []
    end,
    Res2 = if
        Close < Open -> 
            backtrack(<<Cur/binary, ")">>, Open, Close + 1, N);
        true -> 
            []
    end,
    Res1 ++ Res2.
```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (generate-parenthesis n)
  (-> exact-integer? (listof string?))
  ; Time Complexity: O(4^n / sqrt(n))
  ; Memory Complexity: O(n)
  (let backtrack ([cur ""] [open 0] [close 0])
    (cond
      [(= (string-length cur) (* 2 n)) (list cur)]
      [else
       (append
        (if (< open n) (backtrack (string-append cur "(") (+ open 1) close) '())
        (if (< close open) (backtrack (string-append cur ")") open (+ close 1)) '()))])))

```