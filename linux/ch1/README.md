### 1. 进程
- ps：当前终端下的子进程
- ps -e：查看运行的进程
- ps -e | grep 进程名：根据进程名查找对应的进程
- kill -9 pid：杀死当前进程
- nohop ./程序 &：后台运行
### 2. 端口
- lsof -i:端口号

### 3. 文件查找
- find / - name 文件名
- grep -r -l "关键字" 路径：查找指定目录中文件名中含有指定关键字的文件
### 4. 查看程序安装目录
- whereis 程序名
### 5. 日志查看
- cat 文件名
- cat 文件 | tail +n 行数：从第一开始查看n行
- cat 文件 | tail -n 行数：查看末尾n行
- tail -f 文件：实时查看文件
### 6. linux上传文件到linux
- scp -r fileName username@server_ip:/home/username/

### 7. 测试网络
- ping ip：测试目的地址是否可达
- ip addr：查看ip
- ifconfig：查看ip

### 8. 磁盘相关
