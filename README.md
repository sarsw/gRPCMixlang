# gRPC Mixed Language

Exercise with clients and server C++ gRPC comms using VCpkg, Cmake and VSCode.

C++ folder structure & build process :

```project
|______build
|______proto
| |______helloworld.proto
|
|______src
| |______server.cpp
| |______client.cpp
|______CMakeLists.txt

cd proto
protoc -I. --cpp_out=. helloworld.proto 
protoc -I. --grpc_out=. --plugin=protoc-gen-grpc="c:\src\vcpkg\packages\grpc_x64-windows\tools\grpc\grpc_cpp_plugin.exe" helloworld.proto
cd build

cmake -G "Visual Studio 16 2019" ../ -DCMAKE_TOOLCHAIN_FILE=c:\src\vcpkg\scripts\buildsystems\vcpkg.cmake

cmake --build .```
