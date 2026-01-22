# cpp

## Sweet Spot

```cpp
class Solution {
public:
    void setZeroes(vector<vector<int>>& matrix) {
        // Time: O(m * n), Space: O(1)
        int m = matrix.size();
        int n = matrix[0].size();
        bool firstCol = false;
        for (int i = 0; i < m; i++) {
            if (matrix[i][0] == 0) firstCol = true;
            for (int j = 1; j < n; j++) {
                if (matrix[i][j] == 0) {
                    matrix[i][0] = 0;
                    matrix[0][j] = 0;
                }
            }
        }
        for (int i = m - 1; i >= 0; i--) {
            for (int j = n - 1; j >= 1; j--) {
                if (matrix[i][0] == 0 || matrix[0][j] == 0) {
                    matrix[i][j] = 0;
                }
            }
            if (firstCol) matrix[i][0] = 0;
        }
    }
};

```

# java

## Sweet Spot

```java
class Solution {
    public void setZeroes(int[][] matrix) {
        // Time: O(m * n), Space: O(1)
        int m = matrix.length;
        int n = matrix[0].length;
        boolean firstCol = false;
        for (int i = 0; i < m; i++) {
            if (matrix[i][0] == 0) firstCol = true;
            for (int j = 1; j < n; j++) {
                if (matrix[i][j] == 0) {
                    matrix[i][0] = 0;
                    matrix[0][j] = 0;
                }
            }
        }
        for (int i = m - 1; i >= 0; i--) {
            for (int j = n - 1; j >= 1; j--) {
                if (matrix[i][0] == 0 || matrix[0][j] == 0) {
                    matrix[i][j] = 0;
                }
            }
            if (firstCol) matrix[i][0] = 0;
        }
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def setZeroes(self, matrix: List[List[int]]) -> None:
        """
        Do not return anything, modify matrix in-place instead.
        # Time: O(m * n), Space: O(1)
        """
        m, n = len(matrix), len(matrix[0])
        first_col = False
        for i in range(m):
            if matrix[i][0] == 0:
                first_col = True
            for j in range(1, n):
                if matrix[i][j] == 0:
                    matrix[i][0] = 0
                    matrix[0][j] = 0
        for i in range(m - 1, -1, -1):
            for j in range(n - 1, 0, -1):
                if matrix[i][0] == 0 or matrix[0][j] == 0:
                    matrix[i][j] = 0
            if first_col:
                matrix[i][0] = 0

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def setZeroes(self, matrix):
        """
        :type matrix: List[List[int]]
        :rtype: None Do not return anything, modify matrix in-place instead.
        # Time: O(m * n), Space: O(1)
        """
        m = len(matrix)
        n = len(matrix[0])
        first_col = False
        for i in range(m):
            if matrix[i][0] == 0:
                first_col = True
            for j in range(1, n):
                if matrix[i][j] == 0:
                    matrix[i][0] = 0
                    matrix[0][j] = 0
        for i in range(m - 1, -1, -1):
            for j in range(n - 1, 0, -1):
                if matrix[i][0] == 0 or matrix[0][j] == 0:
                    matrix[i][j] = 0
            if first_col:
                matrix[i][0] = 0

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[][]} matrix
 * @return {void} Do not return anything, modify matrix in-place instead.
 */
var setZeroes = function(matrix) {
    // Time: O(m * n), Space: O(1)
    let m = matrix.length;
    let n = matrix[0].length;
    let firstCol = false;
    for (let i = 0; i < m; i++) {
        if (matrix[i][0] === 0) firstCol = true;
        for (let j = 1; j < n; j++) {
            if (matrix[i][j] === 0) {
                matrix[i][0] = 0;
                matrix[0][j] = 0;
            }
        }
    }
    for (let i = m - 1; i >= 0; i--) {
        for (let j = n - 1; j >= 1; j--) {
            if (matrix[i][0] === 0 || matrix[0][j] === 0) {
                matrix[i][j] = 0;
            }
        }
        if (firstCol) matrix[i][0] = 0;
    }
};

```

# Typescript

## Sweet Spot

