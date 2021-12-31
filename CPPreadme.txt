project
|______build
|______proto
| |______helloworld.proto
|
|______src
| |______server.cpp
| |______client.cpp
|______CMakeLists.txt

C++ build process:

## get the packages
vcpkg install grpc:x86-windows
vcpkg install protobuf protobuf:x86-windows
vcpkg integrate install   ## get vcpkg integrated into VS (optional I think)

At a command terminal:

cd proto
protoc -I. --cpp_out=. helloworld.proto 
protoc -I. --grpc_out=. --plugin=protoc-gen-grpc="c:\src\vcpkg\packages\grpc_x64-windows\tools\grpc\grpc_cpp_plugin.exe" helloworld.proto
cd build

cmake -G "Visual Studio 16 2019" ../ -DCMAKE_TOOLCHAIN_FILE=c:\src\vcpkg\scripts\buildsystems\vcpkg.cmake

cmake --build .
