# cpp

## Sweet Spot

```cpp
class Solution {
public:
    double findMedianSortedArrays(vector<int>& nums1, vector<int>& nums2) {
        if (nums1.size() > nums2.size()) return findMedianSortedArrays(nums2, nums1);
        int m = nums1.size();
        int n = nums2.size();
        int left = 0, right = m;
        while (left <= right) {
            int partitionX = (left + right) / 2;
            int partitionY = (m + n + 1) / 2 - partitionX;
            int maxLeftX = (partitionX == 0) ? INT_MIN : nums1[partitionX - 1];
            int minRightX = (partitionX == m) ? INT_MAX : nums1[partitionX];
            int maxLeftY = (partitionY == 0) ? INT_MIN : nums2[partitionY - 1];
            int minRightY = (partitionY == n) ? INT_MAX : nums2[partitionY];
            if (maxLeftX <= minRightY && maxLeftY <= minRightX) {
                if ((m + n) % 2 == 0) {
                    return (max(maxLeftX, maxLeftY) + min(minRightX, minRightY)) / 2.0;
                } else {
                    return max(maxLeftX, maxLeftY);
                }
            } else if (maxLeftX > minRightY) {
                right = partitionX - 1;
            } else {
                left = partitionX + 1;
            }
        }
        return 0.0;
    }
};
// Time Complexity: O(log(min(m, n)))
// Memory Complexity: O(1)

```

# java

## Sweet Spot

```java
class Solution {
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
        if (nums1.length > nums2.length) return findMedianSortedArrays(nums2, nums1);
        int m = nums1.length;
        int n = nums2.length;
        int left = 0, right = m;
        while (left <= right) {
            int partitionX = (left + right) / 2;
            int partitionY = (m + n + 1) / 2 - partitionX;
            int maxLeftX = (partitionX == 0) ? Integer.MIN_VALUE : nums1[partitionX - 1];
            int minRightX = (partitionX == m) ? Integer.MAX_VALUE : nums1[partitionX];
            int maxLeftY = (partitionY == 0) ? Integer.MIN_VALUE : nums2[partitionY - 1];
            int minRightY = (partitionY == n) ? Integer.MAX_VALUE : nums2[partitionY];
            if (maxLeftX <= minRightY && maxLeftY <= minRightX) {
                if ((m + n) % 2 == 0) {
                    return (Math.max(maxLeftX, maxLeftY) + Math.min(minRightX, minRightY)) / 2.0;
                } else {
                    return (double)Math.max(maxLeftX, maxLeftY);
                }
            } else if (maxLeftX > minRightY) {
                right = partitionX - 1;
            } else {
                left = partitionX + 1;
            }
        }
        return 0.0;
    }
}
// Time Complexity: O(log(min(m, n)))
// Memory Complexity: O(1)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:
        if len(nums1) > len(nums2):
            nums1, nums2 = nums2, nums1
        m, n = len(nums1), len(nums2)
        left, right = 0, m
        while left <= right:
            px = (left + right) // 2
            py = (m + n + 1) // 2 - px
            maxLeftX = float('-inf') if px == 0 else nums1[px - 1]
            minRightX = float('inf') if px == m else nums1[px]
            maxLeftY = float('-inf') if py == 0 else nums2[py - 1]
            minRightY = float('inf') if py == n else nums2[py]
            if maxLeftX <= minRightY and maxLeftY <= minRightX:
                if (m + n) % 2 == 0:
                    return (max(maxLeftX, maxLeftY) + min(minRightX, minRightY)) / 2.0
                else:
                    return float(max(maxLeftX, maxLeftY))
            elif maxLeftX > minRightY:
                right = px - 1
            else:
                left = px + 1
        return 0.0
# Time Complexity: O(log(min(m, n)))
# Memory Complexity: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def findMedianSortedArrays(self, nums1, nums2):
        """
        :type nums1: List[int]
        :type nums2: List[int]
        :rtype: float
        """
        if len(nums1) > len(nums2):
            nums1, nums2 = nums2, nums1
        m, n = len(nums1), len(nums2)
        left, right = 0, m
        while left <= right:
            px = (left + right) // 2
            py = (m + n + 1) // 2 - px
            maxLeftX = float('-inf') if px == 0 else nums1[px - 1]
            minRightX = float('inf') if px == m else nums1[px]
            maxLeftY = float('-inf') if py == 0 else nums2[py - 1]
            minRightY = float('inf') if py == n else nums2[py]
            if maxLeftX <= minRightY and maxLeftY <= minRightX:
                if (m + n) % 2 == 0:
                    return (max(maxLeftX, maxLeftY) + min(minRightX, minRightY)) / 2.0
                else:
                    return float(max(maxLeftX, maxLeftY))
            elif maxLeftX > minRightY:
                right = px - 1
            else:
                left = px + 1
        return 0.0
# Time Complexity: O(log(min(m, n)))
# Memory Complexity: O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} nums1
 * @param {number[]} nums2
 * @return {number}
 */
var findMedianSortedArrays = function(nums1, nums2) {
    if (nums1.length > nums2.length) [nums1, nums2] = [nums2, nums1];
    let m = nums1.length;
    let n = nums2.length;
    let left = 0, right = m;
    while (left <= right) {
        let px = Math.floor((left + right) / 2);
        let py = Math.floor((m + n + 1) / 2) - px;
        let maxLeftX = (px === 0) ? -Infinity : nums1[px - 1];
        let minRightX = (px === m) ? Infinity : nums1[px];
        let maxLeftY = (py === 0) ? -Infinity : nums2[py - 1];
        let minRightY = (py === n) ? Infinity : nums2[py];
        if (maxLeftX <= minRightY && maxLeftY <= minRightX) {
            if ((m + n) % 2 === 0) {
                return (Math.max(maxLeftX, maxLeftY) + Math.min(minRightX, minRightY)) / 2;
            } else {
                return Math.max(maxLeftX, maxLeftY);
            }
        } else if (maxLeftX > minRightY) {
            right = px - 1;
        } else {
            left = px + 1;
        }
    }
    return 0.0;
};
// Time Complexity: O(log(min(m, n)))
// Memory Complexity: O(1)

```

