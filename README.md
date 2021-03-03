# Dummy

```
$ make rebuild_debug
make clean_debug
rm -rf debug_BUILD debug_EXECUTABLE
make debug
mkdir debug_BUILD
mkdir debug_EXECUTABLE
cd debug_BUILD ; mkdir EXECUTABLES; cmake -DCMAKE_BUILD_TYPE=Debug -DCMAKE_CXX_FLAGS_DEBUG="-g3 -O0" .. ; make && if test -e EXECUTABLES ; then cd EXECUTABLES; for file in * ; do mv -v $file ../../debug_EXECUTABLE/$FILE ; done ; cd ..; rmdir EXECUTABLES; fi
-- The C compiler identification is AppleClang 12.0.0.12000032
-- The CXX compiler identification is AppleClang 12.0.0.12000032
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- LIB_SUFFIX variable is not defined. It will be autodetected now.
-- You can set it manually with -DLIB_SUFFIX=<value> (64 for example)
-- LIB_SUFFIX autodetected as '', libraries will be installed into /usr/local/lib
-- Found Git: /usr/bin/git (found version "2.24.3 (Apple Git-128)")
-- Found Corrade: /Users/smallville7123/Desktop/Dummy/corrade/src  found components: Containers rc Utility
CMake Error at CMakeLists.txt:26 (target_link_libraries):
  Target "Corrade" of type UTILITY may not be linked into another target.
  One may link only to INTERFACE, OBJECT, STATIC or SHARED libraries, or to
  executables with the ENABLE_EXPORTS property set.


-- Configuring incomplete, errors occurred!
See also "/Users/smallville7123/Desktop/Dummy/debug_BUILD/CMakeFiles/CMakeOutput.log".
make[2]: *** No targets specified and no makefile found.  Stop.
make[1]: *** [build_debug] Error 2
make: *** [rebuild_debug] Error 2
```