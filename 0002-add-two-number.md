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
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode dummy(0);
        ListNode* curr = &dummy;
        int carry = 0;
        while (l1 || l2 || carry) {
            int sum = (l1 ? l1->val : 0) + (l2 ? l2->val : 0) + carry;
            carry = sum / 10;
            curr->next = new ListNode(sum % 10);
            curr = curr->next;
            if (l1) l1 = l1->next;
            if (l2) l2 = l2->next;
        }
        return dummy.next;
    }
};
// Time Complexity: O(max(N, M))
// Memory Complexity: O(max(N, M))

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
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dummyHead = new ListNode(0);
        ListNode curr = dummyHead;
        int carry = 0;
        while (l1 != null || l2 != null || carry != 0) {
            int x = (l1 != null) ? l1.val : 0;
            int y = (l2 != null) ? l2.val : 0;
            int sum = carry + x + y;
            carry = sum / 10;
            curr.next = new ListNode(sum % 10);
            curr = curr.next;
            if (l1 != null) l1 = l1.next;
            if (l2 != null) l2 = l2.next;
        }
        return dummyHead.next;
    }
}
// Time Complexity: O(max(N, M))
// Memory Complexity: O(max(N, M))

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
    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
        dummy = ListNode(0)
        curr = dummy
        carry = 0
        while l1 or l2 or carry:
            v1 = l1.val if l1 else 0
            v2 = l2.val if l2 else 0
            val = v1 + v2 + carry
            carry = val // 10
            val = val % 10
            curr.next = ListNode(val)
            curr = curr.next
            l1 = l1.next if l1 else None
            l2 = l2.next if l2 else None
        return dummy.next
# Time Complexity: O(max(N, M))
# Memory Complexity: O(max(N, M))

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
    def addTwoNumbers(self, l1, l2):
        """
        :type l1: Optional[ListNode]
        :type l2: Optional[ListNode]
        :rtype: Optional[ListNode]
        """
        dummy = ListNode(0)
        curr = dummy
        carry = 0
        while l1 or l2 or carry:
            v1 = l1.val if l1 else 0
            v2 = l2.val if l2 else 0
            val = v1 + v2 + carry
            carry = val / 10
            val = val % 10
            curr.next = ListNode(val)
            curr = curr.next
            l1 = l1.next if l1 else None
            l2 = l2.next if l2 else None
        return dummy.next
# Time Complexity: O(max(N, M))
# Memory Complexity: O(max(N, M))

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
 * @param {ListNode} l1
 * @param {ListNode} l2
 * @return {ListNode}
 */
var addTwoNumbers = function(l1, l2) {
    let dummy = new ListNode(0);
    let curr = dummy;
    let carry = 0;
    while (l1 !== null || l2 !== null || carry > 0) {
        let v1 = l1 !== null ? l1.val : 0;
        let v2 = l2 !== null ? l2.val : 0;
        let sum = v1 + v2 + carry;
        carry = Math.floor(sum / 10);
        curr.next = new ListNode(sum % 10);
        curr = curr.next;
        if (l1 !== null) l1 = l1.next;
        if (l2 !== null) l2 = l2.next;
    }
    return dummy.next;
};
// Time Complexity: O(max(N, M))
// Memory Complexity: O(max(N, M))

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

