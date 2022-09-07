# 转载掘金 ：https://juejin.cn/post/7133397098719870990#heading-11

## 第一题
尝试推测它的输出： <br>
const person = { name: '代码与野兽' } <br>
Object.defineProperty(person, 'age', { value: 18 }) <br>

console.log(person.age) <br>
console.log(Object.keys(person)) <br>
输出： <br>
18 <br>
['name'] <br>
解析：很多人容易搞错第二个输出，因为使用 defineProperty 定义的属性默认是不可枚举的。

## 第二题
尝试推测它的输出： <br>
const name = '代码与野兽' <br>
age = 18 <br>

console.log(delete name) <br>
console.log(delete age) <br>
console.log(typeof age) <br>
输出： <br>
false <br>
true <br>
"undefined" <br>
解析：第一个 false 是因为 delete 只能删除对象上的属性，name 不是属性，所以删除失败。第二个 true 是因为我们不使用任何声明创建变量，它会被视作全局变量，挂载到 window 对象上面，等价于 delete window.age，所以删除成功。第三个 undefined 是因为 age 被删除了。




作者：代码与野兽
链接：https://juejin.cn/post/7133397098719870990
来源：稀土掘金
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
