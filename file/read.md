在Go语言中，有以下几种方式进行读操作：
1. syscall包
2. os包
3. 第三方包

### 1. syscall包
### 2. os包
os.Open()

func Open(name string) (file *File, err error)Open打开一个文件用于读取，如果操作成功，返回的文件对象的方法用于读取数据，对应的文件描述符具有O_RDONLY模式

func OpenFile(name string, flag int, perm FileMode) (*File, error) 该函数可以用来代替Open or Create函数。该函数主要用来指定参数(os.O_APPEND|os.O_CREATE|os.O_WRONLY)以及文件权限(0666)来打开文件，如果打开成功返回的文件对象将被用作I/O操作
### 3. 第三方包 
