# 0x01 Go安装及配置
下载并安装goland 2021.1系列：https://www.jetbrains.com/go/download/other.html
goland 2021.1无限试用方式：https://ybdt.me/2022/01/13/如何放心的白嫖四大主流语言IDE/
下载go语言编译器：https://go.dev/dl/

Ubuntu 18.04下载安装配置Go环境
```
下载go 1.18系列：
wget https://go.dev/dl/go1.18.10.linux-amd64.tar.gz

解压缩并移动到/usr/local下：
tar xvf go1.18.10.linux-amd64.tar.gz && mv go /usr/local/

创建GOPATH目录并在~/.bashrc下配置4个环境变量
mkdir /root/go
export GOROOT=/usr/local/go
export GOPATH=/root/go
export GOPROXY="https://goproxy.cn,direct"
export PATH=$GOROOT/bin:$PATH
```

Win10配置Go环境
```
GOROOT=C:\Program Files\Go
GOPATH=C:\Users\admin\go
GOPROXY=https://goproxy.cn,direct
环境变量Path中添加%GOROOT%\bin

通过命令行设置GO111MODULE的值
go env -w GO111MODULE=on
go env -u GO111MODULE
```

Mac 12.6配置Go环境
```
在~/.zshrc中添加
export GOROOT=/usr/local/go
export GOPATH=/Users/ybdt/go
export GOPROXY="https://goproxy.cn,direct"
export PATH=$PATH:$GOROOT/bin

通过命令行设置GO111MODULE的值
go env -w GO111MODULE=on
go env -u GO111MODULE
```

GO111MODULE解释
```
GO111MODULE环境变量主要是用来开启或关闭模块支持的。

它有三个可选值：off、on、auto，默认值是 auto。

GO111MODULE=off  无模块支持，go 会从 GOPATH 和 vendor 文件夹寻找包。
GO111MODULE=on   有模块支持，go 会忽略 GOPATH 和 vendor 文件夹，只根据 go.mod 下载依赖。
GO111MODULE=auto 在 $GOPATH/src 外面且根目录有 go.mod 文件时，开启模块支持。
在使用模块的时候，GOPATH 是无意义的，不过它还是会把下载的依赖储存在 $GOPATH/src/mod 中，也会把 go install 的结果放在 $GOPATH/bin 中。

可以在DOS命令行下直接使用 go env -w 进行设置。

这个环境变量是在Go-1.11版本引入的，在go1.11版本前，想要对go语言包进行管理，只能依赖第三方库实现，比如Vendor，GoVendor，GoDep，Dep，Glide等等。由于我安装的Go语言是1.14版本的，所以选择开启模块支持，设置如下：
go env -w GO111MODULE=on
<说明> 也可以使用上面的方法设置环境变量的值，但是个人觉得这种命令行设置的方式更方便一些。可以用 go env -u 恢复其默认设置。例如，恢复GO111MODULE的默认值，可以使用：
go env -u GO111MODULE
<备注> 从 Go 1.11 开始 Go 语言开始支持 Go modules 来解决大家长久以来诟病的Go语言依赖包管理问题。go module 是Go语言从 1.11 版本开始官方推出的版本管理工具，并且从 Go 1.13 版本开始，go module 成为了Go语言默认的依赖管理工具。

在Go语言 1.12 版本之前，要启用 go module 工具首先要设置环境变量 GO111MODULE，不过在Go语言 1.13 及以后的版本则不再需要设置该环境变量。

【2021.5.8号修订】从 Go 1.16版本开始，默认启用modules，这在1.15的时候已经预告过了。现在GO111MODULE的默认值为on。在Go 1.17版本中这个环境变量将会被删除。
```

参考文章：
https://www.cnblogs.com/yunfan1024/p/13497686.html
https://www.cnblogs.com/hi3254014978/p/15172691.html

# 0x02 Go跨平台编译
选项解释
```
go tool dist list # 查看支持哪些系统和架构
-ldflags "-s -w" # 用于缩小体积
```

## 01 Windows下通过Powershell编译Windows、Linux、MacOS
编译windows下的可执行文件
```
$Env:GOOS = "windows"; $Env:GOARCH = "amd64"
go build -o windows_amd64.exe main.go

$Env:GOOS = "windows"; $Env:GOARCH = "amd64"
go build -ldflags "-s -w" -o windows_amd64.exe main.go
```

编译linux下的可执行文件
```
$Env:GOOS = "linux"; $Env:GOARCH = "amd64"
go build -o linux_amd64 main.go

$Env:GOOS = "linux"; $Env:GOARCH = "amd64"
go build -ldflags "-s -w" -o linux_amd64 main.go
```

编译macos下的可执行文件
```
$Env:GOOS = "darwin"; $Env:GOARCH = "amd64"
go build -o darwin_amd64 main.go

$Env:GOOS = "darwin"; $Env:GOARCH = "amd64"
go build -ldflags "-s -w" -o darwin_amd64 main.go
```

## 02 Mac、Linux下通过默认shell编译Windows、Linux、MacOS
编译macos下的可执行文件
```
env GOOS=darwin GOARCH=amd64 go build -o darwin_amd64 main.go

env GOOS=darwin GOARCH=amd64 go build -ldflags "-s -w" -o darwin_amd64 main.go
```

编译linux下的可执行文件
```
env GOOS=linux GOARCH=amd64 go build -o linux_amd64 main.go

env GOOS=linux GOARCH=amd64 go build -ldflags "-s -w" -o linux_amd64 main.go
```

编译windows下的可执行文件
```
env GOOS=windows GOARCH=amd64 go build -o windows_amd64.exe main.go

env GOOS=windows GOARCH=amd64 go build -ldflags "-s -w" -o windows_amd64.exe main.go
```