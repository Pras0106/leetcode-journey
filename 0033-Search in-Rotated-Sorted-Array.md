# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int search(vector<int>& nums, int target) {
        int left = 0, right = nums.size() - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] == target) return mid;
            if (nums[left] <= nums[mid]) {
                if (nums[left] <= target && target < nums[mid]) right = mid - 1;
                else left = mid + 1;
            } else {
                if (nums[mid] < target && target <= nums[right]) left = mid + 1;
                else right = mid - 1;
            }
        }
        return -1;
    }
};
// Time complexity: O(log n)
// Memory complexity: O(1)

```

# java

## Sweet Spot

```java
class Solution {
    public int search(int[] nums, int target) {
        int left = 0, right = nums.length - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] == target) return mid;
            if (nums[left] <= nums[mid]) {
                if (nums[left] <= target && target < nums[mid]) right = mid - 1;
                else left = mid + 1;
            } else {
                if (nums[mid] < target && target <= nums[right]) left = mid + 1;
                else right = mid - 1;
            }
        }
        return -1;
    }
}
// Time complexity: O(log n)
// Memory complexity: O(1)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        left, right = 0, len(nums) - 1
        while left <= right:
            mid = (left + right) // 2
            if nums[mid] == target:
                return mid
            if nums[left] <= nums[mid]:
                if nums[left] <= target < nums[mid]:
                    right = mid - 1
                else:
                    left = mid + 1
            else:
                if nums[mid] < target <= nums[right]:
                    left = mid + 1
                else:
                    right = mid - 1
        return -1
