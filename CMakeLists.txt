cmake_minimum_required(VERSION 3.16)
project(crawler)
set(SAMPLE_NAME "crawler")

set(SAMPLE_SRCS Debug)

# dependent libraries
find_package(Poco REQUIRED Foundation Data DataSQLite Net NetSSL Crypto CONFIG)
find_package(easyhttpcpp REQUIRED CONFIG)

add_executable(${SAMPLE_NAME} linkqueue.cpp repo_in_memory.cpp indexer.cpp server.cpp) 
target_link_libraries(crawler
                      easyhttpcpp::easyhttp
                      Poco::Foundation
                      Poco::Data Poco::DataSQLite
                      Poco::Net Poco::NetSSL Poco::Crypto
                      ssl crypto
                      )
