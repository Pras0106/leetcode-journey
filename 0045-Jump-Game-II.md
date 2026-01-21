# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int jump(vector<int>& nums) {
        int jumps = 0, current_end = 0, farthest = 0;
        for (int i = 0; i < (int)nums.size() - 1; ++i) {
            farthest = max(farthest, i + nums[i]);
            if (i == current_end) {
                jumps++;
                current_end = farthest;
            }
        }
        return jumps;
    }
};
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# java

## Sweet Spot

```java
class Solution {
    public int jump(int[] nums) {
        int jumps = 0, currentEnd = 0, farthest = 0;
        for (int i = 0; i < nums.length - 1; i++) {
            farthest = Math.max(farthest, i + nums[i]);
            if (i == currentEnd) {
                jumps++;
                currentEnd = farthest;
            }
        }
        return jumps;
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def jump(self, nums: List[int]) -> int:
        jumps = 0
        current_end = 0
        farthest = 0
        for i in range(len(nums) - 1):
            farthest = max(farthest, i + nums[i])
            if i == current_end:
                jumps += 1
                current_end = farthest
        return jumps
# Time Complexity: O(n)
# Memory Complexity: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def jump(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        jumps = 0
        current_end = 0
        farthest = 0
        for i in xrange(len(nums) - 1):
            farthest = max(farthest, i + nums[i])
            if i == current_end:
                jumps += 1
                current_end = farthest
        return jumps
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
var jump = function(nums) {
    let jumps = 0, currentEnd = 0, farthest = 0;
    for (let i = 0; i < nums.length - 1; i++) {
        farthest = Math.max(farthest, i + nums[i]);
        if (i === currentEnd) {
            jumps++;
            currentEnd = farthest;
        }
    }
    return jumps;
};
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# Typescript

## Sweet Spot

```typescript
function jump(nums: number[]): number {
    let jumps: number = 0;
    let currentEnd: number = 0;
    let farthest: number = 0;
    for (let i = 0; i < nums.length - 1; i++) {
        farthest = Math.max(farthest, i + nums[i]);
        if (i === currentEnd) {
            jumps++;
            currentEnd = farthest;
        }
    }
    return jumps;
};
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int Jump(int[] nums) {
        int jumps = 0, currentEnd = 0, farthest = 0;
        for (int i = 0; i < nums.Length - 1; i++) {
            farthest = Math.Max(farthest, i + nums[i]);
            if (i == currentEnd) {
                jumps++;
                currentEnd = farthest;
            }
        }
        return jumps;
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# C

## Sweet Spot

```c
int jump(int* nums, int numsSize) {
    int jumps = 0, currentEnd = 0, farthest = 0;
    for (int i = 0; i < numsSize - 1; i++) {
        int reach = i + nums[i];
        if (reach > farthest) farthest = reach;
        if (i == currentEnd) {
            jumps++;
            currentEnd = farthest;
        }
    }
    return jumps;
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# Go

## Sweet Spot

```go
func jump(nums []int) int {
    jumps := 0
    currentEnd := 0
    farthest := 0
    for i := 0; i < len(nums) - 1; i++ {
        if i + nums[i] > farthest {
            farthest = i + nums[i]
        }
        if i == currentEnd {
            jumps++
            currentEnd = farthest
        }
    }
    return jumps
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun jump(nums: IntArray): Int {
        var jumps = 0
        var currentEnd = 0
        var farthest = 0
        for (i in 0 until nums.size - 1) {
            farthest = maxOf(farthest, i + nums[i])
            if (i == currentEnd) {
                jumps++
                currentEnd = farthest
            }
        }
        return jumps
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# swift

## Sweet Spot

```swift
class Solution {
    func jump(_ nums: [Int]) -> Int {
        if nums.count <= 1 { return 0 }
        var jumps = 0
        var currentEnd = 0
        var farthest = 0
        for i in 0..<(nums.count - 1) {
            farthest = max(farthest, i + nums[i])
            if i == currentEnd {
                jumps += 1
                currentEnd = farthest
            }
        }
        return jumps
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn jump(nums: Vec<i32>) -> i32 {
        let mut jumps = 0;
        let mut current_end = 0;
        let mut farthest = 0;
        for i in 0..(nums.len() as i32 - 1) {
            farthest = std::cmp::max(farthest, i + nums[i as usize]);
            if i == current_end {
                jumps += 1;
                current_end = farthest;
            }
        }
        jumps
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} nums
# @return {Integer}
def jump(nums)
    jumps = 0
    current_end = 0
    farthest = 0
    (0...(nums.length - 1)).each do |i|
        farthest = [farthest, i + nums[i]].max
        if i == current_end
            jumps += 1
            current_end = farthest
        end
    end
    jumps
end
# Time Complexity: O(n)
# Memory Complexity: O(1)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[] $nums
     * @return Integer
     */
    function jump($nums) {
        $jumps = 0;
        $currentEnd = 0;
        $farthest = 0;
        $n = count($nums);
        for ($i = 0; $i < $n - 1; $i++) {
            $farthest = max($farthest, $i + $nums[$i]);
            if ($i == $currentEnd) {
                $jumps++;
                $currentEnd = $farthest;
            }
        }
        return $jumps;
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# dart

## Sweet Spot

```dart
import 'dart:math';

class Solution {
  int jump(List<int> nums) {
    int jumps = 0;
    int currentEnd = 0;
    int farthest = 0;
    for (int i = 0; i < nums.length - 1; i++) {
      farthest = max(farthest, i + nums[i]);
      if (i == currentEnd) {
        jumps++;
        currentEnd = farthest;
      }
    }
    return jumps;
  }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def jump(nums: Array[Int]): Int = {
        var jumps = 0
        var currentEnd = 0
        var farthest = 0
        
        for (i <- 0 until nums.length - 1) {
            farthest = Math.max(farthest, i + nums(i))
            
            if (i == currentEnd) {
                jumps += 1
                currentEnd = farthest
            }
        }
        
        jumps
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)
```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec jump(nums :: [integer]) :: integer
  def jump(nums) do
    arr = List.to_tuple(nums)
    n = tuple_size(arr)
    if n <= 1 do
      0
    else
      solve(arr, n, 0, 0, 0, 0)
    end
  end

  defp solve(_arr, n, i, jumps, current_end, farthest) when i == n - 1 do
    jumps
  end

  defp solve(arr, n, i, jumps, current_end, farthest) do
    new_farthest = max(farthest, i + elem(arr, i))
    if i == current_end do
      solve(arr, n, i + 1, jumps + 1, new_farthest, new_farthest)
    else
      solve(arr, n, i + 1, jumps, current_end, new_farthest)
    end
  end
end
# Time Complexity: O(n)
# Memory Complexity: O(n)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec jump(Nums :: [integer()]) -> integer().
jump(Nums) ->
    Arr = list_to_tuple(Nums),
    N = tuple_size(Arr),
    if
        N =< 1 -> 0;
        true -> solve(Arr, N, 0, 0, 0, 0)
    end.

solve(_Arr, N, I, Jumps, _CurrentEnd, _Farthest) when I >= N - 1 ->
    Jumps;
solve(Arr, N, I, Jumps, CurrentEnd, Farthest) ->
    NewFarthest = max(Farthest, I + element(I + 1, Arr)),
    if
        I == CurrentEnd ->
            solve(Arr, N, I + 1, Jumps + 1, NewFarthest, NewFarthest);
        true ->
            solve(Arr, N, I + 1, Jumps, CurrentEnd, NewFarthest)
    end.
% Time Complexity: O(n)
% Memory Complexity: O(n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (jump nums)
  (-> (listof exact-integer?) exact-integer?)
  (let* ([vec (list->vector nums)]
         [n (vector-length vec)])
    (if (<= n 1)
        0
        (let loop ([i 0]
                   [jumps 0]
                   [current-end 0]
                   [farthest 0])
          (if (= i (- n 1))
              jumps
              (let ([new-farthest (max farthest (+ i (vector-ref vec i)))])
                (if (= i current-end)
                    (loop (+ i 1) (+ jumps 1) new-farthest new-farthest)
                    (loop (+ i 1) jumps current-end new-farthest))))))))
; Time Complexity: O(n)
; Memory Complexity: O(n)

```