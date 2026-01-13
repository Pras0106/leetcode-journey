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
    ListNode* swapPairs(ListNode* head) {
        if (!head || !head->next) return head;
        ListNode dummy(0);
        dummy.next = head;
        ListNode* prev = &dummy;
        while (prev->next && prev->next->next) {
            ListNode* first = prev->next;
            ListNode* second = first->next;
            first->next = second->next;
            second->next = first;
            prev->next = second;
            prev = first;
        }
        return dummy.next;
    }
};
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# java

## Sweet Spot

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 * public int val;
 * public ListNode next;
 * public ListNode() {}
 * public ListNode(int val) { this.val = val; }
 * public ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode swapPairs(ListNode head) {
        if (head == null || head.next == null) return head;
        ListNode dummy = new ListNode(0);
        dummy.next = head;
        ListNode prev = dummy;
        while (prev.next != null && prev.next.next != null) {
            ListNode first = prev.next;
            ListNode second = first.next;
            first.next = second.next;
            second.next = first;
            prev.next = second;
            prev = first;
        }
        return dummy.next;
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

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
    def swapPairs(self, head: Optional[ListNode]) -> Optional[ListNode]:
        if not head or not head.next:
            return head
        dummy = ListNode(0)
        dummy.next = head
        prev = dummy
        while prev.next and prev.next.next:
            first = prev.next
            second = first.next
            first.next = second.next
            second.next = first
            prev.next = second
            prev = first
        return dummy.next
# Time Complexity: O(n)
# Memory Complexity: O(1)

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
    def swapPairs(self, head):
        """
        :type head: ListNode
        :rtype: ListNode
        """
        if not head or not head.next:
            return head
        dummy = ListNode(0)
        dummy.next = head
        prev = dummy
        while prev.next and prev.next.next:
            first = prev.next
            second = first.next
            first.next = second.next
            second.next = first
            prev.next = second
            prev = first
        return dummy.next
# Time Complexity: O(n)
# Memory Complexity: O(1)

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
 * @return {ListNode}
 */
var swapPairs = function(head) {
    if (!head || !head.next) return head;
    let dummy = new ListNode(0);
    dummy.next = head;
    let prev = dummy;
    while (prev.next && prev.next.next) {
        let first = prev.next;
        let second = first.next;
        first.next = second.next;
        second.next = first;
        prev.next = second;
        prev = first;
    }
    return dummy.next;
};
// Time Complexity: O(n)
// Memory Complexity: O(1)

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

function swapPairs(head: ListNode | null): ListNode | null {
    if (!head || !head.next) return head;
    const dummy = new ListNode(0, head);
    let prev = dummy;
    while (prev.next && prev.next.next) {
        const first: ListNode = prev.next;
        const second: ListNode = first.next!;
        first.next = second.next;
        second.next = first;
        prev.next = second;
        prev = first;
    }
    return dummy.next;
};
// Time Complexity: O(n)
// Memory Complexity: O(1)

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
    public ListNode SwapPairs(ListNode head) {
        if (head == null || head.next == null) return head;
        ListNode dummy = new ListNode(0, head);
        ListNode prev = dummy;
        while (prev.next != null && prev.next.next != null) {
            ListNode first = prev.next;
            ListNode second = first.next;
            first.next = second.next;
            second.next = first;
            prev.next = second;
            prev = first;
        }
        return dummy.next;
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

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
struct ListNode* swapPairs(struct ListNode* head) {
    if (!head || !head->next) return head;
    struct ListNode dummy;
    dummy.next = head;
    struct ListNode* prev = &dummy;
    while (prev->next && prev->next->next) {
        struct ListNode* first = prev->next;
        struct ListNode* second = first->next;
        first->next = second->next;
        second->next = first;
        prev->next = second;
        prev = first;
    }
    return dummy.next;
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

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
func swapPairs(head *ListNode) *ListNode {
    if head == nil || head.Next == nil {
        return head
    }
    dummy := &ListNode{Next: head}
    prev := dummy
    for prev.Next != nil && prev.Next.Next != nil {
        first := prev.Next
        second := first.Next
        first.Next = second.Next
        second.Next = first
        prev.Next = second
        prev = first
    }
    return dummy.Next
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

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
    fun swapPairs(head: ListNode?): ListNode? {
        if (head == null || head.next == null) return head
        val dummy = ListNode(0)
        dummy.next = head
        var prev: ListNode? = dummy
        while (prev?.next != null && prev.next?.next != null) {
            val first = prev.next
            val second = first?.next
            first?.next = second?.next
            second?.next = first
            prev.next = second
            prev = first
        }
        return dummy.next
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

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
    func swapPairs(_ head: ListNode?) -> ListNode? {
        if head == nil || head?.next == nil { return head }
        let dummy = ListNode(0, head)
        var prev: ListNode? = dummy
        while prev?.next != nil && prev?.next?.next != nil {
            let first = prev?.next
            let second = first?.next
            first?.next = second?.next
            second?.next = first
            prev?.next = second
            prev = first
        }
        return dummy.next
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

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
    pub fn swap_pairs(head: Option<Box<ListNode>>) -> Option<Box<ListNode>> {
        let mut head = head;
        let mut dummy = Box::new(ListNode::new(0));
        let mut curr = &mut dummy;
        while let Some(mut first) = head {
            if let Some(mut second) = first.next.take() {
                head = second.next.take();
                first.next = None;
                second.next = Some(first);
                curr.next = Some(second);
                curr = curr.next.as_mut().unwrap().next.as_mut().unwrap();
            } else {
                curr.next = Some(first);
                head = None;
            }
        }
        dummy.next
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(n)

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
# @return {ListNode}
def swap_pairs(head)
    return head if head.nil? || head.next.nil?
    dummy = ListNode.new(0, head)
    prev = dummy
    while !prev.next.nil? && !prev.next.next.nil?
        first = prev.next
        second = first.next
        first.next = second.next
        second.next = first
        prev.next = second
        prev = first
    end
    dummy.next
end
# Time Complexity: O(n)
# Memory Complexity: O(1)

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
     * @param ListNode $head
     * @return ListNode
     */
    function swapPairs($head) {
        if ($head === null || $head->next === null) return $head;
        $dummy = new ListNode(0, $head);
        $prev = $dummy;
        while ($prev->next !== null && $prev->next->next !== null) {
            $first = $prev->next;
            $second = $first->next;
            $first->next = $second->next;
            $second->next = $first;
            $prev->next = $second;
            $prev = $first;
        }
        return $dummy->next;
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

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
  ListNode? swapPairs(ListNode? head) {
    if (head == null || head.next == null) return head;
    ListNode dummy = ListNode(0, head);
    ListNode? prev = dummy;
    while (prev?.next != null && prev?.next?.next != null) {
      ListNode? first = prev?.next;
      ListNode? second = first?.next;
      first?.next = second?.next;
      second?.next = first;
      prev?.next = second;
      prev = first;
    }
    return dummy.next;
  }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

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
    def swapPairs(head: ListNode): ListNode = {
        if (head == null || head.next == null) return head
        val dummy = new ListNode(0, head)
        var prev = dummy
        while (prev.next != null && prev.next.next != null) {
            val first = prev.next
            val second = first.next
            first.next = second.next
            second.next = first
            prev.next = second
            prev = first
        }
        dummy.next
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
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
  @spec swap_pairs(head :: ListNode.t | nil) :: ListNode.t | nil
  def swap_pairs(nil), do: nil
  def swap_pairs(%ListNode{next: nil} = head), do: head
  def swap_pairs(%ListNode{val: v1, next: %ListNode{val: v2, next: rest}}) do
    %ListNode{val: v2, next: %ListNode{val: v1, next: swap_pairs(rest)}}
  end
end
# Time Complexity: O(n)
# Memory Complexity: O(n)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
%% Definition for singly-linked list.
%%
%% -record(list_node, {val = 0 :: integer(),
%%                     next = null :: 'null' | #list_node{}}).

-spec swap_pairs(Head :: #list_node{} | null) -> #list_node{} | null.
swap_pairs(null) -> null;
swap_pairs(#list_node{next = null} = Head) -> Head;
swap_pairs(#list_node{val = V1, next = #list_node{val = V2, next = Rest}}) ->
  #list_node{val = V2, next = #list_node{val = V1, next = swap_pairs(Rest)}}.
%% Time Complexity: O(n)
%% Memory Complexity: O(n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
; Definition for singly-linked list:
#|
; val : integer?
; next : (or/c list-node? #f)
(struct list-node
  (val next) #:mutable #:transparent)
|#

(define/contract (swap-pairs head)
  (-> (or/c list-node? #f) (or/c list-node? #f))
  (cond
    [(not head) #f]
    [(not (list-node-next head)) head]
    [else
     (let* ([first head]
            [second (list-node-next head)]
            [rest (list-node-next second)])
       (set-list-node-next! second first)
       (set-list-node-next! first (swap-pairs rest))
       second)]))
; Time Complexity: O(n)
; Memory Complexity: O(n) due to recursion

```