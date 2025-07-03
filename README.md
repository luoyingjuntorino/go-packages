# go-packages
1. create a repo *go-packages* on github.

2. 初始化项目依赖，生成go.mod文件
```bash
go mod init github.com/luoyingjuntorino/go-packages
```

```go
go-packages/
├── go.mod // module github.com/luoyingjuntorino/go-packages
└── hello/
    └── hello.go // package hello
```

```go
//hello.go

package hello

import "fmt"

func SayHi() {
	fmt.Println("Hello, World! this is a Go package!")
}
```
*push to github*
```bash
git add .
git commit -m "updates"
git tag v0.1.1
git push origin main --tags
```
*others want to use the package*
```go
package main

import hello "github.com/luoyingjuntorino/go-packages/hello"

func main() {
	hello.SayHi()
}

```
```bash
go get github.com/luoyingjuntorino/go-packages/hello@v0.1.1
```
```bash
go run .\main.go
```