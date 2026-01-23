# C++

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
    ListNode* deleteDuplicates(ListNode* head) {
        ListNode* dummy = new ListNode(0, head);
        ListNode* prev = dummy;
        while (head != nullptr) {
            if (head->next != nullptr && head->val == head->next->val) {
                while (head->next != nullptr && head->val == head->next->val) {
                    head = head->next;
                }
                prev->next = head->next;
            } else {
                prev = prev->next;
            }
            head = head->next;
        }
        return dummy->next;
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
 * int val;
 * ListNode next;
 * ListNode() {}
 * ListNode(int val) { this.val = val; }
 * ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        ListNode dummy = new ListNode(0, head);
        ListNode prev = dummy;
        while (head != null) {
            if (head.next != null && head.val == head.next.val) {
                while (head.next != null && head.val == head.next.val) {
                    head = head.next;
                }
                prev.next = head.next;
            } else {
                prev = prev.next;
            }
            head = head.next;
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
    def deleteDuplicates(self, head: Optional[ListNode]) -> Optional[ListNode]:
        dummy = ListNode(0, head)
        prev = dummy
        while head:
            if head.next and head.val == head.next.val:
                while head.next and head.val == head.next.val:
                    head = head.next
                prev.next = head.next
            else:
                prev = prev.next
            head = head.next
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
    def deleteDuplicates(self, head):
        """
        :type head: Optional[ListNode]
        :rtype: Optional[ListNode]
        """
        dummy = ListNode(0, head)
        prev = dummy
        while head:
            if head.next and head.val == head.next.val:
                while head.next and head.val == head.next.val:
                    head = head.next
                prev.next = head.next
            else:
                prev = prev.next
            head = head.next
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
var deleteDuplicates = function(head) {
    let dummy = new ListNode(0, head);
    let prev = dummy;
    while (head !== null) {
        if (head.next !== null && head.val === head.next.val) {
            while (head.next !== null && head.val === head.next.val) {
                head = head.next;
            }
            prev.next = head.next;
        } else {
            prev = prev.next;
        }
        head = head.next;
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

function deleteDuplicates(head: ListNode | null): ListNode | null {
    let dummy = new ListNode(0, head);
    let prev = dummy;
    while (head !== null) {
        if (head.next !== null && head.val === head.next.val) {
            while (head.next !== null && head.val === head.next.val) {
                head = head.next;
            }
            prev.next = head.next;
        } else {
            prev = prev.next;
        }
        head = head.next;
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
    public ListNode DeleteDuplicates(ListNode head) {
        ListNode dummy = new ListNode(0, head);
        ListNode prev = dummy;
        while (head != null) {
            if (head.next != null && head.val == head.next.val) {
                while (head.next != null && head.val == head.next.val) {
                    head = head.next;
                }
                prev.next = head.next;
            } else {
                prev = prev.next;
            }
            head = head.next;
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
struct ListNode* deleteDuplicates(struct ListNode* head) {
    struct ListNode dummy;
    dummy.next = head;
    struct ListNode* prev = &dummy;
    while (head != NULL) {
        if (head->next != NULL && head->val == head->next->val) {
            while (head->next != NULL && head->val == head->next->val) {
                head = head->next;
            }
            prev->next = head->next;
        } else {
            prev = prev->next;
        }
        head = head->next;
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
func deleteDuplicates(head *ListNode) *ListNode {
    dummy := &ListNode{Val: 0, Next: head}
    prev := dummy
    for head != nil {
        if head.Next != nil && head.Val == head.Next.Val {
            for head.Next != nil && head.Val == head.Next.Val {
                head = head.Next
            }
            prev.Next = head.Next
        } else {
            prev = prev.Next
        }
        head = head.Next
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
    fun deleteDuplicates(head: ListNode?): ListNode? {
        val dummy = ListNode(0)
        dummy.next = head
        var prev = dummy
        var curr = head
        while (curr != null) {
            if (curr.next != null && curr.`val` == curr.next!!.`val`) {
                while (curr?.next != null && curr.`val` == curr.next!!.`val`) {
                    curr = curr.next
                }
                prev.next = curr?.next
            } else {
                prev = prev.next!!
            }
            curr = curr?.next
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
    func deleteDuplicates(_ head: ListNode?) -> ListNode? {
        let dummy = ListNode(0, head)
        var prev = dummy
        var curr = head
        while curr != nil {
            if curr?.next != nil && curr?.val == curr?.next?.val {
                while curr?.next != nil && curr?.val == curr?.next?.val {
                    curr = curr?.next
                }
                prev.next = curr?.next
            } else {
                prev = prev.next!
            }
            curr = curr?.next
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
    pub fn delete_duplicates(head: Option<Box<ListNode>>) -> Option<Box<ListNode>> {
        let mut dummy = Box::new(ListNode::new(0));
        dummy.next = head;
        let mut prev = &mut dummy;
        while let Some(mut curr) = prev.next.take() {
            if curr.next.as_ref().map_or(false, |next| next.val == curr.val) {
                let val = curr.val;
                while let Some(next) = curr.next.take() {
                    if next.val == val {
                        curr = next;
                    } else {
                        curr = next;
                        prev.next = Some(curr);
                        break;
                    }
                }
            } else {
                prev.next = Some(curr);
                prev = prev.next.as_mut().unwrap();
            }
        }
        dummy.next
    }
}
// Time Complexity: O(n)
// Memory Complexity: O(1)

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
def delete_duplicates(head)
    dummy = ListNode.new(0, head)
    prev = dummy
    while head
        if head.next && head.val == head.next.val
            while head.next && head.val == head.next.val
                head = head.next
            end
            prev.next = head.next
        else
            prev = prev.next
        end
        head = head.next
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
    function deleteDuplicates($head) {
        $dummy = new ListNode(0, $head);
        $prev = $dummy;
        while ($head !== null) {
            if ($head->next !== null && $head->val === $head->next->val) {
                while ($head->next !== null && $head->val === $head->next->val) {
                    $head = $head->next;
                }
                $prev->next = $head->next;
            } else {
                $prev = $prev->next;
            }
            $head = $head->next;
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
  ListNode? deleteDuplicates(ListNode? head) {
    ListNode dummy = ListNode(0, head);
    ListNode prev = dummy;
    ListNode? curr = head;
    while (curr != null) {
      if (curr.next != null && curr.val == curr.next!.val) {
        while (curr!.next != null && curr.val == curr.next!.val) {
          curr = curr.next;
        }
        prev.next = curr.next;
      } else {
        prev = prev.next!;
      }
      curr = curr.next;
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
    def deleteDuplicates(head: ListNode): ListNode = {
        val dummy = new ListNode(0, head)
        var prev = dummy
        var curr = head
        while (curr != null) {
            if (curr.next != null && curr.x == curr.next.x) {
                while (curr.next != null && curr.x == curr.next.x) {
                    curr = curr.next
                }
                prev.next = curr.next
            } else {
                prev = prev.next
            }
            curr = curr.next
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
  @spec delete_duplicates(head :: ListNode.t | nil) :: ListNode.t | nil
  def delete_duplicates(head) do
    do_delete(head, nil)
  end

  defp do_delete(nil, _), do: nil
  defp do_delete(%ListNode{val: v, next: %ListNode{val: v}} = head, _) do
    next_diff = skip_duplicates(head.next, v)
    do_delete(next_diff, nil)
  end
  defp do_delete(head, _) do
    %ListNode{head | next: do_delete(head.next, nil)}
  end

  defp skip_duplicates(%ListNode{val: v, next: next}, v), do: skip_duplicates(next, v)
  defp skip_duplicates(head, _v), do: head
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

-spec delete_duplicates(Head :: #list_node{} | null) -> #list_node{} | null.
delete_duplicates(null) -> null;
delete_duplicates(#list_node{val = V, next = #list_node{val = V} = Next}) ->
    NewHead = skip_val(Next, V),
    delete_duplicates(NewHead);
delete_duplicates(#list_node{} = Head) ->
    Head#list_node{next = delete_duplicates(Head#list_node.next)}.

skip_val(#list_node{val = V, next = Next}, V) -> skip_val(Next, V);
skip_val(Head, _) -> Head.

% Time Complexity: O(n)
% Memory Complexity: O(n)

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

; constructor
(define (make-list-node [val 0])
  (list-node val #f))

|#

(define/contract (delete-duplicates head)
  (-> (or/c list-node? #f) (or/c list-node? #f))
  (cond
    [(not head) #f]
    [(and (list-node-next head) (= (list-node-val head) (list-node-val (list-node-next head))))
     (let loop ([curr (list-node-next head)] [val (list-node-val head)])
       (if (and curr (= (list-node-val curr) val))
           (loop (list-node-next curr) val)
           (delete-duplicates curr)))]
    [else
     (set-list-node-next! head (delete-duplicates (list-node-next head)))
     head]))
; Time Complexity: O(n)
; Memory Complexity: O(n)

```