# mitmproxy-c++ 版本简易正向代理

## 开发前的工作(Centos7)
```bash
yum -y install gcc gcc-c++ 
#yum -y install epel-release 
yum -y install boost boost-devel 

```

## 编译安装，使用gcc编译，方便调试
```
c++ -o proxy \
    proxy.cpp \
    ProxyServer.cpp ProxyWorker.cpp ProxyHeaders.cpp ProxyAutoBuffer.cpp ProxyUri.cpp ProxyController.cpp \
    -lboost_thread \
    -lboost_system \
    -lboost_regex \
    -lssl \
    -lcrypto \
    -std=c++11
```

## 使用Camke3编译 (RECOMAND)
```
mkdir build && cd build && cmake ../ && make 

```

## 开始运行和使用
```
# 注意 proxy 和 Cert目录在一个目录下。
cp -r ./build/proxy . 
./proxy 
```

## depends 
- cpp 4.9.4
- boost 1.62
- openssl 1.1.1w

## hsts
```
NET::ERR_CERT_AUTHORITY_INVALID
NET::ERR_CERT_AUTHORITY_INVALID
```
