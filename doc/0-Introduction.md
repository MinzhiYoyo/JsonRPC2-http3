# 介绍

这是一个基于C++实现的 `Json RPC 2.0` 的库，并使用`HTTP3`进行传输，使用`xquic`协议来实现。

本项目开发环境：
- `Linux`: Ubuntu 24.04.2 LTS for WSL2
- `GCC`: gcc (Ubuntu 13.3.0-6ubuntu2~24.04) 13.3.0
- `IDE`: Clion IDE Remote Development 以及 Trae AI Remote Development
- `cmake`: version 3.28.3

# 依赖安装

- `C++ 23`：
  - `gcc 13.0` 或者 `clang 16.0`
- `CMake 3.20`
- `xquic`: 以下两个方式选择
  1. 参考[xquic](https://github.com/alibaba/xquic)并把`build`中的静态库和动态库复制到`lib`文件夹下，主要是静态库。
  2. 使用本项目的`lib`文件夹下的`xquic`，以及`include`下的`xquic`头文件（仅在同开发环境使用）
- `nlohmann/json`：参考[nlonhmann/json](https://github.com/nlohmann/json)
  > 仅需要头文件，包含在`include`下，可直接使用
- `openssl`：用于生成证书，`http3`必须使用`tls1.3`加密，需要自签证书，证书放在`certs`目录，里面有测试用的证书，测试证书请勿用于生产环境。
- `boost`: 参考[boost](https://www.boost.org/)，用于异步通信库

# 实现过程

```
quic -> http3 ---------
                      |
json -> jsonrpc 2.0 --|
                      |
                      v
         Json RPC 2.0 Based HTTP3.0
```

# Acknowledgement

感谢以下项目的支持：

Jetbrains

Trea(Byte dancing)

xquic: Alibaba

tquic: Tencent

Json: Nlohmann

