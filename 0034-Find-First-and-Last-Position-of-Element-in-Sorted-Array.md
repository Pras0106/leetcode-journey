# cpp

## Sweet Spot

```cpp
class Solution {
public:
    vector<int> searchRange(vector<int>& nums, int target) {
        // Time Complexity: O(log n)
        // Memory Complexity: O(1)
        int start = -1, end = -1;
        int left = 0, right = (int)nums.size() - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] >= target) {
                if (nums[mid] == target) start = mid;
                right = mid - 1;
            } else {
                left = mid + 1;
            }
        }
        if (start == -1) return {-1, -1};
        left = start, right = (int)nums.size() - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] <= target) {
                if (nums[mid] == target) end = mid;
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return {start, end};
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public int[] searchRange(int[] nums, int target) {
        // Time Complexity: O(log n)
        // Memory Complexity: O(1)
        int[] result = new int[]{-1, -1};
        int left = 0, right = nums.length - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] >= target) {
                if (nums[mid] == target) result[0] = mid;
                right = mid - 1;
            } else {
                left = mid + 1;
            }
        }
        if (result[0] == -1) return result;
        left = result[0]; 
        right = nums.length - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] <= target) {
                if (nums[mid] == target) result[1] = mid;
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return result;
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def searchRange(self, nums: List[int], target: int) -> List[int]:
        # Time Complexity: O(log n)
        # Memory Complexity: O(1)
        def find_bound(is_first):
            left, right = 0, len(nums) - 1
            bound = -1
            while left <= right:
                mid = (left + right) // 2
                if nums[mid] == target:
                    bound = mid
                    if is_first: right = mid - 1
                    else: left = mid + 1
                elif nums[mid] < target: left = mid + 1
                else: right = mid - 1
            return bound
        
        start = find_bound(True)
        if start == -1: return [-1, -1]
        return [start, find_bound(False)]

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def searchRange(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        # Time Complexity: O(log n)
        # Memory Complexity: O(1)
        def find_bound(is_first):
            left, right = 0, len(nums) - 1
            bound = -1
            while left <= right:
                mid = left + (right - left) // 2
                if nums[mid] == target:
                    bound = mid
                    if is_first: right = mid - 1
                    else: left = mid + 1
                elif nums[mid] < target: left = mid + 1
                else: right = mid - 1
            return bound
        
        start = find_bound(True)
        if start == -1: return [-1, -1]
        return [start, find_bound(False)]

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var searchRange = function(nums, target) {
    // Time Complexity: O(log n)
    // Memory Complexity: O(1)
    const findBound = (isFirst) => {
        let left = 0, right = nums.length - 1, bound = -1;
        while (left <= right) {
            let mid = Math.floor(left + (right - left) / 2);
            if (nums[mid] === target) {
                bound = mid;
                if (isFirst) right = mid - 1;
                else left = mid + 1;
            } else if (nums[mid] < target) left = mid + 1;
            else right = mid - 1;
        }
        return bound;
    };
    let start = findBound(true);
    if (start === -1) return [-1, -1];
    return [start, findBound(false)];
};

```

# Typescript

## Sweet Spot

```typescript
function searchRange(nums: number[], target: number): number[] {
    // Time Complexity: O(log n)
    // Memory Complexity: O(1)
    const findBound = (isFirst: boolean): number => {
        let left = 0, right = nums.length - 1, bound = -1;
        while (left <= right) {
            let mid = Math.floor(left + (right - left) / 2);
            if (nums[mid] === target) {
                bound = mid;
                if (isFirst) right = mid - 1;
                else left = mid + 1;
            } else if (nums[mid] < target) left = mid + 1;
            else right = mid - 1;
        }
        return bound;
    };
    const start = findBound(true);
    if (start === -1) return [-1, -1];
    return [start, findBound(false)];
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int[] SearchRange(int[] nums, int target) {
        // Time Complexity: O(log n)
        // Memory Complexity: O(1)
        int[] result = new int[] { -1, -1 };
        int left = 0, right = nums.Length - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] >= target) {
                if (nums[mid] == target) result[0] = mid;
                right = mid - 1;
            } else {
                left = mid + 1;
            }
        }
        if (result[0] == -1) return result;
        left = result[0];
        right = nums.Length - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] <= target) {
                if (nums[mid] == target) result[1] = mid;
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return result;
    }
}

```

# C

## Sweet Spot

