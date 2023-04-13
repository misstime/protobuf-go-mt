# protobuf-go-mt

本项目属于 protoc 的自定义 golang 插件。

本项目对官方 golang 插件进行了少量的修改。官方插件地址 see：

- https://github.com/protocolbuffers/protobuf-go
- https://pkg.go.dev/google.golang.org/protobuf

相对于官方代码，本项目实现了以下两个功能：

- 枚举类型编译规则的改变。例：Color_Color_Green -> Color_Green
- 通过字段注释支持验证库 [golang validator](https://github.com/go-playground/validator)

具体文档参见相关分支 `/testdata` 目录内例子