function addTwoNumbers(l1: ListNode | null, l2: ListNode | null): ListNode | null {
    let dummy = new ListNode(0);
    let curr = dummy;
    let carry = 0;
    while (l1 !== null || l2 !== null || carry > 0) {
        let v1 = l1 !== null ? l1.val : 0;
        let v2 = l2 !== null ? l2.val : 0;
        let sum = v1 + v2 + carry;
        carry = Math.floor(sum / 10);
        curr.next = new ListNode(sum % 10);
        curr = curr.next;
        if (l1 !== null) l1 = l1.next;
        if (l2 !== null) l2 = l2.next;
    }
    return dummy.next;
};
// Time Complexity: O(max(N, M))
// Memory Complexity: O(max(N, M))

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
    public ListNode AddTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dummy = new ListNode(0);
        ListNode curr = dummy;
        int carry = 0;
        while (l1 != null || l2 != null || carry != 0) {
            int v1 = (l1 != null) ? l1.val : 0;
            int v2 = (l2 != null) ? l2.val : 0;
            int sum = v1 + v2 + carry;
            carry = sum / 10;
            curr.next = new ListNode(sum % 10);
            curr = curr.next;
            if (l1 != null) l1 = l1.next;
            if (l2 != null) l2 = l2.next;
        }
        return dummy.next;
    }
}
// Time Complexity: O(max(N, M))
// Memory Complexity: O(max(N, M))

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
struct ListNode* addTwoNumbers(struct ListNode* l1, struct ListNode* l2) {
    struct ListNode dummy;
    struct ListNode* curr = &dummy;
    int carry = 0;
    while (l1 || l2 || carry) {
        int v1 = l1 ? l1->val : 0;
        int v2 = l2 ? l2->val : 0;
        int sum = v1 + v2 + carry;
        carry = sum / 10;
        struct ListNode* node = (struct ListNode*)malloc(sizeof(struct ListNode));
        node->val = sum % 10;
        node->next = NULL;
        curr->next = node;
        curr = curr->next;
        if (l1) l1 = l1->next;
        if (l2) l2 = l2->next;
    }
    return dummy.next;
}
// Time Complexity: O(max(N, M))
// Memory Complexity: O(max(N, M))

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
func addTwoNumbers(l1 *ListNode, l2 *ListNode) *ListNode {
    dummy := &ListNode{}
    curr := dummy
    carry := 0
    for l1 != nil || l2 != nil || carry != 0 {
        v1, v2 := 0, 0
        if l1 != nil {
            v1 = l1.Val
            l1 = l1.Next
        }
        if l2 != nil {
            v2 = l2.Val
            l2 = l2.Next
        }
        sum := v1 + v2 + carry
        carry = sum / 10
        curr.Next = &ListNode{Val: sum % 10}
        curr = curr.Next
    }
    return dummy.Next
}
// Time Complexity: O(max(N, M))
// Memory Complexity: O(max(N, M))

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
    fun addTwoNumbers(l1: ListNode?, l2: ListNode?): ListNode? {
        val dummy = ListNode(0)
        var curr = dummy
        var p1 = l1
        var p2 = l2
        var carry = 0
        while (p1 != null || p2 != null || carry != 0) {
            val v1 = p1?.`val` ?: 0
            val v2 = p2?.`val` ?: 0
            val sum = v1 + v2 + carry
            carry = sum / 10
            curr.next = ListNode(sum % 10)
            curr = curr.next!!
            p1 = p1?.next
            p2 = p2?.next
        }
        return dummy.next
    }
}
// Time Complexity: O(max(N, M))
// Memory Complexity: O(max(N, M))

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
    func addTwoNumbers(_ l1: ListNode?, _ l2: ListNode?) -> ListNode? {
        let dummy = ListNode(0)
        var curr = dummy
        var p1 = l1
        var p2 = l2
        var carry = 0
        while p1 != nil || p2 != nil || carry != 0 {
            let v1 = p1?.val ?? 0
            let v2 = p2?.val ?? 0
            let sum = v1 + v2 + carry
            carry = sum / 10
            curr.next = ListNode(sum % 10)
            curr = curr.next!
            p1 = p1?.next
            p2 = p2?.next
        }
        return dummy.next
    }
}
// Time Complexity: O(max(N, M))
// Memory Complexity: O(max(N, M))

```

# rust

## Sweet Spot

```rust
// Definition for singly-linked list.
// #[derive(PartialEq, Eq, Clone, Debug)]
// pub struct ListNode {
//   pub val: i32,
//   pub next: Option<Box<ListNode>>
// }
// 
// impl ListNode {
//   #[inline]
//   fn new(val: i32) -> Self {
//     ListNode {
//       next: None,
//       val
//     }
//   }
// }
impl Solution {
    pub fn add_two_numbers(l1: Option<Box<ListNode>>, l2: Option<Box<ListNode>>) -> Option<Box<ListNode>> {
        let mut dummy = ListNode::new(0);
        let mut curr = &mut dummy;
        let mut p1 = l1;
        let mut p2 = l2;
        let mut carry = 0;
        while p1.is_some() || p2.is_some() || carry != 0 {
            let mut sum = carry;
            if let Some(node) = p1 {
                sum += node.val;
                p1 = node.next;
            }
            if let Some(node) = p2 {
                sum += node.val;
                p2 = node.next;
            }
            carry = sum / 10;
            curr.next = Some(Box::new(ListNode::new(sum % 10)));
            curr = curr.next.as_mut().unwrap();
        }
        dummy.next
    }
}
// Time Complexity: O(max(N, M))
// Memory Complexity: O(max(N, M))

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
# @param {ListNode} l1
# @param {ListNode} l2
# @return {ListNode}
def add_two_numbers(l1, l2)
    dummy = ListNode.new(0)
    curr = dummy
    carry = 0
    while l1 || l2 || carry > 0
        v1 = l1 ? l1.val : 0
        v2 = l2 ? l2.val : 0
        sum = v1 + v2 + carry
        carry = sum / 10
        curr.next = ListNode.new(sum % 10)
        curr = curr.next
        l1 = l1.next if l1
        l2 = l2.next if l2
    end
    dummy.next
end
# Time Complexity: O(max(N, M))
# Memory Complexity: O(max(N, M))

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
 * $this->val = $val;
 * $this->next = $next;
 * }
 * }
 */
class Solution {

