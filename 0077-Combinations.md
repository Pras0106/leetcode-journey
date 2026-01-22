# cpp

## Sweet Spot

```cpp
class Solution {
public:
    vector<vector<int>> combine(int n, int k) {
        vector<vector<int>> result;
        vector<int> current;
        backtrack(1, n, k, current, result);
        return result;
    }
private:
    void backtrack(int start, int n, int k, vector<int>& current, vector<vector<int>>& result) {
        if (current.size() == k) {
            result.push_back(current);
            return;
        }
        for (int i = start; i <= n; ++i) {
            current.push_back(i);
            backtrack(i + 1, n, k, current, result);
            current.pop_back();
        }
    }
};
// Time Complexity: O(k * C(n, k))
// Memory Complexity: O(k)

```

# java

## Sweet Spot

```java
class Solution {
    public List<List<Integer>> combine(int n, int k) {
        List<List<Integer>> result = new ArrayList<>();
        backtrack(1, n, k, new ArrayList<>(), result);
        return result;
    }

    private void backtrack(int start, int n, int k, List<Integer> current, List<List<Integer>> result) {
        if (current.size() == k) {
            result.add(new ArrayList<>(current));
            return;
        }
        for (int i = start; i <= n; i++) {
            current.add(i);
            backtrack(i + 1, n, k, current, result);
            current.remove(current.size() - 1);
        }
    }
}
// Time Complexity: O(k * C(n, k))
// Memory Complexity: O(k)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def combine(self, n: int, k: int) -> List[List[int]]:
        result = []
        def backtrack(start, path):
            if len(path) == k:
                result.append(path[:])
                return
            for i in range(start, n + 1):
                path.append(i)
                backtrack(i + 1, path)
                path.pop()
        backtrack(1, [])
        return result
# Time Complexity: O(k * C(n, k))
# Memory Complexity: O(k)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def combine(self, n, k):
        """
        :type n: int
        :type k: int
        :rtype: List[List[int]]
        """
        result = []
        def backtrack(start, path):
            if len(path) == k:
                result.append(path[:])
                return
            for i in range(start, n + 1):
                path.append(i)
                backtrack(i + 1, path)
                path.pop()
        backtrack(1, [])
        return result
# Time Complexity: O(k * C(n, k))
# Memory Complexity: O(k)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number} n
 * @param {number} k
 * @return {number[][]}
 */
var combine = function(n, k) {
    const result = [];
    const backtrack = (start, path) => {
        if (path.length === k) {
            result.push([...path]);
            return;
        }
        for (let i = start; i <= n; i++) {
            path.push(i);
            backtrack(i + 1, path);
            path.pop();
        }
    };
    backtrack(1, []);
    return result;
};
// Time Complexity: O(k * C(n, k))
// Memory Complexity: O(k)

```

# Typescript

## Sweet Spot

```typescript
function combine(n: number, k: number): number[][] {
    const result: number[][] = [];
    const backtrack = (start: number, path: number[]) => {
        if (path.length === k) {
            result.push([...path]);
            return;
        }
        for (let i = start; i <= n; i++) {
            path.push(i);
            backtrack(i + 1, path);
            path.pop();
        }
    };
    backtrack(1, []);
    return result;
};
// Time Complexity: O(k * C(n, k))
// Memory Complexity: O(k)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public IList<IList<int>> Combine(int n, int k) {
        var result = new List<IList<int>>();
        Backtrack(1, n, k, new List<int>(), result);
        return result;
    }

    private void Backtrack(int start, int n, int k, List<int> path, IList<IList<int>> result) {
        if (path.Count == k) {
            result.Add(new List<int>(path));
            return;
        }
        for (int i = start; i <= n; i++) {
            path.Add(i);
            Backtrack(i + 1, n, k, path, result);
            path.RemoveAt(path.Count - 1);
        }
    }
}
// Time Complexity: O(k * C(n, k))
// Memory Complexity: O(k)

```

# C

## Sweet Spot

```c
/**
 * Return an array of arrays of size *returnSize.
 * The sizes of the arrays are returned as *returnColumnSizes array.
 * Note: Both returned array and *columnSizes array must be malloced, assume caller calls free().
 */
void backtrack(int start, int n, int k, int* path, int pathSize, int*** res, int* resSize, int** colSizes) {
    if (pathSize == k) {
        (*res)[*resSize] = (int*)malloc(k * sizeof(int));
        for (int i = 0; i < k; i++) (*res)[*resSize][i] = path[i];
        (*colSizes)[*resSize] = k;
        (*resSize)++;
        return;
    }
    for (int i = start; i <= n; i++) {
        path[pathSize] = i;
        backtrack(i + 1, n, k, path, pathSize + 1, res, resSize, colSizes);
    }
}

int** combine(int n, int k, int* returnSize, int** returnColumnSizes) {
    int maxResults = 1;
    for (int i = 0; i < k; i++) maxResults = maxResults * (n - i) / (i + 1);
    int** res = (int**)malloc(maxResults * sizeof(int*));
    *returnColumnSizes = (int*)malloc(maxResults * sizeof(int));
    *returnSize = 0;
    int* path = (int*)malloc(k * sizeof(int));
    backtrack(1, n, k, path, 0, &res, returnSize, returnColumnSizes);
    free(path);
    return res;
}
// Time Complexity: O(k * C(n, k))
// Memory Complexity: O(k)

```

# Go

## Sweet Spot

