### client.go
```golang
package main

import "syscall"

func main() {
	sa := syscall.SockaddrInet4{
		Port: 10000,
		Addr: [4]byte{127,0,0,1},
	}
	fd, err := syscall.Socket(syscall.AF_INET, syscall.SOCK_STREAM, syscall.IPPROTO_TCP)
	if err != nil {
		panic(err)
	}
	if err = syscall.Connect(fd, &sa);err != nil {
		panic(err)
	}
	buf := []byte("123")
	if err = syscall.Sendto(fd, buf, 0, &sa);err != nil {
		panic(err)
	}
}
```
### server
```golang
package main

import (
	"fmt"
	"syscall"
)

func main() {
	sa := syscall.SockaddrInet4{
		Port: 10000,
		Addr: [4]byte{127,0,0,1},
	}
	fd, err := syscall.Socket(syscall.AF_INET, syscall.SOCK_STREAM, syscall.IPPROTO_TCP)
	if err != nil {
		panic(err)
	}
	if err = syscall.Bind(fd, &sa);err != nil {
		panic(err)
	}
	if err = syscall.Listen(fd, 1000);err != nil {
		panic(err)
	}
	for {
		nfd, ca, err := syscall.Accept(fd)
		if err != nil {
			continue
		}
		buf := make([]byte, 1024)
		n, err := syscall.Read(nfd, buf)
		fmt.Println(ca)
		fmt.Println(string(buf[:n]), n)
	}
}
```