```typescript
/**
 Do not return anything, modify matrix in-place instead.
 */
function setZeroes(matrix: number[][]): void {
    // Time: O(m * n), Space: O(1)
    const m = matrix.length;
    const n = matrix[0].length;
    let firstCol = false;
    for (let i = 0; i < m; i++) {
        if (matrix[i][0] === 0) firstCol = true;
        for (let j = 1; j < n; j++) {
            if (matrix[i][j] === 0) {
                matrix[i][0] = 0;
                matrix[0][j] = 0;
            }
        }
    }
    for (let i = m - 1; i >= 0; i--) {
        for (let j = n - 1; j >= 1; j--) {
            if (matrix[i][0] === 0 || matrix[0][j] === 0) {
                matrix[i][j] = 0;
            }
        }
        if (firstCol) matrix[i][0] = 0;
    }
};

```

# C#

## Sweet Spot

```c#
public class Solution {
    public void SetZeroes(int[][] matrix) {
        // Time: O(m * n), Space: O(1)
        int m = matrix.Length;
        int n = matrix[0].Length;
        bool firstCol = false;
        for (int i = 0; i < m; i++) {
            if (matrix[i][0] == 0) firstCol = true;
            for (int j = 1; j < n; j++) {
                if (matrix[i][j] == 0) {
                    matrix[i][0] = 0;
                    matrix[0][j] = 0;
                }
            }
        }
        for (int i = m - 1; i >= 0; i--) {
            for (int j = n - 1; j >= 1; j--) {
                if (matrix[i][0] == 0 || matrix[0][j] == 0) {
                    matrix[i][j] = 0;
                }
            }
            if (firstCol) matrix[i][0] = 0;
        }
    }
}

```

# C

## Sweet Spot

```c
void setZeroes(int** matrix, int matrixSize, int* matrixColSize) {
    // Time: O(m * n), Space: O(1)
    int m = matrixSize;
    int n = matrixColSize[0];
    int firstCol = 0;
    for (int i = 0; i < m; i++) {
        if (matrix[i][0] == 0) firstCol = 1;
        for (int j = 1; j < n; j++) {
            if (matrix[i][j] == 0) {
                matrix[i][0] = 0;
                matrix[0][j] = 0;
            }
        }
    }
    for (int i = m - 1; i >= 0; i--) {
        for (int j = n - 1; j >= 1; j--) {
            if (matrix[i][0] == 0 || matrix[0][j] == 0) {
                matrix[i][j] = 0;
            }
        }
        if (firstCol) matrix[i][0] = 0;
    }
}

```

# Go

## Sweet Spot

```go
func setZeroes(matrix [][]int)  {
    // Time: O(m * n), Space: O(1)
    m := len(matrix)
    n := len(matrix[0])
    firstCol := false
    for i := 0; i < m; i++ {
        if matrix[i][0] == 0 {
            firstCol = true
        }
        for j := 1; j < n; j++ {
            if matrix[i][j] == 0 {
                matrix[i][0] = 0
                matrix[0][j] = 0
            }
        }
    }
    for i := m - 1; i >= 0; i-- {
        for j := n - 1; j >= 1; j-- {
            if matrix[i][0] == 0 || matrix[0][j] == 0 {
                matrix[i][j] = 0
            }
        }
        if firstCol {
            matrix[i][0] = 0
        }
    }
}

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun setZeroes(matrix: Array<IntArray>): Unit {
        // Time: O(m * n), Space: O(1)
        val m = matrix.size
        val n = matrix[0].size
        var firstCol = false
        for (i in 0 until m) {
            if (matrix[i][0] == 0) firstCol = true
            for (j in 1 until n) {
                if (matrix[i][j] == 0) {
                    matrix[i][0] = 0
                    matrix[0][j] = 0
                }
            }
        }
        for (i in m - 1 downTo 0) {
            for (j in n - 1 downTo 1) {
                if (matrix[i][0] == 0 || matrix[0][j] == 0) {
                    matrix[i][j] = 0
                }
            }
            if (firstCol) matrix[i][0] = 0
        }
    }
}

```

# swift

## Sweet Spot

