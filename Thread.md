# Thread

## 内核级线程 & 用户级线程
| kernel-level Thread | User-level Thread |
| ----- | ------ |
| Implemented by OS | Implemented by users |
| Recognized by OS | OS doesn't recognized | 
| Implementation is complicated | Implementation is easy | 
| Context switch time is more | Context switch time is less |
| Hardware support is needed | requires no hardware support | 
| If one kernel thread perform blocking operation then another thread can continue execution | If one user level thread perform blocking operation then entrie process will be blocked | 














