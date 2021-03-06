# CppUniverse

A demo project that showcase how to use C++ to conquer the universe, with the help of [Djinni](https://github.com/dropbox/djinni) and [WebAssembly](http://webassembly.org/) :)

This demo implement exactly the same feature as [JavaUniverse](https://github.com/Piasy/JavaUniverse), but write the main logic in C++.

## Dependencies

+ openssl 1.0.2m;
+ boost 1.65.1;
+ [C++ REST SDK](https://github.com/Microsoft/cpprestsdk) 2.10.1;
+ [Djinni](https://github.com/dropbox/djinni)
+ [xcake](https://github.com/jcampbell05/xcake)

Due to GitHub file size limit, [the `libs` directory is ignored](https://github.com/Piasy/CppUniverse/blob/master/.gitignore#L4), you can [download it here](https://github.com/Piasy/CppUniverse/releases/download/dep_libs/libs.zip), and extract it as `libs`.

## CPP Project

+ `./run_djinni.sh`
+ `cd cpp_project`
+ `xcake make`
+ `open CppUniverse.xcodeproj`

## Android Project

+ `./run_djinni.sh`
+ Just open the `android_project` folder in Android Studio.

## iOS Project

+ `./run_djinni.sh`
+ `cd ios_project`
+ `xcake make`
+ `open CppUniverse.xcodeproj`

## Web Project

WIP...

## Caveat

+ Add ``-DCMAKE_INSTALL_PREFIX=`pwd`/out`` to cmake command to specify install dir;
+ `'cpprest/http_client.h' file not found with <angled> include; use "quotes" instead` [problem solution](https://stackoverflow.com/a/47542681/3077508);
+ `Arithmetic on a pointer to an incomplete type 'cpp_universe::Window'`: add `#include "window.hpp"` to get the complete type info of `cpp_universe::Window`;
+ Extend djinni record to add utility method which is only used by one language;
+ Djinni record is immutable;
+ Building for Android:
  - openssl need use r15c;
  - boost 1.65.1 need r16;
  - can't use nfs shared folder;
  - find boost error;
  - `'BOOST_STDLIB' macro redefined`;
  - `no matching member function for call to 'expires_from_now'`;
+ Building for iOS:
  - `find_package(Threads REQUIRED)` fail, [solution](https://gitlab.kitware.com/cmake/cmake/issues/16695);

All changes on C++ REST SDK [can be found there](https://github.com/Piasy/cpprestsdk/tree/ndk-r16_xc-9b55_ios-11.1_boost-1.65.1_openssl-1.0.2.m).
