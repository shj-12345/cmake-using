#用来显示地指定变量，若有多个参数用空格分开
#如SET(SRC_LIST test1.cpp test2.cpp)
SET(SRC_LIST main.cpp)

#向终端输出用户自定义信息
#主要包含三种信息：1.SEND_ERROR,产生错误，生成过程被跳过；2.STATUS，输出前缀为--的信息；3.FATAL_ERROR,立即终止所有的cmake过程
MESSAGE(STATUS ${HELLO_BINARY_DIR})
MESSAGE(STATUS ${HELLO_SOURCE_DIR})
MESSAGE(STATUS "this is a test process!")

#生成可执行文件
ADD_EXECUTABLE(hello ${SRC_LIST})