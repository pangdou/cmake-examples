# 变量
## PROJECT_BINARY_DIR
如果是 in source 编译，这个变量指得就是工程顶层目录，如果是 out-of-source 编译，指的是工程编译发生的目录。另外 <projectname>_BINARY_DIR 和 CMAKE_BINARY_DIR 跟这个变量指代的内容是一致的。

## PROJECT_SOURCE _DIR
不论采用何种编译方式，都是工程顶层目录。也就是在 in source 编译时，他跟 PROJECT_BINARY_DIR 等变量一致。另外 <projectname>_SOURCE_DIR 和 CMAKE_SOURCE_DIR 跟这个变量指代的内容是一致的。

## CMAKE_CURRENT_SOURCE_DIR
指的是当前处理的 CMakeLists.txt 所在的路径。

## CMAKE_CURRRENT_BINARY_DIR
如果是 in-source 编译，它跟 CMAKE_CURRENT_SOURCE_DIR 一致，如果是 out-ofsource 编译，他指的是 target 编译目录。使用 ADD_SUBDIRECTORY(src bin) 可以更改这个变量的值。

## CMAKE_CURRENT_LIST_FILE
输出调用这个变量的 CMakeLists.txt 的完整路径。

## CMAKE_CURRENT_LIST_LINE
输出这个变量所在的行。

## CMAKE_MODULE_PATH
这个变量用来定义自己的 cmake 模块所在的路径。如果你的工程比较复杂，有可能会自己编写一些 cmake 模块，这些 cmake 模块是随你的工程发布的，为了让 cmake 在处理CMakeLists.txt 时找到这些模块，你需要通过 SET 指令，将自己的 cmake 模块路径设置一下。比如
SET(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)
这时候你就可以通过 INCLUDE 指令来调用自己的模块了。

## EXECUTABLE_OUTPUT_PATH 和 LIBRARY_OUTPUT_PATH
前者用来重新定义目标二进制可执行文件的存放位置，后者用来重新定义目标链接库文件的存放位置。

## PROJECT_NAME
返回通过 project() 指令定义的项目名称。