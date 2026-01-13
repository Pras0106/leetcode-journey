# cpp

## Sweet Spot

```cpp
class Solution {
public:
    bool isValid(string s) {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        std::stack<char> st;
        for (char c : s) {
            if (c == '(' || c == '{' || c == '[') {
                st.push(c);
            } else {
                if (st.empty()) return false;
                if (c == ')' && st.top() != '(') return false;
                if (c == '}' && st.top() != '{') return false;
                if (c == ']' && st.top() != '[') return false;
                st.pop();
            }
        }
        return st.empty();
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public boolean isValid(String s) {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        java.util.Stack<Character> stack = new java.util.Stack<>();
        for (char c : s.toCharArray()) {
            if (c == '(') stack.push(')');
            else if (c == '{') stack.push('}');
            else if (c == '[') stack.push(']');
            else if (stack.isEmpty() || stack.pop() != c) return false;
        }
        return stack.isEmpty();
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def isValid(self, s: str) -> bool:
        # Time Complexity: O(n)
        # Memory Complexity: O(n)
        stack = []
        mapping = {")": "(", "}": "{", "]": "["}
        for char in s:
            if char in mapping:
                top_element = stack.pop() if stack else '#'
                if mapping[char] != top_element:
                    return False
            else:
                stack.append(char)
        return not stack

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def isValid(self, s):
        """
        :type s: str
        :rtype: bool
        """
        # Time Complexity: O(n)
        # Memory Complexity: O(n)
        stack = []
        mapping = {")": "(", "}": "{", "]": "["}
        for char in s:
            if char in mapping:
                top_element = stack.pop() if stack else '#'
                if mapping[char] != top_element:
                    return False
            else:
                stack.append(char)
        return not stack

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {string} s
 * @return {boolean}
 */
var isValid = function(s) {
    // Time Complexity: O(n)
    // Memory Complexity: O(n)
    const stack = [];
    const map = { ')': '(', '}': '{', ']': '[' };
    for (let i = 0; i < s.length; i++) {
        const char = s[i];
        if (map[char]) {
            if (stack.pop() !== map[char]) return false;
        } else {
            stack.push(char);
        }
    }
    return stack.length === 0;
};

```

# Typescript

## Sweet Spot

```typescript
function isValid(s: string): boolean {
    // Time Complexity: O(n)
    // Memory Complexity: O(n)
    const stack: string[] = [];
    const map: Record<string, string> = { ')': '(', '}': '{', ']': '[' };
    for (const char of s) {
        if (map[char]) {
            if (stack.pop() !== map[char]) return false;
        } else {
            stack.push(char);
        }
    }
    return stack.length === 0;
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public bool IsValid(string s) {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        var stack = new System.Collections.Generic.Stack<char>();
        foreach (char c in s) {
            if (c == '(') stack.Push(')');
            else if (c == '{') stack.Push('}');
            else if (c == '[') stack.Push(']');
            else if (stack.Count == 0 || stack.Pop() != c) return false;
        }
        return stack.Count == 0;
    }
}

```

# C

## Sweet Spot

```c
bool isValid(char* s) {
    // Time Complexity: O(n)
    // Memory Complexity: O(n)
    int len = strlen(s);
    char* stack = (char*)malloc(len);
    int top = -1;
    for (int i = 0; i < len; i++) {
        if (s[i] == '(' || s[i] == '{' || s[i] == '[') {
            stack[++top] = s[i];
        } else {
            if (top == -1) { free(stack); return false; }
            if (s[i] == ')' && stack[top] != '(') { free(stack); return false; }
            if (s[i] == '}' && stack[top] != '{') { free(stack); return false; }
            if (s[i] == ']' && stack[top] != '[') { free(stack); return false; }
            top--;
        }
    }
    bool res = (top == -1);
    free(stack);
    return res;
}

```

# Go

## Sweet Spot

