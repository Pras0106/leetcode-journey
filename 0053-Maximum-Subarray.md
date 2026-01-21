# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int max_so_far = nums[0];
        int current_max = nums[0];
        for (size_t i = 1; i < nums.size(); ++i) {
            current_max = max(nums[i], current_max + nums[i]);
            max_so_far = max(max_so_far, current_max);
        }
        return max_so_far;
    }
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
};

```

# java

## Sweet Spot

```java
class Solution {
    public int maxSubArray(int[] nums) {
        int maxSoFar = nums[0];
        int currentMax = nums[0];
        for (int i = 1; i < nums.length; i++) {
            currentMax = Math.max(nums[i], currentMax + nums[i]);
            maxSoFar = Math.max(maxSoFar, currentMax);
        }
        return maxSoFar;
    }
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        max_so_far = current_max = nums[0]
        for x in nums[1:]:
            current_max = max(x, current_max + x)
            max_so_far = max(max_so_far, current_max)
        return max_so_far
    # Time Complexity: O(n)
    # Memory Complexity: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def maxSubArray(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        max_so_far = current_max = nums[0]
        for i in range(1, len(nums)):
            current_max = max(nums[i], current_max + nums[i])
            max_so_far = max(max_so_far, current_max)
        return max_so_far
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
var maxSubArray = function(nums) {
    let maxSoFar = nums[0];
    let currentMax = nums[0];
    for (let i = 1; i < nums.length; i++) {
        currentMax = Math.max(nums[i], currentMax + nums[i]);
        maxSoFar = Math.max(maxSoFar, currentMax);
    }
    return maxSoFar;
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
};

```

# Typescript

## Sweet Spot

```typescript
function maxSubArray(nums: number[]): number {
    let maxSoFar: number = nums[0];
    let currentMax: number = nums[0];
    for (let i = 1; i < nums.length; i++) {
        currentMax = Math.max(nums[i], currentMax + nums[i]);
        maxSoFar = Math.max(maxSoFar, currentMax);
    }
    return maxSoFar;
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int MaxSubArray(int[] nums) {
        int maxSoFar = nums[0];
        int currentMax = nums[0];
        for (int i = 1; i < nums.Length; i++) {
            currentMax = Math.Max(nums[i], currentMax + nums[i]);
            maxSoFar = Math.Max(maxSoFar, currentMax);
        }
        return maxSoFar;
    }
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
}

```

# C

## Sweet Spot

```c
int maxSubArray(int* nums, int numsSize) {
    int maxSoFar = nums[0];
    int currentMax = nums[0];
    for (int i = 1; i < numsSize; i++) {
        int val = nums[i];
        currentMax = (val > currentMax + val) ? val : currentMax + val;
        maxSoFar = (maxSoFar > currentMax) ? maxSoFar : currentMax;
    }
    return maxSoFar;
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
}

```

# Go

## Sweet Spot

```go
func maxSubArray(nums []int) int {
    maxSoFar := nums[0]
    currentMax := nums[0]
    for i := 1; i < len(nums); i++ {
        if nums[i] > currentMax + nums[i] {
            currentMax = nums[i]
        } else {
            currentMax = currentMax + nums[i]
        }
        if currentMax > maxSoFar {
            maxSoFar = currentMax
        }
    }
    return maxSoFar
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun maxSubArray(nums: IntArray): Int {
        var maxSoFar = nums[0]
        var currentMax = nums[0]
        for (i in 1 until nums.size) {
            currentMax = Math.max(nums[i], currentMax + nums[i])
            maxSoFar = Math.max(maxSoFar, currentMax)
        }
        return maxSoFar
    }
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func maxSubArray(_ nums: [Int]) -> Int {
        var maxSoFar = nums[0]
        var currentMax = nums[0]
        for i in 1..<nums.count {
            currentMax = max(nums[i], currentMax + nums[i])
            maxSoFar = max(maxSoFar, currentMax)
        }
        return maxSoFar
    }
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn max_sub_array(nums: Vec<i32>) -> i32 {
        let mut max_so_far = nums[0];
        let mut current_max = nums[0];
        for i in 1..nums.len() {
            current_max = std::cmp::max(nums[i], current_max + nums[i]);
            max_so_far = std::cmp::max(max_so_far, current_max);
        }
        max_so_far
    }
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} nums
# @return {Integer}
def max_sub_array(nums)
  max_so_far = nums[0]
  current_max = nums[0]
  (1...nums.length).each do |i|
    current_max = [nums[i], current_max + nums[i]].max
    max_so_far = [max_so_far, current_max].max
  end
  max_so_far
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
    function maxSubArray($nums) {
        $maxSoFar = $nums[0];
        $currentMax = $nums[0];
        $count = count($nums);
        for ($i = 1; $i < $count; $i++) {
            $currentMax = max($nums[$i], $currentMax + $nums[$i]);
            $maxSoFar = max($maxSoFar, $currentMax);
        }
        return $maxSoFar;
    }
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
}

```

# dart

## Sweet Spot

```dart
class Solution {
  int maxSubArray(List<int> nums) {
    int maxSoFar = nums[0];
    int currentMax = nums[0];
    for (int i = 1; i < nums.length; i++) {
      currentMax = (nums[i] > currentMax + nums[i]) ? nums[i] : currentMax + nums[i];
      maxSoFar = (maxSoFar > currentMax) ? maxSoFar : currentMax;
    }
    return maxSoFar;
  }
  // Time Complexity: O(n)
  // Memory Complexity: O(1)
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def maxSubArray(nums: Array[Int]): Int = {
        var maxSoFar = nums(0)
        var currentMax = nums(0)
        var i = 1
        while (i < nums.length) {
            currentMax = Math.max(nums(i), currentMax + nums(i))
            maxSoFar = Math.max(maxSoFar, currentMax)
            i += 1
        }
        maxSoFar
    }
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec max_sub_array(nums :: [integer]) :: integer
  def max_sub_array([head | tail]) do
    solve(tail, head, head)
  end

  defp solve([], _current_max, max_so_far), do: max_so_far
  defp solve([h | t], current_max, max_so_far) do
    new_current = max(h, current_max + h)
    solve(t, new_current, max(max_so_far, new_current))
  end
  # Time Complexity: O(n)
  # Memory Complexity: O(n)
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec max_sub_array(Nums :: [integer()]) -> integer().
max_sub_array([Head | Tail]) ->
    solve(Tail, Head, Head).

solve([], _CurrentMax, MaxSoFar) ->
    MaxSoFar;
solve([H | T], CurrentMax, MaxSoFar) ->
    NewCurrent = erlang:max(H, CurrentMax + H),
    solve(T, NewCurrent, erlang:max(MaxSoFar, NewCurrent)).
% Time Complexity: O(n)
% Memory Complexity: O(n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (max-sub-array nums)
  (-> (listof exact-integer?) exact-integer?)
  (let loop ([rest (cdr nums)]
             [current-max (car nums)]
             [max-so-far (car nums)])
    (if (null? rest)
        max-so-far
        (let* ([h (car rest)]
               [next-current (max h (+ current-max h))])
          (loop (cdr rest) next-current (max max-so-far next-current))))))
; Time Complexity: O(n)
; Memory Complexity: O(n)

```