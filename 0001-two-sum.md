# README

# cpp

## memory O(1)

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        // Time: O(n^2), Memory: O(1)
        int n = nums.size();
        for (int i = 0; i < n; i++) {
            for (int j = i + 1; j < n; j++) {
                if (nums[i] + nums[j] == target) {
                    return {i, j};
                }
            }
        }
        return {};
    }
};

```

## time O(n) | Sweet Spot

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        // Time: O(n), Memory: O(n)
        unordered_map<int, int> indices;
        for (int i = 0; i < nums.size(); i++) {
            int complement = target - nums[i];
            if (indices.count(complement)) {
                return {indices[complement], i};
            }
            indices[nums[i]] = i;
        }
        return {};
    }
};

```

# java

## memory O(1)

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        // Time: O(n^2), Memory: O(1)
        for (int i = 0; i < nums.length; i++) {
            for (int j = i + 1; j < nums.length; j++) {
                if (nums[i] + nums[j] == target) {
                    return new int[] { i, j };
                }
            }
        }
        return new int[] {};
    }
}

```

## time O(n) | Sweet Spot

```java
import java.util.HashMap;
import java.util.Map;

class Solution {
    public int[] twoSum(int[] nums, int target) {
        // Time: O(n), Memory: O(n)
        Map<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i];
            if (map.containsKey(complement)) {
                return new int[] { map.get(complement), i };
            }
            map.put(nums[i], i);
        }
        return new int[] {};
    }
}

```

# python 3.14

## memory O(1)

```python 3.14
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        # Time: O(n^2), Memory: O(1)
        n = len(nums)
        for i in range(n):
            for j in range(i + 1, n):
                if nums[i] + nums[j] == target:
                    return [i, j]

```

## time O(n) | Sweet Spot

```python 3.14
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        # Time: O(n), Memory: O(n)
        prevMap = {}
        for i, n in enumerate(nums):
            diff = target - n
            if diff in prevMap:
                return [prevMap[diff], i]
            prevMap[n] = i

```

# python 2.7.11

## memory O(1)

```python 2.7.11
class Solution(object):
    def twoSum(self, nums, target):
        # Time: O(n^2), Memory: O(1)
        n = len(nums)
        for i in xrange(n):
            for j in xrange(i + 1, n):
                if nums[i] + nums[j] == target:
                    return [i, j]

```

## time O(n) | Sweet Spot

```python 2.7.11
class Solution(object):
    def twoSum(self, nums, target):
        # Time: O(n), Memory: O(n)
        prevMap = {}
        for i, n in enumerate(nums):
            diff = target - n
            if diff in prevMap:
                return [prevMap[diff], i]
            prevMap[n] = i

```

# JavaScript

## memory O(1)

```javascript
var twoSum = function(nums, target) {
    // Time: O(n^2), Memory: O(1)
    for (let i = 0; i < nums.length; i++) {
        for (let j = i + 1; j < nums.length; j++) {
            if (nums[i] + nums[j] === target) {
                return [i, j];
            }
        }
    }
};

```

## time O(n) | Sweet Spot

```javascript
var twoSum = function(nums, target) {
    // Time: O(n), Memory: O(n)
    const map = new Map();
    for (let i = 0; i < nums.length; i++) {
        const diff = target - nums[i];
        if (map.has(diff)) {
            return [map.get(diff), i];
        }
        map.set(nums[i], i);
    }
};

```

# Typescript

## memory O(1)

```typescript
function twoSum(nums: number[], target: number): number[] {
    // Time: O(n^2), Memory: O(1)
    for (let i = 0; i < nums.length; i++) {
        for (let j = i + 1; j < nums.length; j++) {
            if (nums[i] + nums[j] === target) {
                return [i, j];
            }
        }
    }
    return [];
};

```

## time O(n) | Sweet Spot

```typescript
function twoSum(nums: number[], target: number): number[] {
    // Time: O(n), Memory: O(n)
    const map = new Map<number, number>();
    for (let i = 0; i < nums.length; i++) {
        const diff = target - nums[i];
        if (map.has(diff)) {
            return [map.get(diff)!, i];
        }
        map.set(nums[i], i);
    }
    return [];
};

