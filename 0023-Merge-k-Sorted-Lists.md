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
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
        ListNode dummy(0);
        ListNode* curr = &dummy;
        while (l1 && l2) {
            if (l1->val < l2->val) {
                curr->next = l1;
                l1 = l1->next;
            } else {
                curr->next = l2;
                l2 = l2->next;
            }
            curr = curr->next;
        }
        curr->next = l1 ? l1 : l2;
        return dummy.next;
    }

    ListNode* mergeKLists(vector<ListNode*>& lists) {
        if (lists.empty()) return nullptr;
        int n = lists.size();
        for (int step = 1; step < n; step *= 2) {
            for (int i = 0; i + step < n; i += step * 2) {
                lists[i] = mergeTwoLists(lists[i], lists[i + step]);
            }
        }
        return lists[0];
    }
};
// Time Complexity: O(N log k)
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
    public ListNode mergeKLists(ListNode[] lists) {
        if (lists == null || lists.length == 0) return null;
        int n = lists.length;
        while (n > 1) {
            int k = (n + 1) / 2;
            for (int i = 0; i < n / 2; i++) {
                lists[i] = mergeTwoLists(lists[i], lists[i + k]);
            }
            n = k;
        }
        return lists[0];
    }

    private ListNode mergeTwoLists(ListNode l1, ListNode l2) {
        ListNode dummy = new ListNode(0);
        ListNode curr = dummy;
        while (l1 != null && l2 != null) {
            if (l1.val < l2.val) {
                curr.next = l1;
                l1 = l1.next;
            } else {
                curr.next = l2;
                l2 = l2.next;
            }
            curr = curr.next;
        }
        curr.next = (l1 != null) ? l1 : l2;
        return dummy.next;
    }
}
// Time Complexity: O(N log k)
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
    def mergeKLists(self, lists: List[Optional[ListNode]]) -> Optional[ListNode]:
        if not lists:
            return None
        
        while len(lists) > 1:
            merged_lists = []
            for i in range(0, len(lists), 2):
                l1 = lists[i]
                l2 = lists[i + 1] if (i + 1) < len(lists) else None
                merged_lists.append(self.mergeTwoLists(l1, l2))
            lists = merged_lists
        return lists[0]

    def mergeTwoLists(self, l1, l2):
        dummy = ListNode(0)
        curr = dummy
        while l1 and l2:
            if l1.val < l2.val:
                curr.next = l1
                l1 = l1.next
            else:
                curr.next = l2
                l2 = l2.next
            curr = curr.next
        curr.next = l1 or l2
        return dummy.next
# Time Complexity: O(N log k)
# Memory Complexity: O(k)

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
    def mergeKLists(self, lists):
        """
        :type lists: List[Optional[ListNode]]
        :rtype: Optional[ListNode]
        """
        if not lists:
            return None
        
        while len(lists) > 1:
            merged_lists = []
            for i in range(0, len(lists), 2):
                l1 = lists[i]
                l2 = lists[i + 1] if (i + 1) < len(lists) else None
                merged_lists.append(self.mergeTwoLists(l1, l2))
            lists = merged_lists
        return lists[0]

    def mergeTwoLists(self, l1, l2):
        dummy = ListNode(0)
        curr = dummy
        while l1 and l2:
            if l1.val < l2.val:
                curr.next = l1
                l1 = l1.next
            else:
                curr.next = l2
                l2 = l2.next
            curr = curr.next
        curr.next = l1 or l2
        return dummy.next
# Time Complexity: O(N log k)
# Memory Complexity: O(k)

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
 * @param {ListNode[]} lists
 * @return {ListNode}
 */
var mergeKLists = function(lists) {
    if (lists.length === 0) return null;
    
    while (lists.length > 1) {
        let merged = [];
        for (let i = 0; i < lists.length; i += 2) {
            merged.push(mergeTwoLists(lists[i], lists[i + 1] || null));
        }
        lists = merged;
    }
    return lists[0];
};

var mergeTwoLists = function(l1, l2) {
    let dummy = new ListNode(0);
    let curr = dummy;
    while (l1 && l2) {
        if (l1.val < l2.val) {
            curr.next = l1;
            l1 = l1.next;
        } else {
            curr.next = l2;
            l2 = l2.next;
        }
        curr = curr.next;
    }
    curr.next = l1 || l2;
    return dummy.next;
};
// Time Complexity: O(N log k)
// Memory Complexity: O(k)

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

