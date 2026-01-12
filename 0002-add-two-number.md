# cpp

## memory O(1)

```cpp
/**
 * Time: O(N)
 * Memory: O(1)
 */
class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode* dummy = new ListNode(0);
        ListNode* curr = dummy;
        int carry = 0;
        while (l1 || l2 || carry) {
            int sum = carry + (l1 ? l1->val : 0) + (l2 ? l2->val : 0);
            carry = sum / 10;
            if (l1) {
                l1->val = sum % 10;
                curr->next = l1;
                l1 = l1->next;
            } else if (l2) {
                l2->val = sum % 10;
                curr->next = l2;
                l2 = l2->next;
            } else {
                curr->next = new ListNode(carry);
                break;
            }
            curr = curr->next;
            if (l2 && curr != l2) l2 = l2->next;
        }
        return dummy->next;
    }
};

```

## time O(1)

```cpp
/**
 * Time: O(N)
 * Memory: O(N)
 */
class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode* dummy = new ListNode(0);
        ListNode* curr = dummy;
        int carry = 0;
        while (l1 || l2 || carry) {
            int x = (l1) ? l1->val : 0;
            int y = (l2) ? l2->val : 0;
            int sum = carry + x + y;
            carry = sum / 10;
            curr->next = new ListNode(sum % 10);
            curr = curr->next;
            if (l1) l1 = l1->next;
            if (l2) l2 = l2->next;
        }
        return dummy->next;
    }
};

```

## Sweet Spot

```cpp
/**
 * Time: O(N)
 * Memory: O(1)
 */
class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode dummy(0);
        ListNode* curr = &dummy;
        int carry = 0;
        while (l1 || l2 || carry) {
            int val = carry + (l1 ? l1->val : 0) + (l2 ? l2->val : 0);
            carry = val / 10;
            if (l1) {
                l1->val = val % 10;
                curr->next = l1;
                l1 = l1->next;
            } else if (l2) {
                l2->val = val % 10;
                curr->next = l2;
                l2 = l2->next;
            } else {
                curr->next = new ListNode(carry);
                carry = 0;
            }
            curr = curr->next;
            if (l2 && curr != l2) l2 = l2->next;
        }
        return dummy.next;
    }
};

```

# java

## memory O(1)

```java
/**
 * Time: O(N)
 * Memory: O(1)
 */
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dummy = new ListNode(0);
        ListNode curr = dummy;
        int carry = 0;
        while (l1 != null || l2 != null || carry != 0) {
            int sum = carry + (l1 != null ? l1.val : 0) + (l2 != null ? l2.val : 0);
            carry = sum / 10;
            if (l1 != null) {
                l1.val = sum % 10;
                curr.next = l1;
                l1 = l1.next;
            } else if (l2 != null) {
                l2.val = sum % 10;
                curr.next = l2;
                l2 = l2.next;
            } else {
                curr.next = new ListNode(carry);
                carry = 0;
            }
            curr = curr.next;
            if (l2 != null && curr != l2) l2 = l2.next;
        }
        return dummy.next;
    }
}

```

## time O(1)

```java
/**
 * Time: O(N)
 * Memory: O(N)
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

```

## Sweet Spot

```java
/**
 * Time: O(N)
 * Memory: O(N)
 */
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dummyHead = new ListNode(0);
        ListNode curr = dummyHead;
        int carry = 0;
        while (l1 != null || l2 != null || carry != 0) {
            int sum = carry + (l1 != null ? l1.val : 0) + (l2 != null ? l2.val : 0);
            carry = sum / 10;
            curr.next = new ListNode(sum % 10);
            curr = curr.next;
            if (l1 != null) l1 = l1.next;
            if (l2 != null) l2 = l2.next;
        }
        return dummyHead.next;
    }
}

```

# python 3.14

## memory O(1)

```python 3.14
# Time: O(N)
# Memory: O(1)
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
            if l1:
                l1.val = val
                curr.next = l1
                l1 = l1.next
            elif l2:
                l2.val = val
                curr.next = l2
                l2 = l2.next
            else:
                curr.next = ListNode(val)
            curr = curr.next
            if l2 and curr != l2: l2 = l2.next
        return dummy.next

```

## time O(1)

```python 3.14
# Time: O(N)
# Memory: O(N)
class Solution:
    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
        dummy = ListNode(0)
        curr = dummy
        carry = 0
        while l1 or l2 or carry:
            val = (l1.val if l1 else 0) + (l2.val if l2 else 0) + carry
            carry, val = divmod(val, 10)
            curr.next = ListNode(val)
            curr = curr.next
            l1 = l1.next if l1 else None
            l2 = l2.next if l2 else None
        return dummy.next

```

## Sweet Spot

```python 3.14
# Time: O(N)
# Memory: O(N)
class Solution:
    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
        dummy = ListNode(0)
        curr = dummy
        carry = 0
        while l1 or l2 or carry:
            val = (l1.val if l1 else 0) + (l2.val if l2 else 0) + carry
            carry, val = divmod(val, 10)
            curr.next = ListNode(val)
            curr = curr.next
            l1 = l1.next if l1 else None
            l2 = l2.next if l2 else None
        return dummy.next

```

