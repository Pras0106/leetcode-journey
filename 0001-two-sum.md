# cpp

## memory O(1)

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        // Time: O(n^2), Memory: O(1)
        for (int i = 0; i < nums.size(); i++) {
            for (int j = i + 1; j < nums.size(); j++) {
                if (nums[i] + nums[j] == target) {
                    return {i, j};
                }
            }
        }
        return {};
    }
};

```

## time O(1) | Sweet Spot

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        // Time: O(n), Memory: O(n)
        unordered_map<int, int> m;
        for (int i = 0; i < nums.size(); i++) {
            int complement = target - nums[i];
            if (m.count(complement)) {
                return {m[complement], i};
            }
            m[nums[i]] = i;
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
        return null;
    }
}

```

## time O(1) | Sweet Spot

```java
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
        return null;
    }
}

```

# python 3.14

## memory O(1)

```python 3.14
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        # Time: O(n^2), Memory: O(1)
        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                if nums[i] + nums[j] == target:
                    return [i, j]

```

## time O(1) | Sweet Spot

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
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        # Time: O(n^2), Memory: O(1)
        for i in xrange(len(nums)):
            for j in xrange(i + 1, len(nums)):
                if nums[i] + nums[j] == target:
                    return [i, j]

```

## time O(1) | Sweet Spot

```python 2.7.11
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
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
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
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

## time O(1) | Sweet Spot

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
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

## time O(1) | Sweet Spot

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
        return null;
    }
}

```

## time O(1) | Sweet Spot

```c#
public class Solution {
    public int[] TwoSum(int[] nums, int target) {
        // Time: O(n), Memory: O(n)
        Dictionary<int, int> map = new Dictionary<int, int>();
        for (int i = 0; i < nums.Length; i++) {
            int diff = target - nums[i];
            if (map.ContainsKey(diff)) {
                return new int[] { map[diff], i };
            }
            map[nums[i]] = i;
        }
        return null;
    }
}

```

# C

## memory O(1)

```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
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

## time O(1) | Sweet Spot

