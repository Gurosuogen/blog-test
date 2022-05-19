### 1. 声明对象的两种语法
```js
//1       //属性名//属性值
let obj = {'name':'frank', 'age': 18 }
//2
let obj = new Object({'name': 'frank'})
//3
console.log({'name':'frank','age':18})
```
- 每个key都是对象的属性名(property)
- 每个value都是对象的属性值


### 2. 删
```js
//删除obj的xxx属性
delete obj.xxx
delete obj ['xxx']

//属性名已被删除
'xxx' in obj ===false

//属性名还在，不过该属性名的值为undefined
'xxx' in obj && obj.xxx === undefined

//不能断定'xxx'是否为obj的属性
obj.xxx === undefined
```



### 3. 查
```js
//查看键(属性名)
Object.keys(obj)
//查看值(属性值)
Object.values(obj)
//查看单个属性
obj['key'] //注意单引号，若没有,则查询的是变量
obj.key


//查看所有属性(包含原型)
console.dir(obj)

//查询属性是不是自身所有的(非原型)
obj.hasOwnProperty('xxx')
```

例题
```js
//如何打印出person的所有属性值
let list = ['name', 'age', 'gender']
let person = {name:'frank', age:18, gender:'man'}

for(let i = 0; i < list.length; i++){
	let name = list[i]
	console.log(person__???__)
}
//console.log(person[name])<=正确答案
//console.log(person.name)
//因为在for循环中，声明的变量name遍历了数组list的所有值，这三个值同时在对象person中作为属性存在，所以在for循环中要让console.log()更新name的值才能做到打印出所有person的属性值

```



### 4. 增 / 改
- 有则修改，无则增加

修改或增加属性
```js
//直接赋值
let obj = {name: 'frank'} // name 是字符串

obj.name = 'frank' // name 是字符串

obj['name'] = 'frank'

//obj[name] = 'frank' 错，因 name 值不确定

obj['na'+'me'] = 'frank'

let key = 'name'; obj[key] = 'frank'

//let key = 'name'; obj.key = 'frank'~~ 错，因为 obj.key 等价于 obj['key']

//批量赋值
Object.assign(obj, {age: 18, gender: 'man'})
```

### 5. 'name' in obj和obj.hasOwnProperty('name') 的区别
- 'name' in obj 查看属性name是不是对象obj的属性
- obj.hasOwnProperty('name') 查看属性name是不是对象obj自身(非原型)的属性


