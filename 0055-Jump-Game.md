# cpp

## Sweet Spot

```cpp
class Solution {
public:
    bool canJump(vector<int>& nums) {
        int reachable = 0;
        int n = nums.size();
        for (int i = 0; i < n; ++i) {
            if (i > reachable) return false;
            reachable = max(reachable, i + nums[i]);
            if (reachable >= n - 1) return true;
        }
        return true;
        // Time: O(n), Memory: O(1)
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public boolean canJump(int[] nums) {
        int reachable = 0;
        for (int i = 0; i < nums.length; i++) {
            if (i > reachable) return false;
            reachable = Math.max(reachable, i + nums[i]);
            if (reachable >= nums.length - 1) return true;
        }
        return true;
        // Time: O(n), Memory: O(1)
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def canJump(self, nums: List[int]) -> bool:
        reachable = 0
        for i, jump in enumerate(nums):
            if i > reachable:
                return False
            if i + jump > reachable:
                reachable = i + jump
            if reachable >= len(nums) - 1:
                return True
        return True
        # Time: O(n), Memory: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def canJump(self, nums):
        """
        :type nums: List[int]
        :rtype: bool
        """
        reachable = 0
        for i, jump in enumerate(nums):
            if i > reachable:
                return False
            reachable = max(reachable, i + jump)
            if reachable >= len(nums) - 1:
                return True
        return True
        # Time: O(n), Memory: O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} nums
 * @return {boolean}
 */
var canJump = function(nums) {
    let reachable = 0;
    for (let i = 0; i < nums.length; i++) {
        if (i > reachable) return false;
        reachable = Math.max(reachable, i + nums[i]);
        if (reachable >= nums.length - 1) return true;
    }
    return true;
    // Time: O(n), Memory: O(1)
};

```

# Typescript

## Sweet Spot

```typescript
function canJump(nums: number[]): boolean {
    let reachable = 0;
    for (let i = 0; i < nums.length; i++) {
        if (i > reachable) return false;
        reachable = Math.max(reachable, i + nums[i]);
        if (reachable >= nums.length - 1) return true;
    }
    return true;
    // Time: O(n), Memory: O(1)
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public bool CanJump(int[] nums) {
        int reachable = 0;
        for (int i = 0; i < nums.Length; i++) {
            if (i > reachable) return false;
            if (i + nums[i] > reachable) reachable = i + nums[i];
            if (reachable >= nums.Length - 1) return true;
        }
        return true;
        // Time: O(n), Memory: O(1)
    }
}

```

# C

## Sweet Spot

```c
bool canJump(int* nums, int numsSize) {
    int reachable = 0;
    for (int i = 0; i < numsSize; i++) {
        if (i > reachable) return false;
        int currentReach = i + nums[i];
        if (currentReach > reachable) reachable = currentReach;
        if (reachable >= numsSize - 1) return true;
    }
    return true;
    // Time: O(n), Memory: O(1)
}

```

# Go

## Sweet Spot

```go
func canJump(nums []int) bool {
    reachable := 0
    n := len(nums)
    for i, jump := range nums {
        if i > reachable {
            return false
        }
        if i + jump > reachable {
            reachable = i + jump
        }
        if reachable >= n - 1 {
            return true
        }
    }
    return true
    // Time: O(n), Memory: O(1)
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun canJump(nums: IntArray): Boolean {
        var reachable = 0
        for (i in nums.indices) {
            if (i > reachable) return false
            reachable = maxOf(reachable, i + nums[i])
            if (reachable >= nums.size - 1) return true
        }
        return true
        // Time: O(n), Memory: O(1)
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func canJump(_ nums: [Int]) -> Bool {
        var reachable = 0
        for (i, jump) in nums.enumerated() {
            if i > reachable {
                return false
            }
            reachable = max(reachable, i + jump)
            if reachable >= nums.count - 1 {
                return true
            }
        }
        return true
        // Time: O(n), Memory: O(1)
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn can_jump(nums: Vec<i32>) -> bool {
        let mut reachable = 0;
        let n = nums.len();
        for i in 0..n {
            if i > reachable {
                return false;
            }
            reachable = std::cmp::max(reachable, i + nums[i] as usize);
            if reachable >= n - 1 {
                return true;
            }
        }
        true
        // Time: O(n), Memory: O(1)
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} nums
# @return {Boolean}
def can_jump(nums)
    reachable = 0
    nums.each_with_index do |jump, i|
        return false if i > reachable
        reachable = [reachable, i + jump].max
        return true if reachable >= nums.length - 1
    end
    true
    # Time: O(n), Memory: O(1)
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[] $nums
     * @return Boolean
     */
    function canJump($nums) {
        $reachable = 0;
        $n = count($nums);
        for ($i = 0; $i < $n; $i++) {
            if ($i > $reachable) return false;
            $reachable = max($reachable, $i + $nums[$i]);
            if ($reachable >= $n - 1) return true;
        }
        return true;
        // Time: O(n), Memory: O(1)
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  bool canJump(List<int> nums) {
    int reachable = 0;
    for (int i = 0; i < nums.length; i++) {
      if (i > reachable) return false;
      int currentReach = i + nums[i];
      if (currentReach > reachable) reachable = currentReach;
      if (reachable >= nums.length - 1) return true;
    }
    return true;
    // Time: O(n), Memory: O(1)
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def canJump(nums: Array[Int]): Boolean = {
        var reachable = 0
        var i = 0
        val n = nums.length
        
        while (i < n) {
            if (i > reachable) return false
            reachable = math.max(reachable, i + nums(i))
            if (reachable >= n - 1) return true
            i += 1
        }
        
        true
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}
```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec can_jump(nums :: [integer]) :: boolean
  def can_jump(nums) do
    solve(nums, 0, 0)
  end

  defp solve([], _idx, _reach), do: true
  defp solve([h | t], idx, reach) do
    cond do
      idx > reach -> false
      reach >= idx + length(t) -> true
      true -> solve(t, idx + 1, max(reach, idx + h))
    end
  end
  # Time: O(n), Memory: O(n) due to recursion stack (O(1) in Tail Call Optimization)
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec can_jump(Nums :: [integer()]) -> boolean().
can_jump(Nums) ->
    can_jump(Nums, 0, 0, length(Nums)).

can_jump([], _Idx, _Reach, _N) ->
    true;
can_jump([H|T], Idx, Reach, N) ->
    if
        Idx > Reach -> false;
        Reach >= N - 1 -> true;
        true -> 
            NewReach = if H + Idx > Reach -> H + Idx; true -> Reach end,
            can_jump(T, Idx + 1, NewReach, N)
    end.
% Time: O(n), Memory: O(1) (Tail Recursive)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (can-jump nums)
  (-> (listof exact-integer?) boolean?)
  (let ([len (length nums)])
    (let loop ([lst nums] [idx 0] [reach 0])
      (cond
        [(>= reach (- len 1)) #t]
        [(null? lst) #t]
        [(> idx reach) #f]
        [else (loop (cdr lst) (+ idx 1) (max reach (+ idx (car lst))))])))
  ; Time: O(n), Memory: O(1) (Tail Recursive)
)

```