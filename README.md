Qt/C++ Autotools Skeleton
===================================

This is a skeleton project for Qt/C++ projects.


Structure
-----------

```
[ROOT]
 |- bindings : Language (e.g. Python) bindings
 |- examples : src/lib example code
 |- m4 : M4 macros
 |- src : Source code
  |- app : Application code
  |- lib : Library source
 |- tests : Test source (unit tests, functionality tests, etc)
  |- unitTests : Unit tests
```
Building
---------
In order to build, run the following commands:

```bash
[PROJECT_ROOT]$ ./autogen.sh
[PROJECT_ROOT]$ mkdir -p bin && cd bin
[PROJECT_ROOT]$ ../configure
[PROJECT_ROOT]$ make
```

The compiled executable will be available in in **bin/src/app/qthello**.
