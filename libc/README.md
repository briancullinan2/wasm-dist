Lib.a files for popular libaries. These would be prelinked to wasi-sdk's libc.

# Notes

libminiz - had to comment out tests to get it to build natively. Probably could have used -DBUILD_EXAMPLES=OFF. Built without rtti/abi/etc.

harfbuzz - replaced add_definition(-DHAVE_PTHREAD) with `add_definitions(-DHB_NO_MT)` and `add_definitions(-DHB_NO_MMAP)`. Replaced the line in meson with `cmake_config.set('HB_LIBRARY_TYPE', 'STATIC')`.

pcre2 - Had to set `#undef SUPPORT_PCRE2GREP_CALLOUT_FORK` in the config before building. Stopped debugging at testing because the build already emitted binaries.


