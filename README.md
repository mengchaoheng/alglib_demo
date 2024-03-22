# How to build

## linux
For the demo example
### using commander line tools

run following:
1. create and cd to build folder:
```
mkdir build && cd build
```
2. build the code by g++:
```
$ g++ -I ../src/alglib-cpp/src/ -o demo.out ../src/demo/*.cpp ../src/alglib-cpp/src/*.cpp
```
3. run 
```
./demo.out
```

If create new target, change the name  'demo'. For dir:
```Console
g++ -I ../src/alglib-cpp/src/ -o minlp_basic.out ../src/allocator_dir/*.cpp  ../src/alglib-cpp/src/*.cpp -w -O3
```
then run:
```Console
./minlp_basic.out
```


## test
```Console
➜  build git:(main) ✗ g++ -I ../src/alglib-cpp/src/ -o demo.out ../src/demo/*.cpp ../src/alglib-cpp/src/*.cpp -w
➜  build git:(main) ✗ ./demo.out 
Performance is 2.1 GFLOPS
```

```Console
➜  build git:(main) ✗ g++ -I ../src/alglib-cpp/src/ -o demo.out ../src/demo/*.cpp ../src/alglib-cpp/src/*.cpp -w -O3
➜  build git:(main) ✗ ./demo.out 
Performance is 14.2 GFLOPS
```




## other
为了使用g++编译C++项目并将生成的文件保存到新的build文件夹，你可以在项目根目录下创建一个构建脚本或直接在命令行中执行以下步骤：

创建build文件夹：

mkdir build

进入build文件夹：

cd build

使用g++编译源代码，例如：

g++ -std=c++11 -o my_program main.cpp

这里假设你的源文件是main.cpp，生成的可执行文件名为my_program。-std=c++11是用来指定C++标准的，你可以根据需要替换为其他标准，如c++14, c++17, c++20等。

如果你有多个源文件，你可以将它们全部列出，或者使用通配符：

g++ -std=c++11 -o my_program *.cpp

如果你想要自动化这个过程，你可以写一个简单的构建脚本，例如build.sh（在Unix-like系统中）：

#!/bin/bash
 
# 清理旧的build文件夹
rm -rf build
mkdir build
 
# 进入build文件夹并编译
cd build && g++ -std=c++11 -o my_program ../main.cpp && cd ..

确保给这个脚本可执行权限：

chmod +x build.sh

然后运行它：

./build.sh

这个脚本会清理旧的build文件夹，创建一个新的，并编译源代码文件到build文件夹中。