function mergeKLists(lists: Array<ListNode | null>): ListNode | null {
    if (lists.length === 0) return null;
    
    while (lists.length > 1) {
        let merged: Array<ListNode | null> = [];
        for (let i = 0; i < lists.length; i += 2) {
            merged.push(mergeTwoLists(lists[i], lists[i+1] || null));
        }
        lists = merged;
    }
    return lists[0];
};

function mergeTwoLists(l1: ListNode | null, l2: ListNode | null): ListNode | null {
    let dummy = new ListNode(0);
    let curr = dummy;
    while (l1 && l2) {
        if (l1.val < l2.val) {
            curr.next = l1;
            l1 = l1.next;
        } else {
            curr.next = l2;
            l2 = l2.next;
        }
        curr = curr.next;
    }
    curr.next = l1 || l2;
    return dummy.next;
}
// Time Complexity: O(N log k)
// Memory Complexity: O(k)

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
    public ListNode MergeKLists(ListNode[] lists) {
        if (lists == null || lists.Length == 0) return null;
        int n = lists.Length;
        while (n > 1) {
            int k = (n + 1) / 2;
            for (int i = 0; i < n / 2; i++) {
                lists[i] = MergeTwoLists(lists[i], lists[i + k]);
            }
            n = k;
        }
        return lists[0];
    }

    private ListNode MergeTwoLists(ListNode l1, ListNode l2) {
        ListNode dummy = new ListNode(0);
        ListNode curr = dummy;
        while (l1 != null && l2 != null) {
            if (l1.val < l2.val) {
                curr.next = l1;
                l1 = l1.next;
            } else {
                curr.next = l2;
                l2 = l2.next;
            }
            curr = curr.next;
        }
        curr.next = l1 ?? l2;
        return dummy.next;
    }
}
// Time Complexity: O(N log k)
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
struct ListNode* mergeTwoLists(struct ListNode* l1, struct ListNode* l2) {
    struct ListNode dummy;
    struct ListNode* curr = &dummy;
    while (l1 && l2) {
        if (l1->val < l2->val) {
            curr->next = l1;
            l1 = l1->next;
        } else {
            curr->next = l2;
            l2 = l2->next;
        }
        curr = curr->next;
    }
    curr->next = l1 ? l1 : l2;
    return dummy.next;
}

struct ListNode* mergeKLists(struct ListNode** lists, int listsSize) {
    if (listsSize == 0) return NULL;
    int n = listsSize;
    while (n > 1) {
        int k = (n + 1) / 2;
        for (int i = 0; i < n / 2; i++) {
            lists[i] = mergeTwoLists(lists[i], lists[i + k]);
        }
        n = k;
    }
    return lists[0];
}
// Time Complexity: O(N log k)
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
func mergeTwoLists(l1 *ListNode, l2 *ListNode) *ListNode {
    dummy := &ListNode{}
    curr := dummy
    for l1 != nil && l2 != nil {
        if l1.Val < l2.Val {
            curr.Next = l1
            l1 = l1.Next
        } else {
            curr.Next = l2
            l2 = l2.Next
        }
        curr = curr.Next
    }
    if l1 != nil {
        curr.Next = l1
    } else {
        curr.Next = l2
    }
    return dummy.Next
}

func mergeKLists(lists []*ListNode) *ListNode {
    if len(lists) == 0 {
        return nil
    }
    for len(lists) > 1 {
        var merged []*ListNode
        for i := 0; i < len(lists); i += 2 {
            var l1, l2 *ListNode
            l1 = lists[i]
            if i+1 < len(lists) {
                l2 = lists[i+1]
            }
            merged = append(merged, mergeTwoLists(l1, l2))
        }
        lists = merged
    }
    return lists[0]
}
// Time Complexity: O(N log k)
// Memory Complexity: O(k)

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
    fun mergeKLists(lists: Array<ListNode?>): ListNode? {
        if (lists.isEmpty()) return null
        var n = lists.size
        while (n > 1) {
            val k = (n + 1) / 2
            for (i in 0 until n / 2) {
                lists[i] = mergeTwoLists(lists[i], lists[i + k])
            }
            n = k
        }
        return lists[0]
    }

    private fun mergeTwoLists(l1: ListNode?, l2: ListNode?): ListNode? {
        val dummy = ListNode(0)
        var curr = dummy
        var curL1 = l1
        var curL2 = l2
        while (curL1 != null && curL2 != null) {
            if (curL1.`val` < curL2.`val`) {
                curr.next = curL1
                curL1 = curL1.next
            } else {
                curr.next = curL2
                curL2 = curL2.next
            }
            curr = curr.next!!
        }
        curr.next = curL1 ?: curL2
        return dummy.next
    }
}
// Time Complexity: O(N log k)
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
    func mergeKLists(_ lists: [ListNode?]) -> ListNode? {
        if lists.isEmpty { return nil }
        var currentLists = lists
        while currentLists.count > 1 {
            var merged = [ListNode?]()
            for i in stride(from: 0, to: currentLists.count, by: 2) {
                let l1 = currentLists[i]
                let l2 = (i + 1 < currentLists.count) ? currentLists[i + 1] : nil
                merged.append(mergeTwoLists(l1, l2))
            }
            currentLists = merged
        }
        return currentLists[0]
    }

    private func mergeTwoLists(_ l1: ListNode?, _ l2: ListNode?) -> ListNode? {
        let dummy = ListNode(0)
        var curr = dummy
        var h1 = l1
        var h2 = l2
        while let node1 = h1, let node2 = h2 {
            if node1.val < node2.val {
                curr.next = node1
                h1 = node1.next
            } else {
                curr.next = node2
                h2 = node2.next
            }
            curr = curr.next!
        }
        curr.next = h1 ?? h2
        return dummy.next
    }
}
// Time Complexity: O(N log k)
// Memory Complexity: O(k)

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
use std::collections::BinaryHeap;
use std::cmp::Ordering;

