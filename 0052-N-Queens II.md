# cpp

## Sweet Spot

```cpp
class Solution {
public:
    int totalNQueens(int n) {
        int count = 0;
        int all = (1 << n) - 1;
        solve(0, 0, 0, all, count);
        return count;
    }

private:
    void solve(int row, int ld, int rd, int all, int& count) {
        if (row == all) {
            count++;
            return;
        }
        int pos = all & (~(row | ld | rd));
        while (pos) {
            int p = pos & -pos;
            pos -= p;
            solve(row | p, (ld | p) << 1, (rd | p) >> 1, all, count);
        }
    }
};
// Time Complexity: O(N!)
// Memory Complexity: O(N)

```

# java

## Sweet Spot

```java
class Solution {
    private int count = 0;

    public int totalNQueens(int n) {
        int all = (1 << n) - 1;
        solve(0, 0, 0, all);
        return count;
    }

    private void solve(int row, int ld, int rd, int all) {
        if (row == all) {
            count++;
            return;
        }
        int pos = all & (~(row | ld | rd));
        while (pos != 0) {
            int p = pos & -pos;
            pos ^= p;
            solve(row | p, (ld | p) << 1, (rd | p) >>> 1, all);
        }
    }
}
// Time Complexity: O(N!)
// Memory Complexity: O(N)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def totalNQueens(self, n: int) -> int:
        self.count = 0
        all_bits = (1 << n) - 1
        def solve(row, ld, rd):
            if row == all_bits:
                self.count += 1
                return
            pos = all_bits & (~(row | ld | rd))
            while pos:
                p = pos & -pos
                pos ^= p
                solve(row | p, (ld | p) << 1, (rd | p) >> 1)
        solve(0, 0, 0)
        return self.count
# Time Complexity: O(N!)
# Memory Complexity: O(N)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def totalNQueens(self, n):
        """
        :type n: int
        :rtype: int
        """
        self.count = 0
        all_bits = (1 << n) - 1
        def solve(row, ld, rd):
            if row == all_bits:
                self.count += 1
                return
            pos = all_bits & (~(row | ld | rd))
            while pos:
                p = pos & -pos
                pos ^= p
                solve(row | p, (ld | p) << 1, (rd | p) >> 1)
        solve(0, 0, 0)
        return self.count
# Time Complexity: O(N!)
# Memory Complexity: O(N)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number} n
 * @return {number}
 */
var totalNQueens = function(n) {
    let count = 0;
    const all = (1 << n) - 1;
    const solve = (row, ld, rd) => {
        if (row === all) {
            count++;
            return;
        }
        let pos = all & (~(row | ld | rd));
        while (pos > 0) {
            let p = pos & -pos;
            pos ^= p;
            solve(row | p, (ld | p) << 1, (rd | p) >>> 1);
        }
    };
    solve(0, 0, 0);
    return count;
};
// Time Complexity: O(N!)
// Memory Complexity: O(N)

```

# Typescript

## Sweet Spot

```typescript
function totalNQueens(n: number): number {
    let count = 0;
    const all = (1 << n) - 1;
    const solve = (row: number, ld: number, rd: number): void => {
        if (row === all) {
            count++;
            return;
        }
        let pos = all & (~(row | ld | rd));
        while (pos > 0) {
            const p = pos & -pos;
            pos ^= p;
            solve(row | p, (ld | p) << 1, (rd | p) >>> 1);
        }
    };
    solve(0, 0, 0);
    return count;
};
// Time Complexity: O(N!)
// Memory Complexity: O(N)

```

# C#

## Sweet Spot

```c#
public class Solution {
    private int count = 0;
    public int TotalNQueens(int n) {
        int all = (1 << n) - 1;
        Solve(0, 0, 0, all);
        return count;
    }
    private void Solve(int row, int ld, int rd, int all) {
        if (row == all) {
            count++;
            return;
        }
        int pos = all & (~(row | ld | rd));
        while (pos != 0) {
            int p = pos & -pos;
            pos ^= p;
            Solve(row | p, (ld | p) << 1, (rd | p) >> 1, all);
        }
    }
}
// Time Complexity: O(N!)
// Memory Complexity: O(N)

```