```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
typedef struct {
    int key;
    int val;
} hash_t;

int* twoSum(int* nums, int numsSize, int target, int* returnSize) {
    // Time: O(n), Memory: O(n)
    *returnSize = 2;
    int* result = (int*)malloc(2 * sizeof(int));
    hash_t* hash = (hash_t*)malloc(numsSize * sizeof(hash_t));
    int size = 0;
    for (int i = 0; i < numsSize; i++) {
        int diff = target - nums[i];
        for (int j = 0; j < size; j++) {
            if (hash[j].key == diff) {
                result[0] = hash[j].val;
                result[1] = i;
                free(hash);
                return result;
            }
        }
        hash[size].key = nums[i];
        hash[size].val = i;
        size++;
    }
    free(hash);
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

## time O(1) | Sweet Spot

```go
func twoSum(nums []int, target int) []int {
    // Time: O(n), Memory: O(n)
    m := make(map[int]int)
    for i, n := range nums {
        diff := target - n
        if idx, ok := m[diff]; ok {
            return []int{idx, i}
        }
        m[n] = i
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

## time O(1) | Sweet Spot

```kotlin
class Solution {
    fun twoSum(nums: IntArray, target: Int): IntArray {
        // Time: O(n), Memory: O(n)
        val map = mutableMapOf<Int, Int>()
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

## time O(1) | Sweet Spot

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
            for j in (i + 1)..nums.len() {
                if nums[i] + nums[j] == target {
                    return vec![i as i32, j as i32];
                }
            }
        }
        vec![]
    }
}

```

## time O(1) | Sweet Spot

```rust
use std::collections::HashMap;

impl Solution {
    pub fn two_sum(nums: Vec<i32>, target: i32) -> Vec<i32> {
        // Time: O(n), Memory: O(n)
        let mut map = HashMap::new();
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
# @param {Integer[]} nums
# @param {Integer} target
# @return {Integer[]}
def two_sum(nums, target)
    # Time: O(n^2), Memory: O(1)
    nums.each_with_index do |n1, i|
        ((i + 1)...nums.length).each do |j|
            return [i, j] if n1 + nums[j] == target
        end
    end
end

```

## time O(1) | Sweet Spot

```ruby
# @param {Integer[]} nums
# @param {Integer} target
# @return {Integer[]}
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
    /**
     * @param Integer[] $nums
     * @param Integer $target
     * @return Integer[]
     */
    function twoSum($nums, $target) {
        // Time: O(n^2), Memory: O(1)
        for ($i = 0; $i < count($nums); $i++) {
            for ($j = $i + 1; $j < count($nums); $j++) {
                if ($nums[$i] + $nums[$j] == $target) {
                    return [$i, $j];
                }
            }
        }
    }
}

```

## time O(1) | Sweet Spot

```php
class Solution {
    /**
     * @param Integer[] $nums
     * @param Integer $target
     * @return Integer[]
     */
    function twoSum($nums, $target) {
        // Time: O(n), Memory: O(n)
        $map = [];
        foreach ($nums as $i => $n) {
            $diff = $target - $n;
            if (array_key_exists($diff, $map)) {
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

## time O(1) | Sweet Spot

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

## time O(1) | Sweet Spot

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
      Enum.find_value(Enum.drop(indexed, i + 1), fn {n2, j} ->
        if n1 + n2 == target, do: [i, j]
      end)
    end)
  end
end

```

## time O(1) | Sweet Spot

```elixir
defmodule Solution do
  @spec two_sum(nums :: [integer], target :: integer) :: [integer]
  def two_sum(nums, target) do
    # Time: O(n), Memory: O(n)
    Enum.reduce_while(Enum.with_index(nums), %{}, fn {n, i}, map ->
      diff = target - n
      if Map.has_key?(map, diff) do
        {:halt, [Map.get(map, diff), i]}
      else
        {:cont, Map.put(map, n, i)}
      end
    end)
  end
end

```

# erlang

## memory O(1)

```erlang
-spec two_sum(Nums :: [integer()], Target :: integer()) -> [integer()].
two_sum(Nums, Target) ->
    % Time: O(n^2), Memory: O(1)
    Indexed = lists:zip(Nums, lists:seq(0, length(Nums) - 1)),
    hd([ [I, J] || {N1, I} <- Indexed, {N2, J} <- Indexed, I < J, N1 + N2 == Target ]).

```

## time O(1) | Sweet Spot

```erlang
-spec two_sum(Nums :: [integer()], Target :: integer()) -> [integer()].
two_sum(Nums, Target) ->
    % Time: O(n), Memory: O(n)
    two_sum(Nums, Target, 0, #{}).

two_sum([H|T], Target, Index, Map) ->
    Diff = Target - H,
    case maps:find(Diff, Map) of
        {ok, PrevIndex} -> [PrevIndex, Index];
        error -> two_sum(T, Target, Index + 1, Map#{H => Index})
    end.

```

# Racket

## memory O(1)

```racket
(define/contract (two-sum nums target)
  (-> (listof exact-integer?) exact-integer? (listof exact-integer?))
  ; Time: O(n^2), Memory: O(1)
  (let ([len (length nums)])
    (for*/first ([i (in-range len)]
                 [j (in-range (+ i 1) len)]
                 #:when (= (+ (list-ref nums i) (list-ref nums j)) target))
      (list i j))))

```

## time O(1) | Sweet Spot

```racket
(define/contract (two-sum nums target)
  (-> (listof exact-integer?) exact-integer? (listof exact-integer?))
  ; Time: O(n), Memory: O(n)
  (let loop ([ns nums] [i 0] [seen (hash)])
    (let* ([n (car ns)]
           [diff (- target n)])
      (if (hash-has-key? seen diff)
          (list (hash-ref seen diff) i)
          (loop (cdr ns) (+ i 1) (hash-set seen n i))))))

```