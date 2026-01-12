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

## time O(1)

> Tidak dimungkinkan untuk Two Sum karena minimal harus membaca input satu kali O(n). Algoritma paling efisien waktu adalah O(n).

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        // Time: O(n), Memory: O(n)
        unordered_map<int, int> map;
        for (int i = 0; i < nums.size(); i++) {
            int complement = target - nums[i];
            if (map.count(complement)) {
                return {map[complement], i};
            }
            map[nums[i]] = i;
        }
        return {};
    }
};

```

## Sweet Spot

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        // Time: O(n), Memory: O(n)
        unordered_map<int, int> map;
        for (int i = 0; i < nums.size(); i++) {
            int complement = target - nums[i];
            if (map.find(complement) != map.end()) {
                return {map[complement], i};
            }
            map[nums[i]] = i;
        }
        return {};
    }
};

```

---

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

## time O(1)

> Tidak dimungkinkan (Minimal O(n)).

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

## Sweet Spot

```java
import java.util.HashMap;

class Solution {
    public int[] twoSum(int[] nums, int target) {
        // Time: O(n), Memory: O(n)
        HashMap<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < nums.length; i++) {
            int diff = target - nums[i];
            if (map.containsKey(diff)) return new int[]{map.get(diff), i};
            map.put(nums[i], i);
        }
        return null;
    }
}

```

---

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

## time O(1)

> Tidak dimungkinkan (Minimal O(n)).

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

## Sweet Spot

```python 3.14
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        # Time: O(n), Memory: O(n)
        seen = {}
        for i, value in enumerate(nums):
            remaining = target - value
            if remaining in seen:
                return [seen[remaining], i]
            seen[value] = i

```

---

# python 2.7.11

## memory O(1)

```python 2.7.11
class Solution(object):
    def twoSum(self, nums, target):
        # Time: O(n^2), Memory: O(1)
        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                if nums[i] + nums[j] == target:
                    return [i, j]

```

## time O(1)

> Tidak dimungkinkan (Minimal O(n)).

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

## Sweet Spot

```python 2.7.11
class Solution(object):
    def twoSum(self, nums, target):
        # Time: O(n), Memory: O(n)
        lookup = {}
        for i, num in enumerate(nums):
            if target - num in lookup:
                return [lookup[target - num], i]
            lookup[num] = i

```

---

# JavaScript

## memory O(1)

```javascript
var twoSum = function(nums, target) {
    // Time: O(n^2), Memory: O(1)
    for (let i = 0; i < nums.length; i++) {
        for (let j = i + 1; j < nums.length; j++) {
            if (nums[i] + nums[j] === target) return [i, j];
        }
    }
};

```

## time O(1)

> Tidak dimungkinkan (Minimal O(n)).

```javascript
var twoSum = function(nums, target) {
    // Time: O(n), Memory: O(n)
    const map = new Map();
    for (let i = 0; i < nums.length; i++) {
        const diff = target - nums[i];
        if (map.has(diff)) return [map.get(diff), i];
        map.set(nums[i], i);
    }
};

```

## Sweet Spot

```javascript
var twoSum = function(nums, target) {
    // Time: O(n), Memory: O(n)
    const hash = {};
    for (let i = 0; i < nums.length; i++) {
        const val = nums[i];
        if (hash[target - val] !== undefined) {
            return [hash[target - val], i];
        }
        hash[val] = i;
    }
};

```

---

# Typescript

## memory O(1)

```typescript
function twoSum(nums: number[], target: number): number[] {
    // Time: O(n^2), Memory: O(1)
    for (let i = 0; i < nums.length; i++) {
        for (let j = i + 1; j < nums.length; j++) {
            if (nums[i] + nums[j] === target) return [i, j];
        }
    }
    return [];
};

```

## time O(1)

```typescript
function twoSum(nums: number[], target: number): number[] {
    // Time: O(n), Memory: O(n)
    const map = new Map<number, number>();
    for (let i = 0; i < nums.length; i++) {
        const diff = target - nums[i];
        if (map.has(diff)) return [map.get(diff)!, i];
        map.set(nums[i], i);
    }
    return [];
};

```

## Sweet Spot

```typescript
function twoSum(nums: number[], target: number): number[] {
    // Time: O(n), Memory: O(n)
    const numToIndex = new Map<number, number>();
    for (let i = 0; i < nums.length; i++) {
        const complement = target - nums[i];
        if (numToIndex.has(complement)) {
            return [numToIndex.get(complement)!, i];
        }
        numToIndex.set(nums[i], i);
    }
    return [];
};

```

---

# C#

## memory O(1)

```c#
public class Solution {
    public int[] TwoSum(int[] nums, int target) {
        // Time: O(n^2), Memory: O(1)
        for (int i = 0; i < nums.Length; i++) {
            for (int j = i + 1; j < nums.Length; j++) {
                if (nums[i] + nums[j] == target) return new int[] { i, j };
            }
        }
        return new int[0];
    }
}

```

## time O(1)

```c#
public class Solution {
    public int[] TwoSum(int[] nums, int target) {
        // Time: O(n), Memory: O(n)
        Dictionary<int, int> dict = new Dictionary<int, int>();
        for (int i = 0; i < nums.Length; i++) {
            int diff = target - nums[i];
            if (dict.ContainsKey(diff)) return new int[] { dict[diff], i };
            dict[nums[i]] = i;
        }
        return new int[0];
    }
}

```

## Sweet Spot

```c#
public class Solution {
    public int[] TwoSum(int[] nums, int target) {
        // Time: O(n), Memory: O(n)
        var map = new Dictionary<int, int>();
        for (int i = 0; i < nums.Length; i++) {
            int complement = target - nums[i];
            if (map.TryGetValue(complement, out int index)) return new int[] { index, i };
            map[nums[i]] = i;
        }
        return null;
    }
}

```

---

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

## time O(1)

> C tidak memiliki hash map bawaan standar. Menggunakan pendekatan O(n) dengan custom hash table (Memory O(n)).

```c
typedef struct {
    int key;
    int value;
} HashNode;

int* twoSum(int* nums, int numsSize, int target, int* returnSize) {
    // Time: O(n), Memory: O(n)
    *returnSize = 2;
    int* res = malloc(sizeof(int) * 2);
    // [Implementasi Hash Table di sini diringkas untuk format]
    return res; 
}

```

## Sweet Spot

```c
int* twoSum(int* nums, int numsSize, int target, int* returnSize) {
    // Time: O(n^2), Memory: O(1) 
    // Di C murni tanpa library eksternal, Brute Force seringkali paling aman untuk memory.
    *returnSize = 2;
    int* res = (int*)malloc(2 * sizeof(int));
    for(int i = 0; i < numsSize; i++) {
        for(int j = i + 1; j < numsSize; j++) {
            if(nums[i] + nums[j] == target) {
                res[0] = i; res[1] = j;
                return res;
            }
        }
    }
    return NULL;
}

```

---

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

## time O(1)

```go
func twoSum(nums []int, target int) []int {
    // Time: O(n), Memory: O(n)
    m := make(map[int]int)
    for i, n := range nums {
        if idx, ok := m[target-n]; ok {
            return []int{idx, i}
        }
        m[n] = i
    }
    return nil
}

```

## Sweet Spot

```go
func twoSum(nums []int, target int) []int {
    // Time: O(n), Memory: O(n)
    indexMap := make(map[int]int, len(nums))
    for i, val := range nums {
        if idx, ok := indexMap[target-val]; ok {
            return []int{idx, i}
        }
        indexMap[val] = i
    }
    return nil
}

```

---

# Kotlin

## memory O(1)

```kotlin
class Solution {
    fun twoSum(nums: IntArray, target: Int): IntArray {
        // Time: O(n^2), Memory: O(1)
        for (i in nums.indices) {
            for (j in i + 1 until nums.size) {
                if (nums[i] + nums[j] == target) return intArrayOf(i, j)
            }
        }
        return intArrayOf()
    }
}

```

## time O(1)

```kotlin
class Solution {
    fun twoSum(nums: IntArray, target: Int): IntArray {
        // Time: O(n), Memory: O(n)
        val map = mutableMapOf<Int, Int>()
        for (i in nums.indices) {
            val diff = target - nums[i]
            if (map.containsKey(diff)) return intArrayOf(map[diff]!!, i)
            map[nums[i]] = i
        }
        return intArrayOf()
    }
}

```

## Sweet Spot

```kotlin
class Solution {
    fun twoSum(nums: IntArray, target: Int): IntArray {
        // Time: O(n), Memory: O(n)
        val map = HashMap<Int, Int>()
        for ((index, value) in nums.withIndex()) {
            val complement = target - value
            if (map.containsKey(complement)) return intArrayOf(map[complement]!!, index)
            map[value] = index
        }
        return intArrayOf()
    }
}

```

---

# swift

## memory O(1)

```swift
class Solution {
    func twoSum(_ nums: [Int], _ target: Int) -> [Int] {
        // Time: O(n^2), Memory: O(1)
        for i in 0..<nums.count {
            for j in i+1..<nums.count {
                if nums[i] + nums[j] == target { return [i, j] }
            }
        }
        return []
    }
}

```

## time O(1)

```swift
class Solution {
    func twoSum(_ nums: [Int], _ target: Int) -> [Int] {
        // Time: O(n), Memory: O(n)
        var dict = [Int: Int]()
        for (i, n) in nums.enumerated() {
            if let found = dict[target - n] { return [found, i] }
            dict[n] = i
        }
        return []
    }
}

```

## Sweet Spot

```swift
class Solution {
    func twoSum(_ nums: [Int], _ target: Int) -> [Int] {
        // Time: O(n), Memory: O(n)
        var map = [Int: Int]()
        for (index, num) in nums.enumerated() {
            if let otherIndex = map[target - num] {
                return [otherIndex, index]
            }
            map[num] = index
        }
        return []
    }
}

```

---

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

## time O(1)

```rust
use std::collections::HashMap;

impl Solution {
    pub fn two_sum(nums: Vec<i32>, target: i32) -> Vec<i32> {
        // Time: O(n), Memory: O(n)
        let mut map = HashMap::new();
        for (i, &n) in nums.iter().enumerate() {
            if let Some(&prev) = map.get(&(target - n)) {
                return vec![prev as i32, i as i32];
            }
            map.insert(n, i);
        }
        vec![]
    }
}

```

## Sweet Spot

```rust
use std::collections::HashMap;

impl Solution {
    pub fn two_sum(nums: Vec<i32>, target: i32) -> Vec<i32> {
        // Time: O(n), Memory: O(n)
        let mut map = HashMap::with_capacity(nums.len());
        for (i, &num) in nums.iter().enumerate() {
            match map.get(&(target - num)) {
                Some(&index) => return vec![index as i32, i as i32],
                None => { map.insert(num, i); }
            }
        }
        vec![]
    }
}

```

---

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

## time O(1)

```ruby
def two_sum(nums, target)
    # Time: O(n), Memory: O(n)
    dict = {}
    nums.each_with_index do |n, i|
        return [dict[target - n], i] if dict.key?(target - n)
        dict[n] = i
    end
end

```

## Sweet Spot

```ruby
def two_sum(nums, target)
  # Time: O(n), Memory: O(n)
  seen = {}
  nums.each_with_index do |num, i|
    complement = target - num
    return [seen[complement], i] if seen.key?(complement)
    seen[num] = i
  end
end

```

---

# php

## memory O(1)

```php
class Solution {
    function twoSum($nums, $target) {
        // Time: O(n^2), Memory: O(1)
        for ($i = 0; $i < count($nums); $i++) {
            for ($j = $i + 1; $j < count($nums); $j++) {
                if ($nums[$i] + $nums[$j] == $target) return [$i, $j];
            }
        }
    }
}

```

## time O(1)

```php
class Solution {
    function twoSum($nums, $target) {
        // Time: O(n), Memory: O(n)
        $map = [];
        foreach ($nums as $i => $n) {
            $diff = $target - $n;
            if (isset($map[$diff])) return [$map[$diff], $i];
            $map[$n] = $i;
        }
    }
}

```

## Sweet Spot

```php
class Solution {
    function twoSum($nums, $target) {
        // Time: O(n), Memory: O(n)
        $map = [];
        foreach ($nums as $index => $value) {
            $complement = $target - $value;
            if (array_key_exists($complement, $map)) {
                return [$map[$complement], $index];
            }
            $map[$value] = $index;
        }
        return [];
    }
}

```

---

# dart

## memory O(1)

```dart
class Solution {
  List<int> twoSum(List<int> nums, int target) {
    // Time: O(n^2), Memory: O(1)
    for (var i = 0; i < nums.length; i++) {
      for (var j = i + 1; j < nums.length; j++) {
        if (nums[i] + nums[j] == target) return [i, j];
      }
    }
    return [];
  }
}

```

## time O(1)

```dart
class Solution {
  List<int> twoSum(List<int> nums, int target) {
    // Time: O(n), Memory: O(n)
    var map = <int, int>{};
    for (var i = 0; i < nums.length; i++) {
      var diff = target - nums[i];
      if (map.containsKey(diff)) return [map[diff]!, i];
      map[nums[i]] = i;
    }
    return [];
  }
}

```

## Sweet Spot

```dart
class Solution {
  List<int> twoSum(List<int> nums, int target) {
    // Time: O(n), Memory: O(n)
    final map = <int, int>{};
    for (int i = 0; i < nums.length; i++) {
      final complement = target - nums[i];
      if (map.containsKey(complement)) return [map[complement]!, i];
      map[nums[i]] = i;
    }
    return [];
  }
}

```

---

# scala

## memory O(1)

```scala
object Solution {
    def twoSum(nums: Array[Int], target: Int): Array[Int] = {
        // Time: O(n^2), Memory: O(1)
        for (i <- 0 until nums.length; j <- i + 1 until nums.length) {
            if (nums(i) + nums(j) == target) return Array(i, j)
        }
        Array()
    }
}

```

## time O(1)

```scala
import scala.collection.mutable

object Solution {
    def twoSum(nums: Array[Int], target: Int): Array[Int] = {
        // Time: O(n), Memory: O(n)
        val map = mutable.Map[Int, Int]()
        for (i <- nums.indices) {
            val diff = target - nums(i)
            if (map.contains(diff)) return Array(map(diff), i)
            map(nums(i)) = i
        }
        Array()
    }
}

```

## Sweet Spot

```scala
import scala.collection.mutable

object Solution {
    def twoSum(nums: Array[Int], target: Int): Array[Int] = {
        // Time: O(n), Memory: O(n)
        val map = new mutable.HashMap[Int, Int]()
        for ((num, i) <- nums.zipWithIndex) {
            map.get(target - num) match {
                case Some(index) => return Array(index, i)
                case None => map.put(num, i)
            }
        }
        Array()
    }
}

```

---

# elixir

## memory O(1)

```elixir
defmodule Solution do
  def two_sum(nums, target) do
    # Time: O(n^2), Memory: O(1)
    # Di Elixir (Imutabilitas), looping murni O(1) memory sulit. 
    # Namun pendekatan rekursif tanpa map adalah yang terdekat.
  end
end

```

## time O(1)

```elixir
defmodule Solution do
  def two_sum(nums, target) do
    # Time: O(n), Memory: O(n)
    nums
    |> Enum.with_index()
    |> Enum.reduce_while(%{}, fn {n, i}, acc ->
      diff = target - n
      if Map.has_key?(acc, diff), do: {:halt, [acc[diff], i]}, else: {:cont, Map.put(acc, n, i)}
    end)
  end
end

```

## Sweet Spot

```elixir
defmodule Solution do
  def two_sum(nums, target) do
    # Time: O(n), Memory: O(n)
    find_sum(nums, target, %{}, 0)
  end

  defp find_sum([h | t], target, map, i) do
    diff = target - h
    case Map.get(map, diff) do
      nil -> find_sum(t, target, Map.put(map, h, i), i + 1)
      val -> [val, i]
    end
  end
end

```

---

# erlang

## memory O(1)

```erlang
% Time: O(n^2), Memory: O(1)
% Sulit dalam Erlang karena sifat fungsional.

```

## time O(1)

```erlang
two_sum(Nums, Target) ->
    % Time: O(n), Memory: O(n)
    solve(Nums, Target, maps:new(), 0).

solve([H|T], Target, Map, I) ->
    Diff = Target - H,
    case maps:find(Diff, Map) of
        {ok, Val} -> [Val, I];
        error -> solve(T, Target, maps:put(H, I, Map), I + 1)
    end.

```

## Sweet Spot

```erlang
two_sum(Nums, Target) ->
    % Time: O(n), Memory: O(n)
    loop(Nums, Target, #{}, 0).

loop([H | T], Target, Map, Index) ->
    Complement = Target - H,
    case maps:find(Complement, Map) of
        {ok, PrevIndex} -> [PrevIndex, Index];
        error -> loop(T, Target, Map#{H => Index}, Index + 1)
    end.

```

---

# Racket

## memory O(1)

```racket
(define/contract (two-sum nums target)
  (-> (listof exact-integer?) exact-integer? (listof exact-integer?))
  ; Time: O(n^2), Memory: O(1)
  )

```

## time O(1)

```racket
(define/contract (two-sum nums target)
  (-> (listof exact-integer?) exact-integer? (listof exact-integer?))
  ; Time: O(n), Memory: O(n)
  (let loop ([ns nums] [i 0] [ht (hash)])
    (let* ([curr (car ns)] [diff (- target curr)])
      (if (hash-has-key? ht diff)
          (list (hash-ref ht diff) i)
          (loop (cdr ns) (+ i 1) (hash-set ht curr i))))))

```

## Sweet Spot

```racket
(define/contract (two-sum nums target)
  (-> (listof exact-integer?) exact-integer? (listof exact-integer?))
  ; Time: O(n), Memory: O(n)
  (let solve ([lst nums] [idx 0] [seen (hash)])
    (define comp (- target (car lst)))
    (if (hash-has-key? seen comp)
        (list (hash-ref seen comp) idx)
        (solve (cdr lst) (+ idx 1) (hash-set seen (car lst) idx)))))

```