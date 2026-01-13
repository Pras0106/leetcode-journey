# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int threeSumClosest(vector<int>& nums, int target) {
        /* Time Complexity: O(n^2), Memory Complexity: O(log n) to O(n) depending on sort implementation */
        sort(nums.begin(), nums.end());
        int n = nums.size();
        int closestSum = nums[0] + nums[1] + nums[2];
        for (int i = 0; i < n - 2; ++i) {
            int left = i + 1;
            int right = n - 1;
            while (left < right) {
                int currentSum = nums[i] + nums[left] + nums[right];
                if (abs(currentSum - target) < abs(closestSum - target)) {
                    closestSum = currentSum;
                }
                if (currentSum < target) {
                    left++;
                } else if (currentSum > target) {
                    right--;
                } else {
                    return currentSum;
                }
            }
        }
        return closestSum;
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public int threeSumClosest(int[] nums, int target) {
        /* Time Complexity: O(n^2), Memory Complexity: O(log n) */
        java.util.Arrays.sort(nums);
        int n = nums.length;
        int closestSum = nums[0] + nums[1] + nums[2];
        for (int i = 0; i < n - 2; i++) {
            int left = i + 1;
            int right = n - 1;
            while (left < right) {
                int currentSum = nums[i] + nums[left] + nums[right];
                if (Math.abs(currentSum - target) < Math.abs(closestSum - target)) {
                    closestSum = currentSum;
                }
                if (currentSum < target) {
                    left++;
                } else if (currentSum > target) {
                    right--;
                } else {
                    return currentSum;
                }
            }
        }
        return closestSum;
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def threeSumClosest(self, nums: List[int], target: int) -> int:
        # Time Complexity: O(n^2), Memory Complexity: O(n)
        nums.sort()
        n = len(nums)
        closest_sum = nums[0] + nums[1] + nums[2]
        for i in range(n - 2):
            left, right = i + 1, n - 1
            while left < right:
                current_sum = nums[i] + nums[left] + nums[right]
                if abs(current_sum - target) < abs(closest_sum - target):
                    closest_sum = current_sum
                if current_sum < target:
                    left += 1
                elif current_sum > target:
                    right -= 1
                else:
                    return current_sum
        return closest_sum

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def threeSumClosest(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: int
        """
        # Time Complexity: O(n^2), Memory Complexity: O(n)
        nums.sort()
        n = len(nums)
        closest_sum = nums[0] + nums[1] + nums[2]
        for i in range(n - 2):
            left, right = i + 1, n - 1
            while left < right:
                current_sum = nums[i] + nums[left] + nums[right]
                if abs(current_sum - target) < abs(closest_sum - target):
                    closest_sum = current_sum
                if current_sum < target:
                    left += 1
                elif current_sum > target:
                    right -= 1
                else:
                    return current_sum
        return closest_sum

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
var threeSumClosest = function(nums, target) {
    /* Time Complexity: O(n^2), Memory Complexity: O(log n) */
    nums.sort((a, b) => a - b);
    let n = nums.length;
    let closestSum = nums[0] + nums[1] + nums[2];
    for (let i = 0; i < n - 2; i++) {
        let left = i + 1;
        let right = n - 1;
        while (left < right) {
            let currentSum = nums[i] + nums[left] + nums[right];
            if (Math.abs(currentSum - target) < Math.abs(closestSum - target)) {
                closestSum = currentSum;
            }
            if (currentSum < target) {
                left++;
            } else if (currentSum > target) {
                right--;
            } else {
                return currentSum;
            }
        }
    }
    return closestSum;
};

```

# Typescript

## Sweet Spot

```typescript
function threeSumClosest(nums: number[], target: number): number {
    /* Time Complexity: O(n^2), Memory Complexity: O(log n) */
    nums.sort((a, b) => a - b);
    const n = nums.length;
    let closestSum = nums[0] + nums[1] + nums[2];
    for (let i = 0; i < n - 2; i++) {
        let left = i + 1;
        let right = n - 1;
        while (left < right) {
            const currentSum = nums[i] + nums[left] + nums[right];
            if (Math.abs(currentSum - target) < Math.abs(closestSum - target)) {
                closestSum = currentSum;
            }
            if (currentSum < target) {
                left++;
            } else if (currentSum > target) {
                right--;
            } else {
                return currentSum;
            }
        }
    }
    return closestSum;
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int ThreeSumClosest(int[] nums, int target) {
        /* Time Complexity: O(n^2), Memory Complexity: O(log n) */
        System.Array.Sort(nums);
        int n = nums.Length;
        int closestSum = nums[0] + nums[1] + nums[2];
        for (int i = 0; i < n - 2; i++) {
            int left = i + 1;
            int right = n - 1;
            while (left < right) {
                int currentSum = nums[i] + nums[left] + nums[right];
                if (System.Math.Abs(currentSum - target) < System.Math.Abs(closestSum - target)) {
                    closestSum = currentSum;
                }
                if (currentSum < target) {
                    left++;
                } else if (currentSum > target) {
                    right--;
                } else {
                    return currentSum;
                }
            }
        }
        return closestSum;
    }
}

```

# C

## Sweet Spot

```c
int compare(const void* a, const void* b) {
    return (*(int*)a - *(int*)b);
}

int threeSumClosest(int* nums, int numsSize, int target) {
    /* Time Complexity: O(n^2), Memory Complexity: O(1) */
    qsort(nums, numsSize, sizeof(int), compare);
    int closestSum = nums[0] + nums[1] + nums[2];
    for (int i = 0; i < numsSize - 2; i++) {
        int left = i + 1;
        int right = numsSize - 1;
        while (left < right) {
            int currentSum = nums[i] + nums[left] + nums[right];
            if (abs(currentSum - target) < abs(closestSum - target)) {
                closestSum = currentSum;
            }
            if (currentSum < target) {
                left++;
            } else if (currentSum > target) {
                right--;
            } else {
                return currentSum;
            }
        }
    }
    return closestSum;
}

```

# Go

## Sweet Spot

```go
import (
    "sort"
    "math"
)

func threeSumClosest(nums []int, target int) int {
    /* Time Complexity: O(n^2), Memory Complexity: O(log n) */
    sort.Ints(nums)
    n := len(nums)
    closestSum := nums[0] + nums[1] + nums[2]
    for i := 0; i < n - 2; i++ {
        left, right := i + 1, n - 1
        for left < right {
            currentSum := nums[i] + nums[left] + nums[right]
            if math.Abs(float64(currentSum - target)) < math.Abs(float64(closestSum - target)) {
                closestSum = currentSum
            }
            if currentSum < target {
                left++
            } else if currentSum > target {
                right--
            } else {
                return currentSum
            }
        }
    }
    return closestSum
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun threeSumClosest(nums: IntArray, target: Int): Int {
        /* Time Complexity: O(n^2), Memory Complexity: O(log n) */
        nums.sort()
        val n = nums.size
        var closestSum = nums[0] + nums[1] + nums[2]
        for (i in 0 until n - 2) {
            var left = i + 1
            var right = n - 1
            while (left < right) {
                val currentSum = nums[i] + nums[left] + nums[right]
                if (Math.abs(currentSum - target) < Math.abs(closestSum - target)) {
                    closestSum = currentSum
                }
                when {
                    currentSum < target -> left++
                    currentSum > target -> right--
                    else -> return currentSum
                }
            }
        }
        return closestSum
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func threeSumClosest(_ nums: [Int], _ target: Int) -> Int {
        /* Time Complexity: O(n^2), Memory Complexity: O(n) */
        let sortedNums = nums.sorted()
        let n = sortedNums.count
        var closestSum = sortedNums[0] + sortedNums[1] + sortedNums[2]
        for i in 0..<(n - 2) {
            var left = i + 1
            var right = n - 1
            while left < right {
                let currentSum = sortedNums[i] + sortedNums[left] + sortedNums[right]
                if abs(currentSum - target) < abs(closestSum - target) {
                    closestSum = currentSum
                }
                if currentSum < target {
                    left += 1
                } else if currentSum > target {
                    right -= 1
                } else {
                    return currentSum
                }
            }
        }
        return closestSum
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn three_sum_closest(mut nums: Vec<i32>, target: i32) -> i32 {
        /* Time Complexity: O(n^2), Memory Complexity: O(log n) */
        nums.sort();
        let n = nums.len();
        let mut closest_sum = nums[0] + nums[1] + nums[2];
        for i in 0..n - 2 {
            let mut left = i + 1;
            let mut right = n - 1;
            while left < right {
                let current_sum = nums[i] + nums[left] + nums[right];
                if (current_sum - target).abs() < (closest_sum - target).abs() {
                    closest_sum = current_sum;
                }
                if current_sum < target {
                    left += 1;
                } else if current_sum > target {
                    right -= 1;
                } else {
                    return current_sum;
                }
            }
        }
        closest_sum
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} nums
# @param {Integer} target
# @return {Integer}
def three_sum_closest(nums, target)
    # Time Complexity: O(n^2), Memory Complexity: O(n)
    nums.sort!
    n = nums.length
    closest_sum = nums[0] + nums[1] + nums[2]
    (0..n - 3).each do |i|
        left = i + 1
        right = n - 1
        while left < right
            current_sum = nums[i] + nums[left] + nums[right]
            if (current_sum - target).abs < (closest_sum - target).abs
                closest_sum = current_sum
            end
            if current_sum < target
                left += 1
            elsif current_sum > target
                right -= 1
            else
                return current_sum
            end
        end
    end
    closest_sum
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[] $nums
     * @param Integer $target
     * @return Integer
     */
    function threeSumClosest($nums, $target) {
        /* Time Complexity: O(n^2), Memory Complexity: O(log n) */
        sort($nums);
        $n = count($nums);
        $closestSum = $nums[0] + $nums[1] + $nums[2];

        for ($i = 0; $i < $n - 2; $i++) {
            $left = $i + 1;
            $right = $n - 1;

            while ($left < $right) {
                $currentSum = $nums[$i] + $nums[$left] + $nums[$right];

                if (abs($currentSum - $target) < abs($closestSum - $target)) {
                    $closestSum = $currentSum;
                }

                if ($currentSum < $target) {
                    $left++;
                } elseif ($currentSum > $target) {
                    $right--;
                } else {
                    return $currentSum;
                }
            }
        }

        return $closestSum;
    }
}
```

# dart

## Sweet Spot

```dart
class Solution {
  int threeSumClosest(List<int> nums, int target) {
    /* Time Complexity: O(n^2), Memory Complexity: O(log n) */
    nums.sort();
    int n = nums.length;
    int closestSum = nums[0] + nums[1] + nums[2];
    for (int i = 0; i < n - 2; i++) {
      int left = i + 1;
      int right = n - 1;
      while (left < right) {
        int currentSum = nums[i] + nums[left] + nums[right];
        if ((currentSum - target).abs() < (closestSum - target).abs()) {
          closestSum = currentSum;
        }
        if (currentSum < target) {
          left++;
        } else if (currentSum > target) {
          right--;
        } else {
          return currentSum;
        }
      }
    }
    return closestSum;
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
import scala.util.boundary

object Solution {
    def threeSumClosest(nums: Array[Int], target: Int): Int = boundary {
        /* Time Complexity: O(n^2), Memory Complexity: O(log n) */
        val sortedNums = nums.sorted
        val n = sortedNums.length
        var closestSum = sortedNums(0) + sortedNums(1) + sortedNums(2)

        for (i <- 0 until n - 2) {
            var left = i + 1
            var right = n - 1
            while (left < right) {
                val currentSum = sortedNums(i) + sortedNums(left) + sortedNums(right)
                
                if (Math.abs(currentSum - target) < Math.abs(closestSum - target)) {
                    closestSum = currentSum
                }

                if (currentSum < target) {
                    left += 1
                } else if (currentSum > target) {
                    right -= 1
                } else {
                    boundary.break(currentSum)
                }
            }
        }
        closestSum
    }
}
```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec three_sum_closest(nums :: [integer], target :: integer) :: integer
  def three_sum_closest(nums, target) do
    # Time Complexity: O(n^2), Memory Complexity: O(n)
    sorted_nums = Enum.sort(nums) |> List.to_tuple()
    n = tuple_size(sorted_nums)
    initial_closest = elem(sorted_nums, 0) + elem(sorted_nums, 1) + elem(sorted_nums, 2)
    
    Enum.reduce(0..(n - 3), initial_closest, fn i, acc_closest ->
      find_closest_for_i(i, i + 1, n - 1, sorted_nums, target, acc_closest)
    end)
  end

  defp find_closest_for_i(i, left, right, nums, target, current_closest) when left < right do
    sum = elem(nums, i) + elem(nums, left) + elem(nums, right)
    new_closest = if abs(sum - target) < abs(current_closest - target), do: sum, else: current_closest
    
    cond do
      sum == target -> sum
      sum < target -> find_closest_for_i(i, left + 1, right, nums, target, new_closest)
      sum > target -> find_closest_for_i(i, left, right - 1, nums, target, new_closest)
    end
  end

  defp find_closest_for_i(_i, _left, _right, _nums, _target, current_closest), do: current_closest
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec three_sum_closest(Nums :: [integer()], Target :: integer()) -> integer().
three_sum_closest(Nums, Target) ->
  % Time Complexity: O(n^2), Memory Complexity: O(n)
  SortedNums = list_to_tuple(lists:sort(Nums)),
  N = tuple_size(SortedNums),
  InitialClosest = element(1, SortedNums) + element(2, SortedNums) + element(3, SortedNums),
  loop_i(1, N - 2, SortedNums, Target, InitialClosest).

loop_i(I, Limit, SortedNums, Target, Closest) when I =< Limit ->
  NewClosest = loop_pointers(I, I + 1, tuple_size(SortedNums), SortedNums, Target, Closest),
  case NewClosest == Target of
    true -> Target;
    false -> loop_i(I + 1, Limit, SortedNums, Target, NewClosest)
  end;
loop_i(_I, _Limit, _SortedNums, _Target, Closest) ->
  Closest.

loop_pointers(I, Left, Right, SortedNums, Target, Closest) when Left < Right ->
  Sum = element(I, SortedNums) + element(Left, SortedNums) + element(Right, SortedNums),
  Diff = abs(Sum - Target),
  CurrentDiff = abs(Closest - Target),
  NextClosest = if Diff < CurrentDiff -> Sum; true -> Closest end,
  if
    Sum == Target -> Target;
    Sum < Target -> loop_pointers(I, Left + 1, Right, SortedNums, Target, NextClosest);
    true -> loop_pointers(I, Left, Right - 1, SortedNums, Target, NextClosest)
  end;
loop_pointers(_I, _Left, _Right, _SortedNums, _Target, Closest) ->
  Closest.

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (three-sum-closest nums target)
  (-> (listof exact-integer?) exact-integer? exact-integer?)
  ; Time Complexity: O(n^2), Memory Complexity: O(n)
  (let* ([sorted-nums (list->vector (sort nums <))]
         [n (vector-length sorted-nums)]
         [closest-sum (+ (vector-ref sorted-nums 0) 
                         (vector-ref sorted-nums 1) 
                         (vector-ref sorted-nums 2))])
    (let loop-i ([i 0] [res closest-sum])
      (if (< i (- n 2))
          (let loop-p ([left (+ i 1)] [right (- n 1)] [inner-res res])
            (if (< left right)
                (let* ([current-sum (+ (vector-ref sorted-nums i)
                                       (vector-ref sorted-nums left)
                                       (vector-ref sorted-nums right))])
                  (let ([updated-res (if (< (abs (- current-sum target)) 
                                            (abs (- inner-res target)))
                                         current-sum
                                         inner-res)])
                    (cond
                      [(= current-sum target) target]
                      [(< current-sum target) (loop-p (+ left 1) right updated-res)]
                      [else (loop-p left (- right 1) updated-res)])))
                (loop-i (+ i 1) inner-res)))
          res))))

```