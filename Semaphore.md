# 信号量

## P
P operation is also called **wait, sleep or down（阻塞）** operation 

操作动作：
1. semaphore - 1
2. 若 semaphore 减 1 后仍大于或等于 0，则进程继续执行
3. 若 semaphore 减 1 后小于 0，则该进程被阻塞后进入与该信号相对应的队列中，然后转进程调度

## V
V operation is also called **signal, wake-up or up（唤醒）** operation 

操作动作：
1. semaphore + 1
2. 若 semaphore 加 1 后大于 0，说明没有等待进程
3. 若 semaphore 加 1 后小于等于 0，则从该信号的等待队列中唤醒一个等待进程，然后再返回原进程继续执行或者转进程调度