# python 2.7.11

## memory O(1)

```python 2.7.11
# Time: O(N)
# Memory: O(1)
class Solution(object):
    def addTwoNumbers(self, l1, l2):
        dummy = ListNode(0)
        curr = dummy
        carry = 0
        while l1 or l2 or carry:
            v1 = l1.val if l1 else 0
            v2 = l2.val if l2 else 0
            total = v1 + v2 + carry
            carry = total / 10
            val = total % 10
            if l1:
                l1.val = val
                curr.next = l1
                l1 = l1.next
            elif l2:
                l2.val = val
                curr.next = l2
                l2 = l2.next
            else:
                curr.next = ListNode(val)
            curr = curr.next
            if l2 and curr != l2: l2 = l2.next
        return dummy.next

```

## time O(1)

```python 2.7.11
# Time: O(N)
# Memory: O(N)
class Solution(object):
    def addTwoNumbers(self, l1, l2):
        dummy = ListNode(0)
        curr = dummy
        carry = 0
        while l1 or l2 or carry:
            total = (l1.val if l1 else 0) + (l2.val if l2 else 0) + carry
            carry, val = divmod(total, 10)
            curr.next = ListNode(val)
            curr = curr.next
            l1 = l1.next if l1 else None
            l2 = l2.next if l2 else None
        return dummy.next

```

## Sweet Spot

```python 2.7.11
# Time: O(N)
# Memory: O(N)
class Solution(object):
    def addTwoNumbers(self, l1, l2):
        dummy = ListNode(0)
        curr = dummy
        carry = 0
        while l1 or l2 or carry:
            total = (l1.val if l1 else 0) + (l2.val if l2 else 0) + carry
            carry, val = divmod(total, 10)
            curr.next = ListNode(val)
            curr = curr.next
            l1 = l1.next if l1 else None
            l2 = l2.next if l2 else None
        return dummy.next

```

# JavaScript

## memory O(1)

```javascript
/**
 * Time: O(N)
 * Memory: O(1)
 */
var addTwoNumbers = function(l1, l2) {
    let dummy = new ListNode(0);
    let curr = dummy;
    let carry = 0;
    while (l1 || l2 || carry) {
        let sum = (l1 ? l1.val : 0) + (l2 ? l2.val : 0) + carry;
        carry = Math.floor(sum / 10);
        if (l1) {
            l1.val = sum % 10;
            curr.next = l1;
            l1 = l1.next;
        } else if (l2) {
            l2.val = sum % 10;
            curr.next = l2;
            l2 = l2.next;
        } else {
            curr.next = new ListNode(carry);
            carry = 0;
        }
        curr = curr.next;
        if (l2 && curr !== l2) l2 = l2.next;
    }
    return dummy.next;
};

```

## time O(1)

```javascript
/**
 * Time: O(N)
 * Memory: O(N)
 */
var addTwoNumbers = function(l1, l2) {
    let dummy = new ListNode(0);
    let curr = dummy;
    let carry = 0;
    while (l1 || l2 || carry) {
        let sum = (l1 ? l1.val : 0) + (l2 ? l2.val : 0) + carry;
        carry = Math.floor(sum / 10);
        curr.next = new ListNode(sum % 10);
        curr = curr.next;
        if (l1) l1 = l1.next;
        if (l2) l2 = l2.next;
    }
    return dummy.next;
};

```

## Sweet Spot

```javascript
/**
 * Time: O(N)
 * Memory: O(N)
 */
var addTwoNumbers = function(l1, l2) {
    let dummy = new ListNode(0);
    let curr = dummy;
    let carry = 0;
    while (l1 || l2 || carry) {
        let sum = (l1 ? l1.val : 0) + (l2 ? l2.val : 0) + carry;
        carry = Math.floor(sum / 10);
        curr.next = new ListNode(sum % 10);
        curr = curr.next;
        l1 = l1 ? l1.next : null;
        l2 = l2 ? l2.next : null;
    }
    return dummy.next;
};

```

# Typescript

## memory O(1)

```typescript
/**
 * Time: O(N)
 * Memory: O(1)
 */
function addTwoNumbers(l1: ListNode | null, l2: ListNode | null): ListNode | null {
    let dummy = new ListNode(0);
    let curr = dummy;
    let carry = 0;
    while (l1 || l2 || carry) {
        let sum = (l1 ? l1.val : 0) + (l2 ? l2.val : 0) + carry;
        carry = Math.floor(sum / 10);
        if (l1) {
            l1.val = sum % 10;
            curr.next = l1;
            l1 = l1.next;
        } else if (l2) {
            l2.val = sum % 10;
            curr.next = l2;
            l2 = l2.next;
        } else {
            curr.next = new ListNode(carry);
            carry = 0;
        }
        curr = curr.next;
        if (l2 && curr !== l2) l2 = l2.next;
    }
    return dummy.next;
};

```

## time O(1)