```go
func isValid(s string) bool {
    // Time Complexity: O(n)
    // Memory Complexity: O(n)
    stack := make([]rune, 0)
    mapping := map[rune]rune{')': '(', '}': '{', ']': '['}
    for _, char := range s {
        if opener, ok := mapping[char]; ok {
            if len(stack) == 0 || stack[len(stack)-1] != opener {
                return false
            }
            stack = stack[:len(stack)-1]
        } else {
            stack = append(stack, char)
        }
    }
    return len(stack) == 0
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun isValid(s: String): Boolean {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        val stack = java.util.ArrayDeque<Char>()
        for (c in s) {
            when (c) {
                '(' -> stack.push(')')
                '{' -> stack.push('}')
                '[' -> stack.push(']')
                else -> if (stack.isEmpty() || stack.pop() != c) return false
            }
        }
        return stack.isEmpty()
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func isValid(_ s: String) -> Bool {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        var stack = [Character]()
        let dict: [Character: Character] = [")": "(", "}": "{", "]": "["]
        for char in s {
            if let opener = dict[char] {
                if stack.isEmpty || stack.removeLast() != opener {
                    return false
                }
            } else {
                stack.append(char)
            }
        }
        return stack.isEmpty
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn is_valid(s: String) -> bool {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        let mut stack = Vec::new();
        for c in s.chars() {
            match c {
                '(' => stack.push(')'),
                '{' => stack.push('}'),
                '[' => stack.push(']'),
                ')' | '}' | ']' if Some(c) != stack.pop() => return false,
                _ => (),
            }
        }
        stack.is_empty()
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {String} s
# @return {Boolean}
def is_valid(s)
    # Time Complexity: O(n)
    # Memory Complexity: O(n)
    stack = []
    map = { ')' => '(', '}' => '{', ']' => '[' }
    s.each_char do |char|
        if map.key?(char)
            return false if stack.pop != map[char]
        else
            stack << char
        end
    end
    stack.empty?
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param String $s
     * @return Boolean
     */
    function isValid($s) {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        $stack = [];
        $map = [')' => '(', '}' => '{', ']' => '['];
        for ($i = 0; $i < strlen($s); $i++) {
            $char = $s[$i];
            if (isset($map[$char])) {
                if (array_pop($stack) !== $map[$char]) return false;
            } else {
                array_push($stack, $char);
            }
        }
        return empty($stack);
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  bool isValid(String s) {
    // Time Complexity: O(n)
    // Memory Complexity: O(n)
    List<String> stack = [];
    Map<String, String> map = {')': '(', '}': '{', ']': '['};
    for (int i = 0; i < s.length; i++) {
      String char = s[i];
      if (map.containsKey(char)) {
        if (stack.isEmpty || stack.removeLast() != map[char]) return false;
      } else {
        stack.add(char);
      }
    }
    return stack.isEmpty;
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
import scala.util.boundary
import scala.util.boundary.break

object Solution {
    def isValid(s: String): Boolean = {
        // Time Complexity: O(n)
        // Space Complexity: O(n)
        boundary {
            val stack = scala.collection.mutable.Stack[Char]()
            for (c <- s) {
                c match {
                    case '(' | '{' | '[' => stack.push(c)
                    case ')' => if (stack.isEmpty || stack.pop() != '(') break(false)
                    case '}' => if (stack.isEmpty || stack.pop() != '{') break(false)
                    case ']' => if (stack.isEmpty || stack.pop() != '[') break(false)
                    case _ =>
                }
            }
            stack.isEmpty
        }
    }
}
```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec is_valid(s :: String.t) :: boolean
  def is_valid(s) do
    # Time Complexity: O(n)
    # Memory Complexity: O(n)
    check(String.graphemes(s), [])
  end

  defp check([], []), do: true
  defp check([], _), do: false
  defp check([h | t], stack) when h in ["(", "{", "["] do
    check(t, [h | stack])
  end
  defp check([")" | t], ["(" | rest]), do: check(t, rest)
  defp check(["}" | t], ["{" | rest]), do: check(t, rest)
  defp check(["]" | t], ["[" | rest]), do: check(t, rest)
  defp check(_, _), do: false
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec is_valid(S :: unicode:unicode_binary()) -> boolean().
is_valid(S) ->
  % Time Complexity: O(n)
  % Memory Complexity: O(n)
  is_valid_helper(binary_to_list(S), []).

is_valid_helper([], []) -> true;
is_valid_helper([], _) -> false;
is_valid_helper([C | T], Stack) when C =:= $(; C =:= ${; C =:= $[ ->
  is_valid_helper(T, [C | Stack]);
is_valid_helper([$) | T], [$( | Rest]) -> is_valid_helper(T, Rest);
is_valid_helper([$} | T], [${ | Rest]) -> is_valid_helper(T, Rest);
is_valid_helper([$] | T], [$[ | Rest]) -> is_valid_helper(T, Rest);
is_valid_helper(_, _) -> false.

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (is-valid s)
  (-> string? boolean?)
  ; Time Complexity: O(n)
  ; Memory Complexity: O(n)
  (let loop ([chars (string->list s)]
             [stack '()])
    (cond
      [(empty? chars) (empty? stack)]
      [(member (first chars) '(#\( #\{ #\[))
       (loop (rest chars) (cons (first chars) stack))]
      [(empty? stack) #f]
      [else
       (let ([top (car stack)] 
             [curr (car chars)])
         (if (or (and (char=? curr #\)) (char=? top #\())
                 (and (char=? curr #\}) (char=? top #\{))
                 (and (char=? curr #\]) (char=? top #\[)))
             (loop (cdr chars) (cdr stack))
             #f))])))
```