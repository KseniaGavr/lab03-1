## Laboratory work III

Данная лабораторная работа посвещена изучению систем автоматизации сборки проекта на примере **CMake**

```sh
$ open https://cmake.org/
```

## Tasks

- [x] 1. Создать публичный репозиторий с названием **lab03** на сервисе **GitHub**
- [x] 2. Ознакомиться со ссылками учебного материала
- [x] 3. Выполнить инструкцию учебного материала
- [x] 4. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Homework

Представьте, что вы стажер в компании "Formatter Inc.".
### Задание 1
Вам поручили перейти на систему автоматизированной сборки **CMake**.
Исходные файлы находятся в директории [formatter_lib](formatter_lib).
В этой директории находятся файлы для статической библиотеки *formatter*.
Создайте `CMakeList.txt` в директории [formatter_lib](formatter_lib),
с помощью которого можно будет собирать статическую библиотеку *formatter*.

 `git clone https://github.com/KseniaGavr/lab03-1 lab03_1`
 `cd lab03_1`
 `cat > CMakeLists.txt >> EOF`
 `> cmake_minimum_required (VERSION 3.4)`
 `>`
 `> set(CMAKE_CXX_STANDART 11)`
 `>`
 `> add_library(formatter STATIC{CMAKE_CURRENT_SOURCE_DIR}/formatter_lib/formatter.cpp`
 `>EOF`
 `git add .`
 `git commit -m "создание CMakeLists.cpp`
 `клонирование репозитория и создание CMakeList.txt для formatter_lib`
 
 `cmake .`
 `make`
 `сборка formatter_lib`


### Задание 2
У компании "Formatter Inc." есть перспективная библиотека,
которая является расширением предыдущей библиотеки. Т.к. вы уже овладели
навыком созданием `CMakeList.txt` для статической библиотеки *formatter*, ваш 
руководитель поручает заняться созданием `CMakeList.txt` для библиотеки 
*formatter_ex*, которая в свою очередь использует библиотеку *formatter*.

`cmake_minimum_required(VERSION 3.4)`
`set(CMake_CXX_STANDART 11)`
`project(formatter_ex)`
`add_library(formatter_ex ${CMAKE_CURRENT_SOURCE_DIR}/formatter.cpp_ex`
`target_include_directories(formatter_ex PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/formatter_lib)`
`add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/formatter_lib formatter)`
`target_link_libraries(formatter_ex PUBLIC formatter)`
`создание CMakeList.txt для formatter_ex_lib на основе созданного в formatter_lib`

### Задание 3
Конечно же ваша компания предоставляет примеры использования своих библиотек.
Чтобы продемонстрировать как работать с библиотекой *formatter_ex*,
вам необходимо создать два `CMakeList.txt` для двух простых приложений:
* *hello_world*, которое использует библиотеку *formatter_ex*;
* *solver*, приложение которое испольует статические библиотеки *formatter_ex* и *solver_lib*.

`cmake_minimum_required(VERSION 3.4)`
`set(CMake_CXX_STANDART 11)`
`project(hello_world)`
`add_executable(hello ${CMAKE_CURRENT_SOURCE_DIR}/hello_world.cpp)`
`include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib)`
`add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib formatter_ex)`
`target_link_libraries(hello formatter_ex)`
`CMakeList.txt для приложения hello_world (подключение библиотеки formatter_ex_lib с указанием возможности ее линковки под именем hello; подключение исходного hello_world.cpp файла)`

`cmake_minimum_required(VERSION 3.4)`
`set(CMake_CXX_STANDART 11)`
`project(solver_lib)`
`add_library(solver_lib STATIC ${CMAKE_CURRENT_SOURCE_DIR}/solver.cpp})`
`создание CMakeList.txt для библиотеки solver_lib`

`cmake_minimum_required(VERSION 3.4)`
`set(CMake_CXX_STANDART 11)`
`project(solver)`
`add_executable(solver ${CMAKE_CURRENT_SOURCE_DIR}/equation.cpp})`
`include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib ${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib)`
`add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib formatter_ex)`
`add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib solver_lib)`
`target_link_libraries(solver formatter_ex solver_lib)`

`CMakeList.txt для приложения solver_applicatio


**Удачной стажировки!**

## Links
- [Основы сборки проектов на С/C++ при помощи CMake](https://eax.me/cmake/)
- [CMake Tutorial](http://neerc.ifmo.ru/wiki/index.php?title=CMake_Tutorial)
- [C++ Tutorial - make & CMake](https://www.bogotobogo.com/cplusplus/make.php)
- [Autotools](http://www.gnu.org/software/automake/manual/html_node/Autotools-Introduction.html)
- [CMake](https://cgold.readthedocs.io/en/latest/index.html)

```
Copyright (c) 2015-2021 The ISC Authors
```