```typescript
/**
 * Time: O(N)
 * Memory: O(N)
 */
function addTwoNumbers(l1: ListNode | null, l2: ListNode | null): ListNode | null {
    let dummy = new ListNode(0);
    let curr = dummy;
    let carry = 0;
    while (l1 || l2 || carry) {
        let sum = (l1 ? l1.val : 0) + (l2 ? l2.val : 0) + carry;
        carry = Math.floor(sum / 10);
        curr.next = new ListNode(sum % 10);
        curr = curr.next;
        if (l1) l1 = l1.next;
        if (l2) l2 = l2.next;
    }
    return dummy.next;
};

```

## Sweet Spot

```typescript
/**
 * Time: O(N)
 * Memory: O(N)
 */
function addTwoNumbers(l1: ListNode | null, l2: ListNode | null): ListNode | null {
    let dummy = new ListNode(0);
    let curr = dummy;
    let carry = 0;
    while (l1 || l2 || carry) {
        let sum = (l1 ? l1.val : 0) + (l2 ? l2.val : 0) + carry;
        carry = Math.floor(sum / 10);
        curr.next = new ListNode(sum % 10);
        curr = curr.next;
        l1 = l1 ? l1.next : null;
        l2 = l2 ? l2.next : null;
    }
    return dummy.next;
};

```

# C#

## memory O(1)

```c#
/**
 * Time: O(N)
 * Memory: O(1)
 */
public class Solution {
    public ListNode AddTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dummy = new ListNode(0);
        ListNode curr = dummy;
        int carry = 0;
        while (l1 != null || l2 != null || carry != 0) {
            int sum = carry + (l1 != null ? l1.val : 0) + (l2 != null ? l2.val : 0);
            carry = sum / 10;
            if (l1 != null) {
                l1.val = sum % 10;
                curr.next = l1;
                l1 = l1.next;
            } else if (l2 != null) {
                l2.val = sum % 10;
                curr.next = l2;
                l2 = l2.next;
            } else {
                curr.next = new ListNode(carry);
                carry = 0;
            }
            curr = curr.next;
            if (l2 != null && curr != l2) l2 = l2.next;
        }
        return dummy.next;
    }
}

```

## time O(1)

```c#
/**
 * Time: O(N)
 * Memory: O(N)
 */
public class Solution {
    public ListNode AddTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dummy = new ListNode(0);
        ListNode curr = dummy;
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
        return dummy.next;
    }
}

```

## Sweet Spot

```c#
/**
 * Time: O(N)
 * Memory: O(N)
 */
public class Solution {
    public ListNode AddTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dummy = new ListNode(0);
        ListNode curr = dummy;
        int carry = 0;
        while (l1 != null || l2 != null || carry != 0) {
            int sum = carry + (l1 != null ? l1.val : 0) + (l2 != null ? l2.val : 0);
            carry = sum / 10;
            curr.next = new ListNode(sum % 10);
            curr = curr.next;
            l1 = l1?.next;
            l2 = l2?.next;
        }
        return dummy.next;
    }
}

```

# C

## memory O(1)

```c
/**
 * Time: O(N)
 * Memory: O(1)
 */
struct ListNode* addTwoNumbers(struct ListNode* l1, struct ListNode* l2) {
    struct ListNode dummy;
    struct ListNode* curr = &dummy;
    int carry = 0;
    while (l1 || l2 || carry) {
        int sum = carry + (l1 ? l1->val : 0) + (l2 ? l2->val : 0);
        carry = sum / 10;
        if (l1) {
            l1->val = sum % 10;
            curr->next = l1;
            l1 = l1->next;
        } else if (l2) {
            l2->val = sum % 10;
            curr->next = l2;
            l2 = l2->next;
        } else {
            struct ListNode* newNode = (struct ListNode*)malloc(sizeof(struct ListNode));
            newNode->val = carry;
            newNode->next = NULL;
            curr->next = newNode;
            carry = 0;
        }
        curr = curr->next;
        if (l2 && curr != l2) l2 = l2->next;
    }
    curr->next = NULL;
    return dummy.next;
}

```

## time O(1)

```c
/**
 * Time: O(N)
 * Memory: O(N)
 */
struct ListNode* addTwoNumbers(struct ListNode* l1, struct ListNode* l2) {
    struct ListNode* dummy = (struct ListNode*)malloc(sizeof(struct ListNode));
    struct ListNode* curr = dummy;
    int carry = 0;
    while (l1 || l2 || carry) {
        int sum = carry + (l1 ? l1->val : 0) + (l2 ? l2->val : 0);
        carry = sum / 10;
        struct ListNode* newNode = (struct ListNode*)malloc(sizeof(struct ListNode));
        newNode->val = sum % 10;
        newNode->next = NULL;
        curr->next = newNode;
        curr = curr->next;
        if (l1) l1 = l1->next;
        if (l2) l2 = l2->next;
    }
    return dummy->next;
}

```

## Sweet Spot

