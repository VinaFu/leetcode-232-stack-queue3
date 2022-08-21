# leetcode-232-stack-queue3


用stack写queue：
先写空集。然后增加数值
重要的是pop（）部分：由于待会要改变list，所以先拿一个东西装起来，省得待会改变，这个桶子就是firstValue

          class MyQueue:

              def __init__(self):
                  self.queue = []

              def push(self, x: int) -> None:
                  self.queue.append(x)

              def pop(self) -> int:  
                  newQueue = []
                  firstValue = self.queue[0]
                  for i in range(1, len(self.queue)):
                      newQueue.append(self.queue[i])
                  self.queue = newQueue

                  return firstValue

              def peek(self) -> int:
                  return self.queue[0]

              def empty(self) -> bool:
                  return self.queue == []



          # Your MyQueue object will be instantiated and called as such:
          # obj = MyQueue()
          # obj.push(x)
          # param_2 = obj.pop()
          # param_3 = obj.peek()
          # param_4 = obj.empty()