# Typescript

## Sweet Spot

```typescript
function findMedianSortedArrays(nums1: number[], nums2: number[]): number {
    if (nums1.length > nums2.length) return findMedianSortedArrays(nums2, nums1);
    let m = nums1.length;
    let n = nums2.length;
    let left = 0, right = m;
    while (left <= right) {
        let px = Math.floor((left + right) / 2);
        let py = Math.floor((m + n + 1) / 2) - px;
        let maxLeftX = (px === 0) ? -Infinity : nums1[px - 1];
        let minRightX = (px === m) ? Infinity : nums1[px];
        let maxLeftY = (py === 0) ? -Infinity : nums2[py - 1];
        let minRightY = (py === n) ? Infinity : nums2[py];
        if (maxLeftX <= minRightY && maxLeftY <= minRightX) {
            if ((m + n) % 2 === 0) {
                return (Math.max(maxLeftX, maxLeftY) + Math.min(minRightX, minRightY)) / 2;
            } else {
                return Math.max(maxLeftX, maxLeftY);
            }
        } else if (maxLeftX > minRightY) {
            right = px - 1;
        } else {
            left = px + 1;
        }
    }
    return 0.0;
};
// Time Complexity: O(log(min(m, n)))
// Memory Complexity: O(1)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public double FindMedianSortedArrays(int[] nums1, int[] nums2) {
        if (nums1.Length > nums2.Length) return FindMedianSortedArrays(nums2, nums1);
        int m = nums1.Length;
        int n = nums2.Length;
        int left = 0, right = m;
        while (left <= right) {
            int px = (left + right) / 2;
            int py = (m + n + 1) / 2 - px;
            int maxLeftX = (px == 0) ? int.MinValue : nums1[px - 1];
            int minRightX = (px == m) ? int.MaxValue : nums1[px];
            int maxLeftY = (py == 0) ? int.MinValue : nums2[py - 1];
            int minRightY = (py == n) ? int.MaxValue : nums2[py];
            if (maxLeftX <= minRightY && maxLeftY <= minRightX) {
                if ((m + n) % 2 == 0) {
                    return (Math.Max(maxLeftX, maxLeftY) + Math.Min(minRightX, minRightY)) / 2.0;
                } else {
                    return (double)Math.Max(maxLeftX, maxLeftY);
                }
            } else if (maxLeftX > minRightY) {
                right = px - 1;
            } else {
                left = px + 1;
            }
        }
        return 0.0;
    }
}
// Time Complexity: O(log(min(m, n)))
// Memory Complexity: O(1)

```

