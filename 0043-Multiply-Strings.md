# cpp

## Sweet Spot

```cpp
class Solution {
public:
    string multiply(string num1, string num2) {
        if (num1 == "0" || num2 == "0") return "0";
        int n = num1.size(), m = num2.size();
        string res(n + m, '0');
        for (int i = n - 1; i >= 0; i--) {
            for (int j = m - 1; j >= 0; j--) {
                int mul = (num1[i] - '0') * (num2[j] - '0');
                int sum = mul + (res[i + j + 1] - '0');
                res[i + j + 1] = (sum % 10) + '0';
                res[i + j] += (sum / 10);
            }
        }
        size_t startpos = res.find_first_not_of('0');
        if (string::npos != startpos) return res.substr(startpos);
        return "0";
    }
    // Time Complexity: O(n * m)
    // Memory Complexity: O(n + m)
};

```

# java

## Sweet Spot

```java
class Solution {
    public String multiply(String num1, String num2) {
        if (num1.equals("0") || num2.equals("0")) return "0";
        int n = num1.length(), m = num2.length();
        int[] pos = new int[n + m];
        for (int i = n - 1; i >= 0; i--) {
            for (int j = m - 1; j >= 0; j--) {
                int mul = (num1.charAt(i) - '0') * (num2.charAt(j) - '0');
                int p1 = i + j, p2 = i + j + 1;
                int sum = mul + pos[p2];
                pos[p1] += sum / 10;
                pos[p2] = sum % 10;
            }
        }
        StringBuilder sb = new StringBuilder();
        for (int p : pos) if (!(sb.length() == 0 && p == 0)) sb.append(p);
        return sb.length() == 0 ? "0" : sb.toString();
    }
    // Time Complexity: O(n * m)
    // Memory Complexity: O(n + m)
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def multiply(self, num1: str, num2: str) -> str:
        if num1 == "0" or num2 == "0": return "0"
        res = [0] * (len(num1) + len(num2))
        for i in range(len(num1) - 1, -1, -1):
            for j in range(len(num2) - 1, -1, -1):
                mul = (ord(num1[i]) - ord('0')) * (ord(num2[j]) - ord('0'))
                p1, p2 = i + j, i + j + 1
                total = mul + res[p2]
                res[p1] += total // 10
                res[p2] = total % 10
        ans = "".join(map(str, res))
        return ans.lstrip('0') or "0"
    # Time Complexity: O(n * m)
    # Memory Complexity: O(n + m)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def multiply(self, num1, num2):
        """
        :type num1: str
        :type num2: str
        :rtype: str
        """
        if num1 == "0" or num2 == "0": return "0"
        res = [0] * (len(num1) + len(num2))
        for i in xrange(len(num1) - 1, -1, -1):
            for j in xrange(len(num2) - 1, -1, -1):
                mul = (ord(num1[i]) - ord('0')) * (ord(num2[j]) - ord('0'))
                p1, p2 = i + j, i + j + 1
                total = mul + res[p2]
                res[p1] += total // 10
                res[p2] = total % 10
        ans = "".join(map(str, res))
        return ans.lstrip('0') or "0"
    # Time Complexity: O(n * m)
    # Memory Complexity: O(n + m)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {string} num1
 * @param {string} num2
 * @return {string}
 */
var multiply = function(num1, num2) {
    if (num1 === '0' || num2 === '0') return '0';
    let m = num1.length, n = num2.length;
    let res = new Array(m + n).fill(0);
    for (let i = m - 1; i >= 0; i--) {
        for (let j = n - 1; j >= 0; j--) {
            let mul = (num1[i] - '0') * (num2[j] - '0');
            let sum = mul + res[i + j + 1];
            res[i + j + 1] = sum % 10;
            res[i + j] += Math.floor(sum / 10);
        }
    }
    while (res[0] === 0) res.shift();
    return res.length > 0 ? res.join('') : '0';
};
// Time Complexity: O(n * m)
// Memory Complexity: O(n + m)

```

# Typescript

## Sweet Spot

