# C++

## Sweet Spot

```cpp
class Solution {
public:
    vector<int> grayCode(int n) {
        int count = 1 << n;
        vector<int> result;
        result.reserve(count);
        for (int i = 0; i < count; ++i) {
            result.push_back(i ^ (i >> 1));
        }
        return result;
        /* Time Complexity: O(2^n), Memory Complexity: O(2^n) */
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public List<Integer> grayCode(int n) {
        int count = 1 << n;
        List<Integer> result = new ArrayList<>(count);
        for (int i = 0; i < count; i++) {
            result.add(i ^ (i >> 1));
        }
        return result;
        /* Time Complexity: O(2^n), Memory Complexity: O(2^n) */
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def grayCode(self, n: int) -> List[int]:
        return [i ^ (i >> 1) for i in range(1 << n)]
        # Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def grayCode(self, n):
        """
        :type n: int
        :rtype: List[int]
        """
        return [i ^ (i >> 1) for i in range(1 << n)]
        # Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number} n
 * @return {number[]}
 */
var grayCode = function(n) {
    const count = 1 << n;
    const result = new Array(count);
    for (let i = 0; i < count; i++) {
        result[i] = i ^ (i >> 1);
    }
    return result;
    /* Time Complexity: O(2^n), Memory Complexity: O(2^n) */
};

```

# Typescript

## Sweet Spot

```typescript
function grayCode(n: number): number[] {
    const count = 1 << n;
    const result: number[] = new Array(count);
    for (let i = 0; i < count; i++) {
        result[i] = i ^ (i >> 1);
    }
    return result;
    /* Time Complexity: O(2^n), Memory Complexity: O(2^n) */
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public IList<int> GrayCode(int n) {
        int count = 1 << n;
        List<int> result = new List<int>(count);
        for (int i = 0; i < count; i++) {
            result.Add(i ^ (i >> 1));
        }
        return result;
        /* Time Complexity: O(2^n), Memory Complexity: O(2^n) */
    }
}

```

# C

## Sweet Spot

```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* grayCode(int n, int* returnSize) {
    int count = 1 << n;
    *returnSize = count;
    int* result = (int*)malloc(count * sizeof(int));
    for (int i = 0; i < count; i++) {
        result[i] = i ^ (i >> 1);
    }
    return result;
    /* Time Complexity: O(2^n), Memory Complexity: O(2^n) */
}

```

# Go

## Sweet Spot

```go
func grayCode(n int) []int {
    count := 1 << n
    result := make([]int, count)
    for i := 0; i < count; i++ {
        result[i] = i ^ (i >> 1)
    }
    return result
    /* Time Complexity: O(2^n), Memory Complexity: O(2^n) */
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun grayCode(n: Int): List<Int> {
        val count = 1 shl n
        val result = ArrayList<Int>(count)
        for (i in 0 until count) {
            result.add(i xor (i shr 1))
        }
        return result
        /* Time Complexity: O(2^n), Memory Complexity: O(2^n) */
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func grayCode(_ n: Int) -> [Int] {
        let count = 1 << n
        var result = [Int]()
        result.reserveCapacity(count)
        for i in 0..<count {
            result.append(i ^ (i >> 1))
        }
        return result
        /* Time Complexity: O(2^n), Memory Complexity: O(2^n) */
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn gray_code(n: i32) -> Vec<i32> {
        let count = 1 << n;
        let mut result = Vec::with_capacity(count as usize);
        for i in 0..count {
            result.push(i ^ (i >> 1));
        }
        result
        /* Time Complexity: O(2^n), Memory Complexity: O(2^n) */
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer} n
# @return {Integer[]}
def gray_code(n)
    Array.new(1 << n) { |i| i ^ (i >> 1) }
    # Time Complexity: O(2^n), Memory Complexity: O(2^n)
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer $n
     * @return Integer[]
     */
    function grayCode($n) {
        $count = 1 << $n;
        $result = [];
        for ($i = 0; $i < $count; $i++) {
            $result[] = $i ^ ($i >> 1);
        }
        return $result;
        /* Time Complexity: O(2^n), Memory Complexity: O(2^n) */
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  List<int> grayCode(int n) {
    int count = 1 << n;
    List<int> result = List<int>.filled(count, 0);
    for (int i = 0; i < count; i++) {
      result[i] = i ^ (i >> 1);
    }
    return result;
    /* Time Complexity: O(2^n), Memory Complexity: O(2^n) */
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def grayCode(n: Int): List[Int] = {
        val count = 1 << n
        (0 until count).map(i => i ^ (i >> 1)).toList
        /* Time Complexity: O(2^n), Memory Complexity: O(2^n) */
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec gray_code(n :: integer) :: [integer]
  def gray_code(n) do
    limit = Bitwise.bsl(1, n) - 1
    Enum.map(0..limit, fn i -> Bitwise.bxor(i, Bitwise.bsr(i, 1)) end)
    # Time Complexity: O(2^n), Memory Complexity: O(2^n)
  end
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec gray_code(N :: integer()) -> [integer()].
gray_code(N) ->
  Count = 1 bsl N,
  [I bxor (I bsr 1) || I <- lists:seq(0, Count - 1)].
  % Time Complexity: O(2^n), Memory Complexity: O(2^n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (gray-code n)
  (-> exact-integer? (listof exact-integer?))
  (let ([count (arithmetic-shift 1 n)])
    (for/list ([i (in-range count)])
      (bitwise-xor i (arithmetic-shift i -1))))
  ; Time Complexity: O(2^n), Memory Complexity: O(2^n)
  )

```