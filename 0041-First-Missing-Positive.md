# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int firstMissingPositive(vector<int>& nums) {
        int n = nums.size();
        for (int i = 0; i < n; ++i) {
            while (nums[i] > 0 && nums[i] <= n && nums[nums[i] - 1] != nums[i]) {
                swap(nums[i], nums[nums[i] - 1]);
            }
        }
        for (int i = 0; i < n; ++i) {
            if (nums[i] != i + 1) {
                return i + 1;
            }
        }
        return n + 1;
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public int firstMissingPositive(int[] nums) {
        int n = nums.length;
        for (int i = 0; i < n; i++) {
            while (nums[i] > 0 && nums[i] <= n && nums[nums[i] - 1] != nums[i]) {
                int temp = nums[nums[i] - 1];
                nums[nums[i] - 1] = nums[i];
                nums[i] = temp;
            }
        }
        for (int i = 0; i < n; i++) {
            if (nums[i] != i + 1) {
                return i + 1;
            }
        }
        return n + 1;
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def firstMissingPositive(self, nums: List[int]) -> int:
        n = len(nums)
        for i in range(n):
            while 1 <= nums[i] <= n and nums[nums[i] - 1] != nums[i]:
                correct_idx = nums[i] - 1
                nums[i], nums[correct_idx] = nums[correct_idx], nums[i]
        for i in range(n):
            if nums[i] != i + 1:
                return i + 1
        return n + 1
        # Time Complexity: O(n)
        # Memory Complexity: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def firstMissingPositive(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        n = len(nums)
        for i in range(n):
            while 1 <= nums[i] <= n and nums[nums[i] - 1] != nums[i]:
                correct_idx = nums[i] - 1
                nums[i], nums[correct_idx] = nums[correct_idx], nums[i]
        for i in range(n):
            if nums[i] != i + 1:
                return i + 1
        return n + 1
        # Time Complexity: O(n)
        # Memory Complexity: O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var firstMissingPositive = function(nums) {
    const n = nums.length;
    for (let i = 0; i < n; i++) {
        while (nums[i] > 0 && nums[i] <= n && nums[nums[i] - 1] !== nums[i]) {
            let temp = nums[nums[i] - 1];
            nums[nums[i] - 1] = nums[i];
            nums[i] = temp;
        }
    }
    for (let i = 0; i < n; i++) {
        if (nums[i] !== i + 1) return i + 1;
    }
    return n + 1;
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
};

