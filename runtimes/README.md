Lib.a files for popular libaries. These would be prelinked to wasi-sdk's rt.

Libraries that include a main(args, count) to start and can be activated with command line parameters.

# Notes

Maverik Model 3D - had to run configure locally before using the docker image to generate a ./configure script. Then had to comment out the check for auxillary compiler in automake because Docker doesn't supply and automake on Android. Then I commented out the failure mode for Qt even thought I specified a proper --with-Qt-dir= in configure Failed to find matching components of a complete. Then disable the check for glew, `OpenGL (with GLU) is required.`. All of these things I will provide in a little /wasm/ directory. Hod to comment out references to autoconf just to get it to run the build commands like `$(AM_V_GEN)($(am__cd) $(top_srcdir) && $(AUTOHEADER))`, and remove `$(top_srcdir)/configure` and whatever it does for convenience when a makefile changes won't work inside the Android docker.



