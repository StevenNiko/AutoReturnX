cmake_minimum_required(VERSION 3.10)
project(ProductPriceTracker)

# Set C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Add source files
set(SOURCES main.cpp)

# Find and link libcurl
find_package(CURL REQUIRED)
include_directories(${CURL_INCLUDE_DIRS})
link_libraries(${CURL_LIBRARIES})

# Find and link SQLite3
find_package(SQLite3 REQUIRED)
include_directories(${SQLite3_INCLUDE_DIRS})
link_libraries(${SQLite3_LIBRARIES})

# Add executable
add_executable(ProductPriceTracker ${SOURCES})

# Link libraries
target_link_libraries(ProductPriceTracker ${CURL_LIBRARIES} ${SQLite3_LIBRARIES})
