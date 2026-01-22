# cpp

## Sweet Spot

```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 * int val;
 * ListNode *next;
 * ListNode() : val(0), next(nullptr) {}
 * ListNode(int x) : val(x), next(nullptr) {}
 * ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* rotateRight(ListNode* head, int k) {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        if (!head || !head->next || k == 0) return head;
        
        ListNode* tail = head;
        int length = 1;
        while (tail->next) {
            tail = tail->next;
            length++;
        }
        
        k %= length;
        if (k == 0) return head;
        
        ListNode* newTail = head;
        for (int i = 0; i < length - k - 1; i++) {
            newTail = newTail->next;
        }
        
        ListNode* newHead = newTail->next;
        newTail->next = nullptr;
        tail->next = head;
        
        return newHead;
    }
};

```

# java

## Sweet Spot

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 * int val;
 * ListNode next;
 * ListNode() {}
 * ListNode(int val) { this.val = val; }
 * ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode rotateRight(ListNode head, int k) {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        if (head == null || head.next == null || k == 0) return head;
        
        ListNode tail = head;
        int length = 1;
        while (tail.next != null) {
            tail = tail.next;
            length++;
        }
        
        k %= length;
        if (k == 0) return head;
        
        ListNode newTail = head;
        for (int i = 0; i < length - k - 1; i++) {
            newTail = newTail.next;
        }
        
        ListNode newHead = newTail.next;
        newTail.next = null;
        tail.next = head;
        
        return newHead;
    }
}

```

# python 3.14

## Sweet Spot

```python 3.14
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def rotateRight(self, head: Optional[ListNode], k: int) -> Optional[ListNode]:
        # Time Complexity: O(n)
        # Memory Complexity: O(1)
        if not head or not head.next or k == 0:
            return head
        
        length = 1
        tail = head
        while tail.next:
            tail = tail.next
            length += 1
            
        k %= length
        if k == 0:
            return head
            
        new_tail = head
        for _ in range(length - k - 1):
            new_tail = new_tail.next
            
        new_head = new_tail.next
        new_tail.next = None
        tail.next = head
        
        return new_head

```

# python 2.7.11

## Sweet Spot

```python 2.7.11
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution(object):
    def rotateRight(self, head, k):
        """
        :type head: Optional[ListNode]
        :type k: int
        :rtype: Optional[ListNode]
        """
        # Time Complexity: O(n)
        # Memory Complexity: O(1)
        if not head or not head.next or k == 0:
            return head
            
        length = 1
        tail = head
        while tail.next:
            tail = tail.next
            length += 1
            
        k %= length
        if k == 0:
            return head
            
        new_tail = head
        for _ in range(length - k - 1):
            new_tail = new_tail.next
            
        new_head = new_tail.next
        new_tail.next = None
        tail.next = head
        
        return new_head

```

# JavaScript

## Sweet Spot

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 * this.val = (val===undefined ? 0 : val)
 * this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @param {number} k
 * @return {ListNode}
 */
var rotateRight = function(head, k) {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    if (!head || !head.next || k === 0) return head;
    
    let length = 1;
    let tail = head;
    while (tail.next) {
        tail = tail.next;
        length++;
    }
    
    k = k % length;
    if (k === 0) return head;
    
    let newTail = head;
    for (let i = 0; i < length - k - 1; i++) {
        newTail = newTail.next;
    }
    
    let newHead = newTail.next;
    newTail.next = null;
    tail.next = head;
    
    return newHead;
};

```

# Typescript

## Sweet Spot

