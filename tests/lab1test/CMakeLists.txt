#message( STATUS "gtest_SOURCE_DIR: " ${gtest_SOURCE_DIR} )
#message( STATUS "gmock_SOURCE_DIR: " ${gmock_SOURCE_DIR} )
message(STATUS "lab1test::HAVE_DIR_PALINDROME:  ${HAVE_DIR_PALINDROME}")

include_directories(${gtest_SOURCE_DIR}/include ${gtest_SOURCE_DIR})
include_directories(${gmock_SOURCE_DIR}/include ${gmock_SOURCE_DIR})

set(FACTORIAL_SRC FactorialTest.cpp)
set(REVERSE_STRING_SRC ReverseStringTest.cpp)
set(PALINDROME_SRC PalindromeTest.cpp)
set(MULTIPLICATION_TABLE_SRC MultiplicationTableTest.cpp)
set(DOUBLE_BASE_PALINDROME_SRC DoubleBasePalindromeTest.cpp)
set(SOURCE_FILES ${FACTORIAL_SRC} ${REVERSE_STRING_SRC} ${PALINDROME_SRC} ${MULTIPLICATION_TABLE_SRC} ${DOUBLE_BASE_PALINDROME_SRC} ../../lab4/netstemplateengine/SimpleTemplateEngine.cpp ../../lab4/netstemplateengine/SimpleTemplateEngine.h ../../lab4/netstemplateengine/main.cpp ../../lab5/matrix/Matrix.cpp ../../lab5/matrix/Matrix.h ../../lab5/matrix/main.cpp ../../lab6/wordcounter/WordCounter.cpp ../../lab6/wordcounter/WordCounter.h ../../lab6/wordcounter/main.cpp ../../lab6/wordcounter/Word.cpp ../../lab6/wordcounter/Word.h ../../lab6/wordcounter/Counts.cpp ../../lab6/wordcounter/Counts.h "../../lab6/wordcounter/WordCounter.cpp" "../../lab6/wordcounter/WordCounter.h" ../../lab6/wordcounter/main.cpp ../../lab8/moviesubtitles/main.cpp ../../lab8/moviesubtitles/MovieSubtitles.cpp ../../lab8/moviesubtitles/MovieSubtitles.h ../../lab12/tree/main.cpp ../../lab12/timerecorder/TimeRecorder.cpp ../../lab12/timerecorder/TimeRecorder.h ../../lab12/timerecorder/main.cpp ../../lab12/tree/Tree.cpp)

set(GTEST_LIBS gtest gtest_main gmock gmock_main)

add_executable(lab1_factorial_tests ${FACTORIAL_SRC})

target_link_libraries(lab1_factorial_tests ${GTEST_LIBS})
target_link_libraries(lab1_factorial_tests libfactorial)

add_executable(lab1_reverse_string_tests ${REVERSE_STRING_SRC})

target_link_libraries(lab1_reverse_string_tests ${GTEST_LIBS})
target_link_libraries(lab1_reverse_string_tests libreversestring)

add_executable(lab1_palindrome_tests ${PALINDROME_SRC})

target_link_libraries(lab1_palindrome_tests ${GTEST_LIBS})
target_link_libraries(lab1_palindrome_tests libpalindrome)

add_executable(lab1_multiplication_table_tests ${MULTIPLICATION_TABLE_SRC})

target_link_libraries(lab1_multiplication_table_tests ${GTEST_LIBS})
target_link_libraries(lab1_multiplication_table_tests libmultiplicationtable)

add_executable(lab1_double_base_palindrome_tests ${DOUBLE_BASE_PALINDROME_SRC})

target_link_libraries(lab1_double_base_palindrome_tests ${GTEST_LIBS})
target_link_libraries(lab1_double_base_palindrome_tests libdoublebasepalindromes)

add_executable(lab1_all_tests ${SOURCE_FILES})

target_link_libraries(lab1_all_tests ${GTEST_LIBS})
target_link_libraries(lab1_all_tests libfactorial)
target_link_libraries(lab1_all_tests libreversestring)
target_link_libraries(lab1_all_tests libpalindrome)
target_link_libraries(lab1_all_tests libmultiplicationtable)
target_link_libraries(lab1_all_tests libdoublebasepalindromes)