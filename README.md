# today-I-learned

### 2019-11-14
- microtasks 并不一定是在当前 task 执行完，下一次 task 执行之前执行。在当前 task 执行中时，如果执行栈里没有其他待执行的 JavaScript，就会立即执行 microtasks。
> [Execution of a Job can be initiated only when there is no running execution context and the execution context stack is empty](https://www.ecma-international.org/ecma-262/6.0/#sec-jobs-and-job-queues)