```typescript
/**
 * Definition for singly-linked list.
 * class ListNode {
 * val: number
 * next: ListNode | null
 * constructor(val?: number, next?: ListNode | null) {
 * this.val = (val===undefined ? 0 : val)
 * this.next = (next===undefined ? null : next)
 * }
 * }
 */

function rotateRight(head: ListNode | null, k: number): ListNode | null {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    if (!head || !head.next || k === 0) return head;
    
    let length = 1;
    let tail = head;
    while (tail.next) {
        tail = tail.next;
        length++;
    }
    
    k = k % length;
    if (k === 0) return head;
    
    let newTail = head;
    for (let i = 0; i < length - k - 1; i++) {
        newTail = newTail.next!;
    }
    
    let newHead = newTail.next;
    newTail.next = null;
    tail.next = head;
    
    return newHead;
};

```

# C#

## Sweet Spot

```c#
/**
 * Definition for singly-linked list.
 * public class ListNode {
 * public int val;
 * public ListNode next;
 * public ListNode(int val=0, ListNode next=null) {
 * this.val = val;
 * this.next = next;
 * }
 * }
 */
public class Solution {
    public ListNode RotateRight(ListNode head, int k) {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        if (head == null || head.next == null || k == 0) return head;
        
        ListNode tail = head;
        int length = 1;
        while (tail.next != null) {
            tail = tail.next;
            length++;
        }
        
        k %= length;
        if (k == 0) return head;
        
        ListNode newTail = head;
        for (int i = 0; i < length - k - 1; i++) {
            newTail = newTail.next;
        }
        
        ListNode newHead = newTail.next;
        newTail.next = null;
        tail.next = head;
        
        return newHead;
    }
}

```

# C

## Sweet Spot

```c
/**
 * Definition for singly-linked list.
 * struct ListNode {
 * int val;
 * struct ListNode *next;
 * };
 */
struct ListNode* rotateRight(struct ListNode* head, int k) {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    if (!head || !head->next || k == 0) return head;
    
    struct ListNode* tail = head;
    int length = 1;
    while (tail->next) {
        tail = tail->next;
        length++;
    }
    
    k %= length;
    if (k == 0) return head;
    
    struct ListNode* newTail = head;
    for (int i = 0; i < length - k - 1; i++) {
        newTail = newTail->next;
    }
    
    struct ListNode* newHead = newTail->next;
    newTail->next = NULL;
    tail->next = head;
    
    return newHead;
}

```

# Go

## Sweet Spot

```go
/**
 * Definition for singly-linked list.
 * type ListNode struct {
 * Val int
 * Next *ListNode
 * }
 */
func rotateRight(head *ListNode, k int) *ListNode {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    if head == nil || head.Next == nil || k == 0 {
        return head
    }
    
    length := 1
    tail := head
    for tail.Next != nil {
        tail = tail.Next
        length++
    }
    
    k %= length
    if k == 0 {
        return head
    }
    
    newTail := head
    for i := 0; i < length - k - 1; i++ {
        newTail = newTail.Next
    }
    
    newHead := newTail.Next
    newTail.Next = nil
    tail.Next = head
    
    return newHead
}

```

# Kotlin

## Sweet Spot

```kotlin
/**
 * Example:
 * var li = ListNode(5)
 * var v = li.`val`
 * Definition for singly-linked list.
 * class ListNode(var `val`: Int) {
 * var next: ListNode? = null
 * }
 */
class Solution {
    fun rotateRight(head: ListNode?, k: Int): ListNode? {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        if (head?.next == null || k == 0) return head
        
        var length = 1
        var tail = head
        while (tail?.next != null) {
            tail = tail.next
            length++
        }
        
        val actualK = k % length
        if (actualK == 0) return head
        
        var newTail = head
        for (i in 0 until length - actualK - 1) {
            newTail = newTail?.next
        }
        
        val newHead = newTail?.next
        newTail?.next = null
        tail?.next = head
        
        return newHead
    }
}

```

# swift

## Sweet Spot

