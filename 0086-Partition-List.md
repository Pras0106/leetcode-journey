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
    ListNode* partition(ListNode* head, int x) {
        ListNode lessHead(0), greaterHead(0);
        ListNode *less = &lessHead, *greater = &greaterHead;
        while (head) {
            if (head->val < x) {
                less->next = head;
                less = less->next;
            } else {
                greater->next = head;
                greater = greater->next;
            }
            head = head->next;
        }
        greater->next = nullptr;
        less->next = greaterHead.next;
        return lessHead.next;
    }
};
// Time: O(n), Memory: O(1)

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
    public ListNode partition(ListNode head, int x) {
        ListNode lessHead = new ListNode(0);
        ListNode greaterHead = new ListNode(0);
        ListNode less = lessHead;
        ListNode greater = greaterHead;
        while (head != null) {
            if (head.val < x) {
                less.next = head;
                less = less.next;
            } else {
                greater.next = head;
                greater = greater.next;
            }
            head = head.next;
        }
        greater.next = null;
        less.next = greaterHead.next;
        return lessHead.next;
    }
}
// Time: O(n), Memory: O(1)

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
    def partition(self, head: Optional[ListNode], x: int) -> Optional[ListNode]:
        less_head = ListNode(0)
        greater_head = ListNode(0)
        less = less_head
        greater = greater_head
        while head:
            if head.val < x:
                less.next = head
                less = less.next
            else:
                greater.next = head
                greater = greater.next
            head = head.next
        greater.next = None
        less.next = greater_head.next
        return less_head.next
# Time: O(n), Memory: O(1)

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
    def partition(self, head, x):
        """
        :type head: Optional[ListNode]
        :type x: int
        :rtype: Optional[ListNode]
        """
        less_head = ListNode(0)
        greater_head = ListNode(0)
        less = less_head
        greater = greater_head
        curr = head
        while curr:
            if curr.val < x:
                less.next = curr
                less = less.next
            else:
                greater.next = curr
                greater = greater.next
            curr = curr.next
        greater.next = None
        less.next = greater_head.next
        return less_head.next
# Time: O(n), Memory: O(1)

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
 * @param {number} x
 * @return {ListNode}
 */
var partition = function(head, x) {
    let lessHead = new ListNode(0);
    let greaterHead = new ListNode(0);
    let less = lessHead;
    let greater = greaterHead;
    while (head) {
        if (head.val < x) {
            less.next = head;
            less = less.next;
        } else {
            greater.next = head;
            greater = greater.next;
        }
        head = head.next;
    }
    greater.next = null;
    less.next = greaterHead.next;
    return lessHead.next;
};
// Time: O(n), Memory: O(1)

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

function partition(head: ListNode | null, x: number): ListNode | null {
    const lessHead = new ListNode(0);
    const greaterHead = new ListNode(0);
    let less = lessHead;
    let greater = greaterHead;
    while (head) {
        if (head.val < x) {
            less.next = head;
            less = less.next;
        } else {
            greater.next = head;
            greater = greater.next;
        }
        head = head.next;
    }
    greater.next = null;
    less.next = greaterHead.next;
    return lessHead.next;
};
// Time: O(n), Memory: O(1)

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
    public ListNode Partition(ListNode head, int x) {
        ListNode lessHead = new ListNode(0);
        ListNode greaterHead = new ListNode(0);
        ListNode less = lessHead;
        ListNode greater = greaterHead;
        while (head != null) {
            if (head.val < x) {
                less.next = head;
                less = less.next;
            } else {
                greater.next = head;
                greater = greater.next;
            }
            head = head.next;
        }
        greater.next = null;
        less.next = greaterHead.next;
        return lessHead.next;
    }
}
// Time: O(n), Memory: O(1)

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
struct ListNode* partition(struct ListNode* head, int x) {
    struct ListNode lessHead, greaterHead;
    struct ListNode *less = &lessHead, *greater = &greaterHead;
    lessHead.next = NULL;
    greaterHead.next = NULL;
    while (head) {
        if (head->val < x) {
            less->next = head;
            less = less->next;
        } else {
            greater->next = head;
            greater = greater->next;
        }
        head = head->next;
    }
    greater->next = NULL;
    less->next = greaterHead.next;
    return lessHead.next;
}
// Time: O(n), Memory: O(1)

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
func partition(head *ListNode, x int) *ListNode {
    lessHead := &ListNode{}
    greaterHead := &ListNode{}
    less := lessHead
    greater := greaterHead
    for head != nil {
        if head.Val < x {
            less.Next = head
            less = less.Next
        } else {
            greater.Next = head
            greater = greater.Next
        }
        head = head.Next
    }
    greater.Next = nil
    less.Next = greaterHead.Next
    return lessHead.Next
}
// Time: O(n), Memory: O(1)

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
    fun partition(head: ListNode?, x: Int): ListNode? {
        val lessHead = ListNode(0)
        val greaterHead = ListNode(0)
        var less = lessHead
        var greater = greaterHead
        var curr = head
        while (curr != null) {
            if (curr.`val` < x) {
                less.next = curr
                less = less.next!!
            } else {
                greater.next = curr
                greater = greater.next!!
            }
            curr = curr.next
        }
        greater.next = null
        less.next = greaterHead.next
        return lessHead.next
    }
}
// Time: O(n), Memory: O(1)

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
    func partition(_ head: ListNode?, _ x: Int) -> ListNode? {
        let lessHead = ListNode(0)
        let greaterHead = ListNode(0)
        var less = lessHead
        var greater = greaterHead
        var curr = head
        while let node = curr {
            if node.val < x {
                less.next = node
                less = node
            } else {
                greater.next = node
                greater = node
            }
            curr = node.next
        }
        greater.next = nil
        less.next = greaterHead.next
        return lessHead.next
    }
}
// Time: O(n), Memory: O(1)