```c
/**
 * Time: O(N)
 * Memory: O(1)
 */
struct ListNode* addTwoNumbers(struct ListNode* l1, struct ListNode* l2) {
    struct ListNode dummy;
    dummy.next = NULL;
    struct ListNode* curr = &dummy;
    int carry = 0;
    while (l1 || l2 || carry) {
        int sum = carry + (l1 ? l1->val : 0) + (l2 ? l2->val : 0);
        carry = sum / 10;
        if (l1) {
            l1->val = sum % 10;
            curr->next = l1;
            l1 = l1->next;
        } else if (l2) {
            l2->val = sum % 10;
            curr->next = l2;
            l2 = l2->next;
        } else {
            struct ListNode* newNode = (struct ListNode*)malloc(sizeof(struct ListNode));
            newNode->val = carry;
            newNode->next = NULL;
            curr->next = newNode;
            carry = 0;
        }
        curr = curr->next;
        if (l2 && curr != l2) l2 = l2->next;
    }
    curr->next = NULL;
    return dummy.next;
}

```

# Go

## memory O(1)

```go
/**
 * Time: O(N)
 * Memory: O(1)
 */
func addTwoNumbers(l1 *ListNode, l2 *ListNode) *ListNode {
    dummy := &ListNode{}
    curr := dummy
    carry := 0
    for l1 != nil || l2 != nil || carry != 0 {
        sum := carry
        if l1 != nil { sum += l1.Val }
        if l2 != nil { sum += l2.Val }
        carry = sum / 10
        if l1 != nil {
            l1.Val = sum % 10
            curr.Next = l1
            l1 = l1.Next
        } else if l2 != nil {
            l2.Val = sum % 10
            curr.Next = l2
            l2 = l2.Next
        } else {
            curr.Next = &ListNode{Val: carry}
            carry = 0
        }
        curr = curr.Next
        if l2 != nil && curr != l2 { l2 = l2.Next }
    }
    return dummy.Next
}

```

## time O(1)

```go
/**
 * Time: O(N)
 * Memory: O(N)
 */
func addTwoNumbers(l1 *ListNode, l2 *ListNode) *ListNode {
    dummy := &ListNode{}
    curr := dummy
    carry := 0
    for l1 != nil || l2 != nil || carry != 0 {
        val1, val2 := 0, 0
        if l1 != nil { val1 = l1.Val; l1 = l1.Next }
        if l2 != nil { val2 = l2.Val; l2 = l2.Next }
        sum := val1 + val2 + carry
        carry = sum / 10
        curr.Next = &ListNode{Val: sum % 10}
        curr = curr.Next
    }
    return dummy.Next
}

```

## Sweet Spot

```go
/**
 * Time: O(N)
 * Memory: O(N)
 */
func addTwoNumbers(l1 *ListNode, l2 *ListNode) *ListNode {
    dummy := &ListNode{}
    curr := dummy
    carry := 0
    for l1 != nil || l2 != nil || carry != 0 {
        sum := carry
        if l1 != nil { sum += l1.Val; l1 = l1.Next }
        if l2 != nil { sum += l2.Val; l2 = l2.Next }
        carry = sum / 10
        curr.Next = &ListNode{Val: sum % 10}
        curr = curr.Next
    }
    return dummy.Next
}

```

# Kotlin

## memory O(1)

```kotlin
/**
 * Time: O(N)
 * Memory: O(1)
 */
class Solution {
    fun addTwoNumbers(l1: ListNode?, l2: ListNode?): ListNode? {
        val dummy = ListNode(0)
        var curr = dummy
        var p1 = l1
        var p2 = l2
        var carry = 0
        while (p1 != null || p2 != null || carry != 0) {
            val sum = carry + (p1?.`val` ?: 0) + (p2?.`val` ?: 0)
            carry = sum / 10
            if (p1 != null) {
                p1.`val` = sum % 10
                curr.next = p1
                p1 = p1.next
            } else if (p2 != null) {
                p2.`val` = sum % 10
                curr.next = p2
                p2 = p2.next
            } else {
                curr.next = ListNode(carry)
                carry = 0
            }
            curr = curr.next!!
            if (p2 != null && curr != p2) p2 = p2.next
        }
        return dummy.next
    }
}

```

## time O(1)

```kotlin
/**
 * Time: O(N)
 * Memory: O(N)
 */
class Solution {
    fun addTwoNumbers(l1: ListNode?, l2: ListNode?): ListNode? {
        val dummyHead = ListNode(0)
        var curr = dummyHead
        var p = l1
        var q = l2
        var carry = 0
        while (p != null || q != null || carry != 0) {
            val x = p?.`val` ?: 0
            val y = q?.`val` ?: 0
            val sum = carry + x + y
            carry = sum / 10
            curr.next = ListNode(sum % 10)
            curr = curr.next!!
            p = p?.next
            q = q?.next
        }
        return dummyHead.next
    }
}

```

## Sweet Spot