# Time complexity: O(log n)
# Memory complexity: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def search(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: int
        """
        left, right = 0, len(nums) - 1
        while left <= right:
            mid = (left + right) // 2
            if nums[mid] == target:
                return mid
            if nums[left] <= nums[mid]:
                if nums[left] <= target < nums[mid]:
                    right = mid - 1
                else:
                    left = mid + 1
            else:
                if nums[mid] < target <= nums[right]:
                    left = mid + 1
                else:
                    right = mid - 1
        return -1
# Time complexity: O(log n)
# Memory complexity: O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
var search = function(nums, target) {
    let left = 0, right = nums.length - 1;
    while (left <= right) {
        let mid = Math.floor((left + right) / 2);
        if (nums[mid] === target) return mid;
        if (nums[left] <= nums[mid]) {
            if (nums[left] <= target && target < nums[mid]) right = mid - 1;
            else left = mid + 1;
        } else {
            if (nums[mid] < target && target <= nums[right]) left = mid + 1;
            else right = mid - 1;
        }
    }
    return -1;
};
// Time complexity: O(log n)
// Memory complexity: O(1)

```

# Typescript

## Sweet Spot

```typescript
function search(nums: number[], target: number): number {
    let left = 0, right = nums.length - 1;
    while (left <= right) {
        let mid = Math.floor((left + right) / 2);
        if (nums[mid] === target) return mid;
        if (nums[left] <= nums[mid]) {
            if (nums[left] <= target && target < nums[mid]) right = mid - 1;
            else left = mid + 1;
        } else {
            if (nums[mid] < target && target <= nums[right]) left = mid + 1;
            else right = mid - 1;
        }
    }
    return -1;
};
// Time complexity: O(log n)
// Memory complexity: O(1)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int Search(int[] nums, int target) {
        int left = 0, right = nums.Length - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] == target) return mid;
            if (nums[left] <= nums[mid]) {
                if (nums[left] <= target && target < nums[mid]) right = mid - 1;
                else left = mid + 1;
            } else {
                if (nums[mid] < target && target <= nums[right]) left = mid + 1;
                else right = mid - 1;
            }
        }
        return -1;
    }
}
// Time complexity: O(log n)
// Memory complexity: O(1)

```

# C

## Sweet Spot

```c
int search(int* nums, int numsSize, int target) {
    int left = 0, right = numsSize - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] == target) return mid;
        if (nums[left] <= nums[mid]) {
            if (nums[left] <= target && target < nums[mid]) right = mid - 1;
            else left = mid + 1;
        } else {
            if (nums[mid] < target && target <= nums[right]) left = mid + 1;
            else right = mid - 1;
        }
    }
    return -1;
}
/* Time complexity: O(log n) */
/* Memory complexity: O(1) */

```

# Go

## Sweet Spot

```go
func search(nums []int, target int) int {
    left, right := 0, len(nums) - 1
    for left <= right {
        mid := left + (right - left) / 2
        if nums[mid] == target {
            return mid
        }
        if nums[left] <= nums[mid] {
            if nums[left] <= target && target < nums[mid] {
                right = mid - 1
            } else {
                left = mid + 1
            }
        } else {
            if nums[mid] < target && target <= nums[right] {
                left = mid + 1
            } else {
                right = mid - 1
            }
        }
    }
    return -1
}
// Time complexity: O(log n)
// Memory complexity: O(1)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun search(nums: IntArray, target: Int): Int {
        var left = 0
        var right = nums.size - 1
        while (left <= right) {
            val mid = left + (right - left) / 2
            if (nums[mid] == target) return mid
            if (nums[left] <= nums[mid]) {
                if (nums[left] <= target && target < nums[mid]) right = mid - 1
                else left = mid + 1
            } else {
                if (nums[mid] < target && target <= nums[right]) left = mid + 1
                else right = mid - 1
            }
        }
        return -1
    }
}
// Time complexity: O(log n)
// Memory complexity: O(1)

```

# swift

## Sweet Spot

```swift
class Solution {
    func search(_ nums: [Int], _ target: Int) -> Int {
        var left = 0
        var right = nums.count - 1
        while left <= right {
            let mid = left + (right - left) / 2
            if nums[mid] == target { return mid }
            if nums[left] <= nums[mid] {
                if nums[left] <= target && target < nums[mid] {
                    right = mid - 1
                } else {
                    left = mid + 1
                }
            } else {
                if nums[mid] < target && target <= nums[right] {
                    left = mid + 1
                } else {
                    right = mid - 1
                }
            }
        }
        return -1
    }
}
// Time complexity: O(log n)
// Memory complexity: O(1)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn search(nums: Vec<i32>, target: i32) -> i32 {
        let mut left: i32 = 0;
        let mut right: i32 = nums.len() as i32 - 1;
        while left <= right {
            let mid = left + (right - left) / 2;
            let mid_val = nums[mid as usize];
            if mid_val == target { return mid; }
            if nums[left as usize] <= mid_val {
                if nums[left as usize] <= target && target < mid_val {
                    right = mid - 1;
                } else {
                    left = mid + 1;
                }
            } else {
                if mid_val < target && target <= nums[right as usize] {
                    left = mid + 1;
                } else {
                    right = mid - 1;
                }
            }
        }
        -1
    }
}
// Time complexity: O(log n)
// Memory complexity: O(1)

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} nums
# @param {Integer} target
# @return {Integer}
def search(nums, target)
    left = 0
    right = nums.length - 1
    while left <= right
        mid = left + (right - left) / 2
        return mid if nums[mid] == target
        if nums[left] <= nums[mid]
            if nums[left] <= target && target < nums[mid]
                right = mid - 1
            else
                left = mid + 1
            end
        else
            if nums[mid] < target && target <= nums[right]
                left = mid + 1
            else
                right = mid - 1
            end
        end
    end
    -1
end
# Time complexity: O(log n)
# Memory complexity: O(1)

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
    function search($nums, $target) {
        $left = 0;
        $right = count($nums) - 1;
        while ($left <= $right) {
            $mid = floor($left + ($right - $left) / 2);
            if ($nums[$mid] == $target) return $mid;
            if ($nums[$left] <= $nums[$mid]) {
                if ($nums[$left] <= $target && $target < $nums[$mid]) {
                    $right = $mid - 1;
                } else {
                    $left = $mid + 1;
                }
            } else {
                if ($nums[$mid] < $target && $target <= $nums[$right]) {
                    $left = $mid + 1;
                } else {
                    $right = $mid - 1;
                }
            }
        }
        return -1;
    }
}
// Time complexity: O(log n)
// Memory complexity: O(1)

```

# dart

## Sweet Spot

```dart
class Solution {
  int search(List<int> nums, int target) {
    int left = 0;
    int right = nums.length - 1;
    while (left <= right) {
      int mid = left + (right - left) ~/ 2;
      if (nums[mid] == target) return mid;
      if (nums[left] <= nums[mid]) {
        if (nums[left] <= target && target < nums[mid]) {
          right = mid - 1;
        } else {
          left = mid + 1;
        }
      } else {
        if (nums[mid] < target && target <= nums[right]) {
          left = mid + 1;
        } else {
          right = mid - 1;
        }
      }
    }
    return -1;
  }
}
// Time complexity: O(log n)
// Memory complexity: O(1)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def search(nums: Array[Int], target: Int): Int = {
        var left = 0
        var right = nums.length - 1
        while (left <= right) {
            val mid = left + (right - left) / 2
            if (nums(mid) == target) return mid
            if (nums(left) <= nums(mid)) {
                if (nums(left) <= target && target < nums(mid)) right = mid - 1
                else left = mid + 1
            } else {
                if (nums(mid) < target && target <= nums(right)) left = mid + 1
                else right = mid - 1
            }
        }
        -1
    }
}
// Time complexity: O(log n)
// Memory complexity: O(1)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec search(nums :: [integer], target :: integer) :: integer
  def search(nums, target) do
    vec = List.to_tuple(nums)
    do_search(vec, target, 0, tuple_size(vec) - 1)
  end

  defp do_search(_vec, _target, left, right) when left > right, do: -1
  defp do_search(vec, target, left, right) do
    mid = left + div(right - left, 2)
    mid_val = elem(vec, mid)
    left_val = elem(vec, left)
    right_val = elem(vec, right)

    cond do
      mid_val == target -> mid
      left_val <= mid_val ->
        if left_val <= target and target < mid_val do
          do_search(vec, target, left, mid - 1)
        else
          do_search(vec, target, mid + 1, right)
        end
      true ->
        if mid_val < target and target <= right_val do
          do_search(vec, target, mid + 1, right)
        else
          do_search(vec, target, left, mid - 1)
        end
    end
  end
end
# Time complexity: O(log n)
# Memory complexity: O(n)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec search(Nums :: [integer()], Target :: integer()) -> integer().
search(Nums, Target) ->
    Arr = list_to_tuple(Nums),
    search_helper(Arr, Target, 0, tuple_size(Arr) - 1).

search_helper(_Arr, _Target, Left, Right) when Left > Right -> -1;
search_helper(Arr, Target, Left, Right) ->
    Mid = Left + (Right - Left) div 2,
    MidVal = element(Mid + 1, Arr),
    LeftVal = element(Left + 1, Arr),
    RightVal = element(Right + 1, Arr),
    if
        MidVal =:= Target -> Mid;
        LeftVal =< MidVal ->
            if (LeftVal =< Target) and (Target < MidVal) -> search_helper(Arr, Target, Left, Mid - 1);
               true -> search_helper(Arr, Target, Mid + 1, Right)
            end;
        true ->
            if (MidVal < Target) and (Target =< RightVal) -> search_helper(Arr, Target, Mid + 1, Right);
               true -> search_helper(Arr, Target, Left, Mid - 1)
            end
    end.
% Time complexity: O(log n)
% Memory complexity: O(n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (search nums target)
  (-> (listof exact-integer?) exact-integer? exact-integer?)
  (let ([vec (list->vector nums)])
    (let loop ([left 0] [right (- (vector-length vec) 1)])
      (if (> left right)
          -1
          (let* ([mid (+ left (quotient (- right left) 2))]
                 [mid-val (vector-ref vec mid)]
                 [left-val (vector-ref vec left)]
                 [right-val (vector-ref vec right)])
            (cond
              [(= mid-val target) mid]
              [(<= left-val mid-val)
               (if (and (<= left-val target) (< target mid-val))
                   (loop left (- mid 1))
                   (loop (+ mid 1) right))]
              [else
               (if (and (> target mid-val) (<= target right-val))
                   (loop (+ mid 1) right)
                   (loop left (- mid 1)))]))))))
; Time complexity: O(log n)
; Memory complexity: O(n)

```