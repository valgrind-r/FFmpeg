## Build of FFmpeg Release 7.0 with FDK AAC  and LAME MP3 codecs

#### Note: Building on Windows requires MSYS2 and```mingw-w64-x86_64-toolchain```
Includes a custom makefile ```Makefile.msys``` for building with MSYS2
## Instructions
 ```
git clone https://github.com/valgrind-r/FFmpeg ffmpeg-fork
cd ffmpeg-fork
```
### Build the codec libraries
```
cd fdk-aac
./configure --enable-static --disable-shared
make
make install
```
#### For LAME MP3
```
cd ..
cd lame
```
****Windows****<br>
Builds static libraries without the frontend to enable compilation with FFmpeg. Run in an MSYS2 shell.
```
make -f Makefile.msys install
```
****Unix****
```
./configure
make
make install
```
#### Finally build FFmpeg
```
cd ..
./configure --enable-static --disable-shared --enable-gpl --enable-nonfree --enable-libfdk-aac --enable-libmp3lame
make
make install
```
