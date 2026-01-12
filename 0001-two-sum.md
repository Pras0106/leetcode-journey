# cpp

## memory O(1)

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        for (int i = 0; i < nums.size(); ++i) {
            for (int j = i + 1; j < nums.size(); ++j) {
                if (nums[i] + nums[j] == target) return {i, j};
            }
        }
        return {};
    }
};
// Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> m;
        for (int i = 0; i < nums.size(); ++i) {
            if (m.count(target - nums[i])) return {m[target - nums[i]], i};
            m[nums[i]] = i;
        }
        return {};
    }
};
// Time: O(n), Memory: O(n)

```

# java

## memory O(1)

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        for (int i = 0; i < nums.length; i++) {
            for (int j = i + 1; j < nums.length; j++) {
                if (nums[i] + nums[j] == target) return new int[]{i, j};
            }
        }
        return new int[]{};
    }
}
// Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i];
            if (map.containsKey(complement)) return new int[]{map.get(complement), i};
            map.put(nums[i], i);
        }
        return new int[]{};
    }
}
// Time: O(n), Memory: O(n)

```

# python 3.14

## memory O(1)

```python 3.14
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                if nums[i] + nums[j] == target:
                    return [i, j]
# Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```python 3.14
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        prevMap = {}
        for i, n in enumerate(nums):
            diff = target - n
            if diff in prevMap:
                return [prevMap[diff], i]
            prevMap[n] = i
# Time: O(n), Memory: O(n)

```

# python 2.7.11

## memory O(1)

```python 2.7.11
class Solution(object):
    def twoSum(self, nums, target):
        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                if nums[i] + nums[j] == target:
                    return [i, j]
# Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```python 2.7.11
class Solution(object):
    def twoSum(self, nums, target):
        prevMap = {}
        for i, n in enumerate(nums):
            diff = target - n
            if diff in prevMap:
                return [prevMap[diff], i]
            prevMap[n] = i
# Time: O(n), Memory: O(n)

```

# JavaScript

## memory O(1)

```javascript
var twoSum = function(nums, target) {
    for (let i = 0; i < nums.length; i++) {
        for (let j = i + 1; j < nums.length; j++) {
            if (nums[i] + nums[j] === target) return [i, j];
        }
    }
};
// Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```javascript
var twoSum = function(nums, target) {
    const map = new Map();
    for (let i = 0; i < nums.length; i++) {
        const diff = target - nums[i];
        if (map.has(diff)) return [map.get(diff), i];
        map.set(nums[i], i);
    }
};
// Time: O(n), Memory: O(n)

```

# Typescript

## memory O(1)

```typescript
function twoSum(nums: number[], target: number): number[] {
    for (let i = 0; i < nums.length; i++) {
        for (let j = i + 1; j < nums.length; j++) {
            if (nums[i] + nums[j] === target) return [i, j];
        }
    }
    return [];
};
// Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```typescript
function twoSum(nums: number[], target: number): number[] {
    const map = new Map<number, number>();
    for (let i = 0; i < nums.length; i++) {
        const diff = target - nums[i];
        if (map.has(diff)) return [map.get(diff)!, i];
        map.set(nums[i], i);
    }
    return [];
};
// Time: O(n), Memory: O(n)

```

# C#

## memory O(1)

```c#
public class Solution {
    public int[] TwoSum(int[] nums, int target) {
        for (int i = 0; i < nums.Length; i++) {
            for (int j = i + 1; j < nums.Length; j++) {
                if (nums[i] + nums[j] == target) return new int[] { i, j };
            }
        }
        return new int[0];
    }
}
// Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```c#
public class Solution {
    public int[] TwoSum(int[] nums, int target) {
        Dictionary<int, int> map = new Dictionary<int, int>();
        for (int i = 0; i < nums.Length; i++) {
            int diff = target - nums[i];
            if (map.ContainsKey(diff)) return new int[] { map[diff], i };
            map[nums[i]] = i;
        }
        return new int[0];
    }
}
// Time: O(n), Memory: O(n)

```

# C

## memory O(1)

```c
int* twoSum(int* nums, int numsSize, int target, int* returnSize) {
    *returnSize = 2;
    int* res = (int*)malloc(2 * sizeof(int));
    for (int i = 0; i < numsSize; i++) {
        for (int j = i + 1; j < numsSize; j++) {
            if (nums[i] + nums[j] == target) {
                res[0] = i; res[1] = j;
                return res;
            }
        }
    }
    return res;
}
// Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```c
typedef struct {
    int key;
    int val;
    UT_hash_handle hh;
} map;
int* twoSum(int* nums, int numsSize, int target, int* returnSize) {
    map *hash = NULL, *item;
    *returnSize = 2;
    int* res = (int*)malloc(2 * sizeof(int));
    for (int i = 0; i < numsSize; i++) {
        int diff = target - nums[i];
        HASH_FIND_INT(hash, &diff, item);
        if (item) {
            res[0] = item->val; res[1] = i;
            return res;
        }
        item = malloc(sizeof(map));
        item->key = nums[i]; item->val = i;
        HASH_ADD_INT(hash, key, item);
    }
    return res;
}
// Time: O(n), Memory: O(n)

```

# Go

## memory O(1)

```go
func twoSum(nums []int, target int) []int {
    for i := 0; i < len(nums); i++ {
        for j := i + 1; j < len(nums); j++ {
            if nums[i] + nums[j] == target {
                return []int{i, j}
            }
        }
    }
    return nil
}
// Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```go
func twoSum(nums []int, target int) []int {
    m := make(map[int]int)
    for i, n := range nums {
        if idx, ok := m[target-n]; ok {
            return []int{idx, i}
        }
        m[n] = i
    }
    return nil
}
// Time: O(n), Memory: O(n)

```

# Kotlin

## memory O(1)

```kotlin
class Solution {
    fun twoSum(nums: IntArray, target: Int): IntArray {
        for (i in nums.indices) {
            for (j in i + 1 until nums.size) {
                if (nums[i] + nums[j] == target) return intArrayOf(i, j)
            }
        }
        return intArrayOf()
    }
}
// Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```kotlin
class Solution {
    fun twoSum(nums: IntArray, target: Int): IntArray {
        val map = mutableMapOf<Int, Int>()
        for (i in nums.indices) {
            val complement = target - nums[i]
            if (map.containsKey(complement)) return intArrayOf(map[complement]!!, i)
            map[nums[i]] = i
        }
        return intArrayOf()
    }
}
// Time: O(n), Memory: O(n)

```

# swift

## memory O(1)

```swift
class Solution {
    func twoSum(_ nums: [Int], _ target: Int) -> [Int] {
        for i in 0..<nums.count {
            for j in (i + 1)..<nums.count {
                if nums[i] + nums[j] == target { return [i, j] }
            }
        }
        return []
    }
}
// Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```swift
class Solution {
    func twoSum(_ nums: [Int], _ target: Int) -> [Int] {
        var map = [Int: Int]()
        for (i, n) in nums.enumerated() {
            if let idx = map[target - n] { return [idx, i] }
            map[n] = i
        }
        return []
    }
}
// Time: O(n), Memory: O(n)

```

# rust

## memory O(1)

```rust
impl Solution {
    pub fn two_sum(nums: Vec<i32>, target: i32) -> Vec<i32> {
        for i in 0..nums.len() {
            for j in i + 1..nums.len() {
                if nums[i] + nums[j] == target { return vec![i as i32, j as i32]; }
            }
        }
        vec![]
    }
}
// Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```rust
use std::collections::HashMap;
impl Solution {
    pub fn two_sum(nums: Vec<i32>, target: i32) -> Vec<i32> {
        let mut map = HashMap::new();
        for (i, &n) in nums.iter().enumerate() {
            if let Some(&idx) = map.get(&(target - n)) { return vec![idx as i32, i as i32]; }
            map.insert(n, i);
        }
        vec![]
    }
}
// Time: O(n), Memory: O(n)

```

# ruby

## memory O(1)

```ruby
def two_sum(nums, target)
    nums.each_with_index do |n1, i|
        nums.each_with_index do |n2, j|
            next if i >= j
            return [i, j] if n1 + n2 == target
        end
    end
end
# Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```ruby
def two_sum(nums, target)
    map = {}
    nums.each_with_index do |n, i|
        return [map[target - n], i] if map.key?(target - n)
        map[n] = i
    end
end
# Time: O(n), Memory: O(n)

```

# php

## memory O(1)

```php
class Solution {
    function twoSum($nums, $target) {
        for ($i = 0; $i < count($nums); $i++) {
            for ($j = $i + 1; $j < count($nums); $j++) {
                if ($nums[$i] + $nums[$j] == $target) return [$i, $j];
            }
        }
    }
}
// Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```php
class Solution {
    function twoSum($nums, $target) {
        $map = [];
        foreach ($nums as $i => $n) {
            $diff = $target - $n;
            if (isset($map[$diff])) return [$map[$diff], $i];
            $map[$n] = $i;
        }
    }
}
// Time: O(n), Memory: O(n)

```

# dart

## memory O(1)

```dart
class Solution {
  List<int> twoSum(List<int> nums, int target) {
    for (int i = 0; i < nums.length; i++) {
      for (int j = i + 1; j < nums.length; j++) {
        if (nums[i] + nums[j] == target) return [i, j];
      }
    }
    return [];
  }
}
// Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```dart
class Solution {
  List<int> twoSum(List<int> nums, int target) {
    Map<int, int> map = {};
    for (int i = 0; i < nums.length; i++) {
      int diff = target - nums[i];
      if (map.containsKey(diff)) return [map[diff]!, i];
      map[nums[i]] = i;
    }
    return [];
  }
}
// Time: O(n), Memory: O(n)

```

# scala

## memory O(1)

```scala
object Solution {
    def twoSum(nums: Array[Int], target: Int): Array[Int] = {
        for (i <- 0 until nums.length; j <- i + 1 until nums.length) {
            if (nums(i) + nums(j) == target) return Array(i, j)
        }
        Array()
    }
}
// Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```scala
object Solution {
    def twoSum(nums: Array[Int], target: Int): Array[Int] = {
        val map = scala.collection.mutable.Map[Int, Int]()
        for (i <- nums.indices) {
            val diff = target - nums(i)
            if (map.contains(diff)) return Array(map(diff), i)
            map(nums(i)) = i
        }
        Array()
    }
}
// Time: O(n), Memory: O(n)

```

# elixir

## memory O(1)

```elixir
defmodule Solution do
  def two_sum(nums, target) do
    n = Enum.count(nums)
    indexed = Enum.with_index(nums)
    for {v1, i} <- indexed, {v2, j} <- indexed, i < j, v1 + v2 == target, do: [i, j]
    |> List.first()
  end
end
# Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```elixir
defmodule Solution do
  def two_sum(nums, target) do
    nums
    |> Enum.with_index()
    |> Enum.reduce_while(%{}, fn {n, i}, map ->
      diff = target - n
      if Map.has_key?(map, diff), do: {:halt, [map[diff], i]}, else: {:cont, Map.put(map, n, i)}
    end)
  end
end
# Time: O(n), Memory: O(n)

```

# erlang

## memory O(1)

```erlang
two_sum(Nums, Target) ->
    Indexed = lists:zip(lists:seq(0, length(Nums)-1), Nums),
    [[I, J] || {I, V1} <- Indexed, {J, V2} <- Indexed, I < J, V1 + V2 == Target].
% Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```erlang
two_sum(Nums, Target) ->
    solve(Nums, Target, 0, #{}).
solve([H|T], Target, Index, Map) ->
    Diff = Target - H,
    case maps:find(Diff, Map) of
        {ok, PrevIndex} -> [PrevIndex, Index];
        error -> solve(T, Target, Index + 1, maps:put(H, Index, Map))
    end.
% Time: O(n), Memory: O(n)

```

# Racket

## memory O(1)

```racket
(define/contract (two-sum nums target)
  (-> (listof exact-integer?) exact-integer? (listof exact-integer?))
  (let ([len (length nums)] [arr (list->vector nums)])
    (for*/first ([i (in-range len)] [j (in-range (add1 i) len)] #:when (= (+ (vector-ref arr i) (vector-ref arr j)) target))
      (list i j))))
; Time: O(n^2), Memory: O(1)

```

## Sweet Spot

```racket
(define/contract (two-sum nums target)
  (-> (listof exact-integer?) exact-integer? (listof exact-integer?))
  (let loop ([ns nums] [i 0] [ht (hash)])
    (let* ([n (car ns)] [diff (- target n)])
      (if (hash-has-key? ht diff)
          (list (hash-ref ht diff) i)
          (loop (cdr ns) (add1 i) (hash-set ht n i))))))
; Time: O(n), Memory: O(n)

```