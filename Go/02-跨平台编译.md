# 选项解释
```
go tool dist list  # 查看支持哪些系统和架构
-ldflags "-s -w"  # 用于缩小体积
```
# 01-Windows Powershell下编译Windows、Linux、MacOS
cmd下一行编译会报错”go: unsupported GOOS/GOARCH pair linux /386“，可能需要多行执行，反正没有powershell方便
## 编译windows下amd64和386可执行文件
```
$Env:GOOS = "windows"; $Env:GOARCH = "amd64"; go build -ldflags "-s -w" -o windows-amd64.exe main.go
$Env:GOOS = "windows"; $Env:GOARCH = "386"; go build -ldflags "-s -w" -o windows-386.exe main.go
```
## 编译linux下amd64和386可执行文件
```
$Env:GOOS = "linux"; $Env:GOARCH = "amd64"; go build -ldflags "-s -w" -o linux-amd64 main.go
$Env:GOOS = "linux"; $Env:GOARCH = "386"; go build -ldflags "-s -w" -o linux-386 main.go
```
## 编译macos下amd64和arm64可执行文件
```
$Env:GOOS = "darwin"; $Env:GOARCH = "amd64"; go build -ldflags "-s -w" -o darwin-amd64 main.go
$Env:GOOS = "darwin"; $Env:GOARCH = "arm64"; go build -ldflags "-s -w" -o darwin-arm64 main.go
```
# 02-类unix默认shell下编译Windows、Linux、MacOS
## 编译windows下amd64和386可执行文件
```
env GOOS=windows GOARCH=amd64 go build -ldflags "-s -w" -o windows-amd64.exe main.go
env GOOS=windows GOARCH=386 go build -ldflags "-s -w" -o windows-386.exe main.go
```
## 编译linux下amd64和386可执行文件
```
env GOOS=linux GOARCH=amd64 go build -ldflags "-s -w" -o linux-amd64 main.go
env GOOS=linux GOARCH=386 go build -ldflags "-s -w" -o linux-386 main.go
```
## 编译macos下amd64和arm64可执行文件
```
env GOOS=darwin GOARCH=amd64 go build -ldflags "-s -w" -o darwin-amd64 main.go
env GOOS=darwin GOARCH=arm64 go build -ldflags "-s -w" -o darwin-arm64 main.go
```