```swift
/**
 * Definition for singly-linked list.
 * public class ListNode {
 * public var val: Int
 * public var next: ListNode?
 * public init() { self.val = 0; self.next = nil; }
 * public init(_ val: Int) { self.val = val; self.next = nil; }
 * public init(_ val: Int, _ next: ListNode?) { self.val = val; self.next = next; }
 * }
 */
class Solution {
    func rotateRight(_ head: ListNode?, _ k: Int) -> ListNode? {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        guard let head = head, let _ = head.next, k > 0 else {
            return head
        }
        
        var length = 1
        var tail = head
        while let next = tail.next {
            tail = next
            length += 1
        }
        
        let shift = k % length
        if shift == 0 {
            return head
        }
        
        var newTail = head
        for _ in 0..<(length - shift - 1) {
            newTail = newTail.next!
        }
        
        let newHead = newTail.next
        newTail.next = nil
        tail.next = head
        
        return newHead
    }
}

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn rotate_right(mut head: Option<Box<ListNode>>, k: i32) -> Option<Box<ListNode>> {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        if head.is_none() || k == 0 { return head; }
        
        let mut len = 0;
        let mut curr = &head;
        while let Some(node) = curr {
            curr = &node.next;
            len += 1;
        }
        
        let k = k % len;
        if k == 0 { return head; }
        
        let mut curr = head.as_mut();
        for _ in 0..(len - k - 1) {
            curr = curr.unwrap().next.as_mut();
        }
        
        let mut new_head = curr.unwrap().next.take();
        let mut tail = new_head.as_mut();
        while let Some(node) = tail {
            if node.next.is_none() {
                node.next = head;
                break;
            }
            tail = node.next.as_mut();
        }
        
        new_head
    }
}

```

# ruby

## Sweet Spot

```ruby
# Definition for singly-linked list.
# class ListNode
#     attr_accessor :val, :next
#     def initialize(val = 0, _next = nil)
#         @val = val
#         @next = _next
#     end
# end
# @param {ListNode} head
# @param {Integer} k
# @return {ListNode}
def rotate_right(head, k)
    # Time Complexity: O(n)
    # Memory Complexity: O(1)
    return head if head.nil? || head.next.nil? || k == 0
    
    length = 1
    tail = head
    while tail.next
        tail = tail.next
        length += 1
    end
    
    k %= length
    return head if k == 0
    
    new_tail = head
    (length - k - 1).times { new_tail = new_tail.next }
    
    new_head = new_tail.next
    new_tail.next = nil
    tail.next = head
    
    new_head
end

```

# php

## Sweet Spot

```php
/**
 * Definition for a singly-linked list.
 * class ListNode {
 * public $val = 0;
 * public $next = null;
 * function __construct($val = 0, $next = null) {
 * this->val = $val;
 * this->next = $next;
 * }
 * }
 */
class Solution {

    /**
     * @param ListNode $head
     * @param Integer $k
     * @return ListNode
     */
    function rotateRight($head, $k) {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        if ($head === null || $head->next === null || $k == 0) return $head;
        
        $length = 1;
        $tail = $head;
        while ($tail->next !== null) {
            $tail = $tail->next;
            $length++;
        }
        
        $k %= $length;
        if ($k == 0) return $head;
        
        $newTail = $head;
        for ($i = 0; $i < $length - $k - 1; $i++) {
            $newTail = $newTail->next;
        }
        
        $newHead = $newTail->next;
        $newTail->next = null;
        $tail->next = $head;
        
        return $newHead;
    }
}

```

# dart

## Sweet Spot

```dart
/**
 * Definition for singly-linked list.
 * class ListNode {
 * int val;
 * ListNode? next;
 * ListNode([this.val = 0, this.next]);
 * }
 */
class Solution {
  ListNode? rotateRight(ListNode? head, int k) {
    // Time Complexity: O(n)
    // Memory Complexity: O(1)
    if (head == null || head.next == null || k == 0) return head;
    
    int length = 1;
    ListNode? tail = head;
    while (tail?.next != null) {
      tail = tail?.next;
      length++;
    }
    
    k %= length;
    if (k == 0) return head;
    
    ListNode? newTail = head;
    for (int i = 0; i < length - k - 1; i++) {
      newTail = newTail?.next;
    }
    
    ListNode? newHead = newTail?.next;
    newTail?.next = null;
    tail?.next = head;
    
    return newHead;
  }
}

```

