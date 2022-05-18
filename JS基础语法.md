## 表达式
1 + 2 表达式的**值**为3
add(1,2)表达式的值为函数的**返回值**


## 语句
var a = 1 是一个语句

## 表达式和语句的区别
- 表达式一般都有值，语句可能有也可能没有
- 语句一般不会改变环境（声明、赋值）
- 上面两句并不绝对


## 标识符
### 规则
第一个字符，可以是Unicode字母或`$`或`_`或中文

之后的字符，除了上面的，还可以加数字

例：
- `var $1`  可以
- `var 1$` 报错

## if语句
- `if(表达式) {语句1} else {语句2}`
- `{}`在语句只有一句的时候可以省略

## switch语句
```javascript
switch (fruit) {
  case "apple":
  //....
    break;
  case "banana":
  //....
    break;
  default:
  //....
}
```
- 大部分情况不能省略break，少部分情况可以利用break

## [问号冒号表达式](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)
```
function max(a,b) {
	return a > b ? a: b
}
```

## `&&`短路逻辑
- A && B && C && D 取第一个**假值**或者D

## `||`短路逻辑
- A || B || C || D 取第一个**真值**或者D

## while 循环
`while(表达式) {语句}`

### 其他
浮点数不精确可能会造成死循环
```javascript
var a = 0.1
while (a !== 1) {
	console.log(a)
	a = a + 0.1
}
```

## for循环
`for (语句1;表达式2;语句3){循环体}`

- break退出所有循环
- contineue 推出当前一次循环

## label 
- 语法
```javascript
foo : {
	console.log(1);
	break foo;
	console.log(本行不会输出);
}
console.log(2);
```
- 面试
```
//这是一个代码块，代码块里有一个label，label的内容是1
{
 foo:1
}
```
