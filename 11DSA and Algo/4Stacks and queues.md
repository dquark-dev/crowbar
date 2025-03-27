## Stacks
stack implements a last-in, first-out, or LIFO, policy

```
STACK-EMPTY(S)
1 if S.top == 0
2     return TRUE
3 else return FALSE
```

```
PUSH(S, x)
1 S.top = S.top + 1
2 S[S.top] = x
```

```
POP(S)
1 if STACK-EMPTY(S)
2     error “underflow”
3 else S.top = S.top - 1
4     return S[S.top + 1]
```

shows the effects of the modifying operations PUSH and POP. Each of the three stack operations takes O(1) time

- pop an empty stack, we say the stack underflows
- S.top exceeds n, the stack overflows
## Queues
the queue implements a first-in, first-out, or FIFO, policy
the queue has a head and a tail
- INSERT operation on a queue ENQUEUE - at the tail of the queue
- we call the DELETE operation DEQUEUE - at the head of the queue


simple array to implement each