```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* searchRange(int* nums, int numsSize, int target, int* returnSize) {
    // Time Complexity: O(log n)
    // Memory Complexity: O(1)
    *returnSize = 2;
    int* result = (int*)malloc(2 * sizeof(int));
    result[0] = -1; result[1] = -1;
    int left = 0, right = numsSize - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] >= target) {
            if (nums[mid] == target) result[0] = mid;
            right = mid - 1;
        } else left = mid + 1;
    }
    if (result[0] == -1) return result;
    left = result[0]; right = numsSize - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] <= target) {
            if (nums[mid] == target) result[1] = mid;
            left = mid + 1;
        } else right = mid - 1;
    }
    return result;
}

```

# Go

## Sweet Spot

```go
func searchRange(nums []int, target int) []int {
    // Time Complexity: O(log n)
    // Memory Complexity: O(1)
    findBound := func(isFirst bool) int {
        left, right, bound := 0, len(nums)-1, -1
        for left <= right {
            mid := left + (right-left)/2
            if nums[mid] == target {
                bound = mid
                if isFirst {
                    right = mid - 1
                } else {
                    left = mid + 1
                }
            } else if nums[mid] < target {
                left = mid + 1
            } else {
                right = mid - 1
            }
        }
        return bound
    }
    start := findBound(true)
    if start == -1 {
        return []int{-1, -1}
    }
    return []int{start, findBound(false)}
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun searchRange(nums: IntArray, target: Int): IntArray {
        // Time Complexity: O(log n)
        // Memory Complexity: O(1)
        fun findBound(isFirst: Boolean): Int {
            var left = 0
            var right = nums.size - 1
            var bound = -1
            while (left <= right) {
                val mid = left + (right - left) / 2
                if (nums[mid] == target) {
                    bound = mid
                    if (isFirst) right = mid - 1 else left = mid + 1
                } else if (nums[mid] < target) {
                    left = mid + 1
                } else {
                    right = mid - 1
                }
            }
            return bound
        }
        val start = findBound(true)
        if (start == -1) return intArrayOf(-1, -1)
        return intArrayOf(start, findBound(false))
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func searchRange(_ nums: [Int], _ target: Int) -> [Int] {
        // Time Complexity: O(log n)
        // Memory Complexity: O(1)
        func findBound(_ isFirst: Bool) -> Int {
            var left = 0, right = nums.count - 1, bound = -1
            while left <= right {
                let mid = left + (right - left) / 2
                if nums[mid] == target {
                    bound = mid
                    if isFirst { right = mid - 1 }
                    else { left = mid + 1 }
                } else if nums[mid] < target { left = mid + 1 }
                else { right = mid - 1 }
            }
            return bound
        }
        let start = findBound(true)
        if start == -1 { return [-1, -1] }
        return [start, findBound(false)]
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn search_range(nums: Vec<i32>, target: i32) -> Vec<i32> {
        // Time Complexity: O(log n)
        // Memory Complexity: O(1)
        let find_bound = |is_first: bool| -> i32 {
            let (mut left, mut right, mut bound) = (0i32, nums.len() as i32 - 1, -1i32);
            while left <= right {
                let mid = left + (right - left) / 2;
                if nums[mid as usize] == target {
                    bound = mid;
                    if is_first { right = mid - 1; }
                    else { left = mid + 1; }
                } else if nums[mid as usize] < target { left = mid + 1; }
                else { right = mid - 1; }
            }
            bound
        };
        let start = find_bound(true);
        if start == -1 { return vec![-1, -1]; }
        vec![start, find_bound(false)]
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} nums
# @param {Integer} target
# @return {Integer[]}
def search_range(nums, target)
    # Time Complexity: O(log n)
    # Memory Complexity: O(1)
    find_bound = lambda do |is_first|
        left, right, bound = 0, nums.length - 1, -1
        while left <= right
            mid = left + (right - left) / 2
            if nums[mid] == target
                bound = mid
                is_first ? right = mid - 1 : left = mid + 1
            elsif nums[mid] < target
                left = mid + 1
            else
                right = mid - 1
            end
        end
        bound
    end
    start_idx = find_bound.call(true)
    return [-1, -1] if start_idx == -1
    [start_idx, find_bound.call(false)]
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[] $nums
     * @param Integer $target
     * @return Integer[]
     */
    function searchRange($nums, $target) {
        // Time Complexity: O(log n)
        // Memory Complexity: O(1)
        $findBound = function($isFirst) use ($nums, $target) {
            $left = 0; $right = count($nums) - 1; $bound = -1;
            while ($left <= $right) {
                $mid = $left + floor(($right - $left) / 2);
                if ($nums[$mid] == $target) {
                    $bound = $mid;
                    if ($isFirst) $right = $mid - 1;
                    else $left = $mid + 1;
                } elseif ($nums[$mid] < $target) $left = $mid + 1;
                else $right = $mid - 1;
            }
            return $bound;
        };
        $start = $findBound(true);
        if ($start == -1) return [-1, -1];
        return [$start, $findBound(false)];
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  List<int> searchRange(List<int> nums, int target) {
    // Time Complexity: O(log n)
    // Memory Complexity: O(1)
    int findBound(bool isFirst) {
      int left = 0, right = nums.length - 1, bound = -1;
      while (left <= right) {
        int mid = left + (right - left) ~/ 2;
        if (nums[mid] == target) {
          bound = mid;
          if (isFirst) right = mid - 1;
          else left = mid + 1;
        } else if (nums[mid] < target) {
          left = mid + 1;
        } else {
          right = mid - 1;
        }
      }
      return bound;
    }
    int start = findBound(true);
    if (start == -1) return [-1, -1];
    return [start, findBound(false)];
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def searchRange(nums: Array[Int], target: Int): Array[Int] = {
        // Time Complexity: O(log n)
        // Memory Complexity: O(1)
        def findBound(isFirst: Boolean): Int = {
            var left = 0
            var right = nums.length - 1
            var bound = -1
            while (left <= right) {
                val mid = left + (right - left) / 2
                if (nums(mid) == target) {
                    bound = mid
                    if (isFirst) right = mid - 1 else left = mid + 1
                } else if (nums(mid) < target) left = mid + 1
                else right = mid - 1
            }
            bound
        }
        val start = findBound(true)
        if (start == -1) Array(-1, -1)
        else Array(start, findBound(false))
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec search_range(nums :: [integer], target :: integer) :: [integer]
  def search_range(nums, target) do
    # Time Complexity: O(log n)
    # Memory Complexity: O(n)
    vec = List.to_tuple(nums)
    n = tuple_size(vec)
    start_idx = find_bound(vec, target, 0, n - 1, -1, true)
    if start_idx == -1 do
      [-1, -1]
    else
      [start_idx, find_bound(vec, target, start_idx, n - 1, -1, false)]
    end
  end

  defp find_bound(_vec, _target, left, right, bound, _is_first) when left > right, do: bound
  defp find_bound(vec, target, left, right, bound, is_first) do
    mid = left + div(right - left, 2)
    val = elem(vec, mid)
    cond do
      val == target ->
        if is_first, do: find_bound(vec, target, left, mid - 1, mid, is_first),
        else: find_bound(vec, target, mid + 1, right, mid, is_first)
      val < target -> find_bound(vec, target, mid + 1, right, bound, is_first)
      true -> find_bound(vec, target, left, mid - 1, bound, is_first)
    end
  end
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec search_range(Nums :: [integer()], Target :: integer()) -> [integer()].
search_range(Nums, Target) ->
  % Time Complexity: O(log n)
  % Memory Complexity: O(n)
  Arr = list_to_tuple(Nums),
  Size = tuple_size(Arr),
  Start = find_bound(Arr, Target, 1, Size, -1, true),
  case Start of
    -1 -> [-1, -1];
    _ -> [Start - 1, find_bound(Arr, Target, Start, Size, -1, false) - 1]
  end.

find_bound(_Arr, _Target, L, R, Bound, _IsFirst) when L > R -> Bound;
find_bound(Arr, Target, L, R, Bound, IsFirst) ->
  Mid = L + (R - L) div 2,
  Val = element(Mid, Arr),
  if
    Val == Target ->
      if IsFirst -> find_bound(Arr, Target, L, Mid - 1, Mid, IsFirst);
         true -> find_bound(Arr, Target, Mid + 1, R, Mid, IsFirst)
      end;
    Val < Target -> find_bound(Arr, Target, Mid + 1, R, Bound, IsFirst);
    true -> find_bound(Arr, Target, L, Mid - 1, Bound, IsFirst)
  end.

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (search-range nums target)
  (-> (listof exact-integer?) exact-integer? (listof exact-integer?))
  ; Time Complexity: O(log n)
  ; Memory Complexity: O(n)
  (let* ([vec (list->vector nums)]
         [n (vector-length vec)]
         [find-bound (lambda (is-first)
                       (let loop ([left 0] [right (- n 1)] [bound -1])
                         (if (> left right)
                             bound
                             (let* ([mid (+ left (quotient (- right left) 2))]
                                    [val (vector-ref vec mid)])
                               (cond
                                 [(= val target)
                                  (if is-first
                                      (loop left (- mid 1) mid)
                                      (loop (+ mid 1) right mid))]
                                 [(< val target) (loop (+ mid 1) right bound)]
                                 [else (loop left (- mid 1) bound)])))))])
    (let ([start (find-bound #t)])
      (if (= start -1)
          '(-1 -1)
          (list start (find-bound #f))))))

```