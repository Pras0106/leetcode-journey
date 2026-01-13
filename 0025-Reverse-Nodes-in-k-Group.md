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
    ListNode* reverseKGroup(ListNode* head, int k) {
        if (!head || k == 1) return head;
        ListNode dummy(0);
        dummy.next = head;
        ListNode *curr = &dummy, *next = &dummy, *prev = &dummy;
        int count = 0;
        while (curr->next) {
            curr = curr->next;
            count++;
        }
        while (count >= k) {
            curr = prev->next;
            next = curr->next;
            for (int i = 1; i < k; i++) {
                curr->next = next->next;
                next->next = prev->next;
                prev->next = next;
                next = curr->next;
            }
            prev = curr;
            count -= k;
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
    public ListNode reverseKGroup(ListNode head, int k) {
        if (head == null || k == 1) return head;
        ListNode dummy = new ListNode(0);
        dummy.next = head;
        ListNode prev = dummy, curr = dummy, next = dummy;
        int count = 0;
        while (curr.next != null) {
            curr = curr.next;
            count++;
        }
        while (count >= k) {
            curr = prev.next;
            next = curr.next;
            for (int i = 1; i < k; i++) {
                curr.next = next.next;
                next.next = prev.next;
                prev.next = next;
                next = curr.next;
            }
            prev = curr;
            count -= k;
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
    def reverseKGroup(self, head: Optional[ListNode], k: int) -> Optional[ListNode]:
        if not head or k == 1:
            return head
        dummy = ListNode(0)
        dummy.next = head
        prev = curr = next_node = dummy
        count = 0
        while curr.next:
            curr = curr.next
            count += 1
        while count >= k:
            curr = prev.next
            next_node = curr.next
            for _ in range(1, k):
                curr.next = next_node.next
                next_node.next = prev.next
                prev.next = next_node
                next_node = curr.next
            prev = curr
            count -= k
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
    def reverseKGroup(self, head, k):
        """
        :type head: Optional[ListNode]
        :type k: int
        :rtype: Optional[ListNode]
        """
        if not head or k == 1:
            return head
        dummy = ListNode(0)
        dummy.next = head
        prev = curr = next_node = dummy
        count = 0
        while curr.next:
            curr = curr.next
            count += 1
        while count >= k:
            curr = prev.next
            next_node = curr.next
            for _ in range(1, k):
                curr.next = next_node.next
                next_node.next = prev.next
                prev.next = next_node
                next_node = curr.next
            prev = curr
            count -= k
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
 * @param {number} k
 * @return {ListNode}
 */
var reverseKGroup = function(head, k) {
    if (!head || k === 1) return head;
    let dummy = new ListNode(0);
    dummy.next = head;
    let prev = dummy, curr = dummy, next = dummy;
    let count = 0;
    while (curr.next) {
        curr = curr.next;
        count++;
    }
    while (count >= k) {
        curr = prev.next;
        next = curr.next;
        for (let i = 1; i < k; i++) {
            curr.next = next.next;
            next.next = prev.next;
            prev.next = next;
            next = curr.next;
        }
        prev = curr;
        count -= k;
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

function reverseKGroup(head: ListNode | null, k: number): ListNode | null {
    if (!head || k === 1) return head;
    let dummy = new ListNode(0, head);
    let prev: ListNode = dummy;
    let curr: ListNode | null = dummy;
    let next: ListNode | null = dummy;
    let count = 0;
    while (curr?.next) {
        curr = curr.next;
        count++;
    }
    while (count >= k) {
        curr = prev.next!;
        next = curr.next;
        for (let i = 1; i < k; i++) {
            curr.next = next!.next;
            next!.next = prev.next;
            prev.next = next;
            next = curr.next;
        }
        prev = curr;
        count -= k;
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
    public ListNode ReverseKGroup(ListNode head, int k) {
        if (head == null || k == 1) return head;
        ListNode dummy = new ListNode(0);
        dummy.next = head;
        ListNode prev = dummy, curr = dummy, next = dummy;
        int count = 0;
        while (curr.next != null) {
            curr = curr.next;
            count++;
        }
        while (count >= k) {
            curr = prev.next;
            next = curr.next;
            for (int i = 1; i < k; i++) {
                curr.next = next.next;
                next.next = prev.next;
                prev.next = next;
                next = curr.next;
            }
            prev = curr;
            count -= k;
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
struct ListNode* reverseKGroup(struct ListNode* head, int k) {
    if (!head || k == 1) return head;
    struct ListNode dummy;
    dummy.next = head;
    struct ListNode *prev = &dummy, *curr = &dummy, *next = &dummy;
    int count = 0;
    while (curr->next) {
        curr = curr->next;
        count++;
    }
    while (count >= k) {
        curr = prev->next;
        next = curr->next;
        for (int i = 1; i < k; i++) {
            curr->next = next->next;
            next->next = prev->next;
            prev->next = next;
            next = curr->next;
        }
        prev = curr;
        count -= k;
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
func reverseKGroup(head *ListNode, k int) *ListNode {
    if head == nil || k == 1 {
        return head
    }
    dummy := &ListNode{Next: head}
    prev, curr, next := dummy, dummy, dummy
    count := 0
    for curr.Next != nil {
        curr = curr.Next
        count++
    }
    for count >= k {
        curr = prev.Next
        next = curr.Next
        for i := 1; i < k; i++ {
            curr.Next = next.Next
            next.Next = prev.Next
            prev.Next = next
            next = curr.Next
        }
        prev = curr
        count -= k
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
 * Definition for singly-linked list.
 * class ListNode(var `val`: Int) {
 * var next: ListNode? = null
 * }
 */
class Solution {
    fun reverseKGroup(head: ListNode?, k: Int): ListNode? {
        if (head == null || k == 1) return head
        val dummy = ListNode(0)
        dummy.next = head
        var prev = dummy
        var curr: ListNode? = dummy
        var count = 0
        while (curr?.next != null) {
            curr = curr.next
            count++
        }
        while (count >= k) {
            curr = prev.next
            var nextNode = curr?.next
            for (i in 1 until k) {
                curr?.next = nextNode?.next
                nextNode?.next = prev.next
                prev.next = nextNode
                nextNode = curr?.next
            }
            prev = curr!!
            count -= k
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
    func reverseKGroup(_ head: ListNode?, _ k: Int) -> ListNode? {
        if head == nil || k == 1 { return head }
        let dummy = ListNode(0, head)
        var prev = dummy
        var curr: ListNode? = dummy
        var count = 0
        while curr?.next != nil {
            curr = curr?.next
            count += 1
        }
        while count >= k {
            curr = prev.next
            var nextNode = curr?.next
            for _ in 1..<k {
                curr?.next = nextNode?.next
                nextNode?.next = prev.next
                prev.next = nextNode
                nextNode = curr?.next
            }
            prev = curr!
            count -= k
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
    pub fn reverse_k_group(mut head: Option<Box<ListNode>>, k: i32) -> Option<Box<ListNode>> {
        let mut curr = &head;
        for _ in 0..k {
            if let Some(node) = curr {
                curr = &node.next;
            } else {
                return head;
            }
        }
        let mut new_head = Self::reverse_k_group(curr.clone(), k);
        for _ in 0..k {
            if let Some(mut node) = head {
                head = node.next.take();
                node.next = new_head;
                new_head = Some(node);
            }
        }
        new_head
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(n/k)

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
def reverse_k_group(head, k)
    return head if head.nil? || k == 1
    dummy = ListNode.new(0)
    dummy.next = head
    prev = curr = dummy
    count = 0
    while curr.next
        curr = curr.next
        count += 1
    end
    while count >= k
        curr = prev.next
        nxt = curr.next
        (1...k).each do
            curr.next = nxt.next
            nxt.next = prev.next
            prev.next = nxt
            nxt = curr.next
        end
        prev = curr
        count -= k
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
     * @param Integer $k
     * @return ListNode
     */
    function reverseKGroup($head, $k) {
        if ($head == null || $k == 1) return $head;
        $dummy = new ListNode(0);
        $dummy->next = $head;
        $prev = $curr = $dummy;
        $count = 0;
        while ($curr->next != null) {
            $curr = $curr->next;
            $count++;
        }
        while ($count >= $k) {
            $curr = $prev->next;
            $next = $curr->next;
            for ($i = 1; $i < $k; $i++) {
                $curr->next = $next->next;
                $next->next = $prev->next;
                $prev->next = $next;
                $next = $curr->next;
            }
            $prev = $curr;
            $count -= $k;
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
  ListNode? reverseKGroup(ListNode? head, int k) {
    if (head == null || k == 1) return head;
    ListNode dummy = ListNode(0, head);
    ListNode prev = dummy;
    ListNode? curr = dummy;
    int count = 0;
    while (curr?.next != null) {
      curr = curr?.next;
      count++;
    }
    while (count >= k) {
      curr = prev.next;
      ListNode? nextNode = curr?.next;
      for (int i = 1; i < k; i++) {
        curr?.next = nextNode?.next;
        nextNode?.next = prev.next;
        prev.next = nextNode;
        nextNode = curr?.next;
      }
      prev = curr!;
      count -= k;
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
    def reverseKGroup(head: ListNode, k: Int): ListNode = {
        if (head == null || k == 1) return head
        val dummy = new ListNode(0, head)
        var prev = dummy
        var curr = dummy
        var count = 0
        while (curr.next != null) {
            curr = curr.next
            count += 1
        }
        while (count >= k) {
            curr = prev.next
            var nxt = curr.next
            for (_ <- 1 until k) {
                curr.next = nxt.next
                nxt.next = prev.next
                prev.next = nxt
                nxt = curr.next
            }
            prev = curr
            count -= k
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
  @spec reverse_k_group(head :: ListNode.t | nil, k :: integer) :: ListNode.t | nil
  def reverse_k_group(head, k) do
    case get_next_group(head, k) do
      {:ok, next_group_start} ->
        processed_rest = reverse_k_group(next_group_start, k)

        # Time Complexity: O(n)
        # Memory Complexity: O(n/k)
        reverse_n(head, k, processed_rest)

      :error ->
        head
    end
  end

  defp get_next_group(node, 0), do: {:ok, node}
  defp get_next_group(nil, _k), do: :error
  defp get_next_group(node, k), do: get_next_group(node.next, k - 1)

  defp reverse_n(head, k, acc) do
    Enum.reduce(1..k, {acc, head}, fn _, {prev, curr} ->
      {%{curr | next: prev}, curr.next}
    end)
    |> elem(0)
  end
end
```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
%% Definition for singly-linked list.
%%
%% -record(list_node, {val = 0 :: integer(),
%%                     next = null :: 'null' | #list_node{}}).

-spec reverse_k_group(Head :: #list_node{} | null, K :: integer()) -> #list_node{} | null.
reverse_k_group(Head, K) ->
    case has_k_nodes(Head, K) of
        false -> 
            Head;
        true ->
            NextGroupHead = get_kth_next(Head, K),
            ProcessedRest = reverse_k_group(NextGroupHead, K),
            reverse_n_nodes(Head, K, ProcessedRest)
    end.

has_k_nodes(_Node, 0) -> true;
has_k_nodes(null, _K) -> false;
has_k_nodes(Node, K) -> has_k_nodes(Node#list_node.next, K - 1).

get_kth_next(Node, 0) -> Node;
get_kth_next(Node, K) -> get_kth_next(Node#list_node.next, K - 1).

reverse_n_nodes(Prev, 0, Rest) -> Rest;
reverse_n_nodes(Curr, N, Rest) ->
    NextNode = Curr#list_node.next,
    reverse_n_nodes(NextNode, N - 1, Curr#list_node{next = Rest}).

%% Time Complexity: O(N)
%% Memory Complexity: O(N/K)
```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (reverse-k-group head k)
  (-> (or/c list-node? #f) exact-integer? (or/c list-node? #f))
  (define (get-kth node i)
    (if (or (not node) (= i k)) node (get-kth (list-node-next node) (+ i 1))))
  (let ([kth (get-kth head 1)])
    (if (not kth)
        head
        (let ([next-group (list-node-next kth)])
          (set-list-node-next! kth #f)
          (let ([new-head (reverse-list head)])
            (set-list-node-next! head (reverse-k-group next-group k))
            new-head)))))

(define (reverse-list node)
  (let loop ([curr node] [prev #f])
    (if (not curr)
        prev
        (let ([nxt (list-node-next curr)])
          (set-list-node-next! curr prev)
          (loop nxt curr)))))
; Time Complexity: O(n)
; Memory Complexity: O(n/k)

```