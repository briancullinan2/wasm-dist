Lib.a files for popular libaries. These would be prelinked to wasi-sdk's libc++.

# Notes

assimp - was only generating shared libraries, added static and wondered if BUILD_SHARED_LIBS should be turned off because of this line in cmake `TARGET_COMPILE_DEFINITIONS(assimp PRIVATE OPENDDL_STATIC_LIBARY P2T_STATIC_EXPORTS)`

tinyxml2 - built without error with -fno-rtti -fno-exceptions



