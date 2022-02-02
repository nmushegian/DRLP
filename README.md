double-sided rlp
---

Regular rlp is logically equivalent to a singly-linked list with a reference to the last element.
This means you can have O(1) push and pop from the head (index 0) but only push without pop from the tail.

What would RLP require to be equivalent to a doubly-linked list that supports efficiently popping from the tail as well?

The answer is simple: for each RLP node append the length-prefix to the end of the serialized node, in reverse byte-order.

This doubles the serialization overhead, but it is still O(log(n)). It also doubles the cost of most operations, but they are still O(1).