# C

## Sweet Spot

```c
double findMedianSortedArrays(int* nums1, int nums1Size, int* nums2, int nums2Size) {
    if (nums1Size > nums2Size) return findMedianSortedArrays(nums2, nums2Size, nums1, nums1Size);
    int m = nums1Size;
    int n = nums2Size;
    int left = 0, right = m;
    while (left <= right) {
        int px = (left + right) / 2;
        int py = (m + n + 1) / 2 - px;
        int maxLeftX = (px == 0) ? -2000000 : nums1[px - 1];
        int minRightX = (px == m) ? 2000000 : nums1[px];
        int maxLeftY = (py == 0) ? -2000000 : nums2[py - 1];
        int minRightY = (py == n) ? 2000000 : nums2[py];
        if (maxLeftX <= minRightY && maxLeftY <= minRightX) {
            if ((m + n) % 2 == 0) {
                int maxL = (maxLeftX > maxLeftY) ? maxLeftX : maxLeftY;
                int minR = (minRightX < minRightY) ? minRightX : minRightY;
                return (maxL + minR) / 2.0;
            } else {
                return (double)((maxLeftX > maxLeftY) ? maxLeftX : maxLeftY);
            }
        } else if (maxLeftX > minRightY) {
            right = px - 1;
        } else {
            left = px + 1;
        }
    }
    return 0.0;
}
// Time Complexity: O(log(min(m, n)))
// Memory Complexity: O(1)

```

# Go

## Sweet Spot

```go
func findMedianSortedArrays(nums1 []int, nums2 []int) float64 {
    if len(nums1) > len(nums2) {
        return findMedianSortedArrays(nums2, nums1)
    }
    m, n := len(nums1), len(nums2)
    left, right := 0, m
    for left <= right {
        px := (left + right) / 2
        py := (m + n + 1) / 2 - px
        var maxLeftX, minRightX, maxLeftY, minRightY int
        if px == 0 { maxLeftX = -1000001 } else { maxLeftX = nums1[px-1] }
        if px == m { minRightX = 1000001 } else { minRightX = nums1[px] }
        if py == 0 { maxLeftY = -1000001 } else { maxLeftY = nums2[py-1] }
        if py == n { minRightY = 1000001 } else { minRightY = nums2[py] }
        if maxLeftX <= minRightY && maxLeftY <= minRightX {
            if (m+n)%2 == 0 {
                return float64(max(maxLeftX, maxLeftY)+min(minRightX, minRightY)) / 2.0
            }
            return float64(max(maxLeftX, maxLeftY))
        } else if maxLeftX > minRightY {
            right = px - 1
        } else {
            left = px + 1
        }
    }
    return 0.0
}
func max(a, b int) int { if a > b { return a }; return b }
func min(a, b int) int { if a < b { return a }; return b }
// Time Complexity: O(log(min(m, n)))
// Memory Complexity: O(1)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun findMedianSortedArrays(nums1: IntArray, nums2: IntArray): Double {
        if (nums1.size > nums2.size) return findMedianSortedArrays(nums2, nums1)
        val m = nums1.size
        val n = nums2.size
        var left = 0
        var right = m
        while (left <= right) {
            val px = (left + right) / 2
            val py = (m + n + 1) / 2 - px
            val maxLeftX = if (px == 0) Int.MIN_VALUE else nums1[px - 1]
            val minRightX = if (px == m) Int.MAX_VALUE else nums1[px]
            val maxLeftY = if (py == 0) Int.MIN_VALUE else nums2[py - 1]
            val minRightY = if (py == n) Int.MAX_VALUE else nums2[py]
            if (maxLeftX <= minRightY && maxLeftY <= minRightX) {
                return if ((m + n) % 2 == 0) {
                    (Math.max(maxLeftX, maxLeftY) + Math.min(minRightX, minRightY)) / 2.0
                } else {
                    Math.max(maxLeftX, maxLeftY).toDouble()
                }
            } else if (maxLeftX > minRightY) {
                right = px - 1
            } else {
                left = px + 1
            }
        }
        return 0.0
    }
}
// Time Complexity: O(log(min(m, n)))
// Memory Complexity: O(1)

```

