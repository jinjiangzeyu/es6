#Generator函数
#####Generator 函数是一个普通函数，但是有两个特征：    
1.function关键字与函数名之间有一个星号      
2.函数体内部使用yield表达式，定义不同的内部状态        
Generator 函数的调用方法与普通函数一样，也是在函数名后面加上一对圆括号。         
不同的是，调用 Generator 函数后，该函数并不执行，返回的也不是函数运行结果，而是一个指向内部状态的指针对象     
```
function* helloWorldGenerator() {
  yield 'hello';
  yield 'world';
  return 'ending';
}
var hw = helloWorldGenerator();
hw.next()
// { value: 'hello', done: false }
hw.next()
// { value: 'world', done: false }
hw.next()
// { value: 'ending', done: true }
hw.next()
// { value: undefined, done: true }
```
#####yield 表达式
遍历器对象的next方法的运行逻辑如下。    
>1.遇到yield表达式，就暂停执行后面的操作，并将紧跟在yield后面的那个表达式的值，作为返回的对象的value属性值。     
2.下一次调用next方法时，再继续往下执行，直到遇到下一个yield表达式。      
3.如果没有再遇到新的yield表达式，就一直运行到函数结束，直到return语句为止，并将return语句后面的表达式的值，作为返回的对象的value属性值。      
4.如果该函数没有return语句，则返回的对象的value属性值为undefined。     

*其实Generator函数，就是分段执行，yield是暂停，next方法是恢复执行

#####for...of循环
for...of循环可以自动遍历 Generator 函数时生成的Iterator对象，且此时不再需要调用next方法      
当done：trun停止运行！retrun之后的值也不会返回！
```
function* foo() {
  yield 1;
  yield 2;
  yield 3;
  yield 4;
  yield 5;
  return 6;
}
for (let v of foo()) {
  console.log(v);
}
// 1 2 3 4 5
```