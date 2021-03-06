cmake_minimum_required(VERSION 2.8)

set(CMAKE_MACOSX_RPATH 0)

project(sql-test)

include_directories(sql-test "../")

set(SQL_TEST_SRC
        #        test.cpp
        TestSelectModel.cpp
        TestSelectModel.h
        TestInsertModel.cpp
        TestInsertModel.h
        TestUpdateModel.cpp
        TestUpdateModel.h
        TestDeleteModel.cpp
        TestDeleteModel.h

        ../sql-builder/SqlModel.cpp
        ../sql-builder/SqlModel.h
        ../sql-builder/SelectModel.cpp
        ../sql-builder/SelectModel.h
        ../sql-builder/Column.cpp
        ../sql-builder/Column.h
        ../sql-builder/InsertModel.cpp
        ../sql-builder/InsertModel.h
        ../sql-builder/UpdateModel.cpp
        ../sql-builder/UpdateModel.h
        ../sql-builder/DeleteModel.cpp
        ../sql-builder/DeleteModel.h
        ../sql-builder/Util.h
        )

add_executable(sql-test ${SQL_TEST_SRC})

add_test(all ${PROJECT_NAME})

target_link_libraries(${PROJECT_NAME}
        gtest
        gtest_main
        pthread
        )

enable_testing()
