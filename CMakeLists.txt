project(FileSearcher)

set(CMAKE_CXX_FLAGS "-std=c++2a")

# CMake instructions to make the static lib
add_library(FileSearcher STATIC library/searchfile.cpp)

target_link_libraries(FileSearcher -lpthread)

# CMake instructions to test using the static lib
add_executable(SearcherAppTest main.cpp) 

target_link_libraries(SearcherAppTest FileSearcher -lpthread)