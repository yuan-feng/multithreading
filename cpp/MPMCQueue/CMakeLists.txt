cmake_minimum_required (VERSION 3.1)
project (MPMCQueue)

# System Requirement
set (CMAKE_CXX_STANDARD 11)
set (CMAKE_CXX_STANDARD_REQUIRED ON)
find_package( Threads REQUIRED)


# Executable 1
set( exe1 MPMCQueue_demo.exe ) 
add_executable(${exe1} MPMCQueue_demo.cpp)
target_link_libraries(${exe1} Threads::Threads)


# Executable 2
set( exe2 MPMCQueue_test.exe ) 
add_executable(${exe2} MPMCQueue_test.cpp)
target_link_libraries(${exe2} Threads::Threads)


enable_testing()
add_test(exe1 ${exe1})
add_test(exe2 ${exe2})

