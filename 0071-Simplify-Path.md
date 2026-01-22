# cpp

## Sweet Spot

```cpp
class Solution {
public:
    string simplifyPath(string path) {
        vector<string> stack;
        string res, temp;
        stringstream ss(path);
        while (getline(ss, temp, '/')) {
            if (temp == "" || temp == ".") continue;
            if (temp == "..") {
                if (!stack.empty()) stack.pop_back();
            } else {
                stack.push_back(temp);
            }
        }
        for (auto str : stack) res += "/" + str;
        return res.empty() ? "/" : res;
    }
};
// Time O(n), Memory O(n)

```

# java

## Sweet Spot

```java
class Solution {
    public String simplifyPath(String path) {
        Deque<String> stack = new LinkedList<>();
        for (String dir : path.split("/")) {
            if (dir.equals("..")) {
                if (!stack.isEmpty()) stack.pop();
            } else if (!dir.equals("") && !dir.equals(".")) {
                stack.push(dir);
            }
        }
        StringBuilder res = new StringBuilder();
        while (!stack.isEmpty()) {
            res.append("/").append(stack.pollLast());
        }
        return res.length() == 0 ? "/" : res.toString();
    }
}
// Time O(n), Memory O(n)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def simplifyPath(self, path: str) -> str:
        stack = []
        for part in path.split("/"):
            if part == "..":
                if stack:
                    stack.pop()
            elif part and part != ".":
                stack.append(part)
        return "/" + "/".join(stack)
# Time O(n), Memory O(n)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def simplifyPath(self, path):
        """
        :type path: str
        :rtype: str
        """
        stack = []
        for part in path.split("/"):
            if part == "..":
                if stack:
                    stack.pop()
            elif part and part != ".":
                stack.append(part)
        return "/" + "/".join(stack)
# Time O(n), Memory O(n)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {string} path
 * @return {string}
 */
var simplifyPath = function(path) {
    const stack = [];
    const parts = path.split("/");
    for (const part of parts) {
        if (part === "..") {
            if (stack.length > 0) stack.pop();
        } else if (part !== "" && part !== ".") {
            stack.push(part);
        }
    }
    return "/" + stack.join("/");
};
// Time O(n), Memory O(n)

```

# Typescript

## Sweet Spot

```typescript
function simplifyPath(path: string): string {
    const stack: string[] = [];
    const parts: string[] = path.split("/");
    for (const part of parts) {
        if (part === "..") {
            if (stack.length > 0) stack.pop();
        } else if (part !== "" && part !== ".") {
            stack.push(part);
        }
    }
    return "/" + stack.join("/");
};
// Time O(n), Memory O(n)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public string SimplifyPath(string path) {
        string[] parts = path.Split('/');
        Stack<string> stack = new Stack<string>();
        foreach (string part in parts) {
            if (part == "..") {
                if (stack.Count > 0) stack.Pop();
            } else if (part != "" && part != ".") {
                stack.Push(part);
            }
        }
        string[] res = stack.ToArray();
        Array.Reverse(res);
        return "/" + string.Join("/", res);
    }
}
// Time O(n), Memory O(n)

```

# C

## Sweet Spot

```c
char* simplifyPath(char* path) {
    int n = strlen(path);
    char** stack = (char**)malloc(n * sizeof(char*));
    int top = 0;
    char* token = strtok(path, "/");
    while (token != NULL) {
        if (strcmp(token, "..") == 0) {
            if (top > 0) top--;
        } else if (strcmp(token, ".") != 0) {
            stack[top++] = token;
        }
        token = strtok(NULL, "/");
    }
    char* res = (char*)malloc(n + 1);
    res[0] = '\0';
    if (top == 0) return strcpy(res, "/");
    for (int i = 0; i < top; i++) {
        strcat(res, "/");
        strcat(res, stack[i]);
    }
    free(stack);
    return res;
}
// Time O(n), Memory O(n)

```

# Go

## Sweet Spot

