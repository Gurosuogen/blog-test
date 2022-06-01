1. 解释为什么如下代码会打印 6 个 6

```js
let i = 0
for(i = 0; i<6; i++){
  setTimeout(()=>{
    console.log(i)
  },0)
}
```
答：因为for循环中有一个`setTimeout`的API，它会让整个循环完整的运行完周后输出结果，当运行最后一个循环时`i=5 i++`使得`i=6`不满足条件，于是不继续循环。


2. 写出让上面代码打印 0、1、2、3、4、5 的方法

答：
```js
for(let i = 0; i<6; i++){
  setTimeout(()=>{
    console.log(i)
  },0)
}
```

3. （可选内容）除了使用 for let 配合，还有什么其他方法可以打印出 0、1、2、3、4、5，如果你能找到并写在博客里，可以得到五星好评 :)
```js
let n = -1
while (n < 5) {
  n++;
  console.log(n)
}
```
