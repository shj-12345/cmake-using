SET(LIBHELLO_SRC hello.cpp)

#同时生成同名的动态库和静态库，如下并不能实现
#生成动态库，后缀为 libxxx.so
ADD_LIBRARY(hello_shared SHARED ${LIBHELLO_SRC})
#生成静态库，后缀为 libxxx.a
ADD_LIBRARY(hello_static STATIC ${LIBHELLO_SRC})
INSTALL(FILES hello.h DESTINATION include/hello)
INSTALL(TARGETS hello_shared hello_static LIBRARY DESTINATION lib ARCHIVE DESTINATION lib)

#同时生成同名的动态库和静态库，如下实现
# ADD_LIBRARY(hello_shared SHARED ${LIBHELLO_SRC})
# SET_TARGET_PROPERTIES(hello_shared PROPERTIES OUTPUT_NAME "hello")
# ADD_LIBRARY(hello STATIC ${LIBHELLO_SRC})
# SET_TARGET_PROPERTIES(hello PROPERTIES OUTPUT_NAME "hello")