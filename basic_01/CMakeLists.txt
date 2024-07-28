# 1. give cmake  version 
cmake_minimum_required(VERSION 3.28.3)

#project name 
project("Hello")
# add libray here "calc" is library name, thiis  is static library
#add_library(calc mylib/calc.cpp)

# add libray here "calc" is library name, thiis  SHARED  library
add_library(calc SHARED mylib/calc.cpp)
# add the executable(output iputs)
add_executable(a.out main.cpp )
# when you create the libray you have to link so "calc" is library name
target_link_libraries(a.out calc)