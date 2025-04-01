# 安装
## macOS 15.3.2下安装
```
https://go.dev/dl/go1.22.12.darwin-amd64.pkg
通过安装包安装，默认安装路径：/usr/local/go

# 配置环境变量
在~/.zshrc中添加
export GOROOT=/usr/local/go
export GOPATH=/Users/ybdt/go
export GOPROXY="https://goproxy.cn,direct"
export PATH=$PATH:$GOROOT/bin

# 卸载go
sudo rm -rf /usr/local/go
sudo rm /etc/paths.d/go
```

## Win10下安装
```
https://go.dev/dl/go1.22.12.windows-amd64.msi
通过安装包安装，默认安装路径：C:\Program Files\Go

# 配置环境变量
GOROOT=C:\Program Files\Go
GOPATH=C:\Users\admin\go
GOPROXY=https://goproxy.cn,direct
环境变量Path中添加%GOROOT%\bin

# 卸载go
通过win10的应用和功能卸载即可
```

## Ubuntu 18.04下安装
```
wget https://go.dev/dl/go1.22.12.linux-amd64.tar.gz
tar xvf go1.22.12.linux-amd64.tar.gz
mv ./go /usr/local

# 配置环境变量
mkdir $HOME/go
export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export GOPROXY="https://goproxy.cn,direct"
export PATH=$GOROOT/bin:$PATH

# 卸载go
sudo rm -rf /usr/local/go
```

## GO111MODULE解释
```
GO111MODULE环境变量主要是用来开启或关闭模块支持的。

GO111MODULE的值可通过命令行设置
go env -w GO111MODULE=on
go env -u GO111MODULE

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

# 跨平台编译
```
go tool dist list # 查看支持哪些系统和架构
-ldflags "-s -w" # 用于缩小体积
```

## Windows下编译
cmd下一行编译会报错”go: unsupported GOOS/GOARCH pair linux /386“，可能需要多行执行，没有powershell方便
```
# 编译windows下x86架构64位可执行文件
$Env:GOOS = "windows"; $Env:GOARCH = "amd64"; go build -ldflags "-s -w" -o windows-amd64.exe main.go

# 编译windows下x86架构32位可执行文件
$Env:GOOS = "windows"; $Env:GOARCH = "386"; go build -ldflags "-s -w" -o windows-386.exe main.go

# 编译linux下x86架构64位可执行文件
$Env:GOOS = "linux"; $Env:GOARCH = "amd64"; go build -ldflags "-s -w" -o linux-amd64 main.go

# 编译linux下x86架构32位可执行文件
$Env:GOOS = "linux"; $Env:GOARCH = "386"; go build -ldflags "-s -w" -o linux-386 main.go

# 编译macOS下x86架构64位可执行文件
$Env:GOOS = "darwin"; $Env:GOARCH = "amd64"; go build -ldflags "-s -w" -o darwin-amd64 main.go

# 编译macOS下arm架构64位可执行文件
$Env:GOOS = "darwin"; $Env:GOARCH = "arm64"; go build -ldflags "-s -w" -o darwin-arm64 main.go
```

# Linux下编译
```
# 编译windows下x86架构64位可执行文件
env GOOS=windows GOARCH=amd64 go build -ldflags "-s -w" -o windows-amd64.exe main.go

# 编译windows下x86架构32位可执行文件
env GOOS=windows GOARCH=386 go build -ldflags "-s -w" -o windows-386.exe main.go

# 编译linux下x86架构64位可执行文件
env GOOS=linux GOARCH=amd64 go build -ldflags "-s -w" -o linux-amd64 main.go

# 编译linux下x86架构32位可执行文件
env GOOS=linux GOARCH=386 go build -ldflags "-s -w" -o linux-386 main.go

# 编译macOS下x86架构64位可执行文件
env GOOS=darwin GOARCH=amd64 go build -ldflags "-s -w" -o darwin-amd64 main.go

# 编译macOS下arm架构64位可执行文件
env GOOS=darwin GOARCH=arm64 go build -ldflags "-s -w" -o darwin-arm64 main.go
```