```typescript
function multiply(num1: string, num2: string): string {
    if (num1 === '0' || num2 === '0') return '0';
    const m = num1.length, n = num2.length;
    const res = new Array(m + n).fill(0);
    for (let i = m - 1; i >= 0; i--) {
        for (let j = n - 1; j >= 0; j--) {
            const mul = (num1.charCodeAt(i) - 48) * (num2.charCodeAt(j) - 48);
            const sum = mul + res[i + j + 1];
            res[i + j + 1] = sum % 10;
            res[i + j] += Math.floor(sum / 10);
        }
    }
    const resultStr = res.join('').replace(/^0+/, '');
    return resultStr === '' ? '0' : resultStr;
};
// Time Complexity: O(n * m)
// Memory Complexity: O(n + m)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public string Multiply(string num1, string num2) {
        if (num1 == "0" || num2 == "0") return "0";
        int n = num1.Length, m = num2.Length;
        int[] res = new int[n + m];
        for (int i = n - 1; i >= 0; i--) {
            for (int j = m - 1; j >= 0; j--) {
                int mul = (num1[i] - '0') * (num2[j] - '0');
                int sum = mul + res[i + j + 1];
                res[i + j + 1] = sum % 10;
                res[i + j] += sum / 10;
            }
        }
        System.Text.StringBuilder sb = new System.Text.StringBuilder();
        foreach (int p in res) if (!(sb.Length == 0 && p == 0)) sb.Append(p);
        return sb.Length == 0 ? "0" : sb.ToString();
    }
    // Time Complexity: O(n * m)
    // Memory Complexity: O(n + m)
}

```

# C

## Sweet Spot

```c
char* multiply(char* num1, char* num2) {
    if (num1[0] == '0' || num2[0] == '0') return "0";
    int n = strlen(num1), m = strlen(num2);
    int* res = (int*)calloc(n + m, sizeof(int));
    for (int i = n - 1; i >= 0; i--) {
        for (int j = m - 1; j >= 0; j--) {
            int mul = (num1[i] - '0') * (num2[j] - '0');
            int sum = mul + res[i + j + 1];
            res[i + j + 1] = sum % 10;
            res[i + j] += sum / 10;
        }
    }
    char* result = (char*)malloc(n + m + 1);
    int idx = 0, k = 0;
    while (k < n + m && res[k] == 0) k++;
    while (k < n + m) result[idx++] = res[k++] + '0';
    result[idx] = '\0';
    free(res);
    return idx == 0 ? "0" : result;
}
// Time Complexity: O(n * m)
// Memory Complexity: O(n + m)

```

# Go

## Sweet Spot

```go
func multiply(num1 string, num2 string) string {
    if num1 == "0" || num2 == "0" { return "0" }
    n, m := len(num1), len(num2)
    res := make([]int, n+m)
    for i := n - 1; i >= 0; i-- {
        for j := m - 1; j >= 0; j-- {
            mul := int(num1[i]-'0') * int(num2[j]-'0')
            sum := mul + res[i+j+1]
            res[i+j+1] = sum % 10
            res[i+j] += sum / 10
        }
    }
    ans := ""
    for _, v := range res {
        if len(ans) == 0 && v == 0 { continue }
        ans += strconv.Itoa(v)
    }
    return ans
}
// Time Complexity: O(n * m)
// Memory Complexity: O(n + m)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun multiply(num1: String, num2: String): String {
        if (num1 == "0" || num2 == "0") return "0"
        val n = num1.length
        val m = num2.length
        val res = IntArray(n + m)
        for (i in n - 1 downTo 0) {
            for (j in m - 1 downTo 0) {
                val mul = (num1[i] - '0') * (num2[j] - '0')
                val sum = mul + res[i + j + 1]
                res[i + j + 1] = sum % 10
                res[i + j] += sum / 10
            }
        }
        val sb = StringBuilder()
        for (p in res) if (!(sb.isEmpty() && p == 0)) sb.append(p)
        return if (sb.isEmpty()) "0" else sb.toString()
    }
    // Time Complexity: O(n * m)
    // Memory Complexity: O(n + m)
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func multiply(_ num1: String, _ num2: String) -> String {
        if num1 == "0" || num2 == "0" { return "0" }
        let n1 = Array(num1.compactMap { $0.wholeNumberValue })
        let n2 = Array(num2.compactMap { $0.wholeNumberValue })
        var res = Array(repeating: 0, count: n1.count + n2.count)
        for i in (0..<n1.count).reversed() {
            for j in (0..<n2.count).reversed() {
                let mul = n1[i] * n2[j]
                let sum = mul + res[i + j + 1]
                res[i + j + 1] = sum % 10
                res[i + j] += sum / 10
            }
        }
        let result = res.map { String($0) }.joined()
        if let firstNonZero = result.firstIndex(where: { $0 != "0" }) {
            return String(result[firstNonZero...])
        }
        return "0"
    }
    // Time Complexity: O(n * m)
    // Memory Complexity: O(n + m)
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn multiply(num1: String, num2: String) -> String {
        if num1 == "0" || num2 == "0" { return "0".to_string(); }
        let n = num1.len();
        let m = num2.len();
        let mut res = vec![0; n + m];
        let num1_bytes = num1.as_bytes();
        let num2_bytes = num2.as_bytes();
        for i in (0..n).rev() {
            for j in (0..m).rev() {
                let mul = (num1_bytes[i] - b'0') * (num2_bytes[j] - b'0');
                let sum = mul as i32 + res[i + j + 1];
                res[i + j + 1] = sum % 10;
                res[i + j] += sum / 10;
            }
        }
        let mut result = String::new();
        for &digit in res.iter() {
            if !(result.is_empty() && digit == 0) {
                result.push((digit as u8 + b'0') as char);
            }
        }
        if result.is_empty() { "0".to_string() } else { result }
    }
    // Time Complexity: O(n * m)
    // Memory Complexity: O(n + m)
}

```