```

# rust

## Sweet Spot

```rust
impl Solution {
    pub fn partition(mut head: Option<Box<ListNode>>, x: i32) -> Option<Box<ListNode>> {
        let mut less_head = Box::new(ListNode::new(0));
        let mut greater_head = Box::new(ListNode::new(0));
        let mut less = &mut less_head;
        let mut greater = &mut greater_head;
        while let Some(mut node) = head {
            head = node.next.take();
            if node.val < x {
                less.next = Some(node);
                less = less.next.as_mut().unwrap();
            } else {
                greater.next = Some(node);
                greater = greater.next.as_mut().unwrap();
            }
        }
        less.next = greater_head.next.take();
        less_head.next
    }
}
// Time: O(n), Memory: O(n) due to Box ownership migration

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
# @param {Integer} x
# @return {ListNode}
def partition(head, x)
    less_head = ListNode.new(0)
    greater_head = ListNode.new(0)
    less = less_head
    greater = greater_head
    while head
        if head.val < x
            less.next = head
            less = less.next
        else
            greater.next = head
            greater = greater.next
        end
        head = head.next
    end
    greater.next = nil
    less.next = greater_head.next
    less_head.next
end
# Time: O(n), Memory: O(1)

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
     * @param Integer $x
     * @return ListNode
     */
    function partition($head, $x) {
        $lessHead = new ListNode(0);
        $greaterHead = new ListNode(0);
        $less = $lessHead;
        $greater = $greaterHead;
        while ($head !== null) {
            if ($head->val < $x) {
                $less->next = $head;
                $less = $less->next;
            } else {
                $greater->next = $head;
                $greater = $greater->next;
            }
            $head = $head->next;
        }
        $greater->next = null;
        $less->next = $greaterHead->next;
        return $lessHead->next;
    }
}
// Time: O(n), Memory: O(1)

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
  ListNode? partition(ListNode? head, int x) {
    ListNode lessHead = ListNode(0);
    ListNode greaterHead = ListNode(0);
    ListNode? less = lessHead;
    ListNode? greater = greaterHead;
    while (head != null) {
      if (head.val < x) {
        less?.next = head;
        less = head;
      } else {
        greater?.next = head;
        greater = head;
      }
      head = head.next;
    }
    greater?.next = null;
    less?.next = greaterHead.next;
    return lessHead.next;
  }
}
// Time: O(n), Memory: O(1)

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
    def partition(head: ListNode, x: Int): ListNode = {
        val lessHead = new ListNode(0)
        val greaterHead = new ListNode(0)
        var less = lessHead
        var greater = greaterHead
        var curr = head
        while (curr != null) {
            if (curr.x < x) {
                less.next = curr
                less = curr
            } else {
                greater.next = curr
                greater = curr
            }
            curr = curr.next
        }
        greater.next = null
        less.next = greaterHead.next
        lessHead.next
    }
}
// Time: O(n), Memory: O(1)

```

# Elixir 1.17 with Erlang/OTP 26

## Sweet Spot

```elixir 1.17 with Erlang/OTP 26
defmodule Solution do
  @spec partition(head :: ListNode.t | nil, x :: integer) :: ListNode.t | nil
  def partition(head, x) do
    {less, greater} = split_nodes(head, x, [], [])
    build_list(Enum.reverse(less) ++ Enum.reverse(greater))
  end

  defp split_nodes(nil, _, less, greater), do: {less, greater}
  defp split_nodes(node, x, less, greater) do
    if node.val < x do
      split_nodes(node.next, x, [node.val | less], greater)
    else
      split_nodes(node.next, x, less, [node.val | greater])
    end
  end

  defp build_list([]), do: nil
  defp build_list([h | t]), do: %ListNode{val: h, next: build_list(t)}
end
# Time: O(n), Memory: O(n)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
-spec partition(Head :: #list_node{} | null, X :: integer()) -> #list_node{} | null.
partition(Head, X) ->
    {Less, Greater} = split_nodes(Head, X, [], []),
    build_list(lists:reverse(Less) ++ lists:reverse(Greater)).

split_nodes(null, _, Less, Greater) -> {Less, Greater};
split_nodes(Node, X, Less, Greater) ->
    Val = Node#list_node.val,
    Next = Node#list_node.next,
    case Val < X of
        true -> split_nodes(Next, X, [Val | Less], Greater);
        false -> split_nodes(Next, X, Less, [Val | Greater])
    end.

build_list([]) -> null;
build_list([H | T]) -> #list_node{val = H, next = build_list(T)}.
% Time: O(n), Memory: O(n)

```

# Racket CS v8.15

## Sweet Spot

```racket CS v8.15
(define/contract (partition head x)
  (-> (or/c list-node? #f) exact-integer? (or/c list-node? #f))
  (let ([less-head (make-list-node 0)]
        [greater-head (make-list-node 0)])
    (let loop ([curr head] [l less-head] [g greater-head])
      (cond
        [(not curr)
         (set-list-node-next! g #f)
         (set-list-node-next! l (list-node-next greater-head))
         (list-node-next less-head)]
        [(< (list-node-val curr) x)
         (set-list-node-next! l curr)
         (loop (list-node-next curr) curr g)]
        [else
         (set-list-node-next! g curr)
         (loop (list-node-next curr) l curr)]))))
; Time: O(n), Memory: O(1)

```