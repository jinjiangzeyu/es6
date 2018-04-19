#let和const用法
###let 命令：
1.基本用法
ES6 新增了let命令，用来声明变量。它的用法类似于var，但是所声明的变量，只在let命令所在的代码块内有效。
```
{
  let a = 10;
  var b = 1;
}

a // ReferenceError: a is not defined.
b // 1
```
2.不存在变量提升
```
// var 的情况
console.log(foo); // 输出undefined
var foo = 2;

// let 的情况
console.log(bar); // 报错ReferenceError
let bar = 2;
```
3.暂时性死区(TDZ)
```
var tmp = 123;
if (true) {
  tmp = 'abc'; // ReferenceError
  let tmp;
}
```
4.不允许重复声明
let不允许在相同作用域内，重复声明同一个变量。
```
// 报错
function func() {
  let a = 10;
  var a = 1;
}

// 报错
function func() {
  let a = 10;
  let a = 1;
}
```
5.块级作用域    
第一种场景，内层变量可能会覆盖外层变量。
```
var tmp = new Date();

function f() {
  console.log(tmp);
  if (false) {
    var tmp = 'hello world';
  }
}

f(); // undefined
```
第二种场景，用来计数的循环变量泄露为全局变量。
```
var s = 'hello';

for (var i = 0; i < s.length; i++) {
  console.log(s[i]);
}

console.log(i); // 5
```
###const声明：
#####const声明是一个只读的常量。与let的区别就是，一旦声明，常量的值就不能改变。     
*const声明对象可以添加方法，属性，不能被重新赋值！*       
其他的特性与let声明相同。请参考let相关知识。

#注意es6的变量声明方式共有6种：
1.function声明    
2.var声明   
3.let声明   
4.const声明   
5.class声明  
6.import声明   