    /**
     * @param ListNode $l1
     * @param ListNode $l2
     * @return ListNode
     */
    function addTwoNumbers($l1, $l2) {
        $dummy = new ListNode(0);
        $curr = $dummy;
        $carry = 0;
        while ($l1 !== null || $l2 !== null || $carry > 0) {
            $v1 = $l1 !== null ? $l1->val : 0;
            $v2 = $l2 !== null ? $l2->val : 0;
            $sum = $v1 + $v2 + $carry;
            $carry = (int)($sum / 10);
            $curr->next = new ListNode($sum % 10);
            $curr = $curr->next;
            if ($l1 !== null) $l1 = $l1->next;
            if ($l2 !== null) $l2 = $l2->next;
        }
        return $dummy->next;
    }
}
// Time Complexity: O(max(N, M))
// Memory Complexity: O(max(N, M))

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
  ListNode? addTwoNumbers(ListNode? l1, ListNode? l2) {
    ListNode dummy = ListNode(0);
    ListNode curr = dummy;
    int carry = 0;
    while (l1 != null || l2 != null || carry != 0) {
      int v1 = l1?.val ?? 0;
      int v2 = l2?.val ?? 0;
      int sum = v1 + v2 + carry;
      carry = sum ~/ 10;
      curr.next = ListNode(sum % 10);
      curr = curr.next!;
      l1 = l1?.next;
      l2 = l2?.next;
    }
    return dummy.next;
  }
}
// Time Complexity: O(max(N, M))
// Memory Complexity: O(max(N, M))

```

# scala

## Sweet Spot

```scala
/**
 * Definition for singly-linked list.
 * class ListNode(_x: Int = 0, _next: ListNode = null) {
 * var next: ListNode = _next
 * var x: Int = _x
 * }
 */
object Solution {
    def addTwoNumbers(l1: ListNode, l2: ListNode): ListNode = {
        val dummy = new ListNode(0)
        var curr = dummy
        var p1 = l1
        var p2 = l2
        var carry = 0
        while (p1 != null || p2 != null || carry != 0) {
            val v1 = if (p1 != null) p1.x else 0
            val v2 = if (p2 != null) p2.x else 0
            val sum = v1 + v2 + carry
            carry = sum / 10
            curr.next = new ListNode(sum % 10)
            curr = curr.next
            if (p1 != null) p1 = p1.next
            if (p2 != null) p2 = p2.next
        }
        dummy.next
    }
}
// Time Complexity: O(max(N, M))
// Memory Complexity: O(max(N, M))

```

# elixir

## Sweet Spot

```elixir
# Definition for singly-linked list.
#
# defmodule ListNode do
#   @type t :: %__MODULE__{
#           val: integer,
#           next: ListNode.t() | nil
#         }
#   defstruct val: 0, next: nil
# end

defmodule Solution do
  @spec add_two_numbers(l1 :: ListNode.t | nil, l2 :: ListNode.t | nil) :: ListNode.t | nil
  def add_two_numbers(l1, l2) do
    add_with_carry(l1, l2, 0)
  end

  defp add_with_carry(nil, nil, 0), do: nil
  defp add_with_carry(l1, l2, carry) do
    v1 = if l1, do: l1.val, else: 0
    v2 = if l2, do: l2.val, else: 0
    sum = v1 + v2 + carry
    %ListNode{
      val: rem(sum, 10),
      next: add_with_carry(
        if(l1, do: l1.next, else: nil),
        if(l2, do: l2.next, else: nil),
        div(sum, 10)
      )
    }
  end
end
# Time Complexity: O(max(N, M))
# Memory Complexity: O(max(N, M))

```

# erlang

## Sweet Spot

```erlang
%% Definition for singly-linked list.
%%
%% -record(list_node, {val = 0 :: integer(),
%%                     next = null :: 'null' | #list_node{}}).

-spec add_two_numbers(L1 :: #list_node{} | null, L2 :: #list_node{} | null) -> #list_node{} | null.
add_two_numbers(L1, L2) ->
    add_with_carry(L1, L2, 0).

add_with_carry(null, null, 0) ->
    null;
add_with_carry(L1, L2, Carry) ->
    V1 = case L1 of null -> 0; _ -> L1#list_node.val end,
    V2 = case L2 of null -> 0; _ -> L2#list_node.val end,
    Sum = V1 + V2 + Carry,
    NextL1 = case L1 of null -> null; _ -> L1#list_node.next end,
    NextL2 = case L2 of null -> null; _ -> L2#list_node.next end,
    #list_node{val = Sum rem 10, next = add_with_carry(NextL1, NextL2, Sum div 10)}.
% Time Complexity: O(max(N, M))
% Memory Complexity: O(max(N, M))

```

# Racket

## Sweet Spot

```racket
; Definition for singly-linked list:
#|
; val : integer?
; next : (or/c list-node? #f)
(struct list-node
  (val next) #:mutable #:transparent)

; constructor
(define (make-list-node [val 0])
  (list-node val #f))
|#

(define/contract (add-two-numbers l1 l2)
  (-> (or/c list-node? #f) (or/c list-node? #f) (or/c list-node? #f))
  (let loop ([p1 l1] [p2 l2] [carry 0])
    (cond
      [(and (not p1) (not p2) (zero? carry)) #f]
      [else
       (let* ([v1 (if p1 (list-node-val p1) 0)]
              [v2 (if p2 (list-node-val p2) 0)]
              [sum (+ v1 v2 carry)])
         (list-node (remainder sum 10)
                    (loop (if p1 (list-node-next p1) #f)
                          (if p2 (list-node-next p2) #f)
                          (quotient sum 10))))])))
; Time Complexity: O(max(N, M))
; Memory Complexity: O(max(N, M))

```