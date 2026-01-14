# cpp

## Sweet Spot

```cpp
class Solution {
public:
    // Time Complexity: O(N^(T/M + 1)) where N is the number of candidates, T is target, and M is the minimal value in candidates.
    // Memory Complexity: O(T/M) for recursion depth.
    vector<vector<int>> combinationSum(vector<int>& candidates, int target) {
        vector<vector<int>> results;
        vector<int> current;
        backtrack(candidates, target, 0, current, results);
        return results;
    }

private:
    void backtrack(vector<int>& candidates, int target, int start, vector<int>& current, vector<vector<int>>& results) {
        if (target == 0) {
            results.push_back(current);
            return;
        }
        for (int i = start; i < candidates.size(); ++i) {
            if (candidates[i] <= target) {
                current.push_back(candidates[i]);
                backtrack(candidates, target - candidates[i], i, current, results);
                current.pop_back();
            }
        }
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    // Time Complexity: O(N^(T/M + 1))
    // Memory Complexity: O(T/M)
    public List<List<Integer>> combinationSum(int[] candidates, int target) {
        List<List<Integer>> result = new ArrayList<>();
        backtrack(result, new ArrayList<>(), candidates, target, 0);
        return result;
    }

    private void backtrack(List<List<Integer>> list, List<Integer> tempList, int[] nums, int remain, int start) {
        if (remain < 0) return;
        else if (remain == 0) list.add(new ArrayList<>(tempList));
        else {
            for (int i = start; i < nums.length; i++) {
                tempList.add(nums[i]);
                backtrack(list, tempList, nums, remain - nums[i], i);
                tempList.remove(tempList.size() - 1);
            }
        }
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    # Time Complexity: O(N^(T/M + 1))
    # Memory Complexity: O(T/M)
    def combinationSum(self, candidates: List[int], target: int) -> List[List[int]]:
        results = []
        def backtrack(remain, combo, start):
            if remain == 0:
                results.append(list(combo))
                return
            for i in range(start, len(candidates)):
                if candidates[i] <= remain:
                    combo.append(candidates[i])
                    backtrack(remain - candidates[i], combo, i)
                    combo.pop()
        backtrack(target, [], 0)
        return results

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    # Time Complexity: O(N^(T/M + 1))
    # Memory Complexity: O(T/M)
    def combinationSum(self, candidates, target):
        """
        :type candidates: List[int]
        :type target: int
        :rtype: List[List[int]]
        """
        results = []
        def backtrack(remain, combo, start):
            if remain == 0:
                results.append(list(combo))
                return
            for i in range(start, len(candidates)):
                if candidates[i] <= remain:
                    combo.append(candidates[i])
                    backtrack(remain - candidates[i], combo, i)
                    combo.pop()
        backtrack(target, [], 0)
        return results

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} candidates
 * @param {number} target
 * @return {number[][]}
 */
var combinationSum = function(candidates, target) {
    // Time Complexity: O(N^(T/M + 1))
    // Memory Complexity: O(T/M)
    const result = [];
    const backtrack = (remain, start, path) => {
        if (remain === 0) {
            result.push([...path]);
            return;
        }
        for (let i = start; i < candidates.length; i++) {
            if (candidates[i] <= remain) {
                path.push(candidates[i]);
                backtrack(remain - candidates[i], i, path);
                path.pop();
            }
        }
    };
    backtrack(target, 0, []);
    return result;
};

```

# Typescript

## Sweet Spot

