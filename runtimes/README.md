Lib.a files for popular libaries. These would be prelinked to wasi-sdk's rt.

Libraries that include a main(args, count) to start and can be activated with command line parameters.

# Notes

Maverik Model 3D - had to run configure locally before using the docker image to generate a ./configure script. The Android docker apparently does not have an automake package. Then had to comment out the check for auxillary compiler in automake because Docker doesn't supply and automake on Android. Then I commented out the failure mode for Qt even thought I specified a proper --with-Qt-dir= in configure Failed to find matching components of a complete. Then disable the check for glew, `OpenGL (with GLU) is required.`. All of these things I will provide in a little /wasm/ directory. Hod to comment out references to autoconf just to get it to run the build commands like `$(AM_V_GEN)($(am__cd) $(top_srcdir) && $(AUTOHEADER))`, and remove `$(top_srcdir)/configure` and whatever it does for convenience when a makefile changes won't work inside the Android docker. Finally made it to linking and linked it manually. Found and error `wasm-ld: warning: unexpected existing value for ` which had no explaination but it's because I was importing a shared library as a static, so I recompiled harfbuzz as static. Found an error `warning: linking section is present, so this is not a standard wasm file - binaryen cannot handle this properly!`. Figured out this was because of shared library linkage also.




