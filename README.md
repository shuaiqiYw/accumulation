# 经验积累

## Object.defineProperty方法
转载 ： https://blog.csdn.net/weixin_46726346/article/details/115913752

## 遍历数组赋值给对象失败，取到的都是最后一项的值
转载 ：https://blog.csdn.net/qq_42612810/article/details/93988429

## git的详细使用
转载 ：https://blog.csdn.net/youzhouliu/article/details/78952453

## 宏任务与微任务
  JS的主线程执行的任务中分为同步任务和异步任务，异步任务再分为宏任务（Task）与微任务（Jobs）
  宏任务一般包含：1. script (可以理解为外层同步代码)
                2. setTimeout/setInterval
                3. UI rendering/UI事件
                4. postMessage，MessageChannel
                5. setImmediate，I/O（Node.js）
  微任务一般包含：1. Promise
                2.process.nextTick（Node.js） 
                3. Object.observe（已废弃；Proxy 对象替代）
                4. MutaionObserver
  情况一:不含嵌套
    主线程 >> 主线程上创建的微任务 >> 主线程上创建的宏任务
  情况二:宏任务包含微任务
    主线程 >> 主线程上的宏任务队列1 >> 宏任务队列1中创建的微任务
 
 重点：1、第一次执行的时候，解释器会将整体代码script放入宏任务队列中，因此事件循环是从第一个宏任务开始的；
      2、如果在执行微任务的过程中，产生新的微任务添加到微任务队列中，也需要一起清空；微任务队列没清空之前，是不会执行下一个宏任务的。

## vue组件通信方式