```go
func combine(n int, k int) [][]int {
    var result [][]int
    var backtrack func(start int, path []int)
    backtrack = func(start int, path []int) {
        if len(path) == k {
            temp := make([]int, k)
            copy(temp, path)
            result = append(result, temp)
            return
        }
        for i := start; i <= n; i++ {
            path = append(path, i)
            backtrack(i + 1, path)
            path = path[:len(path)-1]
        }
    }
    backtrack(1, []int{})
    return result
}
// Time Complexity: O(k * C(n, k))
// Memory Complexity: O(k)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun combine(n: Int, k: Int): List<List<Int>> {
        val result = mutableListOf<List<Int>>()
        fun backtrack(start: Int, path: MutableList<Int>) {
            if (path.size == k) {
                result.add(ArrayList(path))
                return
            }
            for (i in start..n) {
                path.add(i)
                backtrack(i + 1, path)
                path.removeAt(path.size - 1)
            }
        }
        backtrack(1, mutableListOf<Int>())
        return result
    }
}
// Time Complexity: O(k * C(n, k))
// Memory Complexity: O(k)

```

# swift

## Sweet Spot

```swift
class Solution {
    func combine(_ n: Int, _ k: Int) -> [[Int]] {
        var result = [[Int]]()
        var path = [Int]()
        
        func backtrack(_ start: Int) {
            if path.count == k {
                result.append(path)
                return
            }
            if start > n { return }
            for i in start...n {
                path.append(i)
                backtrack(i + 1)
                path.removeLast()
            }
        }
        
        backtrack(1)
        return result
    }
}
// Time Complexity: O(k * C(n, k))
// Memory Complexity: O(k)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn combine(n: i32, k: i32) -> Vec<Vec<i32>> {
        let mut result = Vec::new();
        let mut path = Vec::new();
        Self::backtrack(1, n, k, &mut path, &mut result);
        result
    }

    fn backtrack(start: i32, n: i32, k: i32, path: &mut Vec<i32>, result: &mut Vec<Vec<i32>>) {
        if path.len() == k as usize {
            result.push(path.clone());
            return;
        }
        for i in start..=n {
            path.push(i);
            Self::backtrack(i + 1, n, k, path, result);
            path.pop();
        }
    }
}
// Time Complexity: O(k * C(n, k))
// Memory Complexity: O(k)

```

# ruby

## Sweet Spot

```ruby
# @param {Integer} n
# @param {Integer} k
# @return {Integer[][]}
def combine(n, k)
    result = []
    backtrack = lambda do |start, path|
        if path.length == k
            result << path.dup
            return
        end
        (start..n).each do |i|
            path << i
            backtrack.call(i + 1, path)
            path.pop
        end
    end
    backtrack.call(1, [])
    result
end
# Time Complexity: O(k * C(n, k))
# Memory Complexity: O(k)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer $n
     * @param Integer $k
     * @return Integer[][]
     */
    function combine($n, $k) {
        $result = [];
        $this->backtrack(1, $n, $k, [], $result);
        return $result;
    }

    function backtrack($start, $n, $k, $path, &$result) {
        if (count($path) == $k) {
            $result[] = $path;
            return;
        }
        for ($i = $start; $i <= $n; $i++) {
            $path[] = $i;
            $this->backtrack($i + 1, $n, $k, $path, $result);
            array_pop($path);
        }
    }
}
// Time Complexity: O(k * C(n, k))
// Memory Complexity: O(k)

```

# dart

## Sweet Spot

```dart
class Solution {
  List<List<int>> combine(int n, int k) {
    List<List<int>> result = [];
    void backtrack(int start, List<int> path) {
      if (path.length == k) {
        result.add(List.from(path));
        return;
      }
      for (int i = start; i <= n; i++) {
        path.add(i);
        backtrack(i + 1, path);
        path.removeLast();
      }
    }
    backtrack(1, []);
    return result;
  }
}
// Time Complexity: O(k * C(n, k))
// Memory Complexity: O(k)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def combine(n: Int, k: Int): List[List[Int]] = {
        val result = scala.collection.mutable.ListBuffer[List[Int]]()
        def backtrack(start: Int, path: List[Int]): Unit = {
            if (path.length == k) {
                result += path.reverse
                return
            }
            for (i <- start to n) {
                backtrack(i + 1, i :: path)
            }
        }
        backtrack(1, Nil)
        result.toList
    }
}
// Time Complexity: O(k * C(n, k))
// Memory Complexity: O(k)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec combine(n :: integer, k :: integer) :: [[integer]]
  def combine(n, k) do
    backtrack(1, n, k, [])
  end

  defp backtrack(_start, _n, 0, path), do: [Enum.reverse(path)]
  defp backtrack(start, n, k, path) when start > n, do: []
  defp backtrack(start, n, k, path) do
    include = backtrack(start + 1, n, k - 1, [start | path])
    exclude = backtrack(start + 1, n, k, path)
    include ++ exclude
  end
end
# Time Complexity: O(k * C(n, k))
# Memory Complexity: O(k)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec combine(N :: integer(), K :: integer()) -> [[integer()]].
combine(N, K) ->
  backtrack(1, N, K, []).

backtrack(_Start, _N, 0, Path) -> [lists:reverse(Path)];
backtrack(Start, N, _K, _Path) when Start > N -> [];
backtrack(Start, N, K, Path) ->
  Include = backtrack(Start + 1, N, K - 1, [Start | Path]),
  Exclude = backtrack(Start + 1, N, K, Path),
  Include ++ Exclude.
% Time Complexity: O(k * C(n, k))
% Memory Complexity: O(k)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (combine n k)
  (-> exact-integer? exact-integer? (listof (listof exact-integer?)))
  (let backtrack ([start 1] [k k] [path '()])
    (cond
      [(= k 0) (list (reverse path))]
      [(> start n) '()]
      [else
       (append
        (backtrack (+ start 1) (- k 1) (cons start path))
        (backtrack (+ start 1) k path))])))
; Time Complexity: O(k * C(n, k))
; Memory Complexity: O(k)

```