# swift

## Sweet Spot

```swift
class Solution {
    func findMedianSortedArrays(_ nums1: [Int], _ nums2: [Int]) -> Double {
        if nums1.count > nums2.count { return findMedianSortedArrays(nums2, nums1) }
        let m = nums1.count
        let n = nums2.count
        var left = 0
        var right = m
        while left <= right {
            let px = (left + right) / 2
            let py = (m + n + 1) / 2 - px
            let maxLeftX = (px == 0) ? Int.min : nums1[px - 1]
            let minRightX = (px == m) ? Int.max : nums1[px]
            let maxLeftY = (py == 0) ? Int.min : nums2[py - 1]
            let minRightY = (py == n) ? Int.max : nums2[py]
            if maxLeftX <= minRightY && maxLeftY <= minRightX {
                if (m + n) % 2 == 0 {
                    return Double(max(maxLeftX, maxLeftY) + min(minRightX, minRightY)) / 2.0
                } else {
                    return Double(max(maxLeftX, maxLeftY))
                }
            } else if maxLeftX > minRightY {
                right = px - 1
            } else {
                left = px + 1
            }
        }
        return 0.0
    }
}
// Time Complexity: O(log(min(m, n)))
// Memory Complexity: O(1)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn find_median_sorted_arrays(nums1: Vec<i32>, nums2: Vec<i32>) -> f64 {
        let (n1, n2) = if nums1.len() > nums2.len() { (&nums2, &nums1) } else { (&nums1, &nums2) };
        let m = n1.len();
        let n = n2.len();
        let mut left = 0;
        let mut right = m;
        while left <= right {
            let px = (left + right) / 2;
            let py = (m + n + 1) / 2 - px;
            let max_left_x = if px == 0 { i32::MIN } else { n1[px - 1] };
            let min_right_x = if px == m { i32::MAX } else { n1[px] };
            let max_left_y = if py == 0 { i32::MIN } else { n2[py - 1] };
            let min_right_y = if py == n { i32::MAX } else { n2[py] };
            if max_left_x <= min_right_y && max_left_y <= min_right_x {
                if (m + n) % 2 == 0 {
                    return (max_left_x.max(max_left_y) as f64 + min_right_x.min(min_right_y) as f64) / 2.0;
                } else {
                    return max_left_x.max(max_left_y) as f64;
                }
            } else if max_left_x > min_right_y {
                right = px - 1;
            } else {
                left = px + 1;
            }
        }
        0.0
    }
}
// Time Complexity: O(log(min(m, n)))
// Memory Complexity: O(1)

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} nums1
# @param {Integer[]} nums2
# @return {Float}
def find_median_sorted_arrays(nums1, nums2)
    nums1, nums2 = nums2, nums1 if nums1.length > nums2.length
    m, n = nums1.length, nums2.length
    left, right = 0, m
    while left <= right
        px = (left + right) / 2
        py = (m + n + 1) / 2 - px
        max_left_x = px == 0 ? -1.0/0 : nums1[px - 1]
        min_right_x = px == m ? 1.0/0 : nums1[px]
        max_left_y = py == 0 ? -1.0/0 : nums2[py - 1]
        min_right_y = py == n ? 1.0/0 : nums2[py]
        if max_left_x <= min_right_y && max_left_y <= min_right_x
            if (m + n).even?
                return ([max_left_x, max_left_y].max + [min_right_x, min_right_y].min) / 2.0
            else
                return [max_left_x, max_left_y].max.to_f
            end
        elsif max_left_x > min_right_y
            right = px - 1
        else
            left = px + 1
        end
    end
    0.0
end
# Time Complexity: O(log(min(m, n)))
# Memory Complexity: O(1)

```

# php

## Sweet Spot