```

# C#

## memory O(1)

```c#
public class Solution {
    public int[] TwoSum(int[] nums, int target) {
        // Time: O(n^2), Memory: O(1)
        for (int i = 0; i < nums.Length; i++) {
            for (int j = i + 1; j < nums.Length; j++) {
                if (nums[i] + nums[j] == target) {
                    return new int[] { i, j };
                }
            }
        }
        return new int[0];
    }
}

```

## time O(n) | Sweet Spot

```c#
using System.Collections.Generic;

public class Solution {
    public int[] TwoSum(int[] nums, int target) {
        // Time: O(n), Memory: O(n)
        Dictionary<int, int> map = new Dictionary<int, int>();
        for (int i = 0; i < nums.Length; i++) {
            int diff = target - nums[i];
            if (map.ContainsKey(diff)) {
                return new int[] { map[diff], i };
            }
            if (!map.ContainsKey(nums[i])) {
                map.Add(nums[i], i);
            }
        }
        return new int[0];
    }
}

```

# C

## memory O(1)

```c
int* twoSum(int* nums, int numsSize, int target, int* returnSize) {
    // Time: O(n^2), Memory: O(1)
    *returnSize = 2;
    int* result = (int*)malloc(2 * sizeof(int));
    for (int i = 0; i < numsSize; i++) {
        for (int j = i + 1; j < numsSize; j++) {
            if (nums[i] + nums[j] == target) {
                result[0] = i;
                result[1] = j;
                return result;
            }
        }
    }
    return NULL;
}

```

## time O(n) | Sweet Spot

```c
struct HashNode {
    int key;
    int value;
    int occupied;
};

int* twoSum(int* nums, int numsSize, int target, int* returnSize) {
    // Time: O(n), Memory: O(n)
    int size = numsSize * 2;
    struct HashNode* hashTable = (struct HashNode*)calloc(size, sizeof(struct HashNode));
    int* result = (int*)malloc(2 * sizeof(int));
    *returnSize = 2;

    for (int i = 0; i < numsSize; i++) {
        int diff = target - nums[i];
        int hash = abs(diff) % size;
        while (hashTable[hash].occupied) {
            if (hashTable[hash].key == diff) {
                result[0] = hashTable[hash].value;
                result[1] = i;
                free(hashTable);
                return result;
            }
            hash = (hash + 1) % size;
        }
        hash = abs(nums[i]) % size;
        while (hashTable[hash].occupied) {
            hash = (hash + 1) % size;
        }
        hashTable[hash].key = nums[i];
        hashTable[hash].value = i;
        hashTable[hash].occupied = 1;
    }
    free(hashTable);
    return NULL;
}

```

# Go

## memory O(1)

```go
func twoSum(nums []int, target int) []int {
    // Time: O(n^2), Memory: O(1)
    for i := 0; i < len(nums); i++ {
        for j := i + 1; j < len(nums); j++ {
            if nums[i]+nums[j] == target {
                return []int{i, j}
            }
        }
    }
    return nil
}

```

## time O(n) | Sweet Spot

```go
func twoSum(nums []int, target int) []int {
    // Time: O(n), Memory: O(n)
    prevMap := make(map[int]int)
    for i, n := range nums {
        diff := target - n
        if idx, ok := prevMap[diff]; ok {
            return []int{idx, i}
        }
        prevMap[n] = i
    }
    return nil
}

```

# Kotlin

## memory O(1)

```kotlin
class Solution {
    fun twoSum(nums: IntArray, target: Int): IntArray {
        // Time: O(n^2), Memory: O(1)
        for (i in nums.indices) {
            for (j in i + 1 until nums.size) {
                if (nums[i] + nums[j] == target) {
                    return intArrayOf(i, j)
                }
            }
        }
        return intArrayOf()
    }
}

