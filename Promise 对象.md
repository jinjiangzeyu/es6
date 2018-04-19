#Promise 对象
####1.Promise 的含义
Promise 是异步编程的一种解决方案，比传统的解决方案——回调函数和事件——更合理和更强大      
Promise对象有以下两个特点。
>1.对象的状态不受外界影响。Promise对象代表一个异步操作，有三种状态：pending、fulfilled和rejected    
2.一旦状态改变，就不会再变，任何时候都可以得到这个结果。

####2.Promise.prototype.then()
Promise 实例具有then方法.    
第一个参数是resolved状态的回调函数，第二个参数（可选）是rejected状态的回调函数。  
####3.Promise.prototype.catch()
Promise.prototype.catch方法是.then(null, rejection)的别名,用于发生错误时的回调。
####4.Promise.prototype.finally()
finally方法用于指定不管 Promise 对象最后状态如何，都会执行的操作。该方法是 ES2018 引入标准的。
####5.Promise.all()
Promise.all方法用于将多个 Promise 实例，包装成一个新的 Promise 实例
####6.Promise.race() 
Promise.race方法同样是将多个 Promise 实例，包装成一个新的 Promise 实例
####7.Promise.resolve() 
有时需要将现有对象转为 Promise 对象，Promise.resolve方法就起到这个作用。
参数是一个 Promise 实例
参数是一个thenable对象
参数不是具有then方法的对象，或根本就不是对象
不带有任何参数
####8.Promise.reject() 
Promise.reject(reason)方法也会返回一个新的 Promise 实例，该实例的状态为rejected
####9.Promise.try()
适用于：不知道或者不想区分，函数f是同步函数还是异步操作，但是想用 Promise 来处理它