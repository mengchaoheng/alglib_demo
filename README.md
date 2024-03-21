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

If create new target, change the name  'demo'.
