# win32xx

This repository contains my additional files for the [Win32++ framework](https://sourceforge.net/projects/win32-framework/).

The official Win32++ project includes configurations for use with various IDEs but I want to use Win32++ with MSYS2/MinGW and CMake.


Recent Changes:
---------------

16 December 2020:

* Created a CMakeList.txt file so that most sample examples and all tutorial examples can be compiled with CMake for MSYS2/MinGW.

* Note that some examples in the sample folder do not compile under MSYS2. Those examples use DirectX or the Ribbon UI.


Instructions to download and compile all Win32++ examples with MSYS2/MinGW:
---------------------------------------------------------------------------

    git clone https://github.com/mayd/Win32xx
    cd Win32xx
    wget https://sourceforge.net/projects/win32-framework/files/Win32%2B%2B/Version%208.8.0/Win32xx880.zip/download -O Win32xx880.zip
    unzip Win32xx880.zip
    mkdir build
    cd build
    cmake .. -G "MinGW Makefiles"
    cd ..
    MAKEFLAGS=-k cmake --build build --target

