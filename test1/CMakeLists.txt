CMAKE_MINIMUM_REQUIRED(VERSION 3.16)
#会自动生成两个变量HELLO_BINARY_DIR和HELLO_SOURCE_DIR,MESSAGE可以直接使用这两个变量，都指向当前目录
PROJECT(HELLO)
#添加子路径，将生成的可执行文件放入bin文件夹中
ADD_SUBDIRECTORY(src bin)

#输出CMAKE_INSTALL的相对路径
MESSAGE(STATUS ${CMAKE_INSTALL_PREFIX})
#安装文件：DESTINATION为相对路径，默认的相对路径CMAKE_INSTALL_PREFIX为/usr/local
#也可写绝对路径
INSTALL(FILES COPYRIGHT README DESTINATION share/doc/cmake)
#安装脚本(非目标文件脚本)
INSTALL(PROGRAMS runhello.sh DESTINATION bin)
#安装目录,加/表示路径下的文件被安装到目标路径下，不加/表示整个目录被安装到目标路径下
INSTALL(DIRECTORY doc DESTINATION share/doc/cmake)
#执行安装命令sudo make install,执行的脚本为cmake_install.cmake