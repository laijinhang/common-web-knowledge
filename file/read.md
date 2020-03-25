在Go语言中，有以下几种方式进行读操作：
1. syscall包
2. os包
3. 第三方包

### 1. syscall包
### 2. os包
os.Open()

func Open(name string) (file *File, err error)Open打开一个文件用于读取，如果操作成功，返回的文件对象的方法用于读取数据，对应的文件描述符具有O_RDONLY模式
### 3. 第三方包 