```typescript
function combinationSum(candidates: number[], target: number): number[][] {
    // Time Complexity: O(N^(T/M + 1))
    // Memory Complexity: O(T/M)
    const result: number[][] = [];
    const backtrack = (remain: number, start: number, path: number[]) => {
        if (remain === 0) {
            result.push([...path]);
            return;
        }
        for (let i = start; i < candidates.length; i++) {
            if (candidates[i] <= remain) {
                path.push(candidates[i]);
                backtrack(remain - candidates[i], i, path);
                path.pop();
            }
        }
    };
    backtrack(target, 0, []);
    return result;
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    // Time Complexity: O(N^(T/M + 1))
    // Memory Complexity: O(T/M)
    public IList<IList<int>> CombinationSum(int[] candidates, int target) {
        var result = new List<IList<int>>();
        Backtrack(candidates, target, 0, new List<int>(), result);
        return result;
    }

    private void Backtrack(int[] candidates, int remain, int start, List<int> path, IList<IList<int>> result) {
        if (remain == 0) {
            result.Add(new List<int>(path));
            return;
        }
        for (int i = start; i < candidates.Length; i++) {
            if (candidates[i] <= remain) {
                path.Add(candidates[i]);
                Backtrack(candidates, remain - candidates[i], i, path, result);
                path.RemoveAt(path.Count - 1);
            }
        }
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
// Time Complexity: O(N^(T/M + 1))
// Memory Complexity: O(T/M)
void backtrack(int* candidates, int candidatesSize, int target, int start, int* path, int pathSize, int*** res, int* resSize, int** colSizes) {
    if (target == 0) {
        (*resSize)++;
        *res = realloc(*res, sizeof(int*) * (*resSize));
        *colSizes = realloc(*colSizes, sizeof(int) * (*resSize));
        (*res)[*resSize - 1] = malloc(sizeof(int) * pathSize);
        memcpy((*res)[*resSize - 1], path, sizeof(int) * pathSize);
        (*colSizes)[*resSize - 1] = pathSize;
        return;
    }
    for (int i = start; i < candidatesSize; i++) {
        if (candidates[i] <= target) {
            path[pathSize] = candidates[i];
            backtrack(candidates, candidatesSize, target - candidates[i], i, path, pathSize + 1, res, resSize, colSizes);
        }
    }
}

int** combinationSum(int* candidates, int candidatesSize, int target, int* returnSize, int** returnColumnSizes) {
    int** res = malloc(0);
    *returnSize = 0;
    *returnColumnSizes = malloc(0);
    int* path = malloc(sizeof(int) * 40);
    backtrack(candidates, candidatesSize, target, 0, path, 0, &res, returnSize, returnColumnSizes);
    free(path);
    return res;
}

```

# Go

## Sweet Spot

