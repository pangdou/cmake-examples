* project() 命令会将参数赋值给一个全局变量 ${PROJECT_NAME}，所以 add_executable() 的第一个参数可以使用该变量
* 如果出现多个 project() 以最后一个为准
* 