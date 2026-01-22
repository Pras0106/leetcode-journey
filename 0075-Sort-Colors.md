# cpp

## Sweet Spot

```cpp
class Solution {
public:
    void sortColors(vector<int>& nums) {
        int low = 0, mid = 0, high = nums.size() - 1;
        while (mid <= high) {
            if (nums[mid] == 0) {
                swap(nums[low++], nums[mid++]);
            } else if (nums[mid] == 1) {
                mid++;
            } else {
                swap(nums[mid], nums[high--]);
            }
        }
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public void sortColors(int[] nums) {
        int low = 0, mid = 0, high = nums.length - 1;
        while (mid <= high) {
            if (nums[mid] == 0) {
                int temp = nums[low];
                nums[low++] = nums[mid];
                nums[mid++] = temp;
            } else if (nums[mid] == 1) {
                mid++;
            } else {
                int temp = nums[high];
                nums[high--] = nums[mid];
                nums[mid] = temp;
            }
        }
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def sortColors(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        low, mid, high = 0, 0, len(nums) - 1
        while mid <= high:
            if nums[mid] == 0:
                nums[low], nums[mid] = nums[mid], nums[low]
                low += 1
                mid += 1
            elif nums[mid] == 1:
                mid += 1
            else:
                nums[mid], nums[high] = nums[high], nums[mid]
                high -= 1
        # Time Complexity: O(n)
        # Memory Complexity: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def sortColors(self, nums):
        """
        :type nums: List[int]
        :rtype: None Do not return anything, modify nums in-place instead.
        """
        low, mid, high = 0, 0, len(nums) - 1
        while mid <= high:
            if nums[mid] == 0:
                nums[low], nums[mid] = nums[mid], nums[low]
                low += 1
                mid += 1
            elif nums[mid] == 1:
                mid += 1
            else:
                nums[mid], nums[high] = nums[high], nums[mid]
                high -= 1
        # Time Complexity: O(n)
        # Memory Complexity: O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} nums
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var sortColors = function(nums) {
    let low = 0, mid = 0, high = nums.length - 1;
    while (mid <= high) {
        if (nums[mid] === 0) {
            [nums[low], nums[mid]] = [nums[mid], nums[low]];
            low++;
            mid++;
        } else if (nums[mid] === 1) {
            mid++;
        } else {
            [nums[mid], nums[high]] = [nums[high], nums[mid]];
            high--;
        }
    }
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
};

```

# Typescript

## Sweet Spot

```typescript
/**
 Do not return anything, modify nums in-place instead.
 */
function sortColors(nums: number[]): void {
    let low = 0, mid = 0, high = nums.length - 1;
    while (mid <= high) {
        if (nums[mid] === 0) {
            [nums[low], nums[mid]] = [nums[mid], nums[low]];
            low++;
            mid++;
        } else if (nums[mid] === 1) {
            mid++;
        } else {
            [nums[mid], nums[high]] = [nums[high], nums[mid]];
            high--;
        }
    }
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public void SortColors(int[] nums) {
        int low = 0, mid = 0, high = nums.Length - 1;
        while (mid <= high) {
            if (nums[mid] == 0) {
                int temp = nums[low];
                nums[low++] = nums[mid];
                nums[mid++] = temp;
            } else if (nums[mid] == 1) {
                mid++;
            } else {
                int temp = nums[high];
                nums[high--] = nums[mid];
                nums[mid] = temp;
            }
        }
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```

# C

## Sweet Spot

```c
void sortColors(int* nums, int numsSize) {
    int low = 0, mid = 0, high = numsSize - 1;
    while (mid <= high) {
        if (nums[mid] == 0) {
            int temp = nums[low];
            nums[low++] = nums[mid];
            nums[mid++] = temp;
        } else if (nums[mid] == 1) {
            mid++;
        } else {
            int temp = nums[high];
            nums[high--] = nums[mid];
            nums[mid] = temp;
        }
    }
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
}

```

