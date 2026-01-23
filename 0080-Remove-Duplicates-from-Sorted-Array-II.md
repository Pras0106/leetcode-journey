# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        if (nums.size() <= 2) return nums.size();
        int k = 2;
        for (int i = 2; i < nums.size(); i++) {
            if (nums[i] != nums[k - 2]) {
                nums[k] = nums[i];
                k++;
            }
        }
        return k;
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        if (nums.length <= 2) return nums.length;
        int k = 2;
        for (int i = 2; i < nums.length; i++) {
            if (nums[i] != nums[k - 2]) {
                nums[k++] = nums[i];
            }
        }
        return k;
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        if len(nums) <= 2:
            return len(nums)
        k = 2
        for i in range(2, len(nums)):
            if nums[i] != nums[k - 2]:
                nums[k] = nums[i]
                k += 1
        return k
        # Time Complexity: O(n)
        # Memory Complexity: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def removeDuplicates(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        if len(nums) <= 2:
            return len(nums)
        k = 2
        for i in range(2, len(nums)):
            if nums[i] != nums[k - 2]:
                nums[k] = nums[i]
                k += 1
        return k
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
var removeDuplicates = function(nums) {
    if (nums.length <= 2) return nums.length;
    let k = 2;
    for (let i = 2; i < nums.length; i++) {
        if (nums[i] !== nums[k - 2]) {
            nums[k] = nums[i];
            k++;
        }
    }
    return k;
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
};

```

# Typescript

## Sweet Spot

```typescript
function removeDuplicates(nums: number[]): number {
    if (nums.length <= 2) return nums.length;
    let k: number = 2;
    for (let i: number = 2; i < nums.length; i++) {
        if (nums[i] !== nums[k - 2]) {
            nums[k] = nums[i];
            k++;
        }
    }
    return k;
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int RemoveDuplicates(int[] nums) {
        if (nums.Length <= 2) return nums.Length;
        int k = 2;
        for (int i = 2; i < nums.Length; i++) {
            if (nums[i] != nums[k - 2]) {
                nums[k] = nums[i];
                k++;
            }
        }
        return k;
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```

# C

## Sweet Spot

```c
int removeDuplicates(int* nums, int numsSize) {
    if (numsSize <= 2) return numsSize;
    int k = 2;
    for (int i = 2; i < numsSize; i++) {
        if (nums[i] != nums[k - 2]) {
            nums[k] = nums[i];
            k++;
        }
    }
    return k;
    /* Time Complexity: O(n) */
    /* Memory Complexity: O(1) */
}

```

# Go

## Sweet Spot

```go
func removeDuplicates(nums []int) int {
    if len(nums) <= 2 {
        return len(nums)
    }
    k := 2
    for i := 2; i < len(nums); i++ {
        if nums[i] != nums[k-2] {
            nums[k] = nums[i]
            k++
        }
    }
    return k
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun removeDuplicates(nums: IntArray): Int {
        if (nums.size <= 2) return nums.size
        var k = 2
        for (i in 2 until nums.size) {
            if (nums[i] != nums[k - 2]) {
                nums[k] = nums[i]
                k++
            }
        }
        return k
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func removeDuplicates(_ nums: inout [Int]) -> Int {
        if nums.count <= 2 { return nums.count }
        var k = 2
        for i in 2..<nums.count {
            if nums[i] != nums[k - 2] {
                nums[k] = nums[i]
                k += 1
            }
        }
        return k
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn remove_duplicates(nums: &mut Vec<i32>) -> i32 {
        if nums.len() <= 2 { return nums.len() as i32; }
        let mut k = 2;
        for i in 2..nums.len() {
            if nums[i] != nums[k - 2] {
                nums[k] = nums[i];
                k += 1;
            }
        }
        k as i32
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
def remove_duplicates(nums)
    return nums.length if nums.length <= 2
    k = 2
    (2...nums.length).each do |i|
        if nums[i] != nums[k - 2]
            nums[k] = nums[i]
            k += 1
        end
    end
    k
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
    function removeDuplicates(&$nums) {
        $count = count($nums);
        if ($count <= 2) return $count;
        $k = 2;
        for ($i = 2; $i < $count; $i++) {
            if ($nums[$i] != $nums[$k - 2]) {
                $nums[$k] = $nums[$i];
                $k++;
            }
        }
        return $k;
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  int removeDuplicates(List<int> nums) {
    if (nums.length <= 2) return nums.length;
    int k = 2;
    for (int i = 2; i < nums.length; i++) {
      if (nums[i] != nums[k - 2]) {
        nums[k] = nums[i];
        k++;
      }
    }
    return k;
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def removeDuplicates(nums: Array[Int]): Int = {
        if (nums.length <= 2) return nums.length
        var k = 2
        var i = 2
        while (i < nums.length) {
            if (nums(i) != nums(k - 2)) {
                nums(k) = nums(i)
                k += 1
            }
            i += 1
        }
        k
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```