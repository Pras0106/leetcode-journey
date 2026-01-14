# cpp

## Sweet Spot

```cpp
class Solution {
public:
    void backtrack(vector<int>& candidates, int target, int start, vector<int>& current, vector<vector<int>>& result) {
        if (target == 0) {
            result.push_back(current);
            return;
        }
        for (int i = start; i < candidates.size(); ++i) {
            if (i > start && candidates[i] == candidates[i - 1]) continue;
            if (candidates[i] > target) break;
            current.push_back(candidates[i]);
            backtrack(candidates, target - candidates[i], i + 1, current, result);
            current.pop_back();
        }
    }

    vector<vector<int>> combinationSum2(vector<int>& candidates, int target) {
        sort(candidates.begin(), candidates.end());
        vector<vector<int>> result;
        vector<int> current;
        backtrack(candidates, target, 0, current, result);
        return result;
    }
    // Time Complexity: O(2^n)
    // Memory Complexity: O(n)
};

```

# java

## Sweet Spot

```java
class Solution {
    public List<List<Integer>> combinationSum2(int[] candidates, int target) {
        List<List<Integer>> result = new ArrayList<>();
        Arrays.sort(candidates);
        backtrack(result, new ArrayList<>(), candidates, target, 0);
        return result;
    }

    private void backtrack(List<List<Integer>> result, List<Integer> tempList, int[] candidates, int remain, int start) {
        if (remain == 0) {
            result.add(new ArrayList<>(tempList));
        } else if (remain > 0) {
            for (int i = start; i < candidates.length; i++) {
                if (i > start && candidates[i] == candidates[i - 1]) continue;
                if (candidates[i] > remain) break;
                tempList.add(candidates[i]);
                backtrack(result, tempList, candidates, remain - candidates[i], i + 1);
                tempList.remove(tempList.size() - 1);
            }
        }
    }
    // Time Complexity: O(2^n)
    // Memory Complexity: O(n)
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def combinationSum2(self, candidates: List[int], target: int) -> List[List[int]]:
        candidates.sort()
        res = []
        def backtrack(start, target, path):
            if target == 0:
                res.append(path)
                return
            for i in range(start, len(candidates)):
                if i > start and candidates[i] == candidates[i-1]:
                    continue
                if candidates[i] > target:
                    break
                backtrack(i + 1, target - candidates[i], path + [candidates[i]])
        backtrack(0, target, [])
        return res
    # Time Complexity: O(2^n)
    # Memory Complexity: O(n)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def combinationSum2(self, candidates, target):
        """
        :type candidates: List[int]
        :type target: int
        :rtype: List[List[int]]
        """
        candidates.sort()
        res = []
        def backtrack(start, remain, path):
            if remain == 0:
                res.append(list(path))
                return
            for i in range(start, len(candidates)):
                if i > start and candidates[i] == candidates[i-1]:
                    continue
                if candidates[i] > remain:
                    break
                path.append(candidates[i])
                backtrack(i + 1, remain - candidates[i], path)
                path.pop()
        backtrack(0, target, [])
        return res
    # Time Complexity: O(2^n)
    # Memory Complexity: O(n)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} candidates
 * @param {number} target
 * @return {number[][]}
 */
var combinationSum2 = function(candidates, target) {
    let res = [];
    candidates.sort((a, b) => a - b);
    
    function backtrack(start, remain, path) {
        if (remain === 0) {
            res.push([...path]);
            return;
        }
        for (let i = start; i < candidates.length; i++) {
            if (i > start && candidates[i] === candidates[i - 1]) continue;
            if (candidates[i] > remain) break;
            path.push(candidates[i]);
            backtrack(i + 1, remain - candidates[i], path);
            path.pop();
        }
    }
    
    backtrack(0, target, []);
    return res;
};
// Time Complexity: O(2^n)
// Memory Complexity: O(n)

```

# Typescript

## Sweet Spot