# scala 3.3.1

## Sweet Spot

```scala 3.3.1
/**
 * Definition for singly-linked list.
 * class ListNode(_x: Int = 0, _next: ListNode = null) {
 * var next: ListNode = _next
 * var x: Int = _x
 * }
 */
object Solution {
    def rotateRight(head: ListNode, k: Int): ListNode = {
        // Time Complexity: O(n)
        // Memory Complexity: O(1)
        if (head == null || head.next == null || k == 0) return head
        
        var length = 1
        var tail = head
        while (tail.next != null) {
            tail = tail.next
            length += 1
        }
        
        val actualK = k % length
        if (actualK == 0) return head
        
        var newTail = head
        for (i <- 0 until (length - actualK - 1)) {
            newTail = newTail.next
        }
        
        val newHead = newTail.next
        newTail.next = null
        tail.next = head
        
        newHead
    }
}

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec rotate_right(head :: ListNode.t | nil, k :: integer) :: ListNode.t | nil
  def rotate_right(nil, _), do: nil
  def rotate_right(head, k) do
    # Time Complexity: O(n)
    # Memory Complexity: O(n)
    len = get_len(head, 0)
    k = rem(k, len)

    if k == 0 do
      head
    else
      {p1, p2} = split(head, len - k)
      concat(p2, p1)
    end
  end

  defp get_len(nil, n), do: n
  defp get_len(node, n), do: get_len(node.next, n + 1)

  defp split(node, 1) do
    p2 = node.next
    {%{node | next: nil}, p2}
  end

  defp split(node, n) do
    {p1_rest, p2} = split(node.next, n - 1)
    {%{node | next: p1_rest}, p2}
  end

  defp concat(nil, p1), do: p1
  defp concat(node, p1), do: %{node | next: concat(node.next, p1)}
end
```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec rotate_right(Head :: #list_node{} | null, K :: integer()) -> #list_node{} | null.
rotate_right(null, _K) -> null;
rotate_right(Head, K) ->
    %% Time: O(N), Memory: O(N)
    Len = get_len(Head, 0),
    ActualK = K rem Len,
    case ActualK of
        0 -> Head;
        _ ->
            {Prefix, Suffix} = split(Head, Len - ActualK),
            append_nodes(Suffix, Prefix)
    end.

get_len(null, Acc) -> Acc;
get_len(#list_node{next = Next}, Acc) -> get_len(Next, Acc + 1).

split(Node, 0) -> {null, Node};
split(Node, N) ->
    {RestPrefix, Suffix} = split(Node#list_node.next, N - 1),
    {Node#list_node{next = RestPrefix}, Suffix}.

append_nodes(null, List2) -> List2;
append_nodes(Node, List2) ->
    Node#list_node{next = append_nodes(Node#list_node.next, List2)}.
```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (rotate-right head k)
  (-> (or/c list-node? #f) exact-integer? (or/c list-node? #f))
  ; Time Complexity: O(n)
  ; Memory Complexity: O(1)
  (cond
    [(or (not head) (not (list-node-next head)) (= k 0)) head]
    [else
     (let* ([len-info (let loop ([curr head] [n 1])
                        (if (list-node-next curr)
                            (loop (list-node-next curr) (+ n 1))
                            (cons curr n)))]
            [tail (car len-info)]
            [len (cdr len-info)]
            [actual-k (modulo k len)])
       (if (= actual-k 0)
           head
           (let* ([steps (- len actual-k 1)]
                  [new-tail (let loop ([curr head] [i 0])
                              (if (= i steps) curr (loop (list-node-next curr) (+ i 1))))]
                  [new-head (list-node-next new-tail)])
             (set-list-node-next! new-tail #f)
             (set-list-node-next! tail head)
             new-head)))]))

```