# C

## Sweet Spot

```c
void solve(int row, int ld, int rd, int all, int* count) {
    if (row == all) {
        (*count)++;
        return;
    }
    int pos = all & (~(row | ld | rd));
    while (pos) {
        int p = pos & -pos;
        pos ^= p;
        solve(row | p, (ld | p) << 1, (rd | p) >> 1, all, count);
    }
}

int totalNQueens(int n) {
    int count = 0;
    int all = (1 << n) - 1;
    solve(0, 0, 0, all, &count);
    return count;
}
// Time Complexity: O(N!)
// Memory Complexity: O(N)

```

# Go

## Sweet Spot

```go
func totalNQueens(n int) int {
    count := 0
    all := (1 << n) - 1
    var solve func(row, ld, rd int)
    solve = func(row, ld, rd int) {
        if row == all {
            count++
            return
        }
        pos := all & (^(row | ld | rd))
        for pos > 0 {
            p := pos & -pos
            pos ^= p
            solve(row|p, (ld|p)<<1, (rd|p)>>1)
        }
    }
    solve(0, 0, 0)
    return count
}
// Time Complexity: O(N!)
// Memory Complexity: O(N)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    private var count = 0
    fun totalNQueens(n: Int): Int {
        val all = (1 shl n) - 1
        solve(0, 0, 0, all)
        return count
    }
    private fun solve(row: Int, ld: Int, rd: Int, all: Int) {
        if (row == all) {
            count++
            return
        }
        var pos = all and (row or ld or rd).inv()
        while (pos != 0) {
            val p = pos and -pos
            pos = pos xor p
            solve(row or p, (ld or p) shl 1, (rd or p) ushr 1, all)
        }
    }
}
// Time Complexity: O(N!)
// Memory Complexity: O(N)

```

# swift

## Sweet Spot

```swift
class Solution {
    private var count = 0
    func totalNQueens(_ n: Int) -> Int {
        count = 0
        let all = (1 << n) - 1
        solve(0, 0, 0, all)
        return count
    }
    private func solve(_ row: Int, _ ld: Int, _ rd: Int, _ all: Int) {
        if row == all {
            count += 1
            return
        }
        var pos = all & (~(row | ld | rd))
        while pos != 0 {
            let p = pos & -pos
            pos ^= p
            solve(row | p, (ld | p) << 1, (rd | p) >> 1, all)
        }
    }
}
// Time Complexity: O(N!)
// Memory Complexity: O(N)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn total_n_queens(n: i32) -> i32 {
        let mut count = 0;
        let all = (1 << n) - 1;
        Self::solve(0, 0, 0, all, &mut count);
        count
    }
    fn solve(row: i32, ld: i32, rd: i32, all: i32, count: &mut i32) {
        if row == all {
            *count += 1;
            return;
        }
        let mut pos = all & !(row | ld | rd);
        while pos != 0 {
            let p = pos & -pos;
            pos ^= p;
            Self::solve(row | p, (ld | p) << 1, (rd | p) >> 1, all, count);
        }
    }
}
// Time Complexity: O(N!)
// Memory Complexity: O(N)

```

# ruby

## Sweet Spot

```ruby
# @param {Integer} n
# @return {Integer}
def total_n_queens(n)
  @count = 0
  all = (1 << n) - 1
  solve(0, 0, 0, all)
  @count
end

def solve(row, ld, rd, all)
  if row == all
    @count += 1
    return
  end
  pos = all & (~(row | ld | rd))
  while pos > 0
    p = pos & -pos
    pos ^= p
    solve(row | p, (ld | p) << 1, (rd | p) >> 1, all)
  end
end
# Time Complexity: O(N!)
# Memory Complexity: O(N)

```

# php

## Sweet Spot

```php
class Solution {
    private $count = 0;

    /**
     * @param Integer $n
     * @return Integer
     */
    function totalNQueens($n) {
        $this->count = 0;
        $all = (1 << $n) - 1;
        $this->solve(0, 0, 0, $all);
        return $this->count;
    }

    private function solve($row, $ld, $rd, $all) {
        if ($row == $all) {
            $this->count++;
            return;
        }

        $pos = $all & (~($row | $ld | $rd));
        while ($pos > 0) {
            $p = $pos & -$pos;
            $pos ^= $p;
            $this->solve($row | $p, ($ld | $p) << 1, ($rd | $p) >> 1, $all);
        }
    }
}
// Time Complexity: O(N!)
// Space Complexity: O(N)
```

