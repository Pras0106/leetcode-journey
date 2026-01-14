# cpp

## Sweet Spot

```cpp
class Solution {
public:
    void nextPermutation(vector<int>& nums) {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        int n = nums.size();
        int i = n - 2;
        while (i >= 0 && nums[i] >= nums[i + 1]) {
            i--;
        }
        if (i >= 0) {
            int j = n - 1;
            while (nums[j] <= nums[i]) {
                j--;
            }
            swap(nums[i], nums[j]);
        }
        reverse(nums.begin() + i + 1, nums.end());
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public void nextPermutation(int[] nums) {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        int i = nums.length - 2;
        while (i >= 0 && nums[i] >= nums[i + 1]) {
            i--;
        }
        if (i >= 0) {
            int j = nums.length - 1;
            while (nums[j] <= nums[i]) {
                j--;
            }
            swap(nums, i, j);
        }
        reverse(nums, i + 1);
    }

    private void swap(int[] nums, int i, int j) {
        int temp = nums[i];
        nums[i] = nums[j];
        nums[j] = temp;
    }

    private void reverse(int[] nums, int start) {
        int i = start, j = nums.length - 1;
        while (i < j) {
            swap(nums, i, j);
            i++;
            j--;
        }
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def nextPermutation(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        # Time Complexity: O(n)
        # Memory Complexity: O(1)
        i = len(nums) - 2
        while i >= 0 and nums[i] >= nums[i + 1]:
            i -= 1
        if i >= 0:
            j = len(nums) - 1
            while nums[j] <= nums[i]:
                j -= 1
            nums[i], nums[j] = nums[j], nums[i]
        
        nums[i + 1:] = reversed(nums[i + 1:])

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def nextPermutation(self, nums):
        """
        :type nums: List[int]
        :rtype: None Do not return anything, modify nums in-place instead.
        """
        # Time Complexity: O(n)
        # Memory Complexity: O(1)
        i = len(nums) - 2
        while i >= 0 and nums[i] >= nums[i + 1]:
            i -= 1
        if i >= 0:
            j = len(nums) - 1
            while nums[j] <= nums[i]:
                j -= 1
            nums[i], nums[j] = nums[j], nums[i]
        
        left = i + 1
        right = len(nums) - 1
        while left < right:
            nums[left], nums[right] = nums[right], nums[left]
            left += 1
            right -= 1

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} nums
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var nextPermutation = function(nums) {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    let i = nums.length - 2;
    while (i >= 0 && nums[i] >= nums[i + 1]) {
        i--;
    }
    if (i >= 0) {
        let j = nums.length - 1;
        while (nums[j] <= nums[i]) {
            j--;
        }
        [nums[i], nums[j]] = [nums[j], nums[i]];
    }
    let start = i + 1;
    let end = nums.length - 1;
    while (start < end) {
        [nums[start], nums[end]] = [nums[end], nums[start]];
        start++;
        end--;
    }
};

```

# Typescript

## Sweet Spot

```typescript
/**
 Do not return anything, modify nums in-place instead.
 */
function nextPermutation(nums: number[]): void {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    let i: number = nums.length - 2;
    while (i >= 0 && nums[i] >= nums[i + 1]) {
        i--;
    }
    if (i >= 0) {
        let j: number = nums.length - 1;
        while (nums[j] <= nums[i]) {
            j--;
        }
        [nums[i], nums[j]] = [nums[j], nums[i]];
    }
    let start: number = i + 1;
    let end: number = nums.length - 1;
    while (start < end) {
        [nums[start], nums[end]] = [nums[end], nums[start]];
        start++;
        end--;
    }
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public void NextPermutation(int[] nums) {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        int i = nums.Length - 2;
        while (i >= 0 && nums[i] >= nums[i + 1]) {
            i--;
        }
        if (i >= 0) {
            int j = nums.Length - 1;
            while (nums[j] <= nums[i]) {
                j--;
            }
            int temp = nums[i];
            nums[i] = nums[j];
            nums[j] = temp;
        }
        int left = i + 1, right = nums.Length - 1;
        while (left < right) {
            int temp = nums[left];
            nums[left] = nums[right];
            nums[right] = temp;
            left++;
            right--;
        }
    }
}

```

# C

## Sweet Spot

```c
void nextPermutation(int* nums, int numsSize) {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    int i = numsSize - 2;
    while (i >= 0 && nums[i] >= nums[i + 1]) {
        i--;
    }
    if (i >= 0) {
        int j = numsSize - 1;
        while (nums[j] <= nums[i]) {
            j--;
        }
        int temp = nums[i];
        nums[i] = nums[j];
        nums[j] = temp;
    }
    int left = i + 1;
    int right = numsSize - 1;
    while (left < right) {
        int temp = nums[left];
        nums[left] = nums[right];
        nums[right] = temp;
        left++;
        right--;
    }
}

```

# Go

## Sweet Spot

