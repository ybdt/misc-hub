# 01  UEditor .NET版本任意文件上传漏洞原理
```
漏洞核心代码如下

if (response.ContentType.IndexOf("image") == -1) {
    State = "Url is not an image";
    return this;
}

参考链接：
https://learn.microsoft.com/en-us/dotnet/api/system.string.indexof?view=net-5.0
https://www.freebuf.com/vuls/181814.html
https://zhuanlan.zhihu.com/p/85265552
```