# C++

## Sweet Spot

```cpp
class Solution {
public:
    bool search(vector<int>& nums, int target) {
        // Time Complexity: O(n) worst case, O(log n) average case
        // Memory Complexity: O(1)
        int left = 0, right = nums.size() - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] == target) return true;
            if (nums[left] == nums[mid] && nums[mid] == nums[right]) {
                left++;
                right--;
            } else if (nums[left] <= nums[mid]) {
                if (nums[left] <= target && target < nums[mid]) right = mid - 1;
                else left = mid + 1;
            } else {
                if (nums[mid] < target && target <= nums[right]) left = mid + 1;
                else right = mid - 1;
            }
        }
        return false;
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public boolean search(int[] nums, int target) {
        // Time Complexity: O(n) worst case, O(log n) average case
        // Memory Complexity: O(1)
        int left = 0, right = nums.length - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] == target) return true;
            if (nums[left] == nums[mid] && nums[mid] == nums[right]) {
                left++;
                right--;
            } else if (nums[left] <= nums[mid]) {
                if (nums[left] <= target && target < nums[mid]) right = mid - 1;
                else left = mid + 1;
            } else {
                if (nums[mid] < target && target <= nums[right]) left = mid + 1;
                else right = mid - 1;
            }
        }
        return false;
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def search(self, nums: List[int], target: int) -> bool:
        # Time Complexity: O(n) worst case, O(log n) average case
        # Memory Complexity: O(1)
        left, right = 0, len(nums) - 1
        while left <= right:
            mid = (left + right) // 2
            if nums[mid] == target:
                return True
            if nums[left] == nums[mid] == nums[right]:
                left += 1
                right -= 1
            elif nums[left] <= nums[mid]:
                if nums[left] <= target < nums[mid]:
                    right = mid - 1
                else:
                    left = mid + 1
            else:
                if nums[mid] < target <= nums[right]:
                    left = mid + 1
                else:
                    right = mid - 1
        return False

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def search(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: bool
        """
        # Time Complexity: O(n) worst case, O(log n) average case
        # Memory Complexity: O(1)
        left, right = 0, len(nums) - 1
        while left <= right:
            mid = (left + right) // 2
            if nums[mid] == target:
                return True
            if nums[left] == nums[mid] and nums[mid] == nums[right]:
                left += 1
                right -= 1
            elif nums[left] <= nums[mid]:
                if nums[left] <= target < nums[mid]:
                    right = mid - 1
                else:
                    left = mid + 1
            else:
                if nums[mid] < target <= nums[right]:
                    left = mid + 1
                else:
                    right = mid - 1
        return False

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {boolean}
 */
var search = function(nums, target) {
    // Time Complexity: O(n) worst case, O(log n) average case
    // Memory Complexity: O(1)
    let left = 0, right = nums.length - 1;
    while (left <= right) {
        let mid = Math.floor((left + right) / 2);
        if (nums[mid] === target) return true;
        if (nums[left] === nums[mid] && nums[mid] === nums[right]) {
            left++;
            right--;
        } else if (nums[left] <= nums[mid]) {
            if (nums[left] <= target && target < nums[mid]) right = mid - 1;
            else left = mid + 1;
        } else {
            if (nums[mid] < target && target <= nums[right]) left = mid + 1;
            else right = mid - 1;
        }
    }
    return false;
};

```

# Typescript

## Sweet Spot

```typescript
function search(nums: number[], target: number): boolean {
    // Time Complexity: O(n) worst case, O(log n) average case
    // Memory Complexity: O(1)
    let left: number = 0, right: number = nums.length - 1;
    while (left <= right) {
        let mid: number = Math.floor((left + right) / 2);
        if (nums[mid] === target) return true;
        if (nums[left] === nums[mid] && nums[mid] === nums[right]) {
            left++;
            right--;
        } else if (nums[left] <= nums[mid]) {
            if (nums[left] <= target && target < nums[mid]) right = mid - 1;
            else left = mid + 1;
        } else {
            if (nums[mid] < target && target <= nums[right]) left = mid + 1;
            else right = mid - 1;
        }
    }
    return false;
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public bool Search(int[] nums, int target) {
        // Time Complexity: O(n) worst case, O(log n) average case
        // Memory Complexity: O(1)
        int left = 0, right = nums.Length - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] == target) return true;
            if (nums[left] == nums[mid] && nums[mid] == nums[right]) {
                left++;
                right--;
            } else if (nums[left] <= nums[mid]) {
                if (nums[left] <= target && target < nums[mid]) right = mid - 1;
                else left = mid + 1;
            } else {
                if (nums[mid] < target && target <= nums[right]) left = mid + 1;
                else right = mid - 1;
            }
        }
        return false;
    }
}

```

