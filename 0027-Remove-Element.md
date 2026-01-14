# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int removeElement(vector<int>& nums, int val) {
        int k = 0;
        for (int i = 0; i < nums.size(); ++i) {
            if (nums[i] != val) {
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
    public int removeElement(int[] nums, int val) {
        int k = 0;
        for (int i = 0; i < nums.length; i++) {
            if (nums[i] != val) {
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

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def removeElement(self, nums: List[int], val: int) -> int:
        k = 0
        for i in range(len(nums)):
            if nums[i] != val:
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
    def removeElement(self, nums, val):
        """
        :type nums: List[int]
        :type val: int
        :rtype: int
        """
        k = 0
        for i in range(len(nums)):
            if nums[i] != val:
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
 * @param {number} val
 * @return {number}
 */
var removeElement = function(nums, val) {
    let k = 0;
    for (let i = 0; i < nums.length; i++) {
        if (nums[i] !== val) {
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
function removeElement(nums: number[], val: number): number {
    let k: number = 0;
    for (let i: number = 0; i < nums.length; i++) {
        if (nums[i] !== val) {
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
    public int RemoveElement(int[] nums, int val) {
        int k = 0;
        for (int i = 0; i < nums.Length; i++) {
            if (nums[i] != val) {
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
int removeElement(int* nums, int numsSize, int val) {
    int k = 0;
    for (int i = 0; i < numsSize; i++) {
        if (nums[i] != val) {
            nums[k] = nums[i];
            k++;
        }
    }
    return k;
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
}

```

# Go

## Sweet Spot

```go
func removeElement(nums []int, val int) int {
    k := 0
    for i := 0; i < len(nums); i++ {
        if nums[i] != val {
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
    fun removeElement(nums: IntArray, `val`: Int): Int {
        var k = 0
        for (i in nums.indices) {
            if (nums[i] != `val`) {
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
    func removeElement(_ nums: inout [Int], _ val: Int) -> Int {
        var k = 0
        for i in 0..<nums.count {
            if nums[i] != val {
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
    pub fn remove_element(nums: &mut Vec<i32>, val: i32) -> i32 {
        let mut k = 0;
        for i in 0..nums.len() {
            if nums[i] != val {
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
# @param {Integer} val
# @return {Integer}
def remove_element(nums, val)
    k = 0
    nums.each_with_index do |num, i|
        if num != val
            nums[k] = num
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
     * @param Integer $val
     * @return Integer
     */
    function removeElement(&$nums, $val) {
        $k = 0;
        for ($i = 0; $i < count($nums); $i++) {
            if ($nums[$i] != $val) {
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
  int removeElement(List<int> nums, int val) {
    int k = 0;
    for (int i = 0; i < nums.length; i++) {
      if (nums[i] != val) {
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
    def removeElement(nums: Array[Int], `val`: Int): Int = {
        var k = 0
        var i = 0
        while (i < nums.length) {
            if (nums(i) != `val`) {
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