```typescript
function combinationSum2(candidates: number[], target: number): number[][] {
    const res: number[][] = [];
    candidates.sort((a, b) => a - b);
    
    function backtrack(start: number, remain: number, path: number[]): void {
        if (remain === 0) {
            res.push([...path]);
            return;
        }
        for (let i = start; i < candidates.length; i++) {
            if (i > start && candidates[i] === candidates[i - 1]) continue;
            if (candidates[i] > remain) break;
            path.push(candidates[i]);
            backtrack(i + 1, remain - candidates[i], path);
            path.pop();
        }
    }
    
    backtrack(0, target, []);
    return res;
};
// Time Complexity: O(2^n)
// Memory Complexity: O(n)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public IList<IList<int>> CombinationSum2(int[] candidates, int target) {
        Array.Sort(candidates);
        var result = new List<IList<int>>();
        Backtrack(candidates, target, 0, new List<int>(), result);
        return result;
    }

    private void Backtrack(int[] nums, int remain, int start, List<int> path, IList<IList<int>> result) {
        if (remain == 0) {
            result.Add(new List<int>(path));
            return;
        }
        for (int i = start; i < nums.Length; i++) {
            if (i > start && nums[i] == nums[i - 1]) continue;
            if (nums[i] > remain) break;
            path.Add(nums[i]);
            Backtrack(nums, remain - nums[i], i + 1, path, result);
            path.RemoveAt(path.Count - 1);
        }
    }
    // Time Complexity: O(2^n)
    // Memory Complexity: O(n)
}

```

# C

## Sweet Spot

```c
int compare(const void* a, const void* b) {
    return (*(int*)a - *(int*)b);
}

void backtrack(int* nums, int size, int remain, int start, int* path, int pathSize, int** res, int* returnSize, int** columnSizes) {
    if (remain == 0) {
        res[*returnSize] = (int*)malloc(pathSize * sizeof(int));
        memcpy(res[*returnSize], path, pathSize * sizeof(int));
        (*columnSizes)[*returnSize] = pathSize;
        (*returnSize)++;
        return;
    }
    for (int i = start; i < size; i++) {
        if (i > start && nums[i] == nums[i - 1]) continue;
        if (nums[i] > remain) break;
        path[pathSize] = nums[i];
        backtrack(nums, size, remain - nums[i], i + 1, path, pathSize + 1, res, returnSize, columnSizes);
    }
}

int** combinationSum2(int* candidates, int candidatesSize, int target, int* returnSize, int** returnColumnSizes) {
    qsort(candidates, candidatesSize, sizeof(int), compare);
    int** res = (int**)malloc(1000 * sizeof(int*));
    *returnColumnSizes = (int*)malloc(1000 * sizeof(int));
    int* path = (int*)malloc(candidatesSize * sizeof(int));
    *returnSize = 0;
    backtrack(candidates, candidatesSize, target, 0, path, 0, res, returnSize, returnColumnSizes);
    free(path);
    return res;
}
// Time Complexity: O(2^n)
// Memory Complexity: O(n)

```

# Go

## Sweet Spot

