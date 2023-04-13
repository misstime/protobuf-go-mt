项目简介
------

本项目属于 protoc 的自定义 golang 插件。  

本项目是对官方 golang 插件进行了少量的修改。官方插件地址 see：  

- https://github.com/protocolbuffers/protobuf-go
- https://pkg.go.dev/google.golang.org/protobuf

相对于官方代码，本项目实现了以下两个功能：

- 枚举类型编译规则的改变。例：Color_Color_Green -> Color_Green
- 通过字段注释支持验证库 [golang validator](https://github.com/go-playground/validator) 

具体变化参详 `/testdata` 内例子

流程备忘
-------

1. 下载 protoc 可执行文件

https://github.com/protocolbuffers/protobuf/releases 

2. 下载或自行编译 protoc golang 插件

```shell
go build -o .\testdata\protoc-gen-go.exe .\cmd\protoc-gen-go\main.go
```

3. 编译生成 pb 文件

```shell
# 仅为备忘，项目无关
protoc -h
protoc --go_out=. *.proto
protoc --go_out=plugins=grpc:. *.proto
```

```shell
.\testdata\protoc-22.3-win64\bin\protoc.exe --go_out=. *.proto
```

tips: 所有测试均在 `/testdata` 中完成。

自定义插件
---------

```shell
cd 项目根目录
go build -o .\testdata\protoc-gen-go-mt.exe .\cmd\protoc-gen-go\main.go

cd testdata
.\protoc-22.3-win64\bin\protoc.exe --go-mt_out=. *.proto
```












