### Linux进程的五个段

1. BSS段：BSS段（bss segment）通常是指用来存放程序中**未初始化的全局变量**的一块内存区域。BSS是英文Block Started by Symbol的简称。BSS段属于静态内存分配。
2. 数据段：数据段（data segment）通常是指用来存放程序中**已初始化的全局变量**的一块内存区域。数据段属于静态内存分配。
3. 代码段：代码段（code segment/text segment）通常是指用来存放**程序执行代码**的一块内存区域。这部分区域的大小在程序运行前就已经确定，并且内存区域通常属于只读, 某些架构也允许代码段为可写，即允许修改程序。在代码段中，也有可能包含一些**只读的常数变量**，例如字符串常量等。
4. 堆（heap）：堆是用于存放进程运行中被动态分配的内存段，它的大小并不固定，可动态扩张或缩减。当进程调用malloc等函数分配内存时，新分配的内存就被动态添加到堆上（堆被扩张）；当利用free等函数释放内存时，被释放的内存从堆中被剔除（堆被缩减）
5. 栈(stack)：栈又称堆栈， 是用户存放程序临时创建的局部变量，也就是说我们函数括弧“{}”中定义的变量（但不包括static声明的变量，static意味着在数据段中存放变量）。除此以外，在函数被调用时，其参数也会被压入发起调用的进程栈中，并且待到调用结束后，函数的返回值也会被存放回栈中。由于栈的先进后出特点，所以栈特别方便用来保存/恢复调用现场。从这个意义上讲，我们可以把堆栈看成一个寄存、交换临时数据的内存区。