# dart

## Sweet Spot

```dart
class Solution {
  int count = 0;
  int totalNQueens(int n) {
    count = 0;
    int all = (1 << n) - 1;
    solve(0, 0, 0, all);
    return count;
  }
  void solve(int row, int ld, int rd, int all) {
    if (row == all) {
      count++;
      return;
    }
    int pos = all & (~(row | ld | rd));
    while (pos > 0) {
      int p = pos & -pos;
      pos ^= p;
      solve(row | p, (ld | p) << 1, (rd | p) >> 1, all);
    }
  }
}
// Time Complexity: O(N!)
// Memory Complexity: O(N)

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def totalNQueens(n: Int): Int = {
        var count = 0
        val all = (1 << n) - 1
        def solve(row: Int, ld: Int, rd: Int): Unit = {
            if (row == all) {
                count += 1
            } else {
                var pos = all & ~(row | ld | rd)
                while (pos != 0) {
                    val p = pos & -pos
                    pos ^= p
                    solve(row | p, (ld | p) << 1, (rd | p) >>> 1)
                }
            }
        }
        solve(0, 0, 0)
        count
    }
}
// Time Complexity: O(N!)
// Memory Complexity: O(N)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  use Bitwise
  @spec total_n_queens(n :: integer) :: integer
  def total_n_queens(n) do
    all = (1 <<< n) - 1
    solve(0, 0, 0, all)
  end

  defp solve(row, ld, rd, all) when row == all, do: 1
  defp solve(row, ld, rd, all) do
    pos = all &&& bnot(row ||| ld ||| rd)
    iterate_pos(pos, row, ld, rd, all, 0)
  end

  defp iterate_pos(0, _, _, _, _, acc), do: acc
  defp iterate_pos(pos, row, ld, rd, all, acc) do
    p = pos &&& -pos
    new_acc = acc + solve(row ||| p, (ld ||| p) <<< 1, (rd ||| p) >>> 1, all)
    iterate_pos(pos ^^^ p, row, ld, rd, all, new_acc)
  end
end
# Time Complexity: O(N!)
# Memory Complexity: O(N)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec total_n_queens(N :: integer()) -> integer().
total_n_queens(N) ->
  All = (1 bsl N) - 1,
  solve(0, 0, 0, All).

solve(Row, _Ld, _Rd, All) when Row == All -> 1;
solve(Row, Ld, Rd, All) ->
  Pos = All band (bnot (Row bor Ld bor Rd)),
  iterate_pos(Pos, Row, Ld, Rd, All, 0).

iterate_pos(0, _Row, _Ld, _Rd, _All, Acc) -> Acc;
iterate_pos(Pos, Row, Ld, Rd, All, Acc) ->
  P = Pos band -Pos,
  Res = solve(Row bor P, (Ld bor P) bsl 1, (Rd bor P) bsr 1, All),
  iterate_pos(Pos bxor P, Row, Ld, Rd, All, Acc + Res).
% Time Complexity: O(N!)
% Memory Complexity: O(N)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (total-n-queens n)
  (-> exact-integer? exact-integer?)
  (let ([all (- (arithmetic-shift 1 n) 1)])
    (letrec ([solve (lambda (row ld rd)
                      (if (= row all)
                          1
                          (let loop ([pos (bitwise-and all (bitwise-not (bitwise-ior row ld rd)))]
                                     [acc 0])
                            (if (zero? pos)
                                acc
                                (let* ([p (bitwise-and pos (- pos))]
                                       [res (solve (bitwise-ior row p)
                                                   (arithmetic-shift (bitwise-ior ld p) 1)
                                                   (arithmetic-shift (bitwise-ior rd p) -1))])
                                  (loop (bitwise-xor pos p) (+ acc res)))))))])
      (solve 0 0 0))))
; Time Complexity: O(N!)
; Memory Complexity: O(N)

```