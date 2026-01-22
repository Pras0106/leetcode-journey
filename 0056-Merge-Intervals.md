# cpp

## Sweet Spot

```cpp
class Solution {
public:
    vector<vector<int>> merge(vector<vector<int>>& intervals) {
        if (intervals.empty()) return {};
        sort(intervals.begin(), intervals.end());
        vector<vector<int>> merged;
        merged.push_back(intervals[0]);
        for (int i = 1; i < intervals.size(); ++i) {
            if (intervals[i][0] <= merged.back()[1]) {
                merged.back()[1] = max(merged.back()[1], intervals[i][1]);
            } else {
                merged.push_back(intervals[i]);
            }
        }
        return merged;
    }
    // Time Complexity: O(n log n)
    // Memory Complexity: O(n)
};

```

# java

## Sweet Spot

```java
class Solution {
    public int[][] merge(int[][] intervals) {
        if (intervals.length <= 1) return intervals;
        Arrays.sort(intervals, (a, b) -> Integer.compare(a[0], b[0]));
        List<int[]> merged = new ArrayList<>();
        int[] current = intervals[0];
        merged.add(current);
        for (int[] interval : intervals) {
            if (interval[0] <= current[1]) {
                current[1] = Math.max(current[1], interval[1]);
            } else {
                current = interval;
                merged.add(current);
            }
        }
        return merged.toArray(new int[merged.size()][]);
    }
    // Time Complexity: O(n log n)
    // Memory Complexity: O(n)
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def merge(self, intervals: List[List[int]]) -> List[List[int]]:
        if not intervals:
            return []
        intervals.sort(key=lambda x: x[0])
        merged = [intervals[0]]
        for i in range(1, len(intervals)):
            if intervals[i][0] <= merged[-1][1]:
                merged[-1][1] = max(merged[-1][1], intervals[i][1])
            else:
                merged.append(intervals[i])
        return merged
# Time Complexity: O(n log n)
# Memory Complexity: O(n)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def merge(self, intervals):
        """
        :type intervals: List[List[int]]
        :rtype: List[List[int]]
        """
        if not intervals:
            return []
        intervals.sort(key=lambda x: x[0])
        merged = [intervals[0]]
        for i in range(1, len(intervals)):
            if intervals[i][0] <= merged[-1][1]:
                merged[-1][1] = max(merged[-1][1], intervals[i][1])
            else:
                merged.append(intervals[i])
        return merged
# Time Complexity: O(n log n)
# Memory Complexity: O(n)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[][]} intervals
 * @return {number[][]}
 */
var merge = function(intervals) {
    if (intervals.length <= 1) return intervals;
    intervals.sort((a, b) => a[0] - b[0]);
    const merged = [intervals[0]];
    for (let i = 1; i < intervals.length; i++) {
        const last = merged[merged.length - 1];
        if (intervals[i][0] <= last[1]) {
            last[1] = Math.max(last[1], intervals[i][1]);
        } else {
            merged.push(intervals[i]);
        }
    }
    return merged;
};
// Time Complexity: O(n log n)
// Memory Complexity: O(n)

```

# Typescript

## Sweet Spot

```typescript
function merge(intervals: number[][]): number[][] {
    if (intervals.length <= 1) return intervals;
    intervals.sort((a, b) => a[0] - b[0]);
    const merged: number[][] = [intervals[0]];
    for (let i = 1; i < intervals.length; i++) {
        const last = merged[merged.length - 1];
        if (intervals[i][0] <= last[1]) {
            last[1] = Math.max(last[1], intervals[i][1]);
        } else {
            merged.push(intervals[i]);
        }
    }
    return merged;
};
// Time Complexity: O(n log n)
// Memory Complexity: O(n)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int[][] Merge(int[][] intervals) {
        if (intervals.Length <= 1) return intervals;
        Array.Sort(intervals, (a, b) => a[0].CompareTo(b[0]));
        List<int[]> merged = new List<int[]>();
        int[] current = intervals[0];
        merged.Add(current);
        foreach (var interval in intervals) {
            if (interval[0] <= current[1]) {
                current[1] = Math.Max(current[1], interval[1]);
            } else {
                current = interval;
                merged.Add(current);
            }
        }
        return merged.ToArray();
    }
    // Time Complexity: O(n log n)
    // Memory Complexity: O(n)
}

```

# C

## Sweet Spot

