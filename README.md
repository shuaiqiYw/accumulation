# 经验积累

## Object.defineProperty方法
转载 ： https://blog.csdn.net/weixin_46726346/article/details/115913752

## 遍历数组赋值给对象失败，取到的都是最后一项的值
转载 ：https://blog.csdn.net/qq_42612810/article/details/93988429

## git的详细使用
转载 ：https://blog.csdn.net/youzhouliu/article/details/78952453
转载：https://blog.csdn.net/qq_46043634/article/details/104217031

## 宏任务与微任务
  > JS的主线程执行的任务中分为同步任务和异步任务，异步任务再分为宏任务（Task）与微任务（Jobs）
  > 宏任务一般包含：1. script (可以理解为外层同步代码)
                2. setTimeout/setInterval
                3. UI rendering/UI事件
                4. postMessage，MessageChannel
                5. setImmediate，I/O（Node.js）
  > 微任务一般包含：1. Promise
                2.process.nextTick（Node.js） 
                3. Object.observe（已废弃；Proxy 对象替代）
                4. MutaionObserver
  > 情况一:不含嵌套
    主线程 >> 主线程上创建的微任务 >> 主线程上创建的宏任务
  > 情况二:宏任务包含微任务
    主线程 >> 主线程上的宏任务队列1 >> 宏任务队列1中创建的微任务
 
 > 重点：1、第一次执行的时候，解释器会将整体代码script放入宏任务队列中，因此事件循环是从第一个宏任务开始的；
      2、如果在执行微任务的过程中，产生新的微任务添加到微任务队列中，也需要一起清空；微任务队列没清空之前，是不会执行下一个宏任务的。

## vue组件通信方式
/* 
    组件中的通信方式，可以分为
        父==>子：
            1、通过props传值
            2、ref通信
            3、$children通信
        子==>父：
            1、自定义事件this.$emit()
        兄弟==>兄弟：
            1、$parent
            2、事件总线通信eventBus
            3、provide/inject
            4、vuex通信
*/

## 柯里化函数（Currying）
  转载：https://blog.csdn.net/m0_52409770/article/details/123359123

## Object.assign()
   简单来说，就是Object.assign()是对象的静态方法，可以用来复制对象的可枚举属性到目标对象，利用这个特性可以实现对象属性的合并。
   用法： Object.assign(target, ...sources)

  参数：target--->目标对象

      source--->源对象

  返回值：target，即目标对象
  ``` JavaScript
  var target = {name:'qwe',age:'12'};
  var source = {state:'single'};
  var result = Object.assign(target,source)
  console.log(result)
  // {name:'qwe',age:'12',state:'single'}
  /*
    source上的state属性合并到了target对象上。如果只是想将两个或多个对象的属性合并到一起，不改变原有对象的属性，可以用一个空的对象作为target对象。
  */
  // 如果目标对象和源对象有重名属性的，则后面的覆盖前面的
  
## JS高级知识汇总
转载：https://blog.csdn.net/weixin_50926010/article/details/124899601
