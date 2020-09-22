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


## 线程共享/私有资源
|线程共享资源|线程私有资源|
|----------|----------|
进程用户 ID 与进程组 ID|线程 
地址空间 | 程序计数器（PC）|
全局变量 | 寄存器（register）|
进程打开的文件描述符 | 栈（stack） |
子进程 | 状态字|
进程代码段 | 
信号及信号服务程序 |
进程共有数据 |