```

## time O(n) | Sweet Spot

```kotlin
class Solution {
    fun twoSum(nums: IntArray, target: Int): IntArray {
        // Time: O(n), Memory: O(n)
        val map = HashMap<Int, Int>()
        for (i in nums.indices) {
            val diff = target - nums[i]
            if (map.containsKey(diff)) {
                return intArrayOf(map[diff]!!, i)
            }
            map[nums[i]] = i
        }
        return intArrayOf()
    }
}

```

# swift

## memory O(1)

```swift
class Solution {
    func twoSum(_ nums: [Int], _ target: Int) -> [Int] {
        // Time: O(n^2), Memory: O(1)
        for i in 0..<nums.count {
            for j in (i + 1)..<nums.count {
                if nums[i] + nums[j] == target {
                    return [i, j]
                }
            }
        }
        return []
    }
}

```

## time O(n) | Sweet Spot

```swift
class Solution {
    func twoSum(_ nums: [Int], _ target: Int) -> [Int] {
        // Time: O(n), Memory: O(n)
        var dict = [Int: Int]()
        for (i, n) in nums.enumerated() {
            let diff = target - n
            if let idx = dict[diff] {
                return [idx, i]
            }
            dict[n] = i
        }
        return []
    }
}

```

# rust

## memory O(1)

```rust
impl Solution {
    pub fn two_sum(nums: Vec<i32>, target: i32) -> Vec<i32> {
        // Time: O(n^2), Memory: O(1)
        for i in 0..nums.len() {
            for j in i + 1..nums.len() {
                if nums[i] + nums[j] == target {
                    return vec![i as i32, j as i32];
                }
            }
        }
        vec![]
    }
}

```

## time O(n) | Sweet Spot

```rust
use std::collections::HashMap;

impl Solution {
    pub fn two_sum(nums: Vec<i32>, target: i32) -> Vec<i32> {
        // Time: O(n), Memory: O(n)
        let mut map = HashMap::with_capacity(nums.len());
        for (i, &n) in nums.iter().enumerate() {
            let diff = target - n;
            if let Some(&idx) = map.get(&diff) {
                return vec![idx as i32, i as i32];
            }
            map.insert(n, i);
        }
        vec![]
    }
}

```

# ruby

## memory O(1)

```ruby
def two_sum(nums, target)
  # Time: O(n^2), Memory: O(1)
  nums.each_with_index do |n1, i|
    nums.each_with_index do |n2, j|
      next if i == j
      return [i, j] if n1 + n2 == target
    end
  end
end

```

## time O(n) | Sweet Spot

```ruby
def two_sum(nums, target)
  # Time: O(n), Memory: O(n)
  dict = {}
  nums.each_with_index do |n, i|
    diff = target - n
    return [dict[diff], i] if dict.key?(diff)
    dict[n] = i
  end
end

```

# php

## memory O(1)

```php
class Solution {
    function twoSum($nums, $target) {
        // Time: O(n^2), Memory: O(1)
        $count = count($nums);
        for ($i = 0; $i < $count; $i++) {
            for ($j = $i + 1; $j < $count; $j++) {
                if ($nums[$i] + $nums[$j] == $target) {
                    return [$i, $j];
                }
            }
        }
    }
}

```

## time O(n) | Sweet Spot

```php
class Solution {
    function twoSum($nums, $target) {
        // Time: O(n), Memory: O(n)
        $map = [];
        foreach ($nums as $i => $n) {
            $diff = $target - $n;
            if (isset($map[$diff])) {
                return [$map[$diff], $i];
            }
            $map[$n] = $i;
        }
    }
}

```

# dart

## memory O(1)

```dart
class Solution {
  List<int> twoSum(List<int> nums, int target) {
    // Time: O(n^2), Memory: O(1)
    for (int i = 0; i < nums.length; i++) {
      for (int j = i + 1; j < nums.length; j++) {
        if (nums[i] + nums[j] == target) {
          return [i, j];
        }
      }
    }
    return [];
  }
}

```

## time O(n) | Sweet Spot

```dart
class Solution {
  List<int> twoSum(List<int> nums, int target) {
    // Time: O(n), Memory: O(n)
    Map<int, int> map = {};
    for (int i = 0; i < nums.length; i++) {
      int diff = target - nums[i];
      if (map.containsKey(diff)) {
        return [map[diff]!, i];
      }
      map[nums[i]] = i;
    }
    return [];
  }
}