```kotlin
/**
 * Time: O(N)
 * Memory: O(N)
 */
class Solution {
    fun addTwoNumbers(l1: ListNode?, l2: ListNode?): ListNode? {
        val dummy = ListNode(0)
        var curr = dummy
        var p1 = l1
        var p2 = l2
        var carry = 0
        while (p1 != null || p2 != null || carry != 0) {
            val sum = carry + (p1?.`val` ?: 0) + (p2?.`val` ?: 0)
            carry = sum / 10
            curr.next = ListNode(sum % 10)
            curr = curr.next!!
            p1 = p1?.next
            p2 = p2?.next
        }
        return dummy.next
    }
}

```

# swift

## memory O(1)

```swift
/**
 * Time: O(N)
 * Memory: O(1)
 */
class Solution {
    func addTwoNumbers(_ l1: ListNode?, _ l2: ListNode?) -> ListNode? {
        let dummy = ListNode(0)
        var curr = dummy
        var p1 = l1
        var p2 = l2
        var carry = 0
        while p1 != nil || p2 != nil || carry != 0 {
            let sum = (p1?.val ?? 0) + (p2?.val ?? 0) + carry
            carry = sum / 10
            if let node1 = p1 {
                node1.val = sum % 10
                curr.next = node1
                p1 = node1.next
            } else if let node2 = p2 {
                node2.val = sum % 10
                curr.next = node2
                p2 = node2.next
            } else {
                curr.next = ListNode(carry)
                carry = 0
            }
            curr = curr.next!
            if p2 != nil && curr !== p2 { p2 = p2?.next }
        }
        return dummy.next
    }
}

```

## time O(1)

```swift
/**
 * Time: O(N)
 * Memory: O(N)
 */
class Solution {
    func addTwoNumbers(_ l1: ListNode?, _ l2: ListNode?) -> ListNode? {
        let dummy = ListNode(0)
        var curr = dummy
        var p1 = l1
        var p2 = l2
        var carry = 0
        while p1 != nil || p2 != nil || carry != 0 {
            let sum = (p1?.val ?? 0) + (p2?.val ?? 0) + carry
            carry = sum / 10
            curr.next = ListNode(sum % 10)
            curr = curr.next!
            p1 = p1?.next
            p2 = p2?.next
        }
        return dummy.next
    }
}

```

## Sweet Spot

```swift
/**
 * Time: O(N)
 * Memory: O(N)
 */
class Solution {
    func addTwoNumbers(_ l1: ListNode?, _ l2: ListNode?) -> ListNode? {
        let dummy = ListNode(0)
        var curr = dummy
        var p1 = l1
        var p2 = l2
        var carry = 0
        while p1 != nil || p2 != nil || carry != 0 {
            let sum = (p1?.val ?? 0) + (p2?.val ?? 0) + carry
            carry = sum / 10
            curr.next = ListNode(sum % 10)
            curr = curr.next!
            p1 = p1?.next
            p2 = p2?.next
        }
        return dummy.next
    }
}

```

# rust

## memory O(1)

```rust
/**
 * Time: O(N)
 * Memory: O(N)
 */
impl Solution {
    pub fn add_two_numbers(mut l1: Option<Box<ListNode>>, mut l2: Option<Box<ListNode>>) -> Option<Box<ListNode>> {
        let mut dummy = ListNode::new(0);
        let mut curr = &mut dummy;
        let mut carry = 0;
        while l1.is_some() || l2.is_some() || carry != 0 {
            let sum = carry + l1.as_ref().map_or(0, |n| n.val) + l2.as_ref().map_or(0, |n| n.val);
            carry = sum / 10;
            curr.next = Some(Box::new(ListNode::new(sum % 10)));
            curr = curr.next.as_mut().unwrap();
            l1 = l1.and_then(|n| n.next);
            l2 = l2.and_then(|n| n.next);
        }
        dummy.next
    }
}

```

## time O(1)

```rust
/**
 * Time: O(N)
 * Memory: O(N)
 */
impl Solution {
    pub fn add_two_numbers(mut l1: Option<Box<ListNode>>, mut l2: Option<Box<ListNode>>) -> Option<Box<ListNode>> {
        let mut dummy = ListNode::new(0);
        let mut curr = &mut dummy;
        let mut carry = 0;
        while l1.is_some() || l2.is_some() || carry != 0 {
            let mut sum = carry;
            if let Some(node) = l1 {
                sum += node.val;
                l1 = node.next;
            }
            if let Some(node) = l2 {
                sum += node.val;
                l2 = node.next;
            }
            carry = sum / 10;
            curr.next = Some(Box::new(ListNode::new(sum % 10)));
            curr = curr.next.as_mut().unwrap();
        }
        dummy.next
    }
}

```

## Sweet Spot

```rust
/**
 * Time: O(N)
 * Memory: O(N)
 */
impl Solution {
    pub fn add_two_numbers(mut l1: Option<Box<ListNode>>, mut l2: Option<Box<ListNode>>) -> Option<Box<ListNode>> {
        let mut dummy = Box::new(ListNode::new(0));
        let mut curr = &mut dummy;
        let mut carry = 0;
        while l1.is_some() || l2.is_some() || carry != 0 {
            let sum = carry + l1.as_ref().map_or(0, |n| n.val) + l2.as_ref().map_or(0, |n| n.val);
            carry = sum / 10;
            curr.next = Some(Box::new(ListNode::new(sum % 10)));
            curr = curr.next.as_mut().unwrap();
            l1 = l1.and_then(|n| n.next);
            l2 = l2.and_then(|n| n.next);
        }
        dummy.next
    }
}

```

