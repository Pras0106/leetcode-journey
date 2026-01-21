# cpp

## Sweet Spot

```cpp
class Solution {
public:
    void backtrack(vector<int>& nums, vector<bool>& used, vector<int>& path, vector<vector<int>>& result) {
        if (path.size() == nums.size()) {
            result.push_back(path);
            return;
        }
        for (int i = 0; i < nums.size(); ++i) {
            if (used[i] || (i > 0 && nums[i] == nums[i - 1] && !used[i - 1])) continue;
            used[i] = true;
            path.push_back(nums[i]);
            backtrack(nums, used, path, result);
            path.pop_back();
            used[i] = false;
        }
    }
    vector<vector<int>> permuteUnique(vector<int>& nums) {
        vector<vector<int>> result;
        vector<int> path;
        vector<bool> used(nums.size(), false);
        sort(nums.begin(), nums.end());
        backtrack(nums, used, path, result);
        return result;
    }
    /* Time: O(n * n!), Memory: O(n * n!) */
};

```

# java

## Sweet Spot

```java
class Solution {
    public List<List<Integer>> permuteUnique(int[] nums) {
        List<List<Integer>> result = new ArrayList<>();
        Arrays.sort(nums);
        backtrack(nums, new boolean[nums.length], new ArrayList<>(), result);
        return result;
    }
    private void backtrack(int[] nums, boolean[] used, List<Integer> path, List<List<Integer>> result) {
        if (path.size() == nums.length) {
            result.add(new ArrayList<>(path));
            return;
        }
        for (int i = 0; i < nums.length; i++) {
            if (used[i] || (i > 0 && nums[i] == nums[i - 1] && !used[i - 1])) continue;
            used[i] = true;
            path.add(nums[i]);
            backtrack(nums, used, path, result);
            path.remove(path.size() - 1);
            used[i] = false;
        }
    }
    /* Time: O(n * n!), Memory: O(n * n!) */
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def permuteUnique(self, nums: List[int]) -> List[List[int]]:
        res = []
        nums.sort()
        def backtrack(curr, remaining_counts):
            if len(curr) == len(nums):
                res.append(list(curr))
                return
            for val in remaining_counts:
                if remaining_counts[val] > 0:
                    curr.append(val)
                    remaining_counts[val] -= 1
                    backtrack(curr, remaining_counts)
                    remaining_counts[val] += 1
                    curr.pop()
        from collections import Counter
        backtrack([], Counter(nums))
        return res
    # Time: O(n * n!), Memory: O(n * n!)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def permuteUnique(self, nums):
        """
        :type nums: List[int]
        :rtype: List[List[int]]
        """
        res = []
        nums.sort()
        def backtrack(curr, used):
            if len(curr) == len(nums):
                res.append(list(curr))
                return
            for i in range(len(nums)):
                if used[i] or (i > 0 and nums[i] == nums[i-1] and not used[i-1]):
                    continue
                used[i] = True
                curr.append(nums[i])
                backtrack(curr, used)
                curr.pop()
                used[i] = False
        backtrack([], [False] * len(nums))
        return res
    # Time: O(n * n!), Memory: O(n * n!)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} nums
 * @return {number[][]}
 */
var permuteUnique = function(nums) {
    const res = [];
    nums.sort((a, b) => a - b);
    const backtrack = (path, used) => {
        if (path.length === nums.length) {
            res.push([...path]);
            return;
        }
        for (let i = 0; i < nums.length; i++) {
            if (used[i] || (i > 0 && nums[i] === nums[i - 1] && !used[i - 1])) continue;
            used[i] = true;
            path.push(nums[i]);
            backtrack(path, used);
            path.pop();
            used[i] = false;
        }
    };
    backtrack([], new Array(nums.length).fill(false));
    return res;
    /* Time: O(n * n!), Memory: O(n * n!) */
};

```

# Typescript

## Sweet Spot

