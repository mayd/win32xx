# win32xx

This repository contains my additional files for the [Win32++ framework](https://sourceforge.net/projects/win32-framework/).

The official Win32++ project includes configurations for use with various IDEs but I want to use Win32++ with MSYS2/MinGW and CMake.


Recent Changes:
---------------

**16 December 2020:**

  * Created a CMakeList.txt file so that most sample examples and all tutorial examples can be compiled with CMake for MSYS2/MinGW.
  * Note that some examples in the sample folder do not compile under MSYS2. Those examples use DirectX or the Windows Ribbon Framework.

**27 April 2021:**

  * Fixed a couple of Microsoft non-portable statements in `MovieShow` sample application.
  * Fixed a syntax error in resource file for `MovieShow` sample application.
  * Built `MovieShow` sample application with updated MSYS2 include file `shlwapi.h` for IStream helper function declarations.
  * Fixed Microsoft non-portable statements in `NetSimple` sample application.
  * Created a patch file for source code changes.
  * Updated `CMakeLists.txt to build corrected sample applications `MovieShow` and `NetSimple`.


How to download and compile all Win32++ examples with MSYS2/MinGW and CMake:
----------------------------------------------------------------------------

    git clone https://github.com/mayd/Win32xx
    cd win32xx
    wget https://sourceforge.net/projects/win32-framework/files/Win32%2B%2B/Version%208.8.0/Win32xx880.zip/download -O Win32xx880.zip
    unzip Win32xx880.zip
    cd ..
    patch -p0 -i win32xx-MSYS2.patch
    cd win32xx    
    mkdir build
    cd build
    cmake .. -G "MinGW Makefiles"
    cd ..
    MAKEFLAGS=-k cmake --build build
