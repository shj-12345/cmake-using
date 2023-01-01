# 指定库的路径

#     链接时使用绝对路径方式
#     find_library():查找/指定所需的库(推荐).
#     link_directories():指定第三方库所在路径(只有在生成target之前调用才会有效, 即需要放在ADD_EXECUTABLE()之前调用)
#     link_libraries():添加需要链接的库文件路径，注意这里是全路径,(不推荐)

# 指定所需头文件的路径

#     include_directories():添加头文件路径到编译器的头文件搜索路径下，多个路径以空格分隔.

# 其他

#     find_path():和find_library()类似,find_path()可以用来找任何文件.
#     find_package():引入外部依赖包.

# 链接目标

#     target_link_libraries:指定目标（exe或者so文件）需要包含的库
#     target_include_directories:指定目标（exe或者so文件）需要包含的头文件路径



#包含的头文件路径
INCLUDE_DIRECTORIES(/usr/local/include/hello)
#添加第三方库所在路径,放在add_executable之前
LINK_DIRECTORIES(/usr/local/lib)
#生成可执行文件
ADD_EXECUTABLE(hello main.cpp)
#添加可执行文件的链接
TARGET_LINK_LIBRARIES(hello libhello_shared.so)
