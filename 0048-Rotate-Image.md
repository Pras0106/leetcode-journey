# cpp

## Sweet Spot

```cpp
class Solution {
public:
    void rotate(vector<vector<int>>& matrix) {
        int n = matrix.size();
        for (int i = 0; i < n / 2; ++i) {
            for (int j = i; j < n - i - 1; ++j) {
                int temp = matrix[i][j];
                matrix[i][j] = matrix[n - 1 - j][i];
                matrix[n - 1 - j][i] = matrix[n - 1 - i][n - 1 - j];
                matrix[n - 1 - i][n - 1 - j] = matrix[j][n - 1 - i];
                matrix[j][n - 1 - i] = temp;
            }
        }
    }
};
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# java

## Sweet Spot

```java
class Solution {
    public void rotate(int[][] matrix) {
        int n = matrix.length;
        for (int i = 0; i < n / 2; i++) {
            for (int j = i; j < n - i - 1; j++) {
                int temp = matrix[i][j];
                matrix[i][j] = matrix[n - 1 - j][i];
                matrix[n - 1 - j][i] = matrix[n - 1 - i][n - 1 - j];
                matrix[n - 1 - i][n - 1 - j] = matrix[j][n - 1 - i];
                matrix[j][n - 1 - i] = temp;
            }
        }
    }
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# python 3.14

## Sweet Spot

```python 3.14
class Solution:
    def rotate(self, matrix: List[List[int]]) -> None:
        """
        Do not return anything, modify matrix in-place instead.
        """
        n = len(matrix)
        for i in range(n // 2):
            for j in range(i, n - i - 1):
                temp = matrix[i][j]
                matrix[i][j] = matrix[n - 1 - j][i]
                matrix[n - 1 - j][i] = matrix[n - 1 - i][n - 1 - j]
                matrix[n - 1 - i][n - 1 - j] = matrix[j][n - 1 - i]
                matrix[j][n - 1 - i] = temp
# Time Complexity: O(n^2)
# Memory Complexity: O(1)

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
class Solution(object):
    def rotate(self, matrix):
        """
        :type matrix: List[List[int]]
        :rtype: None Do not return anything, modify matrix in-place instead.
        """
        n = len(matrix)
        for i in range(n / 2):
            for j in range(i, n - i - 1):
                temp = matrix[i][j]
                matrix[i][j] = matrix[n - 1 - j][i]
                matrix[n - 1 - j][i] = matrix[n - 1 - i][n - 1 - j]
                matrix[n - 1 - i][n - 1 - j] = matrix[j][n - 1 - i]
                matrix[j][n - 1 - i] = temp
# Time Complexity: O(n^2)
# Memory Complexity: O(1)

```

# JavaScript

## Sweet Spot

```javascript
/**
 * @param {number[][]} matrix
 * @return {void} Do not return anything, modify matrix in-place instead.
 */
var rotate = function(matrix) {
    const n = matrix.length;
    for (let i = 0; i < Math.floor(n / 2); i++) {
        for (let j = i; j < n - i - 1; j++) {
            let temp = matrix[i][j];
            matrix[i][j] = matrix[n - 1 - j][i];
            matrix[n - 1 - j][i] = matrix[n - 1 - i][n - 1 - j];
            matrix[n - 1 - i][n - 1 - j] = matrix[j][n - 1 - i];
            matrix[j][n - 1 - i] = temp;
        }
    }
};
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# Typescript

## Sweet Spot

```typescript
/**
 Do not return anything, modify matrix in-place instead.
 */
function rotate(matrix: number[][]): void {
    const n = matrix.length;
    for (let i = 0; i < Math.floor(n / 2); i++) {
        for (let j = i; j < n - i - 1; j++) {
            let temp = matrix[i][j];
            matrix[i][j] = matrix[n - 1 - j][i];
            matrix[n - 1 - j][i] = matrix[n - 1 - i][n - 1 - j];
            matrix[n - 1 - i][n - 1 - j] = matrix[j][n - 1 - i];
            matrix[j][n - 1 - i] = temp;
        }
    }
};
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# C#

## Sweet Spot

```c#
public class Solution {
    public void Rotate(int[][] matrix) {
        int n = matrix.Length;
        for (int i = 0; i < n / 2; i++) {
            for (int j = i; j < n - i - 1; j++) {
                int temp = matrix[i][j];
                matrix[i][j] = matrix[n - 1 - j][i];
                matrix[n - 1 - j][i] = matrix[n - 1 - i][n - 1 - j];
                matrix[n - 1 - i][n - 1 - j] = matrix[j][n - 1 - i];
                matrix[j][n - 1 - i] = temp;
            }
        }
    }
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# C

## Sweet Spot

```c
void rotate(int** matrix, int matrixSize, int* matrixColSize) {
    for (int i = 0; i < matrixSize / 2; i++) {
        for (int j = i; j < matrixSize - i - 1; j++) {
            int temp = matrix[i][j];
            matrix[i][j] = matrix[matrixSize - 1 - j][i];
            matrix[matrixSize - 1 - j][i] = matrix[matrixSize - 1 - i][matrixSize - 1 - j];
            matrix[matrixSize - 1 - i][matrixSize - 1 - j] = matrix[j][matrixSize - 1 - i];
            matrix[j][matrixSize - 1 - i] = temp;
        }
    }
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# Go

## Sweet Spot

```go
func rotate(matrix [][]int) {
    n := len(matrix)
    for i := 0; i < n/2; i++ {
        for j := i; j < n-i-1; j++ {
            temp := matrix[i][j]
            matrix[i][j] = matrix[n-1-j][i]
            matrix[n-1-j][i] = matrix[n-1-i][n-1-j]
            matrix[n-1-i][n-1-j] = matrix[j][n-1-i]
            matrix[j][n-1-i] = temp
        }
    }
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# Kotlin

## Sweet Spot

```kotlin
class Solution {
    fun rotate(matrix: Array<IntArray>): Unit {
        val n = matrix.size
        for (i in 0 until n / 2) {
            for (j in i until n - i - 1) {
                val temp = matrix[i][j]
                matrix[i][j] = matrix[n - 1 - j][i]
                matrix[n - 1 - j][i] = matrix[n - 1 - i][n - 1 - j]
                matrix[n - 1 - i][n - 1 - j] = matrix[j][n - 1 - i]
                matrix[j][n - 1 - i] = temp
            }
        }
    }
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# swift

## Sweet Spot

```swift
class Solution {
    func rotate(_ matrix: inout [[Int]]) {
        let n = matrix.count
        for i in 0..<n/2 {
            for j in i..<n-i-1 {
                let temp = matrix[i][j]
                matrix[i][j] = matrix[n - 1 - j][i]
                matrix[n - 1 - j][i] = matrix[n - 1 - i][n - 1 - j]
                matrix[n - 1 - i][n - 1 - j] = matrix[j][n - 1 - i]
                matrix[j][n - 1 - i] = temp
            }
        }
    }
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn rotate(matrix: &mut Vec<Vec<i32>>) {
        let n = matrix.len();
        for i in 0..n / 2 {
            for j in i..n - i - 1 {
                let temp = matrix[i][j];
                matrix[i][j] = matrix[n - 1 - j][i];
                matrix[n - 1 - j][i] = matrix[n - 1 - i][n - 1 - j];
                matrix[n - 1 - i][n - 1 - j] = matrix[j][n - 1 - i];
                matrix[j][n - 1 - i] = temp;
            }
        }
    }
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# ruby

## Sweet Spot

```ruby
# @param {Integer[][]} matrix
# @return {Void} Do not return anything, modify matrix in-place instead.
def rotate(matrix)
    n = matrix.length
    (0...n/2).each do |i|
        (i...n-i-1).each do |j|
            temp = matrix[i][j]
            matrix[i][j] = matrix[n - 1 - j][i]
            matrix[n - 1 - j][i] = matrix[n - 1 - i][n - 1 - j]
            matrix[n - 1 - i][n - 1 - j] = matrix[j][n - 1 - i]
            matrix[j][n - 1 - i] = temp
        end
    end
end
# Time Complexity: O(n^2)
# Memory Complexity: O(1)

```

# php

## Sweet Spot

```php
class Solution {

    /**
     * @param Integer[][] $matrix
     * @return NULL
     */
    function rotate(&$matrix) {
        $n = count($matrix);
        for ($i = 0; $i < floor($n / 2); $i++) {
            for ($j = $i; $j < $n - $i - 1; $j++) {
                $temp = $matrix[$i][$j];
                $matrix[$i][$j] = $matrix[$n - 1 - $j][$i];
                $matrix[$n - 1 - $j][$i] = $matrix[$n - 1 - $i][$n - 1 - $j];
                $matrix[$n - 1 - $i][$n - 1 - $j] = $matrix[$j][$n - 1 - $i];
                $matrix[$j][$n - 1 - $i] = $temp;
            }
        }
    }
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# dart

## Sweet Spot

```dart
class Solution {
  void rotate(List<List<int>> matrix) {
    int n = matrix.length;
    for (int i = 0; i < n ~/ 2; i++) {
      for (int j = i; j < n - i - 1; j++) {
        int temp = matrix[i][j];
        matrix[i][j] = matrix[n - 1 - j][i];
        matrix[n - 1 - j][i] = matrix[n - 1 - i][n - 1 - j];
        matrix[n - 1 - i][n - 1 - j] = matrix[j][n - 1 - i];
        matrix[j][n - 1 - i] = temp;
      }
    }
  }
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```

# scala 3.3.1

## Sweet Spot

```scala
object Solution {
    def rotate(matrix: Array[Array[Int]]): Unit = {
        val n = matrix.length
        for (i <- 0 until n / 2) {
            for (j <- i until n - i - 1) {
                val temp = matrix(i)(j)
                matrix(i)(j) = matrix(n - 1 - j)(i)
                matrix(n - 1 - j)(i) = matrix(n - 1 - i)(n - 1 - j)
                matrix(n - 1 - i)(n - 1 - j) = matrix(j)(n - 1 - i)
                matrix(j)(n - 1 - i) = temp
            }
        }
    }
}
// Time Complexity: O(n^2)
// Memory Complexity: O(1)

```