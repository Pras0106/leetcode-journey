# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int searchInsert(vector<int>& nums, int target) {
        // Time: O(log n), Memory: O(1)
        int left = 0;
        int right = (int)nums.size() - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] == target) return mid;
            else if (nums[mid] < target) left = mid + 1;
            else right = mid - 1;
        }
        return left;
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public int searchInsert(int[] nums, int target) {
        // Time: O(log n), Memory: O(1)
        int left = 0;
        int right = nums.length - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] == target) return mid;
            else if (nums[mid] < target) left = mid + 1;
            else right = mid - 1;
        }
        return left;
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
        # Time: O(log n), Memory: O(1)
        left, right = 0, len(nums) - 1
        while left <= right:
            mid = (left + right) // 2
            if nums[mid] == target:
                return mid
            elif nums[mid] < target:
                left = mid + 1
            else:
                right = mid - 1
        return left

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def searchInsert(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: int
        """
        # Time: O(log n), Memory: O(1)
        left, right = 0, len(nums) - 1
        while left <= right:
            mid = (left + right) // 2
            if nums[mid] == target:
                return mid
            elif nums[mid] < target:
                left = mid + 1
            else:
                right = mid - 1
        return left

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
var searchInsert = function(nums, target) {
    // Time: O(log n), Memory: O(1)
    let left = 0;
    let right = nums.length - 1;
    while (left <= right) {
        let mid = Math.floor((left + right) / 2);
        if (nums[mid] === target) return mid;
        else if (nums[mid] < target) left = mid + 1;
        else right = mid - 1;
    }
    return left;
};

```

# Typescript

## Sweet Spot

```typescript
function searchInsert(nums: number[], target: number): number {
    // Time: O(log n), Memory: O(1)
    let left: number = 0;
    let right: number = nums.length - 1;
    while (left <= right) {
        let mid: number = Math.floor((left + right) / 2);
        if (nums[mid] === target) return mid;
        else if (nums[mid] < target) left = mid + 1;
        else right = mid - 1;
    }
    return left;
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int SearchInsert(int[] nums, int target) {
        // Time: O(log n), Memory: O(1)
        int left = 0;
        int right = nums.Length - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] == target) return mid;
            else if (nums[mid] < target) left = mid + 1;
            else right = mid - 1;
        }
        return left;
    }
}

```

# C

## Sweet Spot

```c
int searchInsert(int* nums, int numsSize, int target) {
    // Time: O(log n), Memory: O(1)
    int left = 0;
    int right = numsSize - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] == target) return mid;
        else if (nums[mid] < target) left = mid + 1;
        else right = mid - 1;
    }
    return left;
}

```

# Go

## Sweet Spot

```go
func searchInsert(nums []int, target int) int {
    // Time: O(log n), Memory: O(1)
    left := 0
    right := len(nums) - 1
    for left <= right {
        mid := left + (right-left)/2
        if nums[mid] == target {
            return mid
        } else if nums[mid] < target {
            left = mid + 1
        } else {
            right = mid - 1
        }
    }
    return left
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun searchInsert(nums: IntArray, target: Int): Int {
        // Time: O(log n), Memory: O(1)
        var left = 0
        var right = nums.size - 1
        while (left <= right) {
            val mid = left + (right - left) / 2
            if (nums[mid] == target) return mid
            else if (nums[mid] < target) left = mid + 1
            else right = mid - 1
        }
        return left
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func searchInsert(_ nums: [Int], _ target: Int) -> Int {
        // Time: O(log n), Memory: O(1)
        var left = 0
        var right = nums.count - 1
        while left <= right {
            let mid = left + (right - left) / 2
            if nums[mid] == target {
                return mid
            } else if nums[mid] < target {
                left = mid + 1
            } else {
                right = mid - 1
            }
        }
        return left
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn search_insert(nums: Vec<i32>, target: i32) -> i32 {
        // Time: O(log n), Memory: O(1)
        let mut left = 0i32;
        let mut right = (nums.len() as i32) - 1;
        while left <= right {
            let mid = left + (right - left) / 2;
            if nums[mid as usize] == target {
                return mid;
            } else if nums[mid as usize] < target {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        left
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} nums
# @param {Integer} target
# @return {Integer}
def search_insert(nums, target)
  # Time: O(log n), Memory: O(1)
  left = 0
  right = nums.length - 1
  while left <= right
    mid = (left + right) / 2
    if nums[mid] == target
      return mid
    elsif nums[mid] < target
      left = mid + 1
    else
      right = mid - 1
    end
  end
  left
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
    function searchInsert($nums, $target) {
        // Time: O(log n), Memory: O(1)
        $left = 0;
        $right = count($nums) - 1;
        while ($left <= $right) {
            $mid = floor($left + ($right - $left) / 2);
            if ($nums[$mid] == $target) return $mid;
            elseif ($nums[$mid] < $target) $left = $mid + 1;
            else $right = $mid - 1;
        }
        return $left;
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  int searchInsert(List<int> nums, int target) {
    // Time: O(log n), Memory: O(1)
    int left = 0;
    int right = nums.length - 1;
    while (left <= right) {
      int mid = left + (right - left) ~/ 2;
      if (nums[mid] == target) {
        return mid;
      } else if (nums[mid] < target) {
        left = mid + 1;
      } else {
        right = mid - 1;
      }
    }
    return left;
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def searchInsert(nums: Array[Int], target: Int): Int = {
        // Time: O(log n), Memory: O(1)
        var left = 0
        var right = nums.length - 1
        while (left <= right) {
            val mid = left + (right - left) / 2
            if (nums(mid) == target) return mid
            else if (nums(mid) < target) left = mid + 1
            else right = mid - 1
        }
        left
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec search_insert(nums :: [integer], target :: integer) :: integer
  def search_insert(nums, target) do
    # Time: O(log n), Memory: O(n) due to list to tuple conversion for O(1) access
    arr = List.to_tuple(nums)
    binary_search(arr, target, 0, tuple_size(arr) - 1)
  end

  defp binary_search(_arr, _target, left, right) when left > right, do: left
  defp binary_search(arr, target, left, right) do
    mid = div(left + right, 2)
    val = elem(arr, mid)
    cond do
      val == target -> mid
      val < target -> binary_search(arr, target, mid + 1, right)
      true -> binary_search(arr, target, left, mid - 1)
    end
  end
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec search_insert(Nums :: [integer()], Target :: integer()) -> integer().
search_insert(Nums, Target) ->
    % Time: O(log n), Memory: O(n)
    Tuple = list_to_tuple(Nums),
    search(Tuple, Target, 0, tuple_size(Tuple) - 1).

search(_Tuple, _Target, Left, Right) when Left > Right ->
    Left;
search(Tuple, Target, Left, Right) ->
    Mid = (Left + Right) div 2,
    Val = element(Mid + 1, Tuple),
    if
        Val == Target -> Mid;
        Val < Target -> search(Tuple, Target, Mid + 1, Right);
        true -> search(Tuple, Target, Left, Mid - 1)
    end.

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (search-insert nums target)
  (-> (listof exact-integer?) exact-integer? exact-integer?)
  ;; Time: O(log n), Memory: O(n)
  (let* ([vec (list->vector nums)]
         [n (vector-length vec)])
    (let loop ([left 0]
               [right (- n 1)])
      (if (> left right)
          left
          (let* ([mid (quotient (+ left right) 2)]
                 [val (vector-ref vec mid)])
            (cond
              [(= val target) mid]
              [(< val target) (loop (+ mid 1) right)]
              [else (loop left (- mid 1))]))))))

```