####Set:它类似于数组，但是成员的值都是唯一的，没有重复的值。
Set 结构的实例有以下属性。   
>Set.prototype.constructor：构造函数，默认就是Set函数。    
Set.prototype.size：返回Set实例的成员总数    

四个操作方法:
>add(value)：添加某个值，返回 Set 结构本身。   
delete(value)：删除某个值，返回一个布尔值，表示删除是否成功。   
has(value)：返回一个布尔值，表示该值是否为Set的成员。   
clear()：清除所有成员，没有返回值。   

四个遍历方法:
>keys()：返回键名的遍历器      
values()：返回键值的遍历器     
entries()：返回键值对的遍历器     
forEach()：使用回调函数遍历每个成员     

####WeakSet与 Set 类似
与set的区别1.WeakSet 的成员只能是对象，而不能是其他类型的值。   
2.WeakSet 中的对象都是弱引用，即垃圾回收机制不考虑 WeakSet 对该对象的引用
WeakSet 可以接受一个数组或类似数组的对象作为参数