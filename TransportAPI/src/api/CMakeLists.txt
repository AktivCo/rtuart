project(TransportAPI)

file(GLOB SOURCES "*.[hc]")

file(GLOB_RECURSE PUBLIC_HEADERS "${TRANSPORT_API_PUBLIC_HEADERS_DIR}/*.h")

add_library(${PROJECT_NAME} STATIC ${PUBLIC_HEADERS} ${SOURCES})

target_link_libraries(${PROJECT_NAME} log)

target_include_directories(${PROJECT_NAME} PUBLIC ${TRANSPORT_API_PUBLIC_HEADERS_DIR})

set_property(TARGET ${PROJECT_NAME} PROPERTY POSITION_INDEPENDENT_CODE ON)

target_compile_options(${PROJECT_NAME} PRIVATE -Werror -Wall -Wextra)