```

# Typescript

## Sweet Spot

```typescript
function firstMissingPositive(nums: number[]): number {
    const n = nums.length;
    for (let i = 0; i < n; i++) {
        while (nums[i] > 0 && nums[i] <= n && nums[nums[i] - 1] !== nums[i]) {
            const correctIdx = nums[i] - 1;
            [nums[i], nums[correctIdx]] = [nums[correctIdx], nums[i]];
        }
    }
    for (let i = 0; i < n; i++) {
        if (nums[i] !== i + 1) return i + 1;
    }
    return n + 1;
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int FirstMissingPositive(int[] nums) {
        int n = nums.Length;
        for (int i = 0; i < n; i++) {
            while (nums[i] > 0 && nums[i] <= n && nums[nums[i] - 1] != nums[i]) {
                int targetIdx = nums[i] - 1;
                int temp = nums[targetIdx];
                nums[targetIdx] = nums[i];
                nums[i] = temp;
            }
        }
        for (int i = 0; i < n; i++) {
            if (nums[i] != i + 1) return i + 1;
        }
        return n + 1;
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```

# C

## Sweet Spot

```c
int firstMissingPositive(int* nums, int numsSize) {
    for (int i = 0; i < numsSize; i++) {
        while (nums[i] > 0 && nums[i] <= numsSize && nums[nums[i] - 1] != nums[i]) {
            int temp = nums[nums[i] - 1];
            nums[nums[i] - 1] = nums[i];
            nums[i] = temp;
        }
    }
    for (int i = 0; i < numsSize; i++) {
        if (nums[i] != i + 1) return i + 1;
    }
    return numsSize + 1;
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
}

```

# Go

## Sweet Spot

```go
func firstMissingPositive(nums []int) int {
    n := len(nums)
    for i := 0; i < n; i++ {
        for nums[i] > 0 && nums[i] <= n && nums[nums[i]-1] != nums[i] {
            nums[nums[i]-1], nums[i] = nums[i], nums[nums[i]-1]
        }
    }
    for i := 0; i < n; i++ {
        if nums[i] != i+1 {
            return i + 1
        }
    }
    return n + 1
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun firstMissingPositive(nums: IntArray): Int {
        val n = nums.size
        for (i in 0 until n) {
            while (nums[i] > 0 && nums[i] <= n && nums[nums[i] - 1] != nums[i]) {
                val target = nums[i] - 1
                val temp = nums[target]
                nums[target] = nums[i]
                nums[i] = temp
            }
        }
        for (i in 0 until n) {
            if (nums[i] != i + 1) return i + 1
        }
        return n + 1
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func firstMissingPositive(_ nums: [Int]) -> Int {
        var nums = nums
        let n = nums.count
        for i in 0..<n {
            while nums[i] > 0 && nums[i] <= n && nums[nums[i] - 1] != nums[i] {
                nums.swapAt(i, nums[i] - 1)
            }
        }
        for i in 0..<n {
            if nums[i] != i + 1 {
                return i + 1
            }
        }
        return n + 1
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn first_missing_positive(mut nums: Vec<i32>) -> i32 {
        let n = nums.len();
        for i in 0..n {
            while nums[i] > 0 && nums[i] <= n as i32 && nums[(nums[i] - 1) as usize] != nums[i] {
                let target = (nums[i] - 1) as usize;
                nums.swap(i, target);
            }
        }
        for i in 0..n {
            if nums[i] != (i + 1) as i32 {
                return (i + 1) as i32;
            }
        }
        (n + 1) as i32
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} nums
# @return {Integer}
def first_missing_positive(nums)
  n = nums.length
  n.times do |i|
    while nums[i] > 0 && nums[i] <= n && nums[nums[i] - 1] != nums[i]
      target = nums[i] - 1
      nums[i], nums[target] = nums[target], nums[i]
    end
  end
  n.times do |i|
    return i + 1 if nums[i] != i + 1
  end
  n + 1
  # Time Complexity: O(n)
  # Memory Complexity: O(1)
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[] $nums
     * @return Integer
     */
    function firstMissingPositive($nums) {
        $n = count($nums);
        for ($i = 0; $i < $n; $i++) {
            while ($nums[$i] > 0 && $nums[$i] <= $n && $nums[$nums[$i] - 1] != $nums[$i]) {
                $target = $nums[$i] - 1;
                $temp = $nums[$target];
                $nums[$target] = $nums[$i];
                $nums[$i] = $temp;
            }
        }
        for ($i = 0; $i < $n; $i++) {
            if ($nums[$i] != $i + 1) return $i + 1;
        }
        return $n + 1;
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  int firstMissingPositive(List<int> nums) {
    int n = nums.length;
    for (int i = 0; i < n; i++) {
      while (nums[i] > 0 && nums[i] <= n && nums[nums[i] - 1] != nums[i]) {
        int target = nums[i] - 1;
        int temp = nums[target];
        nums[target] = nums[i];
        nums[i] = temp;
      }
    }
    for (int i = 0; i < n; i++) {
      if (nums[i] != i + 1) return i + 1;
    }
    return n + 1;
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def firstMissingPositive(nums: Array[Int]): Int = {
        val n = nums.length
        var i = 0
        while (i < n) {
            while (nums(i) > 0 && nums(i) <= n && nums(nums(i) - 1) != nums(i)) {
                val target = nums(i) - 1
                val temp = nums(target)
                nums(target) = nums(i)
                nums(i) = temp
            }
            i += 1
        }
        i = 0
        while (i < n) {
            if (nums(i) != i + 1) return i + 1
            i += 1
        }
        n + 1
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec first_missing_positive(nums :: [integer]) :: integer
  def first_missing_positive(nums) do
    set = MapSet.new(nums)
    
    find_first(set, 1)
  end

  defp find_first(set, current) do
    if MapSet.member?(set, current) do
      find_first(set, current + 1)
    else
      current
    end
  end

  # Time Complexity: O(n)
  # Memory Complexity: O(n)
end
```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec first_missing_positive(Nums :: [integer()]) -> integer().
first_missing_positive(Nums) ->
    Map = maps:from_list([{X, true} || X <- Nums, X > 0]),
    find_gap(Map, 1).

find_gap(Map, Current) ->
    case maps:is_key(Current, Map) of
        true -> find_gap(Map, Current + 1);
        false -> Current
    end.

% Time Complexity: O(n)
% Space Complexity: O(n)
```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (first-missing-positive nums)
  (-> (listof exact-integer?) exact-integer?)
  (let* ([vec (list->vector nums)]
         [n (vector-length vec)])
    (for ([i (in-range n)])
      (let loop ()
        (let* ([val (vector-ref vec i)]
               [target-idx (- val 1)])
          (when (and (> val 0) (<= val n) (not (= (vector-ref vec target-idx) val)))
            (let ([temp (vector-ref vec target-idx)])
              (vector-set! vec target-idx val)
              (vector-set! vec i temp)
              (loop))))))
    (let find ([i 0])
      (cond
        [(= i n) (+ n 1)]
        [(not (= (vector-ref vec i) (+ i 1))) (+ i 1)]
        [else (find (+ i 1))]))))
; Time Complexity: O(n)
; Memory Complexity: O(n)

```