# ruby

## Sweet Spot

```ruby
# @param {String} num1
# @param {String} num2
# @return {String}
def multiply(num1, num2)
    return "0" if num1 == "0" || num2 == "0"
    res = Array.new(num1.length + num2.length, 0)
    (num1.length - 1).downto(0) do |i|
        (num2.length - 1).downto(0) do |j|
            mul = (num1[i].ord - '0'.ord) * (num2[j].ord - '0'.ord)
            sum = mul + res[i + j + 1]
            res[i + j + 1] = sum % 10
            res[i + j] += sum / 10
        end
    end
    ans = res.join('').sub(/^0+/, '')
    ans == '' ? "0" : ans
end
# Time Complexity: O(n * m)
# Memory Complexity: O(n + m)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param String $num1
     * @param String $num2
     * @return String
     */
    function multiply($num1, $num2) {
        if ($num1 === "0" || $num2 === "0") return "0";
        $n = strlen($num1);
        $m = strlen($num2);
        $res = array_fill(0, $n + $m, 0);
        for ($i = $n - 1; $i >= 0; $i--) {
            for ($j = $m - 1; $j >= 0; $j--) {
                $mul = (int)$num1[$i] * (int)$num2[$j];
                $sum = $mul + $res[$i + $j + 1];
                $res[$i + $j + 1] = $sum % 10;
                $res[$i + $j] += (int)($sum / 10);
            }
        }
        $ans = implode('', $res);
        $ans = ltrim($ans, '0');
        return $ans === '' ? "0" : $ans;
    }
    // Time Complexity: O(n * m)
    // Memory Complexity: O(n + m)
}

```

# dart

## Sweet Spot