```php
// Time Complexity : O(log(min(m, n)))
// O(1)

class Solution {
    /**
     * @param Integer[] $nums1
     * @param Integer[] $nums2
     * @return Float
     */
    function findMedianSortedArrays($nums1, $nums2) {
        if (count($nums1) > count($nums2)) return $this->findMedianSortedArrays($nums2, $nums1);
        
        $m = count($nums1);
        $n = count($nums2);
        $left = 0; 
        $right = $m;
        
        while ($left <= $right) {
            $px = floor(($left + $right) / 2);
            $py = floor(($m + $n + 1) / 2) - $px;
            
            $maxLeftX = ($px == 0) ? -INF : $nums1[$px - 1];
            $minRightX = ($px == $m) ? INF : $nums1[$px];
            
            $maxLeftY = ($py == 0) ? -INF : $nums2[$py - 1];
            $minRightY = ($py == $n) ? INF : $nums2[$py];
            
            if ($maxLeftX <= $minRightY && $maxLeftY <= $minRightX) {
                if (($m + $n) % 2 == 0) {
                    return (max($maxLeftX, $maxLeftY) + min($minRightX, $minRightY)) / 2.0;
                } else {
                    return (float)max($maxLeftX, $maxLeftY);
                }
            } elseif ($maxLeftX > $minRightY) {
                $right = $px - 1;
            } else {
                $left = $px + 1;
            }
        }
        
        return 0.0;
    }
}
```

# dart

## Sweet Spot

