# cpp

## Sweet Spot

```cpp
class Solution {
public:
    void backtrack(vector<int>& nums, int start, vector<vector<int>>& result) {
        if (start == nums.size()) {
            result.push_back(nums);
            return;
        }
        for (int i = start; i < nums.size(); ++i) {
            swap(nums[start], nums[i]);
            backtrack(nums, start + 1, result);
            swap(nums[start], nums[i]);
        }
    }

    vector<vector<int>> permute(vector<int>& nums) {
        vector<vector<int>> result;
        backtrack(nums, 0, result);
        return result;
    }
};
// Time Complexity: O(n * n!)
// Memory Complexity: O(n)

```

# java

## Sweet Spot

```java
class Solution {
    public List<List<Integer>> permute(int[] nums) {
        List<List<Integer>> result = new ArrayList<>();
        backtrack(nums, 0, result);
        return result;
    }

    private void backtrack(int[] nums, int start, List<List<Integer>> result) {
        if (start == nums.length) {
            List<Integer> list = new ArrayList<>();
            for (int num : nums) list.add(num);
            result.add(list);
            return;
        }
        for (int i = start; i < nums.length; i++) {
            swap(nums, start, i);
            backtrack(nums, start + 1, result);
            swap(nums, start, i);
        }
    }

    private void swap(int[] nums, int i, int j) {
        int temp = nums[i];
        nums[i] = nums[j];
        nums[j] = temp;
    }
}
// Time Complexity: O(n * n!)
// Memory Complexity: O(n)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def permute(self, nums: List[int]) -> List[List[int]]:
        res = []
        def backtrack(start):
            if start == len(nums):
                res.append(nums[:])
                return
            for i in range(start, len(nums)):
                nums[start], nums[i] = nums[i], nums[start]
                backtrack(start + 1)
                nums[start], nums[i] = nums[i], nums[start]
        backtrack(0)
        return res
# Time Complexity: O(n * n!)
# Memory Complexity: O(n)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def permute(self, nums):
        """
        :type nums: List[int]
        :rtype: List[List[int]]
        """
        res = []
        def backtrack(start):
            if start == len(nums):
                res.append(list(nums))
                return
            for i in range(start, len(nums)):
                nums[start], nums[i] = nums[i], nums[start]
                backtrack(start + 1)
                nums[start], nums[i] = nums[i], nums[start]
        backtrack(0)
        return res
# Time Complexity: O(n * n!)
# Memory Complexity: O(n)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} nums
 * @return {number[][]}
 */
var permute = function(nums) {
    const res = [];
    const backtrack = (start) => {
        if (start === nums.length) {
            res.push([...nums]);
            return;
        }
        for (let i = start; i < nums.length; i++) {
            [nums[start], nums[i]] = [nums[i], nums[start]];
            backtrack(start + 1);
            [nums[start], nums[i]] = [nums[i], nums[start]];
        }
    };
    backtrack(0);
    return res;
};
// Time Complexity: O(n * n!)
// Memory Complexity: O(n)

```

# Typescript

## Sweet Spot

```typescript
function permute(nums: number[]): number[][] {
    const res: number[][] = [];
    const backtrack = (start: number): void => {
        if (start === nums.length) {
            res.push([...nums]);
            return;
        }
        for (let i = start; i < nums.length; i++) {
            [nums[start], nums[i]] = [nums[i], nums[start]];
            backtrack(start + 1);
            [nums[start], nums[i]] = [nums[i], nums[start]];
        }
    };
    backtrack(0);
    return res;
};
// Time Complexity: O(n * n!)
// Memory Complexity: O(n)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public IList<IList<int>> Permute(int[] nums) {
        var result = new List<IList<int>>();
        Backtrack(nums, 0, result);
        return result;
    }

    private void Backtrack(int[] nums, int start, IList<IList<int>> result) {
        if (start == nums.Length) {
            result.Add(new List<int>(nums));
            return;
        }
        for (int i = start; i < nums.Length; i++) {
            Swap(nums, start, i);
            Backtrack(nums, start + 1, result);
            Swap(nums, start, i);
        }
    }

    private void Swap(int[] nums, int i, int j) {
        int temp = nums[i];
        nums[i] = nums[j];
        nums[j] = temp;
    }
}
// Time Complexity: O(n * n!)
// Memory Complexity: O(n)

```