```dart
class Solution {
  String multiply(String num1, String num2) {
    if (num1 == "0" || num2 == "0") return "0";
    List<int> res = List.filled(num1.length + num2.length, 0);
    for (int i = num1.length - 1; i >= 0; i--) {
      for (int j = num2.length - 1; j >= 0; j--) {
        int mul = (num1.codeUnitAt(i) - 48) * (num2.codeUnitAt(j) - 48);
        int sum = mul + res[i + j + 1];
        res[i + j + 1] = sum % 10;
        res[i + j] += sum ~/ 10;
      }
    }
    String ans = res.join('').replaceFirst(RegExp(r'^0+'), '');
    return ans == '' ? "0" : ans;
  }
  // Time Complexity: O(n * m)
  // Memory Complexity: O(n + m)
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def multiply(num1: String, num2: String): String = {
        if (num1 == "0" || num2 == "0") return "0"
        val n = num1.length
        val m = num2.length
        val res = Array.fill(n + m)(0)
        for (i <- n - 1 to 0 by -1) {
            for (j <- m - 1 to 0 by -1) {
                val mul = (num1(i) - '0') * (num2(j) - '0')
                val sum = mul + res(i + j + 1)
                res(i + j + 1) = sum % 10
                res(i + j) += sum / 10
            }
        }
        val sb = new StringBuilder()
        for (p <- res) if (!(sb.isEmpty && p == 0)) sb.append(p)
        if (sb.isEmpty) "0" else sb.toString()
    }
    // Time Complexity: O(n * m)
    // Memory Complexity: O(n + m)
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec multiply(num1 :: String.t, num2 :: String.t) :: String.t
  def multiply(num1, num2) do
    if num1 == "0" or num2 == "0" do
      "0"
    else
      n1 = String.to_charlist(num1) |> Enum.map(&(&1 - ?0)) |> List.to_tuple()
      n2 = String.to_charlist(num2) |> Enum.map(&(&1 - ?0)) |> List.to_tuple()
      s1 = tuple_size(n1)
      s2 = tuple_size(n2)
      res = :erlang.make_tuple(s1 + s2, 0)
      
      final_res = Enum.reduce((s1 - 1)..0, res, fn i, acc_i ->
        Enum.reduce((s2 - 1)..0, acc_i, fn j, acc_j ->
          mul = elem(n1, i) * elem(n2, j)
          p2 = i + j + 1
          p1 = i + j
          sum = mul + elem(acc_j, p2)
          acc_j 
          |> put_elem(p2, rem(sum, 10))
          |> put_elem(p1, elem(acc_j, p1) + div(sum, 10))
        end)
      end)
      
      final_res 
      |> Tuple.to_list() 
      |> Enum.drop_while(&(&1 == 0)) 
      |> Enum.map(&Integer.to_string/1) 
      |> Enum.join()
    end
  end
  # Time Complexity: O(n * m)
  # Memory Complexity: O(n + m)
end

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec multiply(Num1 :: unicode:unicode_binary(), Num2 :: unicode:unicode_binary()) -> unicode:unicode_binary().
multiply(Num1, Num2) when Num1 =:= <<"0">>; Num2 =:= <<"0">> -> <<"0">>;
multiply(Num1, Num2) ->
    L1 = [X - $0 || X <- binary_to_list(Num1)],
    L2 = [X - $0 || X <- binary_to_list(Num2)],
    S1 = length(L1),
    S2 = length(L2),
    T1 = list_to_tuple(L1),
    T2 = list_to_tuple(L2),
    Initial = list_to_tuple(lists:duplicate(S1 + S2, 0)),
    SumTuple = lists:foldl(fun(I, AccI) ->
        lists:foldl(fun(J, AccJ) ->
            Mul = element(I + 1, T1) * element(J + 1, T2),
            P = I + J + 2,
            setelement(P, AccJ, element(P, AccJ) + Mul)
        end, AccI, lists:seq(0, S2 - 1))
    end, Initial, lists:seq(0, S1 - 1)),
    {Carry, Digits} = lists:foldr(fun(X, {C, Acc}) ->
        Total = X + C,
        {Total div 10, [Total rem 10 | Acc]}
    end, {0, []}, tuple_to_list(SumTuple)),
    Final = case Carry of
        0 -> Digits;
        _ -> [Carry | Digits]
    end,
    Dropped = lists:dropwhile(fun(X) -> X =:= 0 end, Final),
    list_to_binary([X + $0 || X <- Dropped]).
% Time Complexity: O(n * m)
% Memory Complexity: O(n + m)
```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (multiply num1 num2)
  (-> string? string? string?)
  (if (or (equal? num1 "0") (equal? num2 "0"))
      "0"
      (let* ([n1 (string-length num1)]
             [n2 (string-length num2)]
             [res (make-vector (+ n1 n2) 0)])
        (for ([i (in-range (- n1 1) -1 -1)])
          (for ([j (in-range (- n2 1) -1 -1)])
            (let* ([mul (* (- (char->integer (string-ref num1 i)) 48)
                           (- (char->integer (string-ref num2 j)) 48))]
                   [p2 (+ i j 1)]
                   [p1 (+ i j)]
                   [sum (+ mul (vector-ref res p2))])
              (vector-set! res p2 (remainder sum 10))
              (vector-set! res p1 (+ (vector-ref res p1) (quotient sum 10))))))
        (let* ([res-list (vector->list res)]
               [trimmed (let loop ([lst res-list])
                          (if (and (not (null? lst)) (= (car lst) 0))
                              (loop (cdr lst))
                              lst))])
          (if (null? trimmed) "0"
              (apply string-append (map number->string trimmed)))))))
; Time Complexity: O(n * m)
; Memory Complexity: O(n + m)
```