# C

## Sweet Spot

```c
bool search(int* nums, int numsSize, int target) {
    // Time Complexity: O(n) worst case, O(log n) average case
    // Memory Complexity: O(1)
    int left = 0, right = numsSize - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] == target) return true;
        if (nums[left] == nums[mid] && nums[mid] == nums[right]) {
            left++;
            right--;
        } else if (nums[left] <= nums[mid]) {
            if (nums[left] <= target && target < nums[mid]) right = mid - 1;
            else left = mid + 1;
        } else {
            if (nums[mid] < target && target <= nums[right]) left = mid + 1;
            else right = mid - 1;
        }
    }
    return false;
}

```

# Go

## Sweet Spot

```go
func search(nums []int, target int) bool {
    // Time Complexity: O(n) worst case, O(log n) average case
    // Memory Complexity: O(1)
    left, right := 0, len(nums)-1
    for left <= right {
        mid := left + (right-left)/2
        if nums[mid] == target {
            return true
        }
        if nums[left] == nums[mid] && nums[mid] == nums[right] {
            left++
            right--
        } else if nums[left] <= nums[mid] {
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
    return false
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun search(nums: IntArray, target: Int): Boolean {
        // Time Complexity: O(n) worst case, O(log n) average case
        // Memory Complexity: O(1)
        var left = 0
        var right = nums.size - 1
        while (left <= right) {
            val mid = left + (right - left) / 2
            if (nums[mid] == target) return true
            if (nums[left] == nums[mid] && nums[mid] == nums[right]) {
                left++
                right--
            } else if (nums[left] <= nums[mid]) {
                if (nums[left] <= target && target < nums[mid]) right = mid - 1
                else left = mid + 1
            } else {
                if (nums[mid] < target && target <= nums[right]) left = mid + 1
                else right = mid - 1
            }
        }
        return false
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func search(_ nums: [Int], _ target: Int) -> Bool {
        // Time Complexity: O(n) worst case, O(log n) average case
        // Memory Complexity: O(1)
        var left = 0
        var right = nums.count - 1
        while left <= right {
            let mid = left + (right - left) / 2
            if nums[mid] == target { return true }
            if nums[left] == nums[mid] && nums[mid] == nums[right] {
                left += 1
                right -= 1
            } else if nums[left] <= nums[mid] {
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
        return false
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn search(nums: Vec<i32>, target: i32) -> bool {
        // Time Complexity: O(n) worst case, O(log n) average case
        // Memory Complexity: O(1)
        if nums.is_empty() { return false; }
        let mut left = 0;
        let mut right = nums.len() as i32 - 1;
        while left <= right {
            let mid = left + (right - left) / 2;
            let mid_val = nums[mid as usize];
            if mid_val == target { return true; }
            let left_val = nums[left as usize];
            let right_val = nums[right as usize];
            if left_val == mid_val && mid_val == right_val {
                left += 1;
                right -= 1;
            } else if left_val <= mid_val {
                if left_val <= target && target < mid_val {
                    right = mid - 1;
                } else {
                    left = mid + 1;
                }
            } else {
                if mid_val < target && target <= right_val {
                    left = mid + 1;
                } else {
                    right = mid - 1;
                }
            }
        }
        false
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} nums
# @param {Integer} target
# @return {Boolean}
def search(nums, target)
    # Time Complexity: O(n) worst case, O(log n) average case
    # Memory Complexity: O(1)
    left = 0
    right = nums.length - 1
    while left <= right
        mid = left + (right - left) / 2
        return true if nums[mid] == target
        if nums[left] == nums[mid] && nums[mid] == nums[right]
            left += 1
            right -= 1
        elsif nums[left] <= nums[mid]
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
    false
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[] $nums
     * @param Integer $target
     * @return Boolean
     */
    function search($nums, $target) {
        // Time Complexity: O(n) worst case, O(log n) average case
        // Memory Complexity: O(1)
        $left = 0;
        $right = count($nums) - 1;
        while ($left <= $right) {
            $mid = floor($left + ($right - $left) / 2);
            if ($nums[$mid] == $target) return true;
            if ($nums[$left] == $nums[$mid] && $nums[$mid] == $nums[$right]) {
                $left++;
                $right--;
            } else if ($nums[$left] <= $nums[$mid]) {
                if ($nums[$left] <= $target && $target < $nums[$mid]) $right = $mid - 1;
                else $left = $mid + 1;
            } else {
                if ($nums[$mid] < $target && $target <= $nums[$right]) $left = $mid + 1;
                else $right = $mid - 1;
            }
        }
        return false;
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  bool search(List<int> nums, int target) {
    // Time Complexity: O(n) worst case, O(log n) average case
    // Memory Complexity: O(1)
    int left = 0;
    int right = nums.length - 1;
    while (left <= right) {
      int mid = left + (right - left) ~/ 2;
      if (nums[mid] == target) return true;
      if (nums[left] == nums[mid] && nums[mid] == nums[right]) {
        left++;
        right--;
      } else if (nums[left] <= nums[mid]) {
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
    return false;
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def search(nums: Array[Int], target: Int): Boolean = {
        // Time Complexity: O(n) worst case, O(log n) average case
        // Memory Complexity: O(1)
        var left = 0
        var right = nums.length - 1
        while (left <= right) {
            val mid = left + (right - left) / 2
            if (nums(mid) == target) return true
            if (nums(left) == nums(mid) && nums(mid) == nums(right)) {
                left += 1
                right -= 1
            } else if (nums(left) <= nums(mid)) {
                if (nums(left) <= target && target < nums(mid)) right = mid - 1
                else left = mid + 1
            } else {
                if (nums(mid) < target && target <= nums(right)) left = mid + 1
                else right = mid - 1
            }
        }
        false
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec search(nums :: [integer], target :: integer) :: boolean
  def search(nums, target) do
    # Time Complexity: O(n) worst case, O(log n) average case
    # Memory Complexity: O(n)
    vec = List.to_tuple(nums)
    do_search(vec, target, 0, tuple_size(vec) - 1)
  end

  defp do_search(_vec, _target, left, right) when left > right, do: false
  defp do_search(vec, target, left, right) do
    mid = div(left + right, 2)
    m_val = elem(vec, mid)
    l_val = elem(vec, left)
    r_val = elem(vec, right)
    cond do
      m_val == target -> true
      l_val == m_val and m_val == r_val -> do_search(vec, target, left + 1, right - 1)
      l_val <= m_val ->
        if l_val <= target and target < m_val do
          do_search(vec, target, left, mid - 1)
        else
          do_search(vec, target, mid + 1, right)
        end
      true ->
        if m_val < target and target <= r_val do
          do_search(vec, target, mid + 1, right)
        else
          do_search(vec, target, left, mid - 1)
        end
    end
  end
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec search(Nums :: [integer()], Target :: integer()) -> boolean().
search(Nums, Target) ->
  % Time Complexity: O(n) worst case, O(log n) average case
  % Memory Complexity: O(n)
  Arr = list_to_tuple(Nums),
  search_rec(Arr, Target, 1, tuple_size(Arr)).

search_rec(_Arr, _Target, Left, Right) when Left > Right -> false;
search_rec(Arr, Target, Left, Right) ->
  Mid = Left + (Right - Left) div 2,
  MVal = element(Mid, Arr),
  LVal = element(Left, Arr),
  RVal = element(Right, Arr),
  if
    MVal == Target -> true;
    (LVal == MVal) and (MVal == RVal) -> search_rec(Arr, Target, Left + 1, Right - 1);
    LVal =< MVal ->
      if
        (LVal =< Target) and (Target < MVal) -> search_rec(Arr, Target, Left, Mid - 1);
        true -> search_rec(Arr, Target, Mid + 1, Right)
      end;
    true ->
      if
        (MVal < Target) and (Target =< RVal) -> search_rec(Arr, Target, Mid + 1, Right);
        true -> search_rec(Arr, Target, Left, Mid - 1)
      end
  end.

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (search nums target)
  (-> (listof exact-integer?) exact-integer? boolean?)
  ; Time Complexity: O(n) worst case, O(log n) average case
  ; Memory Complexity: O(n)
  (let ([vec (list->vector nums)])
    (let loop ([left 0] [right (- (vector-length vec) 1)])
      (if (> left right)
          #f
          (let* ([mid (quotient (+ left right) 2)]
                 [m-val (vector-ref vec mid)]
                 [l-val (vector-ref vec left)]
                 [r-val (vector-ref vec right)])
            (cond
              [(= m-val target) #t]
              [(and (= l-val m-val) (= m-val r-val)) (loop (+ left 1) (- right 1))]
              [(<= l-val m-val)
               (if (and (<= l-val target) (< target m-val))
                   (loop left (- mid 1))
                   (loop (+ mid 1) right))]
              [else
               (if (and (> target m-val) (<= target r-val))
                   (loop (+ mid 1) right)
                   (loop left (- mid 1)))]))))))

```