# cpp

## Sweet Spot

```cpp
class Solution {
public:
    string getPermutation(int n, int k) {
        // Time Complexity: O(n^2)
        // Memory Complexity: O(n)
        string res = "";
        vector<int> nums;
        int factorial = 1;
        for (int i = 1; i <= n; i++) {
            nums.push_back(i);
            if (i < n) factorial *= i;
        }
        k--;
        for (int i = n - 1; i >= 0; i--) {
            int index = k / factorial;
            res += to_string(nums[index]);
            nums.erase(nums.begin() + index);
            if (i > 0) k %= factorial, factorial /= i;
        }
        return res;
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public String getPermutation(int n, int k) {
        // Time Complexity: O(n^2)
        // Memory Complexity: O(n)
        StringBuilder res = new StringBuilder();
        List<Integer> nums = new ArrayList<>();
        int factorial = 1;
        for (int i = 1; i <= n; i++) {
            nums.add(i);
            if (i < n) factorial *= i;
        }
        k--;
        for (int i = n - 1; i >= 0; i--) {
            int index = k / factorial;
            res.append(nums.get(index));
            nums.remove(index);
            if (i > 0) {
                k %= factorial;
                factorial /= i;
            }
        }
        return res.toString();
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def getPermutation(self, n: int, k: int) -> str:
        # Time Complexity: O(n^2)
        # Memory Complexity: O(n)
        import math
        nums = [str(i) for i in range(1, n + 1)]
        k -= 1
        res = []
        factorial = math.factorial(n - 1)
        for i in range(n - 1, 0, -1):
            index = k // factorial
            res.append(nums.pop(index))
            k %= factorial
            factorial //= i
        res.append(nums[0])
        return "".join(res)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def getPermutation(self, n, k):
        """
        :type n: int
        :type k: int
        :rtype: str
        """
        # Time Complexity: O(n^2)
        # Memory Complexity: O(n)
        import math
        nums = [str(i) for i in range(1, n + 1)]
        k -= 1
        res = ""
        factorial = math.factorial(n - 1)
        for i in range(n - 1, 0, -1):
            index = k / factorial
            res += nums.pop(index)
            k %= factorial
            factorial /= i
        res += nums[0]
        return res

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number} n
 * @param {number} k
 * @return {string}
 */
var getPermutation = function(n, k) {
    // Time Complexity: O(n^2)
    // Memory Complexity: O(n)
    let res = "";
    let nums = [];
    let factorial = 1;
    for (let i = 1; i <= n; i++) {
        nums.push(i);
        if (i < n) factorial *= i;
    }
    k--;
    for (let i = n - 1; i >= 0; i--) {
        let index = Math.floor(k / factorial);
        res += nums[index];
        nums.splice(index, 1);
        if (i > 0) {
            k %= factorial;
            factorial /= i;
        }
    }
    return res;
};

```

# Typescript

## Sweet Spot

```typescript
function getPermutation(n: number, k: number): string {
    // Time Complexity: O(n^2)
    // Memory Complexity: O(n)
    let res: string = "";
    let nums: number[] = [];
    let factorial: number = 1;
    for (let i = 1; i <= n; i++) {
        nums.push(i);
        if (i < n) factorial *= i;
    }
    k--;
    for (let i = n - 1; i >= 0; i--) {
        let index = Math.floor(k / factorial);
        res += nums[index];
        nums.splice(index, 1);
        if (i > 0) {
            k %= factorial;
            factorial /= i;
        }
    }
    return res;
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public string GetPermutation(int n, int k) {
        // Time Complexity: O(n^2)
        // Memory Complexity: O(n)
        System.Text.StringBuilder res = new System.Text.StringBuilder();
        System.Collections.Generic.List<int> nums = new System.Collections.Generic.List<int>();
        int factorial = 1;
        for (int i = 1; i <= n; i++) {
            nums.Add(i);
            if (i < n) factorial *= i;
        }
        k--;
        for (int i = n - 1; i >= 0; i--) {
            int index = k / factorial;
            res.Append(nums[index]);
            nums.RemoveAt(index);
            if (i > 0) {
                k %= factorial;
                factorial /= i;
            }
        }
        return res.ToString();
    }
}

```

