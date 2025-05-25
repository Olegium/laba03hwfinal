# laba03hwfinal
```bash
ЛАБОРАТОРНАЯ РАБОТА №3 ДЗ
Задание №1
```
```sh
oleg@Computer:~$ cd Olegium/workspace/projects
oleg@Computer:~/Olegium/workspace/projects$ cd lab03homework
-bash: cd: lab03homework: No such file or directory
oleg@Computer:~/Olegium/workspace/projects$ mkdir -p lab03homework
oleg@Computer:~/Olegium/workspace/projects$ cd lab03homework
oleg@Computer:~/Olegium/workspace/projects/lab03homework$ git clone https://github.com/tp-labs/lab03.git
Cloning into 'lab03'...
remote: Enumerating objects: 91, done.
remote: Counting objects: 100% (30/30), done.
remote: Compressing objects: 100% (9/9), done.
remote: Total 91 (delta 23), reused 21 (delta 21), pack-reused 61 (from 1)
Receiving objects: 100% (91/91), 1.02 MiB | 590.00 KiB/s, done.
Resolving deltas: 100% (41/41), done.
oleg@Computer:~/Olegium/workspace/projects/lab03homework$ cd lab03/formatter_lib
oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03/formatter_lib$ cat > CMakeLists.txt <<EOF
> cmake_minimum_required(VERSION 3.4)
> project(formatter_lib)
> set(CMAKE_CXX_STANDARD 11)
> set(CMAKE_CXX_STANDARD_REQUIRED ON)
> add_library(formatter STATIC formatter.cpp)
> target_include_directories(formatter PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
> EOF
oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03/formatter_lib$ mkdir build && cd build
oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03/formatter_lib/build$ cmake ..
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- The C compiler identification is GNU 13.3.0
-- The CXX compiler identification is GNU 13.3.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Configuring done (2.5s)
-- Generating done (0.0s)
-- Build files have been written to: /home/oleg/Olegium/workspace/projects/lab03homework/lab03/formatter_lib/build
oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03/formatter_lib/build$ cmake --build .
[ 50%] Building CXX object CMakeFiles/formatter.dir/formatter.cpp.o
[100%] Linking CXX static library libformatter.a
[100%] Built target formatter
```
```sh
задание2
```
```sh
oleg@Computer:~$ cd Olegium/workspace/projects/lab03homework/lab03
oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03$ cd formatter_ex_lib
oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03/formatter_ex_lib$ cat > CMakeLists.txt <<EOF
> cmake_minimum_required(VERSION 3.4)
> project(formatter_ex_lib)
> set(CMAKE_CXX_STANDARD 11)
> set(CMAKE_CXX_STANDARD_REQUIRED ON)
> add_subdirectory(../formatter_lib formatter_lib_build)
> add_library(formatter_ex STATIC formatter_ex.cpp)
> target_include_directories(formatter_ex PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
> target_link_libraries(formatter_ex PUBLIC formatter)
> EOF
oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03/formatter_ex_lib$ mkdir build && cd build
oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03/formatter_ex_lib/build$ cmake ..
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- The C compiler identification is GNU 13.3.0
-- The CXX compiler identification is GNU 13.3.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
CMake Deprecation Warning at /home/oleg/Olegium/workspace/projects/lab03homework/lab03/formatter_lib/CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- Configuring done (2.2s)
-- Generating done (0.0s)
-- Build files have been written to: /home/oleg/Olegium/workspace/projects/lab03homework/lab03/formatter_ex_lib/build

oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03/formatter_ex_lib/build$ cmake --build .
[ 50%] Built target formatter
[100%] Built target formatter_ex
```
```sh
задание3
```
```sh
oleg@Computer:~$ cd Olegium/workspace/projects/lab03homework/lab03/solver_lib
oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03/solver_lib$ cat > CMakeLists.txt <<EOF
> cmake_minimum_required(VERSION 3.4)
> project(solver_lib)
> set(CMAKE_CXX_STANDARD 11)
> set(CMAKE_CXX_STANDARD_REQUIRED ON)
> add_library(solver_lib STATIC solver.cpp)
> target_include_directories(solver_lib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
> EOF
oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03/solver_lib/build$ cmake ..
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- Configuring done (0.0s)
-- Generating done (0.0s)
-- Build files have been written to: /home/oleg/Olegium/workspace/projects/lab03homework/lab03/solver_lib/build
oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03/solver_lib/build$ cmake --build .
[100%] Built target solver_lib
oleg@Computer:~$ cd Olegium/workspace/projects/lab03homework/lab03/solver_application
oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03/solver_application$ cat > CMakeLists.txt <<EOF
> cmake_minimum_required(VERSION 3.4)
> project(solver_app)
>
> set(CMAKE_CXX_STANDARD 11)
> set(CMAKE_CXX_STANDARD_REQUIRED ON)
> add_subdirectory(../solver_lib build_solver_lib)
> add_subdirectory(../formatter_ex_lib build_formatter_ex)
> add_executable(solver equation.cpp)
> target_link_libraries(solver PUBLIC solver_lib formatter_ex)
> EOF
oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03/solver_application$ mkdir build && cd build
oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03/solver_application/build$ cmake ..
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- The C compiler identification is GNU 13.3.0
-- The CXX compiler identification is GNU 13.3.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
CMake Deprecation Warning at /home/oleg/Olegium/workspace/projects/lab03homework/lab03/solver_lib/CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


CMake Deprecation Warning at /home/oleg/Olegium/workspace/projects/lab03homework/lab03/formatter_ex_lib/CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


CMake Deprecation Warning at /home/oleg/Olegium/workspace/projects/lab03homework/lab03/formatter_lib/CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- Configuring done (1.9s)
-- Generating done (0.0s)
-- Build files have been written to: /home/oleg/Olegium/workspace/projects/lab03homework/lab03/solver_application/build
oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03/solver_application/build$ cmake --build .
[ 25%] Built target formatter
[ 50%] Built target solver_lib
[ 75%] Built target formatter_ex
[ 87%] Building CXX object CMakeFiles/solver.dir/equation.cpp.o
[100%] Linking CXX executable solver
[100%] Built target solver
oleg@Computer:~$ cd Olegium/workspace/projects/lab03homework/lab03/hello_world_application
oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03/hello_world_application$  cat > CMakeLists.txt <<EOF
> cmake_minimum_required(VERSION 3.4)
> project(hello_world)
> set(CMAKE_CXX_STANDARD 11)
> set(CMAKE_CXX_STANDARD_REQUIRED ON)
> add_subdirectory(../formatter_ex_lib build_formatter_ex)
> add_executable(hello_world hello_world.cpp)
> target_link_libraries(hello_world PUBLIC formatter_ex)
> EOF
oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03/hello_world_application/build$ cmake ..
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- Configuring done (0.0s)
-- Generating done (0.0s)
-- Build files have been written to: /home/oleg/Olegium/workspace/projects/lab03homework/lab03/hello_world_application
oleg@Computer:~/Olegium/workspace/projects/lab03homework/lab03/hello_world_application$ cmake --build .
[ 50%] Building CXX object CMakeFiles/print.dir/sources/print.cpp.o
[100%] Linking CXX static library libprint.a
[100%] Built target print
```