```c
/**
 * Return an array of arrays of size *returnSize.
 * The sizes of the arrays are returned as *returnColumnSizes array.
 * Note: Both returned array and *columnSizes array must be malloced, assume caller calls free().
 */
int compare(const void* a, const void* b) {
    return (*(int**)a)[0] - (*(int**)b)[0];
}

int** merge(int** intervals, int intervalsSize, int* intervalsColSize, int* returnSize, int** returnColumnSizes) {
    if (intervalsSize == 0) {
        *returnSize = 0;
        return NULL;
    }
    qsort(intervals, intervalsSize, sizeof(int*), compare);
    int** merged = (int**)malloc(sizeof(int*) * intervalsSize);
    *returnColumnSizes = (int*)malloc(sizeof(int) * intervalsSize);
    int count = 0;
    merged[count] = (int*)malloc(sizeof(int) * 2);
    merged[count][0] = intervals[0][0];
    merged[count][1] = intervals[0][1];
    (*returnColumnSizes)[count] = 2;
    count++;
    for (int i = 1; i < intervalsSize; i++) {
        if (intervals[i][0] <= merged[count - 1][1]) {
            if (intervals[i][1] > merged[count - 1][1]) {
                merged[count - 1][1] = intervals[i][1];
            }
        } else {
            merged[count] = (int*)malloc(sizeof(int) * 2);
            merged[count][0] = intervals[i][0];
            merged[count][1] = intervals[i][1];
            (*returnColumnSizes)[count] = 2;
            count++;
        }
    }
    *returnSize = count;
    return merged;
}
/* Time Complexity: O(n log n) */
/* Memory Complexity: O(n) */

```

# Go

## Sweet Spot

```go
import "sort"

func merge(intervals [][]int) [][]int {
    if len(intervals) <= 1 {
        return intervals
    }
    sort.Slice(intervals, func(i, j int) bool {
        return intervals[i][0] < intervals[j][0]
    })
    merged := [][]int{intervals[0]}
    for i := 1; i < len(intervals); i++ {
        lastIdx := len(merged) - 1
        if intervals[i][0] <= merged[lastIdx][1] {
            if intervals[i][1] > merged[lastIdx][1] {
                merged[lastIdx][1] = intervals[i][1]
            }
        } else {
            merged = append(merged, intervals[i])
        }
    }
    return merged
}
// Time Complexity: O(n log n)
// Memory Complexity: O(n)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun merge(intervals: Array<IntArray>): Array<IntArray> {
        if (intervals.size <= 1) return intervals
        intervals.sortBy { it[0] }
        val merged = mutableListOf<IntArray>()
        var current = intervals[0]
        merged.add(current)
        for (interval in intervals) {
            if (interval[0] <= current[1]) {
                current[1] = maxOf(current[1], interval[1])
            } else {
                current = interval
                merged.add(current)
            }
        }
        return merged.toTypedArray()
    }
}
// Time Complexity: O(n log n)
// Memory Complexity: O(n)

```

# swift

## Sweet Spot

```swift
class Solution {
    func merge(_ intervals: [[Int]]) -> [[Int]] {
        guard intervals.count > 1 else { return intervals }
        let sortedIntervals = intervals.sorted { $0[0] < $1[0] }
        var merged = [sortedIntervals[0]]
        for i in 1..<sortedIntervals.count {
            var last = merged[merged.count - 1]
            if sortedIntervals[i][0] <= last[1] {
                last[1] = max(last[1], sortedIntervals[i][1])
                merged[merged.count - 1] = last
            } else {
                merged.append(sortedIntervals[i])
            }
        }
        return merged
    }
}
// Time Complexity: O(n log n)
// Memory Complexity: O(n)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn merge(mut intervals: Vec<Vec<i32>>) -> Vec<Vec<i32>> {
        if intervals.len() <= 1 {
            return intervals;
        }
        intervals.sort_unstable_by_key(|i| i[0]);
        let mut merged: Vec<Vec<i32>> = Vec::with_capacity(intervals.len());
        merged.push(intervals[0].clone());
        for i in 1..intervals.len() {
            let last_idx = merged.len() - 1;
            if intervals[i][0] <= merged[last_idx][1] {
                merged[last_idx][1] = std::cmp::max(merged[last_idx][1], intervals[i][1]);
            } else {
                merged.push(intervals[i].clone());
            }
        }
        merged
    }
}
// Time Complexity: O(n log n)
// Memory Complexity: O(n)

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[][]} intervals
# @return {Integer[][]}
def merge(intervals)
    return intervals if intervals.length <= 1
    intervals.sort_by! { |x| x[0] }
    merged = [intervals[0]]
    (1...intervals.length).each do |i|
        if intervals[i][0] <= merged.last[1]
            merged.last[1] = [merged.last[1], intervals[i][1]].max
        else
            merged << intervals[i]
        end
    end
    merged
end
# Time Complexity: O(n log n)
# Memory Complexity: O(n)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[][] $intervals
     * @return Integer[][]
     */
    function merge($intervals) {
        if (count($intervals) <= 1) return $intervals;
        usort($intervals, function($a, $b) {
            return $a[0] <=> $b[0];
        });
        $merged = [$intervals[0]];
        for ($i = 1; $i < count($intervals); $i++) {
            $lastIdx = count($merged) - 1;
            if ($intervals[$i][0] <= $merged[$lastIdx][1]) {
                $merged[$lastIdx][1] = max($merged[$lastIdx][1], $intervals[$i][1]);
            } else {
                $merged[] = $intervals[$i];
            }
        }
        return $merged;
    }
}
// Time Complexity: O(n log n)
// Memory Complexity: O(n)

```

