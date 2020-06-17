1、监听地址：`func ResolveUDPAddr(network, address string) (*UDPAddr, error)`

2、创建监听：`func ListenUDP(network, laddr *UDPAddr) (*UDPConn, error)`

3、创建连接：`func Dial(network, address string) (Conn, error)`

4、从UDP中读数据：`func (c *UDPConn) ReadFromUDP(b []byte) (n int, addr *UDPAddr, err os.Error)`

5、往UDP中写数据：`func (c *UDPConn) WriteToUDP(b []byte, addr *UDPAddr) (n int, err os.Error)`

6、服务端关闭监听：`func (c *conn) Close() error`

# 1、服务端
流程：
1. 设置监听地址
2. 监听地址
3. 读数据 或 写数据
4. 关闭监听

```go
package main

import (
	"fmt"
	"net"
)

func main() {
	udpAddr, err := net.ResolveUDPAddr("udp", "127.0.0.1:8001")
	if err != nil {
		fmt.Println("ResolveUDPAddr err:", err)
		return
	}
	conn, err := net.ListenUDP("udp", udpAddr)
	if err != nil {
		fmt.Println("ListenUDP err:", err)
		return
	}
	defer conn.Close()

	buf := make([]byte, 1024)
	n, raddr, err := conn.ReadFromUDP(buf)
	if err != nil {
		return
	}
	fmt.Println("客户端发送:", string(buf[:n]))

	// 向客户端发送数据
	_, err = conn.WriteToUDP([]byte("udp data !"), raddr)
	if err != nil {
		fmt.Println("WriteToUDP err:", err)
		return
	}
}
```
# 2、客户端
流程：
1. 建立连接
2. 读数据 或 写数据

```go
package main

import (
	"fmt"
	"net"
)

func main() {
	conn, err := net.Dial("udp", "127.0.0.1:8001")
	if err != nil {
		fmt.Println("net.Dial err:", err)
		return
	}
	defer conn.Close()

	conn.Write([]byte("client udp data!"))

	buf := make([]byte, 1024)
	n, err1 := conn.Read(buf)
	if err1 != nil {
		return
	}
	fmt.Println("服务器：", string(buf[:n]))
}
```