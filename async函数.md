#async函数
它就是 Generator 函数的语法糖。async函数就是将 Generator 函数的星号（*）替换成async，将yield替换成await，仅此而已。     
async函数对 Generator 函数的改进，体现在以下四点。     
>1.内置执行器。    
2.更好的语义。async和await，比起星号和yield，语义更清楚了。     
3.更广的适用性。      
4.返回值是 Promise。你可以用then方法指定下一步的操作。  