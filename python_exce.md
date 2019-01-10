####一、队列的使用
*Queue是线程安全的队列(FIFO)，用于消费者和生产者线程之间的信息传递*

 `class Queue.Queue（maxsize=0）`maxsize指明了队列中能存放的数据个数上限，如果maxsize小于或者大于0，队列大小无限制，maxsize大于0，则长度为maxsize。默认长度无限制。达到上限，插入受限制，直到队列中的数据被消费掉。

1.FIFO队列

```
import Queue
que=Queue.Queue()
for i in range(10): 
    que.put(i)
whie not que.empty() 
   print (que.get())
```
2.LIFO队列
```
import Queue
que = Queue.LifoQueue()

```
3.优先级队列
```
import Queue
que = Queue.PriorityQueue()

```
#####队列常用方法
1.que.qsize()获取队列长度

2.que.empty()队列是否为空

3.que.ful()队类是否已满

4.que.join()阻塞调用进程，直到队列中的所有任务被处理掉。当消费者调用task_done()，未完成的任务数会减少。当任务数减少到0，join（）解除阻塞。

5.que.get_nowait()/que.put_nowait() 无阻塞的向队列中移除/添加任务，队类满或者空直接抛出异常

####二、