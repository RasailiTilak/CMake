# terminal works
- first <br>
    building  the make file (build system)

    ####   method _1
    - mkdir build
    - cd build
    - cmake ..
    - ls
    ####   method _2
    - cd ../
    - rm -rf build/
    - cmake -Bbuild
    ####   method _3(selecting different build system)
    - cmake -Bbuild -GNinja
    (whhich make)
- second <br>
    compile 
    ###   method _1
    - cd build
    - make
    - ./a.out
    ###   method _2
    - cmake --build build
    - ./build/a.out
## create share libray and static libray
- first make dir move the calc.cpp and calc.h inside the mylib folder
    - mylib/
        - calc.cpp
        - calc.h
 - #### change on the  CMakeLists.txt
  -  check the library(ls ./build/)
  - static library (libcalc.a)
  - share library (libcalc.so)