# C

## Sweet Spot

```c
/**
 * Return an array of arrays of size *returnSize.
 * The sizes of the arrays are returned as *returnColumnSizes array.
 * Note: Both returned array and *columnSizes array must be malloced, assume caller calls free().
 */
void backtrack(int* nums, int numsSize, int start, int*** res, int* returnSize, int** returnColumnSizes) {
    if (start == numsSize) {
        res[0][*returnSize] = (int*)malloc(numsSize * sizeof(int));
        for (int i = 0; i < numsSize; i++) res[0][*returnSize][i] = nums[i];
        (*returnColumnSizes)[*returnSize] = numsSize;
        (*returnSize)++;
        return;
    }
    for (int i = start; i < numsSize; i++) {
        int temp = nums[start]; nums[start] = nums[i]; nums[i] = temp;
        backtrack(nums, numsSize, start + 1, res, returnSize, returnColumnSizes);
        temp = nums[start]; nums[start] = nums[i]; nums[i] = temp;
    }
}

int** permute(int* nums, int numsSize, int* returnSize, int** returnColumnSizes) {
    int total = 1;
    for (int i = 1; i <= numsSize; i++) total *= i;
    int** res = (int**)malloc(total * sizeof(int*));
    *returnColumnSizes = (int*)malloc(total * sizeof(int));
    *returnSize = 0;
    backtrack(nums, numsSize, 0, &res, returnSize, returnColumnSizes);
    return res;
}
// Time Complexity: O(n * n!)
// Memory Complexity: O(n)

```

# Go

## Sweet Spot

```go
func permute(nums []int) [][]int {
    var res [][]int
    var backtrack func(int)
    backtrack = func(start int) {
        if start == len(nums) {
            temp := make([]int, len(nums))
            copy(temp, nums)
            res = append(res, temp)
            return
        }
        for i := start; i < len(nums); i++ {
            nums[start], nums[i] = nums[i], nums[start]
            backtrack(start + 1)
            nums[start], nums[i] = nums[i], nums[start]
        }
    }
    backtrack(0)
    return res
}
// Time Complexity: O(n * n!)
// Memory Complexity: O(n)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun permute(nums: IntArray): List<List<Int>> {
        val res = mutableListOf<List<Int>>()
        backtrack(nums, 0, res)
        return res
    }

    private fun backtrack(nums: IntArray, start: Int, res: MutableList<List<Int>>) {
        if (start == nums.size) {
            res.add(nums.toList())
            return
        }
        for (i in start until nums.size) {
            swap(nums, start, i)
            backtrack(nums, start + 1, res)
            swap(nums, start, i)
        }
    }

    private fun swap(nums: IntArray, i: Int, j: Int) {
        val temp = nums[i]
        nums[i] = nums[j]
        nums[j] = temp
    }
}
// Time Complexity: O(n * n!)
// Memory Complexity: O(n)

```

# swift

## Sweet Spot

```swift
class Solution {
    func permute(_ nums: [Int]) -> [[Int]] {
        var res = [[Int]]()
        var numsArr = nums
        
        func backtrack(_ start: Int) {
            if start == numsArr.count {
                res.append(numsArr)
                return
            }
            for i in start..<numsArr.count {
                numsArr.swapAt(start, i)
                backtrack(start + 1)
                numsArr.swapAt(start, i)
            }
        }
        
        backtrack(0)
        return res
    }
}
// Time Complexity: O(n * n!)
// Memory Complexity: O(n)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn permute(mut nums: Vec<i32>) -> Vec<Vec<i32>> {
        let mut res = Vec::new();
        Self::backtrack(0, &mut nums, &mut res);
        res
    }

    fn backtrack(start: usize, nums: &mut Vec<i32>, res: &mut Vec<Vec<i32>>) {
        if start == nums.len() {
            res.push(nums.clone());
            return;
        }
        for i in start..nums.len() {
            nums.swap(start, i);
            Self::backtrack(start + 1, nums, res);
            nums.swap(start, i);
        }
    }
}
// Time Complexity: O(n * n!)
// Memory Complexity: O(n)

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} nums
# @return {Integer[][]}
def permute(nums)
    res = []
    backtrack = lambda do |start|
        if start == nums.length
            res << nums.dup
            return
        end
        (start...nums.length).each do |i|
            nums[start], nums[i] = nums[i], nums[start]
            backtrack.call(start + 1)
            nums[start], nums[i] = nums[i], nums[start]
        end
    end
    backtrack.call(0)
    res
end
# Time Complexity: O(n * n!)
# Memory Complexity: O(n)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[] $nums
     * @return Integer[][]
     */
    function permute($nums) {
        $res = [];
        $this->backtrack($nums, 0, $res);
        return $res;
    }

    function backtrack(&$nums, $start, &$res) {
        if ($start == count($nums)) {
            $res[] = $nums;
            return;
        }
        for ($i = $start; $i < count($nums); $i++) {
            $temp = $nums[$start];
            $nums[$start] = $nums[$i];
            $nums[$i] = $temp;
            $this->backtrack($nums, $start + 1, $res);
            $temp = $nums[$start];
            $nums[$start] = $nums[$i];
            $nums[$i] = $temp;
        }
    }
}
// Time Complexity: O(n * n!)
// Memory Complexity: O(n)

```

# dart

## Sweet Spot

```dart
class Solution {
  List<List<int>> permute(List<int> nums) {
    List<List<int>> res = [];
    void backtrack(int start) {
      if (start == nums.length) {
        res.add(List.from(nums));
        return;
      }
      for (int i = start; i < nums.length; i++) {
        int temp = nums[start];
        nums[start] = nums[i];
        nums[i] = temp;
        backtrack(start + 1);
        temp = nums[start];
        nums[start] = nums[i];
        nums[i] = temp;
      }
    }
    backtrack(0);
    return res;
  }
}
// Time Complexity: O(n * n!)
// Memory Complexity: O(n)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def permute(nums: Array[Int]): List[List[Int]] = {
        var res = List[List[Int]]()
        def backtrack(start: Int, current: Array[Int]): Unit = {
            if (start == current.length) {
                res = current.toList :: res
            } else {
                for (i <- start until current.length) {
                    val temp = current(start)
                    current(start) = current(i)
                    current(i) = temp
                    backtrack(start + 1, current)
                    val temp2 = current(start)
                    current(start) = current(i)
                    current(i) = temp2
                }
            }
        }
        backtrack(0, nums.clone())
        res
    }
}
// Time Complexity: O(n * n!)
// Memory Complexity: O(n)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec permute(nums :: [integer]) :: [[integer]]
  def permute(nums) do
    generate(nums)
  end

  defp generate([]), do: [[]]
  defp generate(nums) do
    for h <- nums, t <- generate(nums -- [h]), do: [h | t]
  end
end
# Time Complexity: O(n * n!)
# Memory Complexity: O(n^2)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec permute(Nums :: [integer()]) -> [[integer()]].
permute([]) -> [[]];
permute(Nums) ->
    [[X | Y] || X <- Nums, Y <- permute(Nums -- [X])].
% Time Complexity: O(n * n!)
% Memory Complexity: O(n^2)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (permute nums)
  (-> (listof exact-integer?) (listof (listof exact-integer?)))
  (cond
    [(empty? nums) '(())]
    [else (apply append
                 (map (lambda (x)
                        (map (lambda (p) (cons x p))
                             (permute (remove x nums))))
                      nums))]))
; Time Complexity: O(n * n!)
; Memory Complexity: O(n^2)

```