```go
func nextPermutation(nums []int)  {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    i := len(nums) - 2
    for i >= 0 && nums[i] >= nums[i+1] {
        i--
    }
    if i >= 0 {
        j := len(nums) - 1
        for nums[j] <= nums[i] {
            j--
        }
        nums[i], nums[j] = nums[j], nums[i]
    }
    left, right := i+1, len(nums)-1
    for left < right {
        nums[left], nums[right] = nums[right], nums[left]
        left++
        right--
    }
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun nextPermutation(nums: IntArray): Unit {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        var i = nums.size - 2
        while (i >= 0 && nums[i] >= nums[i + 1]) {
            i--
        }
        if (i >= 0) {
            var j = nums.size - 1
            while (nums[j] <= nums[i]) {
                j--
            }
            swap(nums, i, j)
        }
        reverse(nums, i + 1)
    }

    private fun swap(nums: IntArray, i: Int, j: Int) {
        val temp = nums[i]
        nums[i] = nums[j]
        nums[j] = temp
    }

    private fun reverse(nums: IntArray, start: Int) {
        var i = start
        var j = nums.size - 1
        while (i < j) {
            swap(nums, i, j)
            i++
            j--
        }
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func nextPermutation(_ nums: inout [Int]) {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        var i = nums.count - 2
        while i >= 0 && nums[i] >= nums[i + 1] {
            i -= 1
        }
        if i >= 0 {
            var j = nums.count - 1
            while nums[j] <= nums[i] {
                j -= 1
            }
            nums.swapAt(i, j)
        }
        var left = i + 1
        var right = nums.count - 1
        while left < right {
            nums.swapAt(left, right)
            left += 1
            right -= 1
        }
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn next_permutation(nums: &mut Vec<i32>) {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        let n = nums.len();
        if n <= 1 { return; }
        let mut i = (n - 2) as i32;
        while i >= 0 && nums[i as usize] >= nums[(i + 1) as usize] {
            i -= 1;
        }
        if i >= 0 {
            let mut j = (n - 1) as i32;
            while nums[j as usize] <= nums[i as usize] {
                j -= 1;
            }
            nums.swap(i as usize, j as usize);
        }
        let mut left = (i + 1) as usize;
        let mut right = n - 1;
        while left < right {
            nums.swap(left, right);
            left += 1;
            right -= 1;
        }
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} nums
# @return {Void} Do not return anything, modify nums in-place instead.
def next_permutation(nums)
    # Time Complexity: O(n)
    # Memory Complexity: O(1)
    i = nums.length - 2
    while i >= 0 && nums[i] >= nums[i + 1]
        i -= 1
    end
    if i >= 0
        j = nums.length - 1
        while nums[j] <= nums[i]
            j -= 1
        end
        nums[i], nums[j] = nums[j], nums[i]
    end
    left = i + 1
    right = nums.length - 1
    while left < right
        nums[left], nums[right] = nums[right], nums[left]
        left += 1
        right -= 1
    end
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[] $nums
     * @return NULL
     */
    function nextPermutation(&$nums) {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        $n = count($nums);
        $i = $n - 2;
        while ($i >= 0 && $nums[$i] >= $nums[$i + 1]) {
            $i--;
        }
        if ($i >= 0) {
            $j = $n - 1;
            while ($nums[$j] <= $nums[$i]) {
                $j--;
            }
            $temp = $nums[$i];
            $nums[$i] = $nums[$j];
            $nums[$j] = $temp;
        }
        $left = $i + 1;
        $right = $n - 1;
        while ($left < $right) {
            $temp = $nums[$left];
            $nums[$left] = $nums[$right];
            $nums[$right] = $temp;
            $left++;
            $right--;
        }
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  void nextPermutation(List<int> nums) {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    int i = nums.length - 2;
    while (i >= 0 && nums[i] >= nums[i + 1]) {
      i--;
    }
    if (i >= 0) {
      int j = nums.length - 1;
      while (nums[j] <= nums[i]) {
        j--;
      }
      int temp = nums[i];
      nums[i] = nums[j];
      nums[j] = temp;
    }
    int left = i + 1;
    int right = nums.length - 1;
    while (left < right) {
      int temp = nums[left];
      nums[left] = nums[right];
      nums[right] = temp;
      left++;
      right--;
    }
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def nextPermutation(nums: Array[Int]): Unit = {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        var i = nums.length - 2
        while (i >= 0 && nums(i) >= nums(i + 1)) {
            i -= 1
        }
        if (i >= 0) {
            var j = nums.length - 1
            while (nums(j) <= nums(i)) {
                j -= 1
            }
            val temp = nums(i)
            nums(i) = nums(j)
            nums(j) = temp
        }
        var left = i + 1
        var right = nums.length - 1
        while (left < right) {
            val temp = nums(left)
            nums(left) = nums(right)
            nums(right) = temp
            left += 1
            right -= 1
        }
    }
}

```