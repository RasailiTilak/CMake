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
- second <br>
compile 
###   method _1
- cd build
- make
- a.out
###   method _2
- cmake --build build
- ./build/a.out