```go
func combinationSum2(candidates []int, target int) [][]int {
    sort.Ints(candidates)
    var res [][]int
    var backtrack func(start int, remain int, path []int)
    
    backtrack = func(start int, remain int, path []int) {
        if remain == 0 {
            temp := make([]int, len(path))
            copy(temp, path)
            res = append(res, temp)
            return
        }
        for i := start; i < len(candidates); i++ {
            if i > start && candidates[i] == candidates[i-1] {
                continue
            }
            if candidates[i] > remain {
                break
            }
            backtrack(i+1, remain-candidates[i], append(path, candidates[i]))
        }
    }
    
    backtrack(0, target, []int{})
    return res
}
// Time Complexity: O(2^n)
// Memory Complexity: O(n)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun combinationSum2(candidates: IntArray, target: Int): List<List<Int>> {
        val result = mutableListOf<List<Int>>()
        candidates.sort()
        
        fun backtrack(start: Int, remain: Int, path: MutableList<Int>) {
            if (remain == 0) {
                result.add(ArrayList(path))
                return
            }
            for (i in start until candidates.size) {
                if (i > start && candidates[i] == candidates[i - 1]) continue
                if (candidates[i] > remain) break
                path.add(candidates[i])
                backtrack(i + 1, remain - candidates[i], path)
                path.removeAt(path.size - 1)
            }
        }
        
        backtrack(0, target, mutableListOf())
        return result
    }
    // Time Complexity: O(2^n)
    // Memory Complexity: O(n)
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func combinationSum2(_ candidates: [Int], _ target: Int) -> [[Int]] {
        var res = [[Int]]()
        let sortedCandidates = candidates.sorted()
        
        func backtrack(_ start: Int, _ remain: Int, _ path: inout [Int]) {
            if remain == 0 {
                res.append(path)
                return
            }
            for i in start..<sortedCandidates.count {
                if i > start && sortedCandidates[i] == sortedCandidates[i-1] { continue }
                if sortedCandidates[i] > remain { break }
                path.append(sortedCandidates[i])
                backtrack(i + 1, remain - sortedCandidates[i], &path)
                path.removeLast()
            }
        }
        
        var currentPath = [Int]()
        backtrack(0, target, &currentPath)
        return res
    }
    // Time Complexity: O(2^n)
    // Memory Complexity: O(n)
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn combination_sum2(mut candidates: Vec<i32>, target: i32) -> Vec<Vec<i32>> {
        candidates.sort();
        let mut res = Vec::new();
        let mut path = Vec::new();
        Self::backtrack(&candidates, target, 0, &mut path, &mut res);
        res
    }

    fn backtrack(nums: &Vec<i32>, remain: i32, start: usize, path: &mut Vec<i32>, res: &mut Vec<Vec<i32>>) {
        if remain == 0 {
            res.push(path.clone());
            return;
        }
        for i in start..nums.len() {
            if i > start && nums[i] == nums[i - 1] { continue; }
            if nums[i] > remain { break; }
            path.push(nums[i]);
            Self::backtrack(nums, remain - nums[i], i + 1, path, res);
            path.pop();
        }
    }
    // Time Complexity: O(2^n)
    // Memory Complexity: O(n)
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} candidates
# @param {Integer} target
# @return {Integer[][]}
def combination_sum2(candidates, target)
    candidates.sort!
    res = []
    
    backtrack = lambda do |start, remain, path|
        if remain == 0
            res << path.dup
            return
        end
        (start...candidates.length).each do |i|
            next if i > start && candidates[i] == candidates[i-1]
            break if candidates[i] > remain
            path << candidates[i]
            backtrack.call(i + 1, remain - candidates[i], path)
            path.pop
        end
    end
    
    backtrack.call(0, target, [])
    res
end
# Time Complexity: O(2^n)
# Memory Complexity: O(n)

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
    function combinationSum2($candidates, $target) {
        sort($candidates);
        $res = [];
        $this->backtrack($candidates, $target, 0, [], $res);
        return $res;
    }

    function backtrack($nums, $remain, $start, $path, &$res) {
        if ($remain === 0) {
            $res[] = $path;
            return;
        }
        for ($i = $start; $i < count($nums); $i++) {
            if ($i > $start && $nums[$i] == $nums[$i-1]) continue;
            if ($nums[$i] > $remain) break;
            $path[] = $nums[$i];
            $this->backtrack($nums, $remain - $nums[$i], $i + 1, $path, $res);
            array_pop($path);
        }
    }
    // Time Complexity: O(2^n)
    // Memory Complexity: O(n)
}

```

# dart

## Sweet Spot

