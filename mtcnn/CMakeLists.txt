
cmake_minimum_required (VERSION 2.8)
project(mtcnn)

set( INSTALL_DIR ${TENGINE_DIR} )
set( TENGINE_LIBS tengine hclcpu)

set( MTCNN_SRCS mtcnn_utils.cpp mtcnn.cpp test_mtcnn.cpp )

#include
include_directories(${INSTALL_DIR}/include)

#lib
link_directories(${INSTALL_DIR}/lib)

#exe
add_executable(mtcnn ${MTCNN_SRCS})
target_link_libraries(mtcnn ${TENGINE_LIBS} ${PROTOBUF_LIB}  ${BLAS_LIB} ${ACL_LIB})

