Lib.a files for popular libaries. These would be unlinked to Libc using -exclude-syms.


# Notes

libpng - added wasi-sdk-unlinked compile options directly to cmake file to get it to build because they were being reset somehow. needed to unset PNG_SETJMP_SUPPORTED from make config but build system wouldn't let me so I wrapped it in -DPNG_NO_SETJMP like their own instructions suggest. Code must have a check for a define because it compiled after that.

libzlib - had to define Z_HAVE_UNISTD_H in zconf.h because I was getting weird import errors from the build system. Something to do with how zlib registers 16/32/64 bit integers I think, Javascript uses a single long type for all integers.

FreeType - commented out find_package(HarfBuzz) and added `add_compile_options(-mllvm -wasm-enable-sjlj)` to compile jumps. It would seem that freetype jumps can easily be unwound, and that's probably what emscripten-ports initially did. There was no option to turn off jumps and just back out quietly like an importing program might expact.

FreeImage - allowed -frtti. Commented out the entire file Source/LibOpenJPEG/obj_clock to avoid wasi-sdk error.





