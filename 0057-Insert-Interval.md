# cpp

## Sweet Spot

```cpp
class Solution {
public:
    vector<vector<int>> insert(vector<vector<int>>& intervals, vector<int>& newInterval) {
        vector<vector<int>> result;
        int i = 0;
        int n = intervals.size();
        while (i < n && intervals[i][1] < newInterval[0]) {
            result.push_back(intervals[i]);
            i++;
        }
        while (i < n && intervals[i][0] <= newInterval[1]) {
            newInterval[0] = min(newInterval[0], intervals[i][0]);
            newInterval[1] = max(newInterval[1], intervals[i][1]);
            i++;
        }
        result.push_back(newInterval);
        while (i < n) {
            result.push_back(intervals[i]);
            i++;
        }
        return result;
    }
};
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# java

## Sweet Spot

```java
class Solution {
    public int[][] insert(int[][] intervals, int[] newInterval) {
        List<int[]> result = new ArrayList<>();
        int i = 0;
        int n = intervals.length;
        while (i < n && intervals[i][1] < newInterval[0]) {
            result.add(intervals[i++]);
        }
        while (i < n && intervals[i][0] <= newInterval[1]) {
            newInterval[0] = Math.min(newInterval[0], intervals[i][0]);
            newInterval[1] = Math.max(newInterval[1], intervals[i][1]);
            i++;
        }
        result.add(newInterval);
        while (i < n) {
            result.add(intervals[i++]);
        }
        return result.toArray(new int[result.size()][]);
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def insert(self, intervals: List[List[int]], newInterval: List[int]) -> List[List[int]]:
        res = []
        i = 0
        n = len(intervals)
        while i < n and intervals[i][1] < newInterval[0]:
            res.append(intervals[i])
            i += 1
        while i < n and intervals[i][0] <= newInterval[1]:
            newInterval[0] = min(newInterval[0], intervals[i][0])
            newInterval[1] = max(newInterval[1], intervals[i][1])
            i += 1
        res.append(newInterval)
        res.extend(intervals[i:])
        return res
# Time Complexity: O(n)
# Memory Complexity: O(n)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def insert(self, intervals, newInterval):
        """
        :type intervals: List[List[int]]
        :type newInterval: List[int]
        :rtype: List[List[int]]
        """
        res = []
        i = 0
        n = len(intervals)
        while i < n and intervals[i][1] < newInterval[0]:
            res.append(intervals[i])
            i += 1
        while i < n and intervals[i][0] <= newInterval[1]:
            newInterval[0] = min(newInterval[0], intervals[i][0])
            newInterval[1] = max(newInterval[1], intervals[i][1])
            i += 1
        res.append(newInterval)
        while i < n:
            res.append(intervals[i])
            i += 1
        return res
# Time Complexity: O(n)
# Memory Complexity: O(n)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[][]} intervals
 * @param {number[]} newInterval
 * @return {number[][]}
 */
var insert = function(intervals, newInterval) {
    const result = [];
    let i = 0;
    while (i < intervals.length && intervals[i][1] < newInterval[0]) {
        result.push(intervals[i]);
        i++;
    }
    while (i < intervals.length && intervals[i][0] <= newInterval[1]) {
        newInterval[0] = Math.min(newInterval[0], intervals[i][0]);
        newInterval[1] = Math.max(newInterval[1], intervals[i][1]);
        i++;
    }
    result.push(newInterval);
    while (i < intervals.length) {
        result.push(intervals[i]);
        i++;
    }
    return result;
};
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# Typescript

## Sweet Spot

```typescript
function insert(intervals: number[][], newInterval: number[]): number[][] {
    const result: number[][] = [];
    let i = 0;
    while (i < intervals.length && intervals[i][1] < newInterval[0]) {
        result.push(intervals[i]);
        i++;
    }
    while (i < intervals.length && intervals[i][0] <= newInterval[1]) {
        newInterval[0] = Math.min(newInterval[0], intervals[i][0]);
        newInterval[1] = Math.max(newInterval[1], intervals[i][1]);
        i++;
    }
    result.push(newInterval);
    while (i < intervals.length) {
        result.push(intervals[i]);
        i++;
    }
    return result;
};
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int[][] Insert(int[][] intervals, int[] newInterval) {
        List<int[]> result = new List<int[]>();
        int i = 0;
        int n = intervals.Length;
        while (i < n && intervals[i][1] < newInterval[0]) {
            result.Add(intervals[i++]);
        }
        while (i < n && intervals[i][0] <= newInterval[1]) {
            newInterval[0] = Math.Min(newInterval[0], intervals[i][0]);
            newInterval[1] = Math.Max(newInterval[1], intervals[i][1]);
            i++;
        }
        result.Add(newInterval);
        while (i < n) {
            result.Add(intervals[i++]);
        }
        return result.ToArray();
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# C

## Sweet Spot

```c
/**
 * Return an array of arrays of size *returnSize.
 * The sizes of the arrays are returned as *returnColumnSizes array.
 * Note: Both returned array and *columnSizes array must be malloced, assume caller calls free().
 */
int** insert(int** intervals, int intervalsSize, int* intervalsColSize, int* newInterval, int newIntervalSize, int* returnSize, int** returnColumnSizes) {
    int** res = (int**)malloc((intervalsSize + 1) * sizeof(int*));
    *returnColumnSizes = (int*)malloc((intervalsSize + 1) * sizeof(int));
    int i = 0, count = 0;
    while (i < intervalsSize && intervals[i][1] < newInterval[0]) {
        res[count] = (int*)malloc(2 * sizeof(int));
        res[count][0] = intervals[i][0];
        res[count][1] = intervals[i][1];
        (*returnColumnSizes)[count] = 2;
        count++;
        i++;
    }
    while (i < intervalsSize && intervals[i][0] <= newInterval[1]) {
        if (intervals[i][0] < newInterval[0]) newInterval[0] = intervals[i][0];
        if (intervals[i][1] > newInterval[1]) newInterval[1] = intervals[i][1];
        i++;
    }
    res[count] = (int*)malloc(2 * sizeof(int));
    res[count][0] = newInterval[0];
    res[count][1] = newInterval[1];
    (*returnColumnSizes)[count] = 2;
    count++;
    while (i < intervalsSize) {
        res[count] = (int*)malloc(2 * sizeof(int));
        res[count][0] = intervals[i][0];
        res[count][1] = intervals[i][1];
        (*returnColumnSizes)[count] = 2;
        count++;
        i++;
    }
    *returnSize = count;
    return res;
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# Go

## Sweet Spot

```go
func insert(intervals [][]int, newInterval []int) [][]int {
    res := make([][]int, 0)
    i := 0
    n := len(intervals)
    for i < n && intervals[i][1] < newInterval[0] {
        res = append(res, intervals[i])
        i++
    }
    for i < n && intervals[i][0] <= newInterval[1] {
        if intervals[i][0] < newInterval[0] {
            newInterval[0] = intervals[i][0]
        }
        if intervals[i][1] > newInterval[1] {
            newInterval[1] = intervals[i][1]
        }
        i++
    }
    res = append(res, newInterval)
    for i < n {
        res = append(res, intervals[i])
        i++
    }
    return res
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun insert(intervals: Array<IntArray>, newInterval: IntArray): Array<IntArray> {
        val result = mutableListOf<IntArray>()
        var i = 0
        val n = intervals.size
        var start = newInterval[0]
        var end = newInterval[1]
        while (i < n && intervals[i][1] < start) {
            result.add(intervals[i++])
        }
        while (i < n && intervals[i][0] <= end) {
            start = Math.min(start, intervals[i][0])
            end = Math.max(end, intervals[i][1])
            i++
        }
        result.add(intArrayOf(start, end))
        while (i < n) {
            result.add(intervals[i++])
        }
        return result.toTypedArray()
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# swift

## Sweet Spot

```swift
class Solution {
    func insert(_ intervals: [[Int]], _ newInterval: [Int]) -> [[Int]] {
        var result = [[Int]]()
        var i = 0
        let n = intervals.count
        var newStart = newInterval[0]
        var newEnd = newInterval[1]
        while i < n && intervals[i][1] < newStart {
            result.append(intervals[i])
            i += 1
        }
        while i < n && intervals[i][0] <= newEnd {
            newStart = min(newStart, intervals[i][0])
            newEnd = max(newEnd, intervals[i][1])
            i += 1
        }
        result.append([newStart, newEnd])
        while i < n {
            result.append(intervals[i])
            i += 1
        }
        return result
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn insert(intervals: Vec<Vec<i32>>, new_interval: Vec<i32>) -> Vec<Vec<i32>> {
        let mut result = Vec::new();
        let mut i = 0;
        let n = intervals.len();
        let mut start = new_interval[0];
        let mut end = new_interval[1];
        while i < n && intervals[i][1] < start {
            result.push(intervals[i].clone());
            i += 1;
        }
        while i < n && intervals[i][0] <= end {
            start = std::cmp::min(start, intervals[i][0]);
            end = std::cmp::max(end, intervals[i][1]);
            i += 1;
        }
        result.push(vec![start, end]);
        while i < n {
            result.push(intervals[i].clone());
            i += 1;
        }
        result
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[][]} intervals
# @param {Integer[]} new_interval
# @return {Integer[][]}
def insert(intervals, new_interval)
    res = []
    i = 0
    n = intervals.length
    while i < n && intervals[i][1] < new_interval[0]
        res << intervals[i]
        i += 1
    end
    while i < n && intervals[i][0] <= new_interval[1]
        new_interval[0] = [new_interval[0], intervals[i][0]].min
        new_interval[1] = [new_interval[1], intervals[i][1]].max
        i += 1
    end
    res << new_interval
    while i < n
        res << intervals[i]
        i += 1
    end
    res
end
# Time Complexity: O(n)
# Memory Complexity: O(n)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[][] $intervals
     * @param Integer[] $newInterval
     * @return Integer[][]
     */
    function insert($intervals, $newInterval) {
        $result = [];
        $i = 0;
        $n = count($intervals);
        while ($i < $n && $intervals[$i][1] < $newInterval[0]) {
            $result[] = $intervals[$i++];
        }
        while ($i < $n && $intervals[$i][0] <= $newInterval[1]) {
            $newInterval[0] = min($newInterval[0], $intervals[$i][0]);
            $newInterval[1] = max($newInterval[1], $intervals[$i][1]);
            $i++;
        }
        $result[] = $newInterval;
        while ($i < $n) {
            $result[] = $intervals[$i++];
        }
        return $result;
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# dart

## Sweet Spot

```dart
class Solution {
  List<List<int>> insert(List<List<int>> intervals, List<int> newInterval) {
    List<List<int>> result = [];
    int i = 0;
    int n = intervals.length;
    while (i < n && intervals[i][1] < newInterval[0]) {
      result.add(intervals[i++]);
    }
    while (i < n && intervals[i][0] <= newInterval[1]) {
      newInterval[0] = newInterval[0] < intervals[i][0] ? newInterval[0] : intervals[i][0];
      newInterval[1] = newInterval[1] > intervals[i][1] ? newInterval[1] : intervals[i][1];
      i++;
    }
    result.add(newInterval);
    while (i < n) {
      result.add(intervals[i++]);
    }
    return result;
  }
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def insert(intervals: Array[Array[Int]], newInterval: Array[Int]): Array[Array[Int]] = {
        val result = scala.collection.mutable.ArrayBuffer[Array[Int]]()
        var i = 0
        val n = intervals.length
        var start = newInterval(0)
        var end = newInterval(1)
        while (i < n && intervals(i)(1) < start) {
            result += intervals(i)
            i += 1
        }
        while (i < n && intervals(i)(0) <= end) {
            start = Math.min(start, intervals(i)(0))
            end = Math.max(end, intervals(i)(1))
            i += 1
        }
        result += Array(start, end)
        while (i < n) {
            result += intervals(i)
            i += 1
        }
        result.toArray
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec insert(intervals :: [[integer]], new_interval :: [integer]) :: [[integer]]
  def insert(intervals, new_interval) do
    do_insert(intervals, new_interval, [])
  end

  defp do_insert([], [s, e], acc), do: Enum.reverse([[s, e] | acc])
  defp do_insert([[s_i, e_i] | rest] = intervals, [s, e], acc) do
    cond do
      e_i < s -> do_insert(rest, [s, e], [[s_i, e_i] | acc])
      s_i > e -> Enum.reverse([[s, e] | acc]) ++ intervals
      true -> do_insert(rest, [min(s, s_i), max(e, e_i)], acc)
    end
  end
end
# Time Complexity: O(n)
# Memory Complexity: O(n)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec insert(Intervals :: [[integer()]], NewInterval :: [integer()]) -> [[integer()]].
insert(Intervals, NewInterval) ->
    do_insert(Intervals, NewInterval, []).

do_insert([], [S, E], Acc) ->
    lists:reverse([[S, E] | Acc]);
do_insert([[SI, EI] | Rest] = Intervals, [S, E], Acc) ->
    if
        EI < S -> do_insert(Rest, [S, E], [[SI, EI] | Acc]);
        SI > E -> lists:reverse([[S, E] | Acc]) ++ Intervals;
        true -> do_insert(Rest, [min(S, SI), max(E, EI)], Acc)
    end.
% Time Complexity: O(n)
% Memory Complexity: O(n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (insert intervals newInterval)
  (-> (listof (listof exact-integer?)) (listof exact-integer?) (listof (listof exact-integer?)))
  (let loop ([ints intervals] [curr-new newInterval] [acc '()])
    (cond
      [(null? ints) (reverse (cons curr-new acc))]
      [(< (second (car ints)) (first curr-new))
       (loop (cdr ints) curr-new (cons (car ints) acc))]
      [(> (first (car ints)) (second curr-new))
       (append (reverse acc) (cons curr-new ints))]
      [else
       (let ([merged (list (min (first (car ints)) (first curr-new))
                           (max (second (car ints)) (second curr-new)))])
         (loop (cdr ints) merged acc))])))
; Time Complexity: O(n)
; Memory Complexity: O(n)

```