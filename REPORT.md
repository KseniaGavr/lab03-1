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

 ![image](https://user-images.githubusercontent.com/77126126/225571945-6a48ea5a-9f2f-475d-acd6-595d2bd19d92.png)
 `клонирование репозитория и создание CMakeList.txt для formatter_lib`
 
 ![image](https://user-images.githubusercontent.com/77126126/225573376-cfd145c2-9ab7-47fa-8d5c-41b5d10436d1.png)
 `сборка formatter_lib`


### Задание 2
У компании "Formatter Inc." есть перспективная библиотека,
которая является расширением предыдущей библиотеки. Т.к. вы уже овладели
навыком созданием `CMakeList.txt` для статической библиотеки *formatter*, ваш 
руководитель поручает заняться созданием `CMakeList.txt` для библиотеки 
*formatter_ex*, которая в свою очередь использует библиотеку *formatter*.

![image](https://user-images.githubusercontent.com/77126126/225576889-b2be4d04-7269-4f34-8659-2c5e80f8efef.png)
`создание CMakeList.txt для formatter_ex_lib на основе созданного в formatter_lib`

### Задание 3
Конечно же ваша компания предоставляет примеры использования своих библиотек.
Чтобы продемонстрировать как работать с библиотекой *formatter_ex*,
вам необходимо создать два `CMakeList.txt` для двух простых приложений:
* *hello_world*, которое использует библиотеку *formatter_ex*;
* *solver*, приложение которое испольует статические библиотеки *formatter_ex* и *solver_lib*.

![image](https://user-images.githubusercontent.com/77126126/225580259-e82627cf-2a27-43de-98a6-4bd08dfd5033.png)
`CMakeList.txt для приложения hello_world (подключение библиотеки formatter_ex_lib с указанием возможности ее линковки под именем hello; подключение исходного hello_world.cpp файла)`

![image](https://user-images.githubusercontent.com/77126126/225579760-d0208cf5-b4e2-4cf0-9812-beb7d5b2215f.png)
`создание CMakeList.txt для библиотеки solver_lib`

![image](https://user-images.githubusercontent.com/77126126/225581794-91be9cbf-57e7-4f3e-912c-8f436d2cd53c.png)
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
