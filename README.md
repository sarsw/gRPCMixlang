# gRPC Mixed Language

Exercise with HelloWorld gRPC client and server in C++ with a C# client.  C++ was managed via vcpkg and built using cmake. VSCode was the ide of choice with VS 2019 as the compiler.

## Prerequisites
1. [Install VCPKG](https://vcpkg.io/en/getting-started.html). I installed it under c:\src\vcpkg and added it to PATH 
2. Get VS2019 (Community edition will be ok)
3. Get VSCode

Folder structure :

```project
|______build
|______proto
| |______helloworld.proto
|
|______DotNetClient
|______src
| |______server.cpp
| |______client.cpp
|______CMakeLists.txt
```
See the [C++ Readme](CPPreadme.txt) for C++ build details.
To compile and run the c# app use `dotnet run`
