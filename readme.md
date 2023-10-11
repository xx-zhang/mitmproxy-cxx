# 代理

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


## depends 
- cpp 4.9.4
- boost 1.62
- openssl 1.1.1w


## hsts
```
NET::ERR_CERT_AUTHORITY_INVALID
NET::ERR_CERT_AUTHORITY_INVALID
```