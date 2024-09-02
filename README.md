# wasm-dist
A hopeful distribution system to linkable wasm files. Honestly, I've never liked the design or philosophy behind Emscripten. I'd rather have libraries that are expecting fopen() from the next system up than have it linked to Emscripten internally. This is the difference between building a library instead of an application and Emscripten blurs that line with polyfills between library and application. So when there are a bunch of library prelinked to functions I want to provide, then the library is not longer redistributable, which explains why there are no library downloads on pages like these.  https://github.com/emscripten-ports/FreeType/releases Great, only source code. I hope you were planning to spend the entire day building someone else's code instead of your own. This isn't my only criticism of Emscripten, this is just one the nicest. This page serves to change all of that. Instead of polyfilling libraries with my own crappy code, I'll be compiling original sources and uploading full libraries with wasi-sdk and libc. Libc and Libc++ directories will be prelinked libraries, and wasm-dist will be libraries expecting to be linked to internal system handling. If a polyfill is used, it should be detailed in a readme.md accompanying the library.


## Libraries

Libc
Libc++
Lib.a files for popular libaries. These would be prelinked to wasi-sdk's libc++.


## Runtimes
Lib.a files for popular libaries. These would be prelinked to wasi-sdk's rt.


## Apps 
.wasm files for popular apps that load and work with generic javascript inputs/localStorage/compile.
