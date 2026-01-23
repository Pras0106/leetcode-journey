# C++

## Sweet Spot

```cpp
class Solution {
public:
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
        int i = m - 1;
        int j = n - 1;
        int k = m + n - 1;
        while (j >= 0) {
            if (i >= 0 && nums1[i] > nums2[j]) {
                nums1[k--] = nums1[i--];
            } else {
                nums1[k--] = nums2[j--];
            }
        }
        // Time O(m + n), Memory O(1)
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        int i = m - 1;
        int j = n - 1;
        int k = m + n - 1;
        while (j >= 0) {
            if (i >= 0 && nums1[i] > nums2[j]) {
                nums1[k--] = nums1[i--];
            } else {
                nums1[k--] = nums2[j--];
            }
        }
        // Time O(m + n), Memory O(1)
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """
        i, j, k = m - 1, n - 1, m + n - 1
        while j >= 0:
            if i >= 0 and nums1[i] > nums2[j]:
                nums1[k] = nums1[i]
                i -= 1
            else:
                nums1[k] = nums2[j]
                j -= 1
            k -= 1
        # Time O(m + n), Memory O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def merge(self, nums1, m, nums2, n):
        """
        :type nums1: List[int]
        :type m: int
        :type nums2: List[int]
        :type n: int
        :rtype: None Do not return anything, modify nums1 in-place instead.
        """
        i, j, k = m - 1, n - 1, m + n - 1
        while j >= 0:
            if i >= 0 and nums1[i] > nums2[j]:
                nums1[k] = nums1[i]
                i -= 1
            else:
                nums1[k] = nums2[j]
                j -= 1
            k -= 1
        # Time O(m + n), Memory O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} nums1
 * @param {number} m
 * @param {number[]} nums2
 * @param {number} n
 * @return {void} Do not return anything, modify nums1 in-place instead.
 */
var merge = function(nums1, m, nums2, n) {
    let i = m - 1;
    let j = n - 1;
    let k = m + n - 1;
    while (j >= 0) {
        if (i >= 0 && nums1[i] > nums2[j]) {
            nums1[k--] = nums1[i--];
        } else {
            nums1[k--] = nums2[j--];
        }
    }
    // Time O(m + n), Memory O(1)
};

```

# Typescript

## Sweet Spot

```typescript
/**
 Do not return anything, modify nums1 in-place instead.
 */
function merge(nums1: number[], m: number, nums2: number[], n: number): void {
    let i: number = m - 1;
    let j: number = n - 1;
    let k: number = m + n - 1;
    while (j >= 0) {
        if (i >= 0 && nums1[i] > nums2[j]) {
            nums1[k--] = nums1[i--];
        } else {
            nums1[k--] = nums2[j--];
        }
    }
    // Time O(m + n), Memory O(1)
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public void Merge(int[] nums1, int m, int[] nums2, int n) {
        int i = m - 1;
        int j = n - 1;
        int k = m + n - 1;
        while (j >= 0) {
            if (i >= 0 && nums1[i] > nums2[j]) {
                nums1[k--] = nums1[i--];
            } else {
                nums1[k--] = nums2[j--];
            }
        }
        // Time O(m + n), Memory O(1)
    }
}

```

# C

## Sweet Spot

```c
void merge(int* nums1, int nums1Size, int m, int* nums2, int nums2Size, int n) {
    int i = m - 1;
    int j = n - 1;
    int k = m + n - 1;
    while (j >= 0) {
        if (i >= 0 && nums1[i] > nums2[j]) {
            nums1[k--] = nums1[i--];
        } else {
            nums1[k--] = nums2[j--];
        }
    }
    // Time O(m + n), Memory O(1)
}

```

# Go

## Sweet Spot

```go
func merge(nums1 []int, m int, nums2 []int, n int)  {
    i := m - 1
    j := n - 1
    k := m + n - 1
    for j >= 0 {
        if i >= 0 && nums1[i] > nums2[j] {
            nums1[k] = nums1[i]
            i--
        } else {
            nums1[k] = nums2[j]
            j--
        }
        k--
    }
    // Time O(m + n), Memory O(1)
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun merge(nums1: IntArray, m: Int, nums2: IntArray, n: Int): Unit {
        var i = m - 1
        var j = n - 1
        var k = m + n - 1
        while (j >= 0) {
            if (i >= 0 && nums1[i] > nums2[j]) {
                nums1[k--] = nums1[i--]
            } else {
                nums1[k--] = nums2[j--]
            }
        }
        // Time O(m + n), Memory O(1)
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func merge(_ nums1: inout [Int], _ m: Int, _ nums2: [Int], _ n: Int) {
        var i = m - 1
        var j = n - 1
        var k = m + n - 1
        while j >= 0 {
            if i >= 0 && nums1[i] > nums2[j] {
                nums1[k] = nums1[i]
                i -= 1
            } else {
                nums1[k] = nums2[j]
                j -= 1
            }
            k -= 1
        }
        // Time O(m + n), Memory O(1)
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn merge(nums1: &mut Vec<i32>, m: i32, nums2: &mut Vec<i32>, n: i32) {
        let mut i = m - 1;
        let mut j = n - 1;
        let mut k = m + n - 1;
        while j >= 0 {
            if i >= 0 && nums1[i as usize] > nums2[j as usize] {
                nums1[k as usize] = nums1[i as usize];
                i -= 1;
            } else {
                nums1[k as usize] = nums2[j as usize];
                j -= 1;
            }
            k -= 1;
        }
        // Time O(m + n), Memory O(1)
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} nums1
# @param {Integer} m
# @param {Integer[]} nums2
# @param {Integer} n
# @return {Void} Do not return anything, modify nums1 in-place instead.
def merge(nums1, m, nums2, n)
    i = m - 1
    j = n - 1
    k = m + n - 1
    while j >= 0
        if i >= 0 && nums1[i] > nums2[j]
            nums1[k] = nums1[i]
            i -= 1
        else
            nums1[k] = nums2[j]
            j -= 1
        end
        k -= 1
    end
    # Time O(m + n), Memory O(1)
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[] $nums1
     * @param Integer $m
     * @param Integer[] $nums2
     * @param Integer $n
     * @return NULL
     */
    function merge(&$nums1, $m, $nums2, $n) {
        $i = $m - 1;
        $j = $n - 1;
        $k = $m + $n - 1;
        while ($j >= 0) {
            if ($i >= 0 && $nums1[$i] > $nums2[$j]) {
                $nums1[$k--] = $nums1[$i--];
            } else {
                $nums1[$k--] = $nums2[$j--];
            }
        }
        // Time O(m + n), Memory O(1)
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  void merge(List<int> nums1, int m, List<int> nums2, int n) {
    int i = m - 1;
    int j = n - 1;
    int k = m + n - 1;
    while (j >= 0) {
      if (i >= 0 && nums1[i] > nums2[j]) {
        nums1[k--] = nums1[i--];
      } else {
        nums1[k--] = nums2[j--];
      }
    }
    // Time O(m + n), Memory O(1)
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def merge(nums1: Array[Int], m: Int, nums2: Array[Int], n: Int): Unit = {
        var i = m - 1
        var j = n - 1
        var k = m + n - 1
        while (j >= 0) {
            if (i >= 0 && nums1(i) > nums2(j)) {
                nums1(k) = nums1(i)
                i -= 1
            } else {
                nums1(k) = nums2(j)
                j -= 1
            }
            k -= 1
        }
        // Time O(m + n), Memory O(1)
    }
}

```