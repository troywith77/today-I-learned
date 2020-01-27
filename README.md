# today-I-learned

### 2020-01-27
在`c`中，数组里的元素的内存地址是根据数组里的类型控制的，比如`int nums[3]`，每个`int`都是`int`占4个`byte`，`nums[0]`的内存地址是`0x100`，接下来的元素内存地址就是`0x104`和`0x108`。

### 2020-01-27
在`c`中，定义一个`string`可以使用`char *s`来定义，`s`是一个指针指向第一个`char`的内存地址。

### 2019-12-25
In React 16 and earlier, only updates inside React event handlers are batched by default. There is an unstable API `ReactDOM.unstable_batchedUpdates` to force batching outside React event handlers.

多次 setState 不会立即重新调用 render 重新渲染，React 会 batch 然后只执行一次渲染，但是这只在 `React event handlers` 中表现（在  `Promise.then` 或 `setTimeout` 等中没有实现），因为 `React event handlers` 实际调用了 `ReactDOM.unstable_batchedUpdates` 这个方法来批量处理更新。

### 2019-12-22
`rAF` 是在下一次重绘之前调用，通常是一秒钟60次，与屏幕刷新率相同。如果刷新率更高，浏览器也会与之匹配。所以使用 `rAF` 绘制动画时，不能默认每一次间隔就是 1/60 sec。

### 2019-12-01
- `toLocaleString` 可以传入 `options` 来修改日期格式。 
```javascript
new Date().toLocaleString('zh-cn', { weekday: 'long' })
// "星期日"
new Date().toLocaleString('zh-cn', { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' })
// "2019年12月1日星期日"
```

### 2019-11-14
- microtasks 并不一定是在当前 task 执行完，下一次 task 执行之前执行。在当前 task 执行中时，如果执行栈里没有其他待执行的 JavaScript，就会立即执行 microtasks。
> [Execution of a Job can be initiated only when there is no running execution context and the execution context stack is empty](https://www.ecma-international.org/ecma-262/6.0/#sec-jobs-and-job-queues)