impl PartialOrd for ListNode {
    fn partial_cmp(&self, other: &Self) -> Option<Ordering> {
        Some(other.val.cmp(&self.val))
    }
}

impl Ord for ListNode {
    fn cmp(&self, other: &Self) -> Ordering {
        other.val.cmp(&self.val)
    }
}

impl Solution {
    pub fn merge_k_lists(lists: Vec<Option<Box<ListNode>>>) -> Option<Box<ListNode>> {
        let mut heap = BinaryHeap::new();
        for node in lists {
            if let Some(n) = node {
                heap.push(n);
            }
        }
        
        let mut dummy = Box::new(ListNode::new(0));
        let mut curr = &mut dummy;
        
        while let Some(mut node) = heap.pop() {
            if let Some(next) = node.next.take() {
                heap.push(next);
            }
            curr.next = Some(node);
            curr = curr.next.as_mut().unwrap();
        }
        
        dummy.next
    }
}
// Time Complexity: O(N log k)
// Memory Complexity: O(k)

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
# @param {ListNode[]} lists
# @return {ListNode}
def merge_k_lists(lists)
    return nil if lists.empty?
    while lists.length > 1
        merged = []
        (0...lists.length).step(2) do |i|
            merged << merge_two_lists(lists[i], lists[i + 1])
        end
        lists = merged
    end
    lists[0]
end

def merge_two_lists(l1, l2)
    dummy = ListNode.new(0)
    curr = dummy
    while l1 && l2
        if l1.val < l2.val
            curr.next = l1
            l1 = l1.next
        else
            curr.next = l2
            l2 = l2.next
        end
        curr = curr.next
    end
    curr.next = l1 || l2
    dummy.next