```go
func simplifyPath(path string) string {
    parts := strings.Split(path, "/")
    stack := []string{}
    for _, part := range parts {
        if part == ".." {
            if len(stack) > 0 {
                stack = stack[:len(stack)-1]
            }
        } else if part != "" && part != "." {
            stack = append(stack, part)
        }
    }
    return "/" + strings.Join(stack, "/")
}
// Time O(n), Memory O(n)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun simplifyPath(path: String): String {
        val stack = java.util.Stack<String>()
        val parts = path.split("/")
        for (part in parts) {
            if (part == "..") {
                if (!stack.isEmpty()) stack.pop()
            } else if (part.isNotEmpty() && part != ".") {
                stack.push(part)
            }
        }
        return "/" + stack.joinToString("/")
    }
}
// Time O(n), Memory O(n)

```

# swift

## Sweet Spot

```swift
class Solution {
    func simplifyPath(_ path: String) -> String {
        let parts = path.split(separator: "/")
        var stack = [String]()
        for part in parts {
            if part == ".." {
                if !stack.isEmpty { stack.removeLast() }
            } else if part != "." && !part.isEmpty {
                stack.append(String(part))
            }
        }
        return "/" + stack.joined(separator: "/")
    }
}
// Time O(n), Memory O(n)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn simplify_path(path: String) -> String {
        let mut stack = Vec::new();
        for part in path.split('/') {
            match part {
                "" | "." => continue,
                ".." => { stack.pop(); },
                _ => stack.push(part),
            }
        }
        format!("/{}", stack.join("/"))
    }
}
// Time O(n), Memory O(n)

```

# ruby

## Sweet Spot

```ruby
# @param {String} path
# @return {String}
def simplify_path(path)
    stack = []
    path.split('/').each do |part|
        if part == '..'
            stack.pop
        elsif !part.empty? && part != '.'
            stack.push(part)
        end
    end
    '/' + stack.join('/')
end
# Time O(n), Memory O(n)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param String $path
     * @return String
     */
    function simplifyPath($path) {
        $parts = explode('/', $path);
        $stack = [];
        foreach ($parts as $part) {
            if ($part === '..') {
                array_pop($stack);
            } elseif ($part !== '' && $part !== '.') {
                array_push($stack, $part);
            }
        }
        return '/' . implode('/', $stack);
    }
}
// Time O(n), Memory O(n)

```

# dart

## Sweet Spot

```dart
class Solution {
  String simplifyPath(String path) {
    List<String> stack = [];
    List<String> parts = path.split('/');
    for (var part in parts) {
      if (part == '..') {
        if (stack.isNotEmpty) stack.removeLast();
      } else if (part.isNotEmpty && part != '.') {
        stack.add(part);
      }
    }
    return '/' + stack.join('/');
  }
}
// Time O(n), Memory O(n)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def simplifyPath(path: String): String = {
        val stack = scala.collection.mutable.Stack[String]()
        path.split("/").foreach {
            case ".." => if (stack.nonEmpty) stack.pop()
            case "" | "." => 
            case s => stack.push(s)
        }
        "/" + stack.reverse.mkString("/")
    }
}
// Time O(n), Memory O(n)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec simplify_path(path :: String.t) :: String.t
  def simplify_path(path) do
    path
    |> String.split("/", trim: true)
    |> Enum.reduce([], fn
      "..", [_ | tail] -> tail
      "..", [] -> []
      ".", acc -> acc
      dir, acc -> [dir | acc]
    end)
    |> Enum.reverse()
    |> Enum.join("/")
    |> then(&("/" <> &1))
  end
end
# Time O(n), Memory O(n)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec simplify_path(Path :: unicode:unicode_binary()) -> unicode:unicode_binary().
simplify_path(Path) ->
    Parts = binary:split(Path, <<"/">>, [global, trim_all]),
    Stack = lists:foldl(fun
        (<<"..">>, [_ | T]) -> T;
        (<<"..">>, []) -> [];
        (<<".">>, Acc) -> Acc;
        (Dir, Acc) -> [Dir | Acc]
    end, [], Parts),
    Res = lists:join(<<"/">>, lists:reverse(Stack)),
    unicode:characters_to_binary([<<"/">>, Res]).
% Time O(n), Memory O(n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (simplify-path path)
  (-> string? string?)
  (let* ([parts (string-split path "/")]
         [stack (foldl (lambda (part acc)
                         (cond
                           [(string=? part "..") (if (null? acc) '() (cdr acc))]
                           [(or (string=? part ".") (string=? part "")) acc]
                           [else (cons part acc)]))
                       '()
                       parts)])
    (string-append "/" (string-join (reverse stack) "/"))))
; Time O(n), Memory O(n)

```