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
        if (!head) return nullptr;
        ListNode* current = head;
        while (current->next) {
            if (current->val == current->next->val) {
                ListNode* temp = current->next;
                current->next = current->next->next;
                delete temp;
            } else {
                current = current->next;
            }
        }
        return head;
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
        ListNode current = head;
        while (current != null && current.next != null) {
            if (current.val == current.next.val) {
                current.next = current.next.next;
            } else {
                current = current.next;
            }
        }
        return head;
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
        current = head
        while current and current.next:
            if current.val == current.next.val:
                current.next = current.next.next
            else:
                current = current.next
        return head
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
        current = head
        while current and current.next:
            if current.val == current.next.val:
                current.next = current.next.next
            else:
                current = current.next
        return head
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
    let current = head;
    while (current !== null && current.next !== null) {
        if (current.val === current.next.val) {
            current.next = current.next.next;
        } else {
            current = current.next;
        }
    }
    return head;
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
    let current = head;
    while (current !== null && current.next !== null) {
        if (current.val === current.next.val) {
            current.next = current.next.next;
        } else {
            current = current.next;
        }
    }
    return head;
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
        ListNode current = head;
        while (current != null && current.next != null) {
            if (current.val == current.next.val) {
                current.next = current.next.next;
            } else {
                current = current.next;
            }
        }
        return head;
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
    struct ListNode* current = head;
    while (current != NULL && current->next != NULL) {
        if (current->val == current->next->val) {
            struct ListNode* next_node = current->next;
            current->next = next_node->next;
            // Freeing memory for strictly "compiler-ready" safety where applicable
        } else {
            current = current->next;
        }
    }
    return head;
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
    current := head
    for current != nil && current.Next != nil {
        if current.Val == current.Next.Val {
            current.Next = current.Next.Next
        } else {
            current = current.Next
        }
    }
    return head
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
        var current = head
        while (current?.next != null) {
            if (current.`val` == current.next?.`val`) {
                current.next = current.next?.next
            } else {
                current = current.next
            }
        }
        return head
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
        var current = head
        while let currentUnwrapped = current, let nextNode = currentUnwrapped.next {
            if currentUnwrapped.val == nextNode.val {
                currentUnwrapped.next = nextNode.next
            } else {
                current = nextNode
            }
        }
        return head
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
    pub fn delete_duplicates(mut head: Option<Box<ListNode>>) -> Option<Box<ListNode>> {
        let mut current = head.as_mut();
        while let Some(node) = current {
            while let Some(next) = node.next.as_mut() {
                if node.val == next.val {
                    node.next = next.next.take();
                } else {
                    break;
                }
            }
            current = node.next.as_mut();
        }
        head
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
    current = head
    while current && current.next
        if current.val == current.next.val
            current.next = current.next.next
        else
            current = current.next
        end
    end
    head
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
        $current = $head;
        while ($current !== null && $current->next !== null) {
            if ($current->val === $current->next->val) {
                $current->next = $current->next->next;
            } else {
                $current = $current->next;
            }
        }
        return $head;
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
    ListNode? current = head;
    while (current != null && current.next != null) {
        if (current.val == current.next!.val) {
            current.next = current.next!.next;
        } else {
            current = current.next;
        }
    }
    return head;
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
        var current = head
        while (current != null && current.next != null) {
            if (current.x == current.next.x) {
                current.next = current.next.next
            } else {
                current = current.next
            }
        }
        head
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
  def delete_duplicates(nil), do: nil
  def delete_duplicates(%ListNode{val: v, next: %ListNode{val: v, next: n}}), do: delete_duplicates(%ListNode{val: v, next: n})
  def delete_duplicates(%ListNode{val: v, next: n}), do: %ListNode{val: v, next: delete_duplicates(n)}
  def delete_duplicates(node), do: node
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
delete_duplicates(#list_node{val = V, next = #list_node{val = V, next = N}}) ->
    delete_duplicates(#list_node{val = V, next = N});
delete_duplicates(#list_node{val = V, next = N}) ->
    #list_node{val = V, next = delete_duplicates(N)};
delete_duplicates(Node) -> Node.
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

; constructor
(define (make-list-node [val 0])
  (list-node val #f))

|#

(define/contract (delete-duplicates head)
  (-> (or/c list-node? #f) (or/c list-node? #f))
  (let loop ([current head])
    (cond
      [(or (not current) (not (list-node-next current))) head]
      [(= (list-node-val current) (list-node-val (list-node-next current)))
       (set-list-node-next! current (list-node-next (list-node-next current)))
       (loop current)]
      [else
       (loop (list-node-next current))]))
  head)
; Time Complexity: O(n)
; Memory Complexity: O(1)

```