end
# Time Complexity: O(N log k)
# Memory Complexity: O(k)

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
     * @param ListNode[] $lists
     * @return ListNode
     */
    function mergeKLists($lists) {
        if (empty($lists)) return null;
        while (count($lists) > 1) {
            $merged = [];
            for ($i = 0; $i < count($lists); $i += 2) {
                $merged[] = $this->mergeTwoLists($lists[$i], $lists[$i + 1] ?? null);
            }
            $lists = $merged;
        }
        return $lists[0];
    }

    function mergeTwoLists($l1, $l2) {
        $dummy = new ListNode(0);
        $curr = $dummy;
        while ($l1 !== null && $l2 !== null) {
            if ($l1->val < $l2->val) {
                $curr->next = $l1;
                $l1 = $l1->next;
            } else {
                $curr->next = $l2;
                $l2 = $l2->next;
            }
            $curr = $curr->next;
        }
        $curr->next = $l1 ?? $l2;
        return $dummy->next;
    }
}
// Time Complexity: O(N log k)
// Memory Complexity: O(k)

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
  ListNode? mergeKLists(List<ListNode?> lists) {
    if (lists.isEmpty) return null;
    while (lists.length > 1) {
      List<ListNode?> merged = [];
      for (int i = 0; i < lists.length; i += 2) {
        merged.add(mergeTwoLists(lists[i], i + 1 < lists.length ? lists[i + 1] : null));
      }
      lists = merged;
    }
    return lists[0];
  }

  ListNode? mergeTwoLists(ListNode? l1, ListNode? l2) {
    ListNode dummy = ListNode(0);
    ListNode curr = dummy;
    while (l1 != null && l2 != null) {
      if (l1.val < l2.val) {
        curr.next = l1;
        l1 = l1.next;
      } else {
        curr.next = l2;
        l2 = l2.next;
      }
      curr = curr.next!;
    }
    curr.next = l1 ?? l2;
    return dummy.next;
  }
}
// Time Complexity: O(N log k)
// Memory Complexity: O(k)

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
    def mergeKLists(lists: Array[ListNode]): ListNode = {
        if (lists == null || lists.length == 0) return null
        var n = lists.length
        while (n > 1) {
            val k = (n + 1) / 2
            for (i <- 0 until n / 2) {
                lists(i) = mergeTwoLists(lists(i), lists(i + k))
            }
            n = k
        }
        lists(0)
    }

    private def mergeTwoLists(l1: ListNode, l2: ListNode): ListNode = {
        val dummy = new ListNode(0)
        var curr = dummy
        var h1 = l1
        var h2 = l2
        while (h1 != null && h2 != null) {
            if (h1.x < h2.x) {
                curr.next = h1
                h1 = h1.next
            } else {
                curr.next = h2
                h2 = h2.next
            }
            curr = curr.next
        }
        if (h1 != null) curr.next = h1 else curr.next = h2
        dummy.next
    }
}
// Time Complexity: O(N log k)
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
  @spec merge_k_lists(lists :: [ListNode.t | nil]) :: ListNode.t | nil
  def merge_k_lists([]), do: nil
  def merge_k_lists([l]), do: l
  def merge_k_lists(lists) do
    lists
    |> Enum.chunk_every(2)
    |> Enum.map(fn 
      [l1, l2] -> merge_two_lists(l1, l2)
      [l1] -> l1
    end)
    |> merge_k_lists()
  end

  defp merge_two_lists(nil, l2), do: l2
  defp merge_two_lists(l1, nil), do: l1
  defp merge_two_lists(l1, l2) do
    if l1.val < l2.val do
      %{l1 | next: merge_two_lists(l1.next, l2)}
    else
      %{l2 | next: merge_two_lists(l1, l2.next)}
    end
  end
end
# Time Complexity: O(N log k)
# Memory Complexity: O(N)

```

# Erlang/OTP 26

## Sweet Spot

```erlang/otp 26
%% Definition for singly-linked list.
%%
%% -record(list_node, {val = 0 :: integer(),
%%                     next = null :: 'null' | #list_node{}}).

-spec merge_k_lists(Lists :: [#list_node{} | null]) -> #list_node{} | null.
merge_k_lists([]) -> null;
merge_k_lists([L]) -> L;
merge_k_lists(Lists) ->
    Pairs = chunk(Lists),
    Merged = [merge_two(A, B) || {A, B} <- Pairs],
    merge_k_lists(Merged).

chunk([]) -> [];
chunk([A]) -> [{A, null}];
chunk([A, B | T]) -> [{A, B} | chunk(T)].

merge_two(null, L2) -> L2;
merge_two(L1, null) -> L1;
merge_two(L1, L2) ->
    V1 = L1#list_node.val,
    V2 = L2#list_node.val,
    if
        V1 < V2 -> L1#list_node{next = merge_two(L1#list_node.next, L2)};
        true -> L2#list_node{next = merge_two(L1, L2#list_node.next)}
    end.
%% Time Complexity: O(N log k)
%% Memory Complexity: O(N)

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

(define/contract (merge-k-lists lists)
  (-> (listof (or/c list-node? #f)) (or/c list-node? #f))
  (cond
    [(empty? lists) #f]
    [(= (length lists) 1) (first lists)]
    [else
     (let loop ([lst lists] [acc '()])
       (cond
         [(empty? lst) (merge-k-lists acc)]
         [(empty? (rest lst)) (merge-k-lists (cons (first lst) acc))]
         [else (loop (rest (rest lst)) (cons (merge-two (first lst) (second lst)) acc))]))]))

(define (merge-two l1 l2)
  (cond
    [(not l1) l2]
    [(not l2) l1]
    [(< (list-node-val l1) (list-node-val l2))
     (set-list-node-next! l1 (merge-two (list-node-next l1) l2))
     l1]
    [else
     (set-list-node-next! l2 (merge-two l1 (list-node-next l2)))
     l2]))
; Time Complexity: O(N log k)
; Memory Complexity: O(log k) due to recursion stack

```