# ruby

## memory O(1)

```ruby
# Time: O(N)
# Memory: O(1)
def add_two_numbers(l1, l2)
    dummy = ListNode.new(0)
    curr = dummy
    carry = 0
    while l1 || l2 || carry != 0
        sum = (l1 ? l1.val : 0) + (l2 ? l2.val : 0) + carry
        carry = sum / 10
        if l1
            l1.val = sum % 10
            curr.next = l1
            l1 = l1.next
        elsif l2
            l2.val = sum % 10
            curr.next = l2
            l2 = l2.next
        else
            curr.next = ListNode.new(carry)
            carry = 0
        end
        curr = curr.next
        if l2 && curr != l2 then l2 = l2.next end
    end
    dummy.next
end

```

## time O(1)

```ruby
# Time: O(N)
# Memory: O(N)
def add_two_numbers(l1, l2)
    dummy = ListNode.new(0)
    curr = dummy
    carry = 0
    while l1 || l2 || carry != 0
        sum = (l1 ? l1.val : 0) + (l2 ? l2.val : 0) + carry
        carry = sum / 10
        curr.next = ListNode.new(sum % 10)
        curr = curr.next
        l1 = l1.next if l1
        l2 = l2.next if l2
    end
    dummy.next
end

```

## Sweet Spot

```ruby
# Time: O(N)
# Memory: O(N)
def add_two_numbers(l1, l2)
    dummy = ListNode.new(0)
    curr = dummy
    carry = 0
    while l1 || l2 || carry != 0
        sum = (l1 ? l1.val : 0) + (l2 ? l2.val : 0) + carry
        carry = sum / 10
        curr.next = ListNode.new(sum % 10)
        curr = curr.next
        l1 = l1 ? l1.next : nil
        l2 = l2 ? l2.next : nil
    end
    dummy.next
end

```

# php

## memory O(1)

```php
/**
 * Time: O(N)
 * Memory: O(1)
 */
class Solution {
    function addTwoNumbers($l1, $l2) {
        $dummy = new ListNode(0);
        $curr = $dummy;
        $carry = 0;
        while ($l1 !== null || $l2 !== null || $carry !== 0) {
            $sum = ($l1 ? $l1->val : 0) + ($l2 ? $l2->val : 0) + $carry;
            $carry = (int)($sum / 10);
            if ($l1 !== null) {
                $l1->val = $sum % 10;
                $curr->next = $l1;
                $l1 = $l1->next;
            } elseif ($l2 !== null) {
                $l2->val = $sum % 10;
                $curr->next = $l2;
                $l2 = $l2->next;
            } else {
                $curr->next = new ListNode($carry);
                $carry = 0;
            }
            $curr = $curr->next;
            if ($l2 !== null && $curr !== $l2) $l2 = $l2->next;
        }
        return $dummy->next;
    }
}

```

## time O(1)

```php
/**
 * Time: O(N)
 * Memory: O(N)
 */
class Solution {
    function addTwoNumbers($l1, $l2) {
        $dummy = new ListNode(0);
        $curr = $dummy;
        $carry = 0;
        while ($l1 !== null || $l2 !== null || $carry !== 0) {
            $sum = ($l1 ? $l1->val : 0) + ($l2 ? $l2->val : 0) + $carry;
            $carry = (int)($sum / 10);
            $curr->next = new ListNode($sum % 10);
            $curr = $curr->next;
            if ($l1) $l1 = $l1->next;
            if ($l2) $l2 = $l2->next;
        }
        return $dummy->next;
    }
}

```

## Sweet Spot

```php
/**
 * Time: O(N)
 * Memory: O(N)
 */
class Solution {
    function addTwoNumbers($l1, $l2) {
        $dummy = new ListNode(0);
        $curr = $dummy;
        $carry = 0;
        while ($l1 || $l2 || $carry) {
            $sum = ($l1 ? $l1->val : 0) + ($l2 ? $l2->val : 0) + $carry;
            $carry = (int)($sum / 10);
            $curr->next = new ListNode($sum % 10);
            $curr = $curr->next;
            $l1 = $l1 ? $l1->next : null;
            $l2 = $l2 ? $l2->next : null;
        }
        return $dummy->next;
    }
}

```

# dart

## memory O(1)