```dart
import 'dart:math';
class Solution {
  double findMedianSortedArrays(List<int> nums1, List<int> nums2) {
    if (nums1.length > nums2.length) return findMedianSortedArrays(nums2, nums1);
    int m = nums1.length;
    int n = nums2.length;
    int left = 0, right = m;
    while (left <= right) {
      int px = (left + right) ~/ 2;
      int py = (m + n + 1) ~/ 2 - px;
      num maxLeftX = (px == 0) ? -double.infinity : nums1[px - 1];
      num minRightX = (px == m) ? double.infinity : nums1[px];
      num maxLeftY = (py == 0) ? -double.infinity : nums2[py - 1];
      num minRightY = (py == n) ? double.infinity : nums2[py];
      if (maxLeftX <= minRightY && maxLeftY <= minRightX) {
        if ((m + n) % 2 == 0) {
          return (max(maxLeftX, maxLeftY) + min(minRightX, minRightY)) / 2.0;
        } else {
          return max(maxLeftX, maxLeftY).toDouble();
        }
      } else if (maxLeftX > minRightY) {
        right = px - 1;
      } else {
        left = px + 1;
      }
    }
    return 0.0;
  }
}
// Time Complexity: O(log(min(m, n)))
// Memory Complexity: O(1)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def findMedianSortedArrays(nums1: Array[Int], nums2: Array[Int]): Double = {
        if (nums1.length > nums2.length) return findMedianSortedArrays(nums2, nums1)
        val m = nums1.length
        val n = nums2.length
        var left = 0
        var right = m
        while (left <= right) {
            val px = (left + right) / 2
            val py = (m + n + 1) / 2 - px
            val maxLeftX = if (px == 0) Int.MinValue else nums1(px - 1)
            val minRightX = if (px == m) Int.MaxValue else nums1(px)
            val maxLeftY = if (py == 0) Int.MinValue else nums2(py - 1)
            val minRightY = if (py == n) Int.MaxValue else nums2(py)
            if (maxLeftX <= minRightY && maxLeftY <= minRightX) {
                if ((m + n) % 2 == 0) {
                    return (Math.max(maxLeftX, maxLeftY).toDouble + Math.min(minRightX, minRightY).toDouble) / 2.0
                } else {
                    return Math.max(maxLeftX, maxLeftY).toDouble
                }
            } else if (maxLeftX > minRightY) {
                right = px - 1
            } else {
                left = px + 1
            }
        }
        0.0
    }
}
// Time Complexity: O(log(min(m, n)))
// Memory Complexity: O(1)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec find_median_sorted_arrays(nums1 :: [integer], nums2 :: [integer]) :: float
  def find_median_sorted_arrays(nums1, nums2) do
    a = List.to_tuple(nums1)
    b = List.to_tuple(nums2)
    {a, b} = if tuple_size(a) > tuple_size(b), do: {b, a}, else: {a, b}
    m = tuple_size(a)
    n = tuple_size(b)
    binary_search(a, b, 0, m, m, n)
  end

  defp binary_search(a, b, left, right, m, n) do
    px = div(left + right, 2)
    py = div(m + n + 1, 2) - px
    max_lx = if px == 0, do: -1_000_001, else: elem(a, px - 1)
    min_rx = if px == m, do: 1_000_001, else: elem(a, px)
    max_ly = if py == 0, do: -1_000_001, else: elem(b, py - 1)
    min_ry = if py == n, do: 1_000_001, else: elem(b, py)
    cond do
      max_lx <= min_ry and max_ly <= min_rx ->
        if rem(m + n, 2) == 0 do
          (max(max_lx, max_ly) + min(min_rx, min_ry)) / 2.0
        else
          max(max_lx, max_ly) / 1.0
        end
      max_lx > min_ry -> binary_search(a, b, left, px - 1, m, n)
      true -> binary_search(a, b, px + 1, right, m, n)
    end
  end
end
# Time Complexity: O(log(min(m, n)))
# Memory Complexity: O(m + n)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec find_median_sorted_arrays(Nums1 :: [integer()], Nums2 :: [integer()]) -> float().
find_median_sorted_arrays(Nums1, Nums2) ->
    A = list_to_tuple(Nums1),
    B = list_to_tuple(Nums2),
    {T1, T2} = case tuple_size(A) > tuple_size(B) of
        true -> {B, A};
        false -> {A, B}
    end,
    search(T1, T2, 0, tuple_size(T1), tuple_size(T1), tuple_size(T2)).

search(A, B, Left, Right, M, N) ->
    PX = (Left + Right) div 2,
    PY = (M + N + 1) div 2 - PX,
    MaxLX = if PX == 0 -> -2000000; true -> element(PX, A) end,
    MinRX = if PX == M -> 2000000; true -> element(PX + 1, A) end,
    MaxLY = if PY == 0 -> -2000000; true -> element(PY, B) end,
    MinRY = if PY == N -> 2000000; true -> element(PY + 1, B) end,
    if MaxLX =< MinRY andalso MaxLY =< MinRX ->
        case (M + N) rem 2 of
            0 -> (max(MaxLX, MaxLY) + min(MinRX, MinRY)) / 2.0;
            1 -> float(max(MaxLX, MaxLY))
        end;
       MaxLX > MinRY -> search(A, B, Left, PX - 1, M, N);
       true -> search(A, B, PX + 1, Right, M, N)
    end.
% Time Complexity: O(log(min(m, n)))
% Memory Complexity: O(m + n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (find-median-sorted-arrays nums1 nums2)
  (-> (listof exact-integer?) (listof exact-integer?) flonum?)
  ;; Time Complexity: O(log(min(m, n)))
  ;; Memory Complexity: O(m + n)
  (let* ([v1 (list->vector nums1)]
         [v2 (list->vector nums2)]
         [m (vector-length v1)]
         [n (vector-length v2)])
    (if (> m n)
        (find-median-sorted-arrays nums2 nums1)
        (let loop ([left 0] [right m])
          (let* ([px (quotient (+ left right) 2)]
                 [py (- (quotient (+ m n 1) 2) px)]
                 [maxLX (if (= px 0) -inf.0 (exact->inexact (vector-ref v1 (- px 1))))]
                 [minRX (if (= px m) +inf.0 (exact->inexact (vector-ref v1 px)))]
                 [maxLY (if (= py 0) -inf.0 (exact->inexact (vector-ref v2 (- py 1))))]
                 [minRY (if (= py n) +inf.0 (exact->inexact (vector-ref v2 py)))])
            (cond
              [(and (<= maxLX minRY) (<= maxLY minRX))
               (if (= (remainder (+ m n) 2) 0)
                   (/ (+ (max maxLX maxLY) (min minRX minRY)) 2.0)
                   (max maxLX maxLY))]
              [(> maxLX minRY) 
               (loop left (- px 1))]
              [else 
               (loop (+ px 1) right)]))))))
```