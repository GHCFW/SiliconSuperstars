# Wokwi Debug Guide

**Error:**

![alt text](https://github.com/GHCFW/GHCSiliconSuperstars/blob/main/WokwiMissingPicoInclude.PNG)

**Resolution:**
Add <#include "pico/stdlib.h"> in the top header include

<br>

# Compiler Explorer Debug Guide

**Error:**
Compiler Error/Catch2 framework not found.

**Resolution:**
Change the compiler to x86-64 gcc 10.2 and in "Libraries" add Catch2 version 3.0.0-preview2

<br>

**Error:**
Running main code instead of unit tests or vice versa.

**Resolution:**
Use -DRUN_UNIT_TESTS=0 (for main code) or -DRUN_UNIT_TESTS=1 (for unit tests) in Tree=>CMake options

<br>

**Error:**
Build failed
  
**Resolution 1:**
Compiler Explorer ran fast enough to not capture latest changes. Hit the replay/clear cache and compile button at the bottom window to rerun manually.

<br>

# Compiler Explorer User Guide

Disclaimer: Easiest way to resolve any setup issues is to open the compiler explorer project link again, or copy over the code in your local gcc setup along with Catch2 unit-testing framework.

1. Build and run code in compiler explorer

   Compiler Explorer auto-runs with any change in the source file. To manually build and run hit the replay button in the compiler window
   
   ![rerun_code](https://github.com/GHCFW/GHCSiliconSuperstars/blob/main/images/rerun_code_in_ce.png)
   
 2. Check your compiler version is set to x86-64 gcc 10.2 in the compiler window
 
    ![compiler_version](https://github.com/GHCFW/GHCSiliconSuperstars/blob/main/images/compiler_version.png)
    
 3. Check catch2 library is included within the compiler tree and use version 3.0.0-preview2
 
    ![libraries_included](https://github.com/GHCFW/GHCSiliconSuperstars/blob/main/images/libraries_included_1.png)
    ![catch2_library](https://github.com/GHCFW/GHCSiliconSuperstars/blob/main/images/catch2_library.png)

4. Check the CMAKE arguments within the Tree#1 window (highlighted in the image below) are passed in correctly and RUN_UNIT_TESTS=1. The object to build is set as *gpio*

   ![cmake](https://github.com/GHCFW/GHCSiliconSuperstars/blob/main/images/cmake_arguments_within_tree.png)



5. Compiler output with unit tests failing

   ![tests_failing_output](https://github.com/GHCFW/GHCSiliconSuperstars/blob/main/images/output_window_with_failures.png)


6. Compiler output with all tests passing

   ![tests_passing](https://github.com/GHCFW/GHCSiliconSuperstars/blob/main/images/output_window_all_tests_pass.png)