# C

## Sweet Spot

```c
char* getPermutation(int n, int k) {
    // Time Complexity: O(n^2)
    // Memory Complexity: O(n)
    char* res = (char*)malloc((n + 1) * sizeof(char));
    int nums[9];
    int factorial = 1;
    for (int i = 1; i <= n; i++) {
        nums[i - 1] = i;
        if (i < n) factorial *= i;
    }
    k--;
    for (int i = 0; i < n; i++) {
        int index = k / factorial;
        res[i] = nums[index] + '0';
        for (int j = index; j < n - i - 1; j++) {
            nums[j] = nums[j + 1];
        }
        if (n - 1 - i > 0) {
            k %= factorial;
            factorial /= (n - 1 - i);
        }
    }
    res[n] = '\0';
    return res;
}

```

# Go

## Sweet Spot

```go
func getPermutation(n int, k int) string {
    // Time Complexity: O(n^2)
    // Memory Complexity: O(n)
    nums := make([]int, n)
    factorial := 1
    for i := 1; i <= n; i++ {
        nums[i-1] = i
        if i < n {
            factorial *= i
        }
    }
    k--
    res := ""
    for i := n - 1; i >= 0; i-- {
        index := k / factorial
        res += strconv.Itoa(nums[index])
        nums = append(nums[:index], nums[index+1:]...)
        if i > 0 {
            k %= factorial
            factorial /= i
        }
    }
    return res
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun getPermutation(n: Int, k: Int): String {
        // Time Complexity: O(n^2)
        // Memory Complexity: O(n)
        val res = StringBuilder()
        val nums = mutableListOf<Int>()
        var factorial = 1
        for (i in 1..n) {
            nums.add(i)
            if (i < n) factorial *= i
        }
        var curK = k - 1
        var curFact = factorial
        for (i in n - 1 downTo 0) {
            val index = curK / curFact
            res.append(nums[index])
            nums.removeAt(index)
            if (i > 0) {
                curK %= curFact
                curFact /= i
            }
        }
        return res.toString()
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func getPermutation(_ n: Int, _ k: Int) -> String {
        // Time Complexity: O(n^2)
        // Memory Complexity: O(n)
        var res = ""
        var nums = Array(1...n)
        var factorial = (1..<n).reduce(1, *)
        var k = k - 1
        for i in (1...n).reversed() {
            let index = k / factorial
            res += String(nums.remove(at: index))
            if i > 1 {
                k %= factorial
                factorial /= (i - 1)
            }
        }
        return res
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn get_permutation(n: i32, k: i32) -> String {
        // Time Complexity: O(n^2)
        // Memory Complexity: O(n)
        let mut res = String::new();
        let mut nums: Vec<i32> = (1..=n).collect();
        let mut factorial = (1..n).product::<i32>();
        let mut k = k - 1;
        for i in (1..=n).rev() {
            let index = (k / factorial) as usize;
            res.push_str(&nums.remove(index).to_string());
            if i > 1 {
                k %= factorial;
                factorial /= i - 1;
            }
        }
        res
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer} n
# @param {Integer} k
# @return {String}
def get_permutation(n, k)
    # Time Complexity: O(n^2)
    # Memory Complexity: O(n)
    nums = (1..n).to_a
    factorial = (1...n).inject(1, :*) || 1
    k -= 1
    res = ""
    (n - 1).downto(0) do |i|
        index = k / factorial
        res += nums.delete_at(index).to_s
        if i > 0
            k %= factorial
            factorial /= i
        end
    end
    res
end
```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer $n
     * @param Integer $k
     * @return String
     */
    function getPermutation($n, $k) {
        // Time Complexity: O(n^2)
        // Memory Complexity: O(n)
        $nums = range(1, $n);
        $factorial = 1;
        for ($i = 1; $i < $n; $i++) $factorial *= $i;
        $k--;
        $res = "";
        for ($i = $n - 1; $i >= 0; $i--) {
            $index = intdiv($k, $factorial);
            $res .= array_splice($nums, $index, 1)[0];
            if ($i > 0) {
                $k %= $factorial;
                $factorial /= $i;
            }
        }
        return $res;
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  String getPermutation(int n, int k) {
    // Time Complexity: O(n^2)
    // Memory Complexity: O(n)
    List<int> nums = List.generate(n, (i) => i + 1);
    int factorial = 1;
    for (int i = 1; i < n; i++) factorial *= i;
    k--;
    String res = "";
    for (int i = n - 1; i >= 0; i--) {
      int index = k ~/ factorial;
      res += nums.removeAt(index).toString();
      if (i > 0) {
        k %= factorial;
        factorial ~/= i;
      }
    }
    return res;
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def getPermutation(n: Int, k: Int): String = {
        // Time Complexity: O(n^2)
        // Memory Complexity: O(n)
        var nums = (1 to n).toBuffer
        var factorial = (1 until n).product
        var curK = k - 1
        val res = new StringBuilder()
        for (i <- (n - 1) to 0 by -1) {
            val index = curK / factorial
            res.append(nums.remove(index))
            if (i > 0) {
                curK %= factorial
                factorial /= i
            }
        }
        res.toString()
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec get_permutation(n :: integer, k :: integer) :: String.t
  def get_permutation(n, k) do
    # Time Complexity: O(n^2)
    # Memory Complexity: O(n)
    nums = Enum.to_list(1..n)
    fact = Enum.reduce(1..max(1, n-1), 1, &*/2)
    solve(nums, k - 1, fact, n - 1, "")
  end

  defp solve(_, _, _, -1, acc), do: acc
  defp solve(nums, k, fact, i, acc) do
    index = div(k, fact)
    {val, rest} = List.pop_at(nums, index)
    new_k = if i > 0, do: rem(k, fact), else: 0
    new_fact = if i > 0, do: div(fact, i), else: 1
    solve(rest, new_k, new_fact, i - 1, acc <> Integer.to_string(val))
  end
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec get_permutation(N :: integer(), K :: integer()) -> unicode:unicode_binary().
get_permutation(N, K) ->
  % Time Complexity: O(N^2)
  % Memory Complexity: O(N)
  Nums = lists:seq(1, N),
  Fact = lists:foldl(fun(X, Acc) -> X * Acc end, 1, lists:seq(1, max(1, N-1))),
  solve(Nums, K - 1, Fact, N - 1, <<>>).

solve(_, _, _, -1, Acc) -> Acc;
solve(Nums, K, Fact, I, Acc) ->
  Index = K div Fact,
  Val = lists:nth(Index + 1, Nums),
  Rest = lists:delete(Val, Nums),
  {NewK, NewFact} = if I > 0 -> {K rem Fact, Fact div I}; true -> {0, 1} end,
  solve(Rest, NewK, NewFact, I - 1, <<Acc/binary, (integer_to_binary(Val))/binary>>).

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (get-permutation n k)
  (-> exact-integer? exact-integer? string?)
  ; Time Complexity: O(n^2)
  ; Memory Complexity: O(n)
  (let* ([factorial (for/fold ([acc 1]) ([i (in-range 1 n)]) (* acc i))]
         [nums (for/list ([i (in-range 1 (+ n 1))]) i)])
    (let loop ([i (- n 1)] [curr-k (- k 1)] [curr-fact factorial] [curr-nums nums] [acc ""])
      (if (< i 0)
          acc
          (let* ([index (quotient curr-k curr-fact)]
                 [val (list-ref curr-nums index)]
                 [next-nums (append (take curr-nums index) (drop curr-nums (+ index 1)))]
                 [next-k (if (> i 0) (remainder curr-k curr-fact) 0)]
                 [next-fact (if (> i 0) (quotient curr-fact i) 1)])
            (loop (- i 1) next-k next-fact next-nums (string-append acc (number->string val))))))))

```