# cpp

## Sweet Spot

```cpp
class Solution {
public:
    vector<vector<int>> subsets(vector<int>& nums) {
        vector<vector<int>> result;
        int n = nums.size();
        int subsetCount = 1 << n;
        result.reserve(subsetCount);
        for (int i = 0; i < subsetCount; ++i) {
            vector<int> current;
            for (int j = 0; j < n; ++j) {
                if ((i >> j) & 1) {
                    current.push_back(nums[j]);
                }
            }
            result.push_back(current);
        }
        return result;
    }
};
// Time Complexity: O(n * 2^n)
// Memory Complexity: O(n * 2^n)

```

# java

## Sweet Spot

```java
class Solution {
    public List<List<Integer>> subsets(int[] nums) {
        List<List<Integer>> result = new ArrayList<>();
        int n = nums.length;
        int subsetCount = 1 << n;
        for (int i = 0; i < subsetCount; i++) {
            List<Integer> current = new ArrayList<>();
            for (int j = 0; j < n; j++) {
                if (((i >> j) & 1) == 1) {
                    current.add(nums[j]);
                }
            }
            result.add(current);
        }
        return result;
    }
}
// Time Complexity: O(n * 2^n)
// Memory Complexity: O(n * 2^n)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def subsets(self, nums: List[int]) -> List[List[int]]:
        result = [[]]
        for num in nums:
            result += [curr + [num] for curr in result]
        return result
# Time Complexity: O(n * 2^n)
# Memory Complexity: O(n * 2^n)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def subsets(self, nums):
        """
        :type nums: List[int]
        :rtype: List[List[int]]
        """
        result = [[]]
        for num in nums:
            new_subsets = []
            for curr in result:
                new_subsets.append(curr + [num])
            result.extend(new_subsets)
        return result
# Time Complexity: O(n * 2^n)
# Memory Complexity: O(n * 2^n)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} nums
 * @return {number[][]}
 */
var subsets = function(nums) {
    const result = [[]];
    for (const num of nums) {
        const size = result.length;
        for (let i = 0; i < size; i++) {
            result.push([...result[i], num]);
        }
    }
    return result;
};
// Time Complexity: O(n * 2^n)
// Memory Complexity: O(n * 2^n)

```

# Typescript

## Sweet Spot

```typescript
function subsets(nums: number[]): number[][] {
    const result: number[][] = [[]];
    for (const num of nums) {
        const size = result.length;
        for (let i = 0; i < size; i++) {
            result.push([...result[i], num]);
        }
    }
    return result;
};
// Time Complexity: O(n * 2^n)
// Memory Complexity: O(n * 2^n)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public IList<IList<int>> Subsets(int[] nums) {
        IList<IList<int>> result = new List<IList<int>>();
        result.Add(new List<int>());
        foreach (int num in nums) {
            int size = result.Count;
            for (int i = 0; i < size; i++) {
                List<int> current = new List<int>(result[i]);
                current.Add(num);
                result.Add(current);
            }
        }
        return result;
    }
}
// Time Complexity: O(n * 2^n)
// Memory Complexity: O(n * 2^n)

```

# C

## Sweet Spot

```c
/**
 * Return an array of arrays of size *returnSize.
 * The sizes of the arrays are returned as *returnColumnSizes array.
 * Note: Both returned array and *columnSizes array must be malloced, assume caller calls free().
 */
int** subsets(int* nums, int numsSize, int* returnSize, int** returnColumnSizes) {
    int totalSubsets = 1 << numsSize;
    *returnSize = totalSubsets;
    int** result = (int**)malloc(totalSubsets * sizeof(int*));
    *returnColumnSizes = (int*)malloc(totalSubsets * sizeof(int));
    for (int i = 0; i < totalSubsets; i++) {
        int count = 0;
        for (int j = 0; j < numsSize; j++) {
            if ((i >> j) & 1) count++;
        }
        (*returnColumnSizes)[i] = count;
        result[i] = (int*)malloc(count * sizeof(int));
        int index = 0;
        for (int j = 0; j < numsSize; j++) {
            if ((i >> j) & 1) {
                result[i][index++] = nums[j];
            }
        }
    }
    return result;
}
/* Time Complexity: O(n * 2^n) */
/* Memory Complexity: O(n * 2^n) */

```