```dart
/**
 * Time: O(N)
 * Memory: O(1)
 */
class Solution {
  ListNode? addTwoNumbers(ListNode? l1, ListNode? l2) {
    ListNode dummy = ListNode(0);
    ListNode curr = dummy;
    int carry = 0;
    while (l1 != null || l2 != null || carry != 0) {
      int sum = (l1?.val ?? 0) + (l2?.val ?? 0) + carry;
      carry = sum ~/ 10;
      if (l1 != null) {
        l1.val = sum % 10;
        curr.next = l1;
        l1 = l1.next;
      } else if (l2 != null) {
        l2.val = sum % 10;
        curr.next = l2;
        l2 = l2.next;
      } else {
        curr.next = ListNode(carry);
        carry = 0;
      }
      curr = curr.next!;
      if (l2 != null && curr != l2) l2 = l2.next;
    }
    return dummy.next;
  }
}

```

## time O(1)

```dart
/**
 * Time: O(N)
 * Memory: O(N)
 */
class Solution {
  ListNode? addTwoNumbers(ListNode? l1, ListNode? l2) {
    ListNode dummyHead = ListNode(0);
    ListNode curr = dummyHead;
    int carry = 0;
    while (l1 != null || l2 != null || carry != 0) {
      int sum = (l1?.val ?? 0) + (l2?.val ?? 0) + carry;
      carry = sum ~/ 10;
      curr.next = ListNode(sum % 10);
      curr = curr.next!;
      l1 = l1?.next;
      l2 = l2?.next;
    }
    return dummyHead.next;
  }
}

```

## Sweet Spot

```dart
/**
 * Time: O(N)
 * Memory: O(N)
 */
class Solution {
  ListNode? addTwoNumbers(ListNode? l1, ListNode? l2) {
    ListNode dummy = ListNode(0);
    ListNode curr = dummy;
    int carry = 0;
    while (l1 != null || l2 != null || carry != 0) {
      int sum = (l1?.val ?? 0) + (l2?.val ?? 0) + carry;
      carry = sum ~/ 10;
      curr.next = ListNode(sum % 10);
      curr = curr.next!;
      l1 = l1?.next;
      l2 = l2?.next;
    }
    return dummy.next;
  }
}

```

# scala

## memory O(1)

```scala
/**
 * Time: O(N)
 * Memory: O(1)
 */
object Solution {
    def addTwoNumbers(l1: ListNode, l2: ListNode): ListNode = {
        val dummy = new ListNode(0)
        var curr = dummy
        var p1 = l1
        var p2 = l2
        var carry = 0
        while (p1 != null || p2 != null || carry != 0) {
            val sum = (if (p1 != null) p1.x else 0) + (if (p2 != null) p2.x else 0) + carry
            carry = sum / 10
            if (p1 != null) {
                p1.x = sum % 10
                curr.next = p1
                p1 = p1.next
            } else if (p2 != null) {
                p2.x = sum % 10
                curr.next = p2
                p2 = p2.next
            } else {
                curr.next = new ListNode(carry)
                carry = 0
            }
            curr = curr.next
            if (p2 != null && curr != p2) p2 = p2.next
        }
        dummy.next
    }
}

```

## time O(1)

```scala
/**
 * Time: O(N)
 * Memory: O(N)
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

```

## Sweet Spot

```scala
/**
 * Time: O(N)
 * Memory: O(N)
 */
object Solution {
    def addTwoNumbers(l1: ListNode, l2: ListNode): ListNode = {
        val dummy = new ListNode(0)
        var curr = dummy
        var p1 = l1
        var p2 = l2
        var carry = 0
        while (p1 != null || p2 != null || carry != 0) {
            val sum = (if (p1 != null) p1.x else 0) + (if (p2 != null) p2.x else 0) + carry
            carry = sum / 10
            curr.next = new ListNode(sum % 10)
            curr = curr.next
            if (p1 != null) p1 = p1.next
            if (p2 != null) p2 = p2.next
        }
        dummy.next
    }
}

```

# elixir

## memory O(1)

```elixir
# Time: O(N)
# Memory: O(N)
defmodule Solution do
  @spec add_two_numbers(l1 :: ListNode.t | nil, l2 :: ListNode.t | nil) :: ListNode.t | nil
  def add_two_numbers(l1, l2), do: add(l1, l2, 0)

  defp add(nil, nil, 0), do: nil
  defp add(nil, nil, carry), do: %ListNode{val: carry, next: nil}
  defp add(l1, l2, carry) do
    v1 = if l1, do: l1.val, else: 0
    v2 = if l2, do: l2.val, else: 0
    sum = v1 + v2 + carry
    %ListNode{
      val: rem(sum, 10),
      next: add(if(l1, do: l1.next), if(l2, do: l2.next), div(sum, 10))
    }
  end
end

```

## time O(1)

```elixir
# Time: O(N)
# Memory: O(N)
defmodule Solution do
  @spec add_two_numbers(l1 :: ListNode.t | nil, l2 :: ListNode.t | nil) :: ListNode.t | nil
  def add_two_numbers(l1, l2), do: solve(l1, l2, 0)

  defp solve(nil, nil, 0), do: nil
  defp solve(l1, l2, carry) do
    v1 = if l1, do: l1.val, else: 0
    v2 = if l2, do: l2.val, else: 0
    sum = v1 + v2 + carry
    %ListNode{val: rem(sum, 10), next: solve(if(l1, do: l1.next), if(l2, do: l2.next), div(sum, 10))}
  end
end

```

