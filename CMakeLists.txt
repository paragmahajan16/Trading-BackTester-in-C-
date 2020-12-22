cmake_minimum_required(VERSION 3.12)
project(ieorclassproject9)

FIND_PACKAGE(Boost 1.69 REQUIRED date_time program_options thread filesystem system unit_test_framework)
IF(${Boost_FOUND})
    INCLUDE_DIRECTORIES(${Boost_INCLUDE_DIR})
ENDIF()

set(SOURCE_FILES main.cpp MDReader.h MDReader.cpp OrderManager.h OrderManager.cpp MarketSimulator.h MarketSimulator.cpp Order.h Order.cpp AppBase.h AppBase.cpp BookUpdate.h BookUpdate.cpp MyOrderBook.h MyOrderBook.cpp PriceUpdate.h PriceUpdate.cpp TradingStrategy.h TradingStrategy.cpp)

add_executable(ieorclassproject9 ${SOURCE_FILES})

add_subdirectory(ProjectTests)


target_link_libraries(ieorclassproject9 ${Boost_LIBRARIES})