# Go

## Sweet Spot

```go
func sortColors(nums []int) {
    low, mid, high := 0, 0, len(nums)-1
    for mid <= high {
        if nums[mid] == 0 {
            nums[low], nums[mid] = nums[mid], nums[low]
            low++
            mid++
        } else if nums[mid] == 1 {
            mid++
        } else {
            nums[mid], nums[high] = nums[high], nums[mid]
            high--
        }
    }
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun sortColors(nums: IntArray): Unit {
        var low = 0
        var mid = 0
        var high = nums.size - 1
        while (mid <= high) {
            if (nums[mid] == 0) {
                val temp = nums[low]
                nums[low++] = nums[mid]
                nums[mid++] = temp
            } else if (nums[mid] == 1) {
                mid++
            } else {
                val temp = nums[high]
                nums[high--] = nums[mid]
                nums[mid] = temp
            }
        }
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func sortColors(_ nums: inout [Int]) {
        var low = 0
        var mid = 0
        var high = nums.count - 1
        while mid <= high {
            if nums[mid] == 0 {
                nums.swapAt(low, mid)
                low += 1
                mid += 1
            } else if nums[mid] == 1 {
                mid += 1
            } else {
                nums.swapAt(mid, high)
                high -= 1
            }
        }
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn sort_colors(nums: &mut Vec<i32>) {
        if nums.is_empty() { return; }
        let mut low = 0;
        let mut mid = 0;
        let mut high = nums.len() as i32 - 1;
        while mid <= high {
            if nums[mid as usize] == 0 {
                nums.swap(low as usize, mid as usize);
                low += 1;
                mid += 1;
            } else if nums[mid as usize] == 1 {
                mid += 1;
            } else {
                nums.swap(mid as usize, high as usize);
                high -= 1;
            }
        }
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} nums
# @return {Void} Do not return anything, modify nums in-place instead.
def sort_colors(nums)
  low = 0
  mid = 0
  high = nums.length - 1
  while mid <= high
    if nums[mid] == 0
      nums[low], nums[mid] = nums[mid], nums[low]
      low += 1
      mid += 1
    elsif nums[mid] == 1
      mid += 1
    else
      nums[mid], nums[high] = nums[high], nums[mid]
      high -= 1
    end
  end
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
     * @return NULL
     */
    function sortColors(&$nums) {
        $low = 0;
        $mid = 0;
        $high = count($nums) - 1;
        while ($mid <= $high) {
            if ($nums[$mid] == 0) {
                $temp = $nums[$low];
                $nums[$low++] = $nums[$mid];
                $nums[$mid++] = $temp;
            } else if ($nums[$mid] == 1) {
                $mid++;
            } else {
                $temp = $nums[$high];
                $nums[$high--] = $nums[$mid];
                $nums[$mid] = $temp;
            }
        }
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  void sortColors(List<int> nums) {
    int low = 0;
    int mid = 0;
    int high = nums.length - 1;
    while (mid <= high) {
      if (nums[mid] == 0) {
        int temp = nums[low];
        nums[low++] = nums[mid];
        nums[mid++] = temp;
      } else if (nums[mid] == 1) {
        mid++;
      } else {
        int temp = nums[high];
        nums[high--] = nums[mid];
        nums[mid] = temp;
      }
    }
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def sortColors(nums: Array[Int]): Unit = {
        var low = 0
        var mid = 0
        var high = nums.length - 1
        while (mid <= high) {
            if (nums(mid) == 0) {
                val temp = nums(low)
                nums(low) = nums(mid)
                nums(mid) = temp
                low += 1
                mid += 1
            } else if (nums(mid) == 1) {
                mid += 1
            } else {
                val temp = nums(high)
                nums(high) = nums(mid)
                nums(mid) = temp
                high -= 1
            }
        }
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
    }
}

```