```dart
class Solution {
  List<List<int>> combinationSum2(List<int> candidates, int target) {
    candidates.sort();
    List<List<int>> res = [];
    
    void backtrack(int start, int remain, List<int> path) {
      if (remain == 0) {
        res.add(List.from(path));
        return;
      }
      for (int i = start; i < candidates.length; i++) {
        if (i > start && candidates[i] == candidates[i - 1]) continue;
        if (candidates[i] > remain) break;
        path.add(candidates[i]);
        backtrack(i + 1, remain - candidates[i], path);
        path.removeLast();
      }
    }
    
    backtrack(0, target, []);
    return res;
  }
  // Time Complexity: O(2^n)
  // Memory Complexity: O(n)
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def combinationSum2(candidates: Array[Int], target: Int): List[List[Int]] = {
        val sorted = candidates.sorted
        var result = List[List[Int]]()

        def backtrack(start: Int, remain: Int, path: List[Int]): Unit = {
            if (remain == 0) {
                result = path.reverse :: result
            } else {
                for (i <- start until sorted.length) {
                    if (!(i > start && sorted(i) == sorted(i - 1))) {
                        if (sorted(i) <= remain) {
                            backtrack(i + 1, remain - sorted(i), sorted(i) :: path)
                        }
                    }
                }
            }
        }
        backtrack(0, target, Nil)
        result
    }
    // Time Complexity: O(2^n)
    // Memory Complexity: O(n)
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec combination_sum2(candidates :: [integer], target :: integer) :: [[integer]]
  def combination_sum2(candidates, target) do
    candidates
    |> Enum.sort()
    |> backtrack(target, 0, [])
  end

  defp backtrack(candidates, target, start, path) do
    cond do
      target == 0 -> [Enum.reverse(path)]
      target < 0 -> []
      true ->
        candidates
        |> Enum.with_index()
        |> Enum.slice(start..-1//1)
        |> Enum.reduce({[], nil}, fn {val, idx}, {acc, prev} ->
          if val == prev or val > target do
            {acc, val}
          else
            {acc ++ backtrack(candidates, target - val, idx + 1, [val | path]), val}
          end
        end)
        |> elem(0)
    end
  end
  # Time Complexity: O(2^n)
  # Memory Complexity: O(n)
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec combination_sum2(Candidates :: [integer()], Target :: integer()) -> [[integer()]].
combination_sum2(Candidates, Target) ->
    Sorted = lists:sort(Candidates),
    backtrack(Sorted, Target, []).

backtrack(_, 0, Path) -> [lists:reverse(Path)];
backtrack([], _, _) -> [];
backtrack([H|T], Target, Path) when H > Target -> [];
backtrack([H|T], Target, Path) ->
    WithH = backtrack(T, Target - H, [H|Path]),
    NextT = skip_duplicates(H, T),
    WithoutH = backtrack(NextT, Target, Path),
    WithH ++ WithoutH.

skip_duplicates(Val, [Val|T]) -> skip_duplicates(Val, T);
skip_duplicates(_, T) -> T.
% Time Complexity: O(2^n)
% Memory Complexity: O(n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (combination-sum2 candidates target)
  (-> (listof exact-integer?) exact-integer? (listof (listof exact-integer?)))
  (let ([sorted (sort candidates <)])
    (define (solve remaining start path)
      (cond
        [(= remaining 0) (list (reverse path))]
        [(or (< remaining 0) (>= start (length sorted))) '()]
        [else
         (let loop ([i start] [acc '()])
           (if (>= i (length sorted))
               acc
               (let ([val (list-ref sorted i)])
                 (if (> val remaining)
                     acc
                     (let ([with (solve (- remaining val) (+ i 1) (cons val path))]
                           [next-i (let skip ([j (+ i 1)])
                                     (if (and (< j (length sorted)) (= (list-ref sorted j) val))
                                         (skip (+ j 1))
                                         j))])
                       (loop next-i (append acc with)))))))]))
    (solve target 0 '())))
; Time Complexity: O(2^n)
; Memory Complexity: O(n)

```