# dart

## Sweet Spot

```dart
class Solution {
  List<List<int>> merge(List<List<int>> intervals) {
    if (intervals.length <= 1) return intervals;
    intervals.sort((a, b) => a[0].compareTo(b[0]));
    List<List<int>> merged = [intervals[0]];
    for (int i = 1; i < intervals.length; i++) {
      if (intervals[i][0] <= merged.last[1]) {
        merged.last[1] = intervals[i][1] > merged.last[1] ? intervals[i][1] : merged.last[1];
      } else {
        merged.add(intervals[i]);
      }
    }
    return merged;
  }
}
// Time Complexity: O(n log n)
// Memory Complexity: O(n)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def merge(intervals: Array[Array[Int]]): Array[Array[Int]] = {
        if (intervals.length <= 1) return intervals
        val sorted = intervals.sortBy(_(0))
        val merged = scala.collection.mutable.ArrayBuffer[Array[Int]]()
        var current = sorted(0)
        merged += current
        for (i <- 1 until sorted.length) {
            val next = sorted(i)
            if (next(0) <= current(1)) {
                current(1) = Math.max(current(1), next(1))
            } else {
                current = next
                merged += current
            }
        }
        merged.toArray
    }
}
// Time Complexity: O(n log n)
// Memory Complexity: O(n)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec merge(intervals :: [[integer]]) :: [[integer]]
  def merge([]), do: []
  def merge(intervals) do
    intervals
    |> Enum.sort_by(fn [s, _] -> s end)
    |> do_merge([])
  end

  defp do_merge([], acc), do: Enum.reverse(acc)
  defp do_merge([h | t], []), do: do_merge(t, [h])
  defp do_merge([[s2, e2] | t], [[s1, e1] | acc_t] = acc) do
    if s2 <= e1 do
      do_merge(t, [[s1, max(e1, e2)] | acc_t])
    else
      do_merge(t, [[s2, e2] | acc])
    end
  end
end
# Time Complexity: O(n log n)
# Memory Complexity: O(n)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec merge(Intervals :: [[integer()]]) -> [[integer()]].
merge([]) -> [];
merge(Intervals) ->
    Sorted = lists:sort(fun([A1, _], [B1, _]) -> A1 =< B1 end, Intervals),
    [H|T] = Sorted,
    do_merge(T, [H]).

do_merge([], Acc) -> lists:reverse(Acc);
do_merge([[S2, E2] | T], [[S1, E1] | AccT]) ->
    if
        S2 =< E1 -> do_merge(T, [[S1, max(E1, E2)] | AccT]);
        true -> do_merge(T, [[S2, E2], [S1, E1] | AccT])
    end.
% Time Complexity: O(n log n)
% Memory Complexity: O(n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (merge intervals)
  (-> (listof (listof exact-integer?)) (listof (listof exact-integer?)))
  (if (null? intervals)
      '()
      (let ([sorted (sort intervals < #:key car)])
        (reverse
         (foldl (lambda (curr acc)
                  (let ([last (car acc)])
                    (if (<= (car curr) (second last))
                        (cons (list (car last) (max (second last) (second curr))) (cdr acc))
                        (cons curr acc))))
                (list (car sorted))
                (cdr sorted))))))
; Time Complexity: O(n log n)
; Memory Complexity: O(n)

```