```typescript
function permuteUnique(nums: number[]): number[][] {
    const res: number[][] = [];
    nums.sort((a, b) => a - b);
    const used = new Array(nums.length).fill(false);
    const backtrack = (path: number[]) => {
        if (path.length === nums.length) {
            res.push([...path]);
            return;
        }
        for (let i = 0; i < nums.length; i++) {
            if (used[i] || (i > 0 && nums[i] === nums[i - 1] && !used[i - 1])) continue;
            used[i] = true;
            path.push(nums[i]);
            backtrack(path);
            path.pop();
            used[i] = false;
        }
    };
    backtrack([]);
    return res;
    /* Time: O(n * n!), Memory: O(n * n!) */
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public IList<IList<int>> PermuteUnique(int[] nums) {
        var res = new List<IList<int>>();
        Array.Sort(nums);
        Backtrack(nums, new bool[nums.Length], new List<int>(), res);
        return res;
    }
    private void Backtrack(int[] nums, bool[] used, List<int> path, IList<IList<int>> res) {
        if (path.Count == nums.Length) {
            res.Add(new List<int>(path));
            return;
        }
        for (int i = 0; i < nums.Length; i++) {
            if (used[i] || (i > 0 && nums[i] == nums[i - 1] && !used[i - 1])) continue;
            used[i] = true;
            path.Add(nums[i]);
            Backtrack(nums, used, path, res);
            path.RemoveAt(path.Count - 1);
            used[i] = false;
        }
    }
    /* Time: O(n * n!), Memory: O(n * n!) */
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
int compare(const void* a, const void* b) { return (*(int*)a - *(int*)b); }
void solve(int* nums, int n, int* returnSize, int** res, int** colSizes, int* path, int* used, int depth) {
    if (depth == n) {
        res[*returnSize] = (int*)malloc(sizeof(int) * n);
        memcpy(res[*returnSize], path, sizeof(int) * n);
        (*colSizes)[*returnSize] = n;
        (*returnSize)++;
        return;
    }
    for (int i = 0; i < n; i++) {
        if (used[i] || (i > 0 && nums[i] == nums[i - 1] && !used[i - 1])) continue;
        used[i] = 1;
        path[depth] = nums[i];
        solve(nums, n, returnSize, res, colSizes, path, used, depth + 1);
        used[i] = 0;
    }
}
int** permuteUnique(int* nums, int numsSize, int* returnSize, int** returnColumnSizes) {
    qsort(nums, numsSize, sizeof(int), compare);
    int max = 1;
    for (int i = 1; i <= numsSize; i++) max *= i;
    int** res = (int**)malloc(sizeof(int*) * max);
    *returnColumnSizes = (int*)malloc(sizeof(int) * max);
    int* path = (int*)malloc(sizeof(int) * numsSize);
    int* used = (int*)calloc(numsSize, sizeof(int));
    *returnSize = 0;
    solve(nums, numsSize, returnSize, res, returnColumnSizes, path, used, 0);
    free(path); free(used);
    return res;
}
/* Time: O(n * n!), Memory: O(n * n!) */

```

# Go

## Sweet Spot

```go
func permuteUnique(nums []int) [][]int {
    sort.Ints(nums)
    res := [][]int{}
    used := make([]bool, len(nums))
    var backtrack func([]int)
    backtrack = func(path []int) {
        if len(path) == len(nums) {
            temp := make([]int, len(path))
            copy(temp, path)
            res = append(res, temp)
            return
        }
        for i := 0; i < len(nums); i++ {
            if used[i] || (i > 0 && nums[i] == nums[i-1] && !used[i-1]) {
                continue
            }
            used[i] = true
            backtrack(append(path, nums[i]))
            used[i] = false
        }
    }
    backtrack([]int{})
    return res
}
/* Time: O(n * n!), Memory: O(n * n!) */

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun permuteUnique(nums: IntArray): List<List<Int>> {
        val result = mutableListOf<List<Int>>()
        nums.sort()
        val used = BooleanArray(nums.size)
        fun backtrack(path: MutableList<Int>) {
            if (path.size == nums.size) {
                result.add(ArrayList(path))
                return
            }
            for (i in nums.indices) {
                if (used[i] || (i > 0 && nums[i] == nums[i - 1] && !used[i - 1])) continue
                used[i] = true
                path.add(nums[i])
                backtrack(path)
                path.removeAt(path.size - 1)
                used[i] = false
            }
        }
        backtrack(mutableListOf())
        return result
    }
    /* Time: O(n * n!), Memory: O(n * n!) */
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func permuteUnique(_ nums: [Int]) -> [[Int]] {
        var res = [[Int]]()
        let sortedNums = nums.sorted()
        var used = [Bool](repeating: false, count: nums.count)
        func backtrack(_ path: inout [Int]) {
            if path.count == nums.count {
                res.append(path)
                return
            }
            for i in 0..<sortedNums.count {
                if used[i] || (i > 0 && sortedNums[i] == sortedNums[i-1] && !used[i-1]) {
                    continue
                }
                used[i] = true
                path.append(sortedNums[i])
                backtrack(&path)
                path.removeLast()
                used[i] = false
            }
        }
        var path = [Int]()
        backtrack(&path)
        return res
    }
    /* Time: O(n * n!), Memory: O(n * n!) */
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn permute_unique(mut nums: Vec<i32>) -> Vec<Vec<i32>> {
        let mut res = Vec::new();
        nums.sort();
        let mut used = vec![false; nums.len()];
        let mut path = Vec::new();
        Self::backtrack(&nums, &mut used, &mut path, &mut res);
        res
    }
    fn backtrack(nums: &Vec<i32>, used: &mut Vec<bool>, path: &mut Vec<i32>, res: &mut Vec<Vec<i32>>) {
        if path.len() == nums.len() {
            res.push(path.clone());
            return;
        }
        for i in 0..nums.len() {
            if used[i] || (i > 0 && nums[i] == nums[i - 1] && !used[i - 1]) {
                continue;
            }
            used[i] = true;
            path.push(nums[i]);
            Self::backtrack(nums, used, path, res);
            path.pop();
            used[i] = false;
        }
    }
    /* Time: O(n * n!), Memory: O(n * n!) */
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} nums
# @return {Integer[][]}
def permute_unique(nums)
    res = []
    nums.sort!
    used = Array.new(nums.length, false)
    backtrack = ->(path) {
        if path.length == nums.length
            res << path.dup
            return
        end
        nums.each_with_index do |num, i|
            next if used[i] || (i > 0 && nums[i] == nums[i-1] && !used[i-1])
            used[i] = true
            path << num
            backtrack.call(path)
            path.pop
            used[i] = false
        end
    }
    backtrack.call([])
    res
end
# Time: O(n * n!), Memory: O(n * n!)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[] $nums
     * @return Integer[][]
     */
    function permuteUnique($nums) {
        $res = [];
        sort($nums);
        $used = array_fill(0, count($nums), false);
        $this->backtrack($nums, $used, [], $res);
        return $res;
    }
    function backtrack($nums, &$used, $path, &$res) {
        if (count($path) == count($nums)) {
            $res[] = $path;
            return;
        }
        for ($i = 0; $i < count($nums); $i++) {
            if ($used[$i] || ($i > 0 && $nums[$i] == $nums[$i-1] && !$used[$i-1])) continue;
            $used[$i] = true;
            $path[] = $nums[$i];
            $this->backtrack($nums, $used, $path, $res);
            array_pop($path);
            $used[$i] = false;
        }
    }
    /* Time: O(n * n!), Memory: O(n * n!) */
}

```