```go
// Time Complexity: O(N^(T/M + 1))
// Memory Complexity: O(T/M)
func combinationSum(candidates []int, target int) [][]int {
    result := [][]int{}
    var backtrack func(remain int, start int, path []int)
    backtrack = func(remain int, start int, path []int) {
        if remain == 0 {
            temp := make([]int, len(path))
            copy(temp, path)
            result = append(result, temp)
            return
        }
        for i := start; i < len(candidates); i++ {
            if candidates[i] <= remain {
                backtrack(remain - candidates[i], i, append(path, candidates[i]))
            }
        }
    }
    backtrack(target, 0, []int{})
    return result
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    // Time Complexity: O(N^(T/M + 1))
    // Memory Complexity: O(T/M)
    fun combinationSum(candidates: IntArray, target: Int): List<List<Int>> {
        val result = mutableListOf<List<Int>>()
        fun backtrack(remain: Int, start: Int, path: MutableList<Int>) {
            if (remain == 0) {
                result.add(ArrayList(path))
                return
            }
            for (i in start until candidates.size) {
                if (candidates[i] <= remain) {
                    path.add(candidates[i])
                    backtrack(remain - candidates[i], i, path)
                    path.removeAt(path.size - 1)
                }
            }
        }
        backtrack(target, 0, mutableListOf())
        return result
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    // Time Complexity: O(N^(T/M + 1))
    // Memory Complexity: O(T/M)
    func combinationSum(_ candidates: [Int], _ target: Int) -> [[Int]] {
        var result = [[Int]]()
        var current = [Int]()
        
        func backtrack(_ remain: Int, _ start: Int) {
            if remain == 0 {
                result.append(current)
                return
            }
            for i in start..<candidates.count {
                if candidates[i] <= remain {
                    current.append(candidates[i])
                    backtrack(remain - candidates[i], i)
                    current.removeLast()
                }
            }
        }
        
        backtrack(target, 0)
        return result
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    // Time Complexity: O(N^(T/M + 1))
    // Memory Complexity: O(T/M)
    pub fn combination_sum(candidates: Vec<i32>, target: i32) -> Vec<Vec<i32>> {
        let mut result = Vec::new();
        let mut current = Vec::new();
        Self::backtrack(&candidates, target, 0, &mut current, &mut result);
        result
    }

    fn backtrack(candidates: &Vec<i32>, remain: i32, start: usize, current: &mut Vec<i32>, result: &mut Vec<Vec<i32>>) {
        if remain == 0 {
            result.push(current.clone());
            return;
        }
        for i in start..candidates.len() {
            if candidates[i] <= remain {
                current.push(candidates[i]);
                Self::backtrack(candidates, remain - candidates[i], i, current, result);
                current.pop();
            }
        }
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} candidates
# @param {Integer} target
# @return {Integer[][]}
# Time Complexity: O(N^(T/M + 1))
# Memory Complexity: O(T/M)
def combination_sum(candidates, target)
  result = []
  backtrack = lambda do |remain, start, path|
    if remain == 0
      result << Array.new(path)
      return
    end
    (start...candidates.length).each do |i|
      if candidates[i] <= remain
        path << candidates[i]
        backtrack.call(remain - candidates[i], i, path)
        path.pop
      end
    end
  end
  backtrack.call(target, 0, [])
  result
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[] $candidates
     * @param Integer $target
     * @return Integer[][]
     */
    // Time Complexity: O(N^(T/M + 1))
    // Memory Complexity: O(T/M)
    function combinationSum($candidates, $target) {
        $result = [];
        $this->backtrack($candidates, $target, 0, [], $result);
        return $result;
    }

    private function backtrack($candidates, $remain, $start, $path, &$result) {
        if ($remain === 0) {
            $result[] = $path;
            return;
        }
        for ($i = $start; $i < count($candidates); $i++) {
            if ($candidates[$i] <= $remain) {
                $path[] = $candidates[$i];
                $this->backtrack($candidates, $remain - $candidates[$i], $i, $path, $result);
                array_pop($path);
            }
        }
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  // Time Complexity: O(N^(T/M + 1))
  // Memory Complexity: O(T/M)
  List<List<int>> combinationSum(List<int> candidates, int target) {
    List<List<int>> result = [];
    void backtrack(int remain, int start, List<int> path) {
      if (remain == 0) {
        result.add(List.from(path));
        return;
      }
      for (int i = start; i < candidates.length; i++) {
        if (candidates[i] <= remain) {
          path.add(candidates[i]);
          backtrack(remain - candidates[i], i, path);
          path.removeLast();
        }
      }
    }
    backtrack(target, 0, []);
    return result;
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    // Time Complexity: O(N^(T/M + 1)) where N is number of candidates, T is target, and M is the minimum value in candidates.
    // Memory Complexity: O(T/M) for the recursion stack.
    def combinationSum(candidates: Array[Int], target: Int): List[List[Int]] = {
        var result = List[List[Int]]()
        val sortedCandidates = candidates.sorted

        def backtrack(remain: Int, start: Int, path: List[Int]): Unit = {
            if (remain == 0) {
                result = path :: result
                return
            }

            for (i <- start until sortedCandidates.length) {
                val current = sortedCandidates(i)
                if (current <= remain) {
                    backtrack(remain - current, i, current :: path)
                }
            }
        }

        backtrack(target, 0, Nil)
        result
    }
}
```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec combination_sum(candidates :: [integer], target :: integer) :: [[integer]]
  # Time Complexity: O(N^(T/M + 1))
  # Memory Complexity: O(T/M)
  def combination_sum(candidates, target) do
    backtrack(candidates, target, 0, [])
  end

  defp backtrack(_, 0, _, path), do: [Enum.reverse(path)]
  defp backtrack(candidates, remain, start, path) do
    candidates
    |> Enum.with_index()
    |> Enum.slice(start..-1//1)
    |> Enum.flat_map(fn {val, idx} ->
      if val <= remain do
        backtrack(candidates, remain - val, idx, [val | path])
      else
        []
      end
    end)
  end
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec combination_sum(Candidates :: [integer()], Target :: integer()) -> [[integer()]].
% Time Complexity: O(N^(T/M)) where N is the number of candidates, T is the target value, and M is the minimum candidate value.
% Space Complexity: O(T/M)
combination_sum(Candidates, Target) ->
    SortedCandidates = lists:sort(Candidates),
    backtrack(list_to_tuple(SortedCandidates), Target, 1, []).

backtrack(_, 0, _, Path) -> [lists:reverse(Path)];
backtrack(Candidates, Remain, Start, Path) ->
    Size = tuple_size(Candidates),
    lists:foldl(fun(I, Acc) ->
        Val = element(I, Candidates),
        if 
            Val =< Remain ->
                Acc ++ backtrack(Candidates, Remain - Val, I, [Val | Path]);
            true -> 
                Acc
        end
    end, [], lists:seq(Start, Size)).
```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (combination-sum candidates target)
  (-> (listof exact-integer?) exact-integer? (listof (listof exact-integer?)))
  ; Time Complexity: O(N^(T/M + 1))
  ; Memory Complexity: O(T/M)
  (let ([cand-vec (list->vector candidates)])
    (let backtrack ([remain target] [start 0] [path '()])
      (cond
        [(= remain 0) (list (reverse path))]
        [else
         (for/fold ([res '()])
                   ([i (in-range start (vector-length cand-vec))])
           (let ([val (vector-ref cand-vec i)])
             (if (<= val remain)
                 (append res (backtrack (- remain val) i (cons val path)))
                 res)))]))))

```