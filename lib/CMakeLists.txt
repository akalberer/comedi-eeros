include_directories(../include/)

set(COMEDIEEROS_SRCS ComediDevice.cpp DigIn.cpp DigOut.cpp AnalogIn.cpp AnalogOut.cpp Fqd.cpp)

add_library(comedieeros SHARED ${COMEDIEEROS_SRCS})
add_library(comedieeros_static ${COMEDIEEROS_SRCS})

target_link_libraries(comedieeros comedi eeros)
target_link_libraries(comedieeros_static comedi eeros)

INSTALL(FILES ${CMAKE_CURRENT_BINARY_DIR}/libcomedieeros.so ${CMAKE_CURRENT_BINARY_DIR}/libcomedieeros_static.a DESTINATION lib)