## Sweet Spot

```elixir
# Time: O(N)
# Memory: O(N)
defmodule Solution do
  @spec add_two_numbers(l1 :: ListNode.t | nil, l2 :: ListNode.t | nil) :: ListNode.t | nil
  def add_two_numbers(l1, l2), do: solve(l1, l2, 0)

  defp solve(nil, nil, 0), do: nil
  defp solve(l1, l2, carry) do
    val1 = if l1, do: l1.val, else: 0
    val2 = if l2, do: l2.val, else: 0
    sum = val1 + val2 + carry
    %ListNode{val: rem(sum, 10), next: solve(next_node(l1), next_node(l2), div(sum, 10))}
  end

  defp next_node(nil), do: nil
  defp next_node(node), do: node.next
end

```

# erlang

## memory O(1)

```erlang
%% Time: O(N)
%% Memory: O(N)
add_two_numbers(L1, L2) -> add_with_carry(L1, L2, 0).

add_with_carry(null, null, 0) -> null;
add_with_carry(null, null, C) -> #list_node{val = C, next = null};
add_with_carry(L1, L2, C) ->
    V1 = case L1 of null -> 0; _ -> L1#list_node.val end,
    V2 = case L2 of null -> 0; _ -> L2#list_node.val end,
    Sum = V1 + V2 + C,
    N1 = case L1 of null -> null; _ -> L1#list_node.next end,
    N2 = case L2 of null -> null; _ -> L2#list_node.next end,
    #list_node{val = Sum rem 10, next = add_with_carry(N1, N2, Sum div 10)}.

```

## time O(1)

```erlang
%% Time: O(N)
%% Memory: O(N)
add_two_numbers(L1, L2) -> do_add(L1, L2, 0).

do_add(null, null, 0) -> null;
do_add(L1, L2, Carry) ->
    V1 = if L1 == null -> 0; true -> L1#list_node.val end,
    V2 = if L2 == null -> 0; true -> L2#list_node.val end,
    Sum = V1 + V2 + Carry,
    #list_node{
        val = Sum rem 10,
        next = do_add(if L1 == null -> null; true -> L1#list_node.next end,
                      if L2 == null -> null; true -> L2#list_node.next end,
                      Sum div 10)
    }.

```

## Sweet Spot

```erlang
%% Time: O(N)
%% Memory: O(N)
add_two_numbers(L1, L2) -> do_add(L1, L2, 0).

do_add(null, null, 0) -> null;
do_add(L1, L2, Carry) ->
    V1 = case L1 of null -> 0; _ -> L1#list_node.val end,
    V2 = case L2 of null -> 0; _ -> L2#list_node.val end,
    Sum = V1 + V2 + Carry,
    #list_node{
        val = Sum rem 10,
        next = do_add(case L1 of null -> null; _ -> L1#list_node.next end,
                      case L2 of null -> null; _ -> L2#list_node.next end,
                      Sum div 10)
    }.

```

# Racket

## memory O(1)

```racket
; Time: O(N)
; Memory: O(N)
(define/contract (add-two-numbers l1 l2)
  (-> (or/c list-node? #f) (or/c list-node? #f) (or/c list-node? #f))
  (let loop ([l1 l1] [l2 l2] [carry 0])
    (cond
      [(and (not l1) (not l2) (zero? carry)) #f]
      [else
       (let* ([v1 (if l1 (list-node-val l1) 0)]
              [v2 (if l2 (list-node-val l2) 0)]
              [sum (+ v1 v2 carry)])
         (list-node (remainder sum 10)
                    (loop (if l1 (list-node-next l1) #f)
                          (if l2 (list-node-next l2) #f)
                          (quotient sum 10))))])))

```

## time O(1)

```racket
; Time: O(N)
; Memory: O(N)
(define/contract (add-two-numbers l1 l2)
  (-> (or/c list-node? #f) (or/c list-node? #f) (or/c list-node? #f))
  (let add ([a l1] [b l2] [c 0])
    (if (and (not a) (not b) (zero? c)) #f
        (let* ([v1 (if a (list-node-val a) 0)]
               [v2 (if b (list-node-val b) 0)]
               [s (+ v1 v2 c)])
          (list-node (remainder s 10) (add (and a (list-node-next a)) (and b (list-node-next b)) (quotient s 10)))))))

```

## Sweet Spot

```racket
; Time: O(N)
; Memory: O(N)
(define/contract (add-two-numbers l1 l2)
  (-> (or/c list-node? #f) (or/c list-node? #f) (or/c list-node? #f))
  (let helper ([l1 l1] [l2 l2] [c 0])
    (if (and (not l1) (not l2) (= c 0)) #f
        (let* ([v1 (if l1 (list-node-val l1) 0)]
               [v2 (if l2 (list-node-val l2) 0)]
               [sum (+ v1 v2 c)])
          (list-node (remainder sum 10) 
                     (helper (if l1 (list-node-next l1) #f) 
                             (if l2 (list-node-next l2) #f) 
                             (quotient sum 10)))))))

```