```swift
class Solution {
    func setZeroes(_ matrix: inout [[Int]]) {
        // Time: O(m * n), Space: O(1)
        let m = matrix.count
        let n = matrix[0].count
        var firstCol = false
        for i in 0..<m {
            if matrix[i][0] == 0 {
                firstCol = true
            }
            for j in 1..<n {
                if matrix[i][j] == 0 {
                    matrix[i][0] = 0
                    matrix[0][j] = 0
                }
            }
        }
        for i in (0..<m).reversed() {
            for j in (1..<n).reversed() {
                if matrix[i][0] == 0 || matrix[0][j] == 0 {
                    matrix[i][j] = 0
                }
            }
            if firstCol {
                matrix[i][0] = 0
            }
        }
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn set_zeroes(matrix: &mut Vec<Vec<i32>>) {
        // Time: O(m * n), Space: O(1)
        let m = matrix.len();
        let n = matrix[0].len();
        let mut first_col = false;
        for i in 0..m {
            if matrix[i][0] == 0 {
                first_col = true;
            }
            for j in 1..n {
                if matrix[i][j] == 0 {
                    matrix[i][0] = 0;
                    matrix[0][j] = 0;
                }
            }
        }
        for i in (0..m).rev() {
            for j in (1..n).rev() {
                if matrix[i][0] == 0 || matrix[0][j] == 0 {
                    matrix[i][j] = 0;
                }
            }
            if first_col {
                matrix[i][0] = 0;
            }
        }
    }
}

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[][]} matrix
# @return {Void} Do not return anything, modify matrix in-place instead.
def set_zeroes(matrix)
    # Time: O(m * n), Space: O(1)
    m = matrix.length
    n = matrix[0].length
    first_col = false
    (0...m).each do |i|
        first_col = true if matrix[i][0] == 0
        (1...n).each do |j|
            if matrix[i][j] == 0
                matrix[i][0] = 0
                matrix[0][j] = 0
            end
        end
    end
    (m - 1).step(0, -1).each do |i|
        (n - 1).step(1, -1).each do |j|
            matrix[i][j] = 0 if matrix[i][0] == 0 || matrix[0][j] == 0
        end
        matrix[i][0] = 0 if first_col
    end
end

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[][] $matrix
     * @return NULL
     */
    function setZeroes(&$matrix) {
        // Time: O(m * n), Space: O(1)
        $m = count($matrix);
        $n = count($matrix[0]);
        $firstCol = false;
        for ($i = 0; $i < $m; $i++) {
            if ($matrix[$i][0] === 0) $firstCol = true;
            for ($j = 1; $j < $n; $j++) {
                if ($matrix[$i][$j] === 0) {
                    $matrix[$i][0] = 0;
                    $matrix[0][$j] = 0;
                }
            }
        }
        for ($i = $m - 1; $i >= 0; $i--) {
            for ($j = $n - 1; $j >= 1; $j--) {
                if ($matrix[$i][0] === 0 || $matrix[0][$j] === 0) {
                    $matrix[$i][$j] = 0;
                }
            }
            if ($firstCol) $matrix[$i][0] = 0;
        }
    }
}

```

# dart

## Sweet Spot

```dart
class Solution {
  void setZeroes(List<List<int>> matrix) {
    // Time: O(m * n), Space: O(1)
    int m = matrix.length;
    int n = matrix[0].length;
    bool firstCol = false;
    for (int i = 0; i < m; i++) {
      if (matrix[i][0] == 0) firstCol = true;
      for (int j = 1; j < n; j++) {
        if (matrix[i][j] == 0) {
          matrix[i][0] = 0;
          matrix[0][j] = 0;
        }
      }
    }
    for (int i = m - 1; i >= 0; i--) {
      for (int j = n - 1; j >= 1; j--) {
        if (matrix[i][0] == 0 || matrix[0][j] == 0) {
          matrix[i][j] = 0;
        }
      }
      if (firstCol) matrix[i][0] = 0;
    }
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
object Solution {
    def setZeroes(matrix: Array[Array[Int]]): Unit = {
        // Time: O(m * n), Space: O(1)
        val m = matrix.length
        val n = matrix(0).length
        var firstCol = false
        for (i <- 0 until m) {
            if (matrix(i)(0) == 0) firstCol = true
            for (j <- 1 until n) {
                if (matrix(i)(j) == 0) {
                    matrix(i)(0) = 0
                    matrix(0)(j) = 0
                }
            }
        }
        for (i <- m - 1 to 0 by -1) {
            for (j <- n - 1 to 1 by -1) {
                if (matrix(i)(0) == 0 || matrix(0)(j) == 0) {
                    matrix(i)(j) = 0
                }
            }
            if (firstCol) matrix(i)(0) = 0
        }
    }
}

```