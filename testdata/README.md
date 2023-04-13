tips:

- 所有测试均在 `/testdata` 中完成。

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

### 自定义插件

```shell
cd 项目根目录
go build -o .\testdata\protoc-gen-go-mt.exe .\cmd\protoc-gen-go\main.go

cd testdata
.\protoc-22.3-win64\bin\protoc.exe --go-mt_out=. *.proto
```