# dart

## Sweet Spot

```dart
class Solution {
  List<List<int>> permuteUnique(List<int> nums) {
    List<List<int>> res = [];
    nums.sort();
    List<bool> used = List.filled(nums.length, false);
    void backtrack(List<int> path) {
      if (path.length == nums.length) {
        res.add(List.from(path));
        return;
      }
      for (int i = 0; i < nums.length; i++) {
        if (used[i] || (i > 0 && nums[i] == nums[i - 1] && !used[i - 1])) continue;
        used[i] = true;
        path.add(nums[i]);
        backtrack(path);
        path.removeLast();
        used[i] = false;
      }
    }
    backtrack([]);
    return res;
  }
  /* Time: O(n * n!), Memory: O(n * n!) */
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def permuteUnique(nums: Array[Int]): List[List[Int]] = {
        val sorted = nums.sorted
        val res = scala.collection.mutable.ListBuffer[List[Int]]()
        val used = Array.fill(nums.length)(false)

        def backtrack(path: List[Int]): Unit = {
            if (path.length == nums.length) {
                res += path
                return
            }
            for (i <- sorted.indices) {
                if (used(i) || (i > 0 && sorted(i) == sorted(i - 1) && !used(i - 1))) {
                    // Skip
                } else {
                    used(i) = true
                    backtrack(sorted(i) :: path)
                    used(i) = false
                }
            }
        }

        backtrack(Nil)
        res.toList
    }
    /* Time complexity: O(n * n!), Memory complexity: O(n * n!) */
}
```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec permute_unique(nums :: [integer]) :: [[integer]]
  def permute_unique(nums) do
    nums
    |> Enum.frequencies()
    |> backtrack(length(nums), [])
  end

  defp backtrack(counts, 0, path), do: [Enum.reverse(path)]
  defp backtrack(counts, remaining, path) do
    counts
    |> Enum.flat_map(fn {val, count} ->
      if count > 0 do
        new_counts = Map.put(counts, val, count - 1)
        backtrack(new_counts, remaining - 1, [val | path])
      else
        []
      end
    end)
  end

  # Time Complexity: O(Σ_{k=1}^{n} P(n, k)) which is bounded by O(n * n!)
  # Memory Complexity: O(n * n!)
end
```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec permute_unique(Nums :: [integer()]) -> [[integer()]].
permute_unique(Nums) ->
    Counts = maps:to_list(lists:foldl(fun(X, Acc) -> 
        Acc#{X => maps:get(X, Acc, 0) + 1} 
    end, #{}, Nums)),
    backtrack(Counts, length(Nums), []).

backtrack(_, 0, Path) -> [Path];
backtrack(Counts, Remaining, Path) ->
    lists:flatmap(fun({Val, Count}) ->
        case Count > 0 of
            true ->
                NewCounts = lists:keyreplace(Val, 1, Counts, {Val, Count - 1}),
                backtrack(NewCounts, Remaining - 1, [Val | Path]);
            false -> []
        end
    end, Counts).

% Time Complexity: O(∑_{k=1}^{n} P(n, k))
% Space Complexity: O(n * n!)
```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (permute-unique nums)
  (-> (listof exact-integer?) (listof (listof exact-integer?)))
  (let* ([sorted (sort nums <)]
         [counts (foldl (lambda (x acc) (dict-set acc x (+ 1 (dict-ref acc x 0)))) '() sorted)])
    (let backtrack ([curr-counts counts] [remaining (length nums)])
      (if (zero? remaining)
          '(())
          (append-map (lambda (entry)
                        (let ([val (car entry)] [count (cdr entry)])
                          (if (> count 0)
                              (map (lambda (p) (cons val p))
                                   (backtrack (dict-set curr-counts val (- count 1)) (- remaining 1)))
                              '())))
                      curr-counts)))))
; Time: O(n * n!), Memory: O(n * n!)

```