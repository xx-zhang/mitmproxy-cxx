cmake_minimum_required(VERSION 3.1)

project(proxy)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(SOURCE_FILES
    proxy.cpp
    ProxyServer.cpp
    ProxyWorker.cpp
    ProxyHeaders.cpp
    ProxyAutoBuffer.cpp
    ProxyUri.cpp
    ProxyController.cpp
)

add_executable(proxy ${SOURCE_FILES})

find_package(Boost REQUIRED COMPONENTS thread system regex)
find_package(OpenSSL REQUIRED)

target_link_libraries(proxy
    Boost::thread
    Boost::system
    Boost::regex
    OpenSSL::SSL
    OpenSSL::Crypto
)