# Go

## Sweet Spot

```go
func subsets(nums []int) [][]int {
    result := [][]int{{}}
    for _, num := range nums {
        size := len(result)
        for i := 0; i < size; i++ {
            curr := make([]int, len(result[i]))
            copy(curr, result[i])
            curr = append(curr, num)
            result = append(result, curr)
        }
    }
    return result
}
// Time Complexity: O(n * 2^n)
// Memory Complexity: O(n * 2^n)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun subsets(nums: IntArray): List<List<Int>> {
        val result = mutableListOf<List<Int>>(emptyList())
        for (num in nums) {
            val size = result.size
            for (i in 0 until size) {
                val current = result[i].toMutableList()
                current.add(num)
                result.add(current)
            }
        }
        return result
    }
}
// Time Complexity: O(n * 2^n)
// Memory Complexity: O(n * 2^n)

```

# swift

## Sweet Spot

```swift
class Solution {
    func subsets(_ nums: [Int]) -> [[Int]] {
        var result: [[Int]] = [[]]
        for num in nums {
            for i in 0..<result.count {
                var current = result[i]
                current.append(num)
                result.append(current)
            }
        }
        return result
    }
}
// Time Complexity: O(n * 2^n)
// Memory Complexity: O(n * 2^n)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn subsets(nums: Vec<i32>) -> Vec<Vec<i32>> {
        let mut result = vec![vec![]];
        for num in nums {
            let size = result.len();
            for i in 0..size {
                let mut current = result[i].clone();
                current.push(num);
                result.push(current);
            }
        }
        result
    }
}
// Time Complexity: O(n * 2^n)
// Space Complexity: O(n * 2^n)
```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} nums
# @return {Integer[][]}
def subsets(nums)
    result = [[]]
    nums.each do |num|
        new_subsets = []
        result.each do |curr|
            new_subsets << (curr + [num])
        end
        result += new_subsets
    end
    result
end
# Time Complexity: O(n * 2^n)
# Memory Complexity: O(n * 2^n)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[] $nums
     * @return Integer[][]
     */
    function subsets($nums) {
        $result = [[]];
        foreach ($nums as $num) {
            $size = count($result);
            for ($i = 0; $i < $size; $i++) {
                $current = $result[$i];
                $current[] = $num;
                $result[] = $current;
            }
        }
        return $result;
    }
}
// Time Complexity: O(n * 2^n)
// Memory Complexity: O(n * 2^n)

```

# dart

## Sweet Spot

```dart
class Solution {
  List<List<int>> subsets(List<int> nums) {
    List<List<int>> result = [[]];
    for (int num in nums) {
      int size = result.length;
      for (int i = 0; i < size; i++) {
        List<int> current = List.from(result[i]);
        current.add(num);
        result.add(current);
      }
    }
    return result;
  }
}
// Time Complexity: O(n * 2^n)
// Memory Complexity: O(n * 2^n)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def subsets(nums: Array[Int]): List[List[Int]] = {
        nums.foldLeft(List(List.empty[Int])) { (acc, num) =>
            acc ++ acc.map(_ :+ num)
        }
    }
}
// Time Complexity: O(n * 2^n)
// Memory Complexity: O(n * 2^n)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec subsets(nums :: [integer]) :: [[integer]]
  def subsets(nums) do
    Enum.reduce(nums, [[]], fn num, acc ->
      acc ++ Enum.map(acc, fn sub -> sub ++ [num] end)
    end)
  end
end
# Time Complexity: O(n * 2^n)
# Memory Complexity: O(n * 2^n)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec subsets(Nums :: [integer()]) -> [[integer()]].
subsets(Nums) ->
    lists:foldl(fun(Num, Acc) ->
        Acc ++ [Sub ++ [Num] || Sub <- Acc]
    end, [[]], Nums).
% Time Complexity: O(n * 2^n)
% Memory Complexity: O(n * 2^n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (subsets nums)
  (-> (listof exact-integer?) (listof (listof exact-integer?)))
  (foldl (lambda (num acc)
           (append acc (map (lambda (sub) (append sub (list num))) acc)))
         '(())
         nums))
; Time Complexity: O(n * 2^n)
; Memory Complexity: O(n * 2^n)

```