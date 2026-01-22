# cpp

## Sweet Spot

```cpp
class Solution {
public:
    vector<int> plusOne(vector<int>& digits) {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        for (int i = digits.size() - 1; i >= 0; --i) {
            if (digits[i] < 9) {
                digits[i]++;
                return digits;
            }
            digits[i] = 0;
        }
        digits.insert(digits.begin(), 1);
        return digits;
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public int[] plusOne(int[] digits) {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        for (int i = digits.length - 1; i >= 0; i--) {
            if (digits[i] < 9) {
                digits[i]++;
                return digits;
            }
            digits[i] = 0;
        }
        int[] result = new int[digits.length + 1];
        result[0] = 1;
        return result;
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def plusOne(self, digits: List[int]) -> List[int]:
        # Time Complexity: O(n)
        # Memory Complexity: O(n)
        for i in range(len(digits) - 1, -1, -1):
            if digits[i] < 9:
                digits[i] += 1
                return digits
            digits[i] = 0
        return [1] + digits

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def plusOne(self, digits):
        """
        :type digits: List[int]
        :rtype: List[int]
        """
        # Time Complexity: O(n)
        # Memory Complexity: O(n)
        for i in range(len(digits) - 1, -1, -1):
            if digits[i] < 9:
                digits[i] += 1
                return digits
            digits[i] = 0
        return [1] + digits

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[]} digits
 * @return {number[]}
 */
var plusOne = function(digits) {
    // Time Complexity: O(n)
    // Memory Complexity: O(n)
    for (let i = digits.length - 1; i >= 0; i--) {
        if (digits[i] < 9) {
            digits[i]++;
            return digits;
        }
        digits[i] = 0;
    }
    digits.unshift(1);
    return digits;
};

```

# Typescript

## Sweet Spot

```typescript
function plusOne(digits: number[]): number[] {
    // Time Complexity: O(n)
    // Memory Complexity: O(n)
    for (let i = digits.length - 1; i >= 0; i--) {
        if (digits[i] < 9) {
            digits[i]++;
            return digits;
        }
        digits[i] = 0;
    }
    digits.unshift(1);
    return digits;
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public int[] PlusOne(int[] digits) {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        for (int i = digits.Length - 1; i >= 0; i--) {
            if (digits[i] < 9) {
                digits[i]++;
                return digits;
            }
            digits[i] = 0;
        }
        int[] res = new int[digits.Length + 1];
        res[0] = 1;
        return res;
    }
}

```

# C

## Sweet Spot

```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* plusOne(int* digits, int digitsSize, int* returnSize) {
    // Time Complexity: O(n)
    // Memory Complexity: O(n)
    for (int i = digitsSize - 1; i >= 0; i--) {
        if (digits[i] < 9) {
            digits[i]++;
            *returnSize = digitsSize;
            int* res = (int*)malloc(sizeof(int) * digitsSize);
            for (int j = 0; j < digitsSize; j++) res[j] = digits[j];
            return res;
        }
        digits[i] = 0;
    }
    *returnSize = digitsSize + 1;
    int* res = (int*)malloc(sizeof(int) * (digitsSize + 1));
    res[0] = 1;
    for (int j = 1; j <= digitsSize; j++) res[j] = 0;
    return res;
}

```

# Go

## Sweet Spot

```go
func plusOne(digits []int) []int {
    // Time Complexity: O(n)
    // Memory Complexity: O(n)
    for i := len(digits) - 1; i >= 0; i-- {
        if digits[i] < 9 {
            digits[i]++
            return digits
        }
        digits[i] = 0
    }
    return append([]int{1}, digits...)
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun plusOne(digits: IntArray): IntArray {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        for (i in digits.indices.reversed()) {
            if (digits[i] < 9) {
                digits[i]++
                return digits
            }
            digits[i] = 0
        }
        val result = IntArray(digits.size + 1)
        result[0] = 1
        return result
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func plusOne(_ digits: [Int]) -> [Int] {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        var res = digits
        for i in (0..<res.count).reversed() {
            if res[i] < 9 {
                res[i] += 1
                return res
            }
            res[i] = 0
        }
        res.insert(1, at: 0)
        return res
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn plus_one(digits: Vec<i32>) -> Vec<i32> {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        let mut digits = digits;
        for i in (0..digits.len()).rev() {
            if digits[i] < 9 {
                digits[i] += 1;
                return digits;
            }
            digits[i] = 0;
        }
        let mut res = vec![0; digits.len() + 1];
        res[0] = 1;
        res
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[]} digits
# @return {Integer[]}
def plus_one(digits)
    # Time Complexity: O(n)
    # Memory Complexity: O(n)
    (digits.length - 1).step(0, -1) do |i|
        if digits[i] < 9
            digits[i] += 1
            return digits
        end
        digits[i] = 0
    end
    digits.unshift(1)
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[] $digits
     * @return Integer[]
     */
    function plusOne($digits) {
        // Time Complexity: O(n)
        // Memory Complexity: O(n)
        for ($i = count($digits) - 1; $i >= 0; $i--) {
            if ($digits[$i] < 9) {
                $digits[$i]++;
                return $digits;
            }
            $digits[$i] = 0;
        }
        array_unshift($digits, 1);
        return $digits;
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  List<int> plusOne(List<int> digits) {
    // Time Complexity: O(n)
    // Memory Complexity: O(n)
    for (int i = digits.length - 1; i >= 0; i--) {
      if (digits[i] < 9) {
        digits[i]++;
        return digits;
      }
      digits[i] = 0;
    }
    List<int> res = List.filled(digits.length + 1, 0);
    res[0] = 1;
    return res;
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def plusOne(digits: Array[Int]): Array[Int] = {
        // Time Complexity: O(n)
        // Space Complexity: O(n)
        var i = digits.length - 1
        var carry = true
        
        while (i >= 0 && carry) {
            if (digits(i) < 9) {
                digits(i) += 1
                carry = false
            } else {
                digits(i) = 0
                i -= 1
            }
        }
        
        if (carry) {
            val res = new Array[Int](digits.length + 1)
            res(0) = 1
            res
        } else {
            digits
        }
    }
}
```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec plus_one(digits :: [integer]) :: [integer]
  def plus_one(digits) do
    # Time Complexity: O(n)
    # Memory Complexity: O(n)
    digits
    |> Enum.reverse()
    |> increment()
    |> Enum.reverse()
  end

  defp increment([]), do: [1]

  defp increment([9 | t]) do
    [0 | increment(t)]
  end

  defp increment([h | t]) do
    [h + 1 | t]
  end
end
```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec plus_one(Digits :: [integer()]) -> [integer()].
plus_one(Digits) ->
    % Time Complexity: O(n)
    % Memory Complexity: O(n)
    lists:reverse(add_one(lists:reverse(Digits))).

add_one([]) -> 
    [1];
add_one([9 | T]) -> 
    [0 | add_one(T)];
add_one([H | T]) -> 
    [H + 1 | T].
```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (plus-one digits)
  (-> (listof exact-integer?) (listof exact-integer?))
  ; Time Complexity: O(n)
  ; Memory Complexity: O(n)
  (let loop ([rev-digits (reverse digits)])
    (cond
      [(empty? rev-digits) '(1)]
      [(< (car rev-digits) 9) 
       (reverse (cons (add1 (car rev-digits)) (cdr rev-digits)))]
      [else 
       (let ([res (loop (cdr rev-digits))])
         (if (= (length res) (length (cdr rev-digits)))
             (reverse (cons 0 (reverse res)))
             (append res '(0))))])))
```