```

# scala

## memory O(1)

```scala
object Solution {
    def twoSum(nums: Array[Int], target: Int): Array[Int] = {
        // Time: O(n^2), Memory: O(1)
        for (i <- 0 until nums.length) {
            for (j <- i + 1 until nums.length) {
                if (nums(i) + nums(j) == target) {
                    return Array(i, j)
                }
            }
        }
        Array()
    }
}

```

## time O(n) | Sweet Spot

```scala
import scala.collection.mutable

object Solution {
    def twoSum(nums: Array[Int], target: Int): Array[Int] = {
        // Time: O(n), Memory: O(n)
        val map = mutable.HashMap[Int, Int]()
        for (i <- 0 until nums.length) {
            val diff = target - nums(i)
            if (map.contains(diff)) {
                return Array(map(diff), i)
            }
            map(nums(i)) = i
        }
        Array()
    }
}

```

# elixir

## memory O(1)

```elixir
defmodule Solution do
  @spec two_sum(nums :: [integer], target :: integer) :: [integer]
  def two_sum(nums, target) do
    # Time: O(n^2), Memory: O(1)
    indexed = Enum.with_index(nums)
    Enum.find_value(indexed, fn {n1, i} ->
      Enum.find_value(indexed, fn {n2, j} ->
        if i < j and n1 + n2 == target, do: [i, j]
      end)
    end)
  end
end

```

## time O(n) | Sweet Spot

```elixir
defmodule Solution do
  @spec two_sum(nums :: [integer], target :: integer) :: [integer]
  def two_sum(nums, target) do
    # Time: O(n), Memory: O(n)
    solve(nums, target, 0, %{})
  end

  defp solve([h | t], target, i, map) do
    diff = target - h
    case Map.get(map, diff) do
      nil -> solve(t, target, i + 1, Map.put(map, h, i))
      idx -> [idx, i]
    end
  end
end

```

# erlang

## memory O(1)

```erlang
-spec two_sum(Nums :: [integer()], Target :: integer()) -> [integer()].
two_sum(Nums, Target) ->
    % Time: O(n^2), Memory: O(1)
    Indexed = lists:zip(lists:seq(0, length(Nums)-1), Nums),
    hd([ [I, J] || {I, X} <- Indexed, {J, Y} <- Indexed, I < J, X + Y =:= Target ]).

```

## time O(n) | Sweet Spot

```erlang
-spec two_sum(Nums :: [integer()], Target :: integer()) -> [integer()].
two_sum(Nums, Target) ->
    % Time: O(n), Memory: O(n)
    solve(Nums, Target, 0, #{}).

solve([H | T], Target, I, Map) ->
    Diff = Target - H,
    case maps:find(Diff, Map) of
        {ok, Idx} -> [Idx, I];
        error -> solve(T, Target, I + 1, maps:put(H, I, Map))
    end.

```

# Racket

## memory O(1)

```racket
(define/contract (two-sum nums target)
  (-> (listof exact-integer?) exact-integer? (listof exact-integer?))
  ; Time: O(n^2), Memory: O(1)
  (let ([vec (list->vector nums)])
    (let loop-i ([i 0])
      (let loop-j ([j (+ i 1)])
        (cond
          [(= j (vector-length vec)) (loop-i (+ i 1))]
          [(= (+ (vector-ref vec i) (vector-ref vec j)) target) (list i j)]
          [else (loop-j (+ j 1))])))))

```

## time O(n) | Sweet Spot

```racket
(define/contract (two-sum nums target)
  (-> (listof exact-integer?) exact-integer? (listof exact-integer?))
  ; Time: O(n), Memory: O(n)
  (let loop ([lst nums] [i 0] [h (hash)])
    (let* ([curr (car lst)]
           [diff (- target curr)])
      (if (hash-has-key? h diff)
          (list (hash-ref h diff) i)
          (loop (cdr lst) (+ i 1) (hash-set h curr i))))))

```