cmake_minimum_required(VERSION 3.20 FATAL_ERROR)

# project name and enable C++ support
project(movement_trainer LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)  
 
 
find_package(Boost COMPONENTS system filesystem thread unit_test_framework REQUIRED)
find_package(OpenSSL REQUIRED)

add_definitions(${Boost_LIB_DIAGNOSTIC_DEFINITIONS})


set( EXECUTABLE_NAME example_beast_client )

add_executable(${EXECUTABLE_NAME} websocket_client_async.cpp )

target_include_directories(${EXECUTABLE_NAME} PRIVATE include . )
target_link_directories(${EXECUTABLE_NAME} PRIVATE ${Boost_LIBRARY_DIRS} )

 
target_link_libraries(${EXECUTABLE_NAME}  OpenSSL::SSL Boost::system Boost::thread )


     

