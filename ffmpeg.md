1. ffmpeg播放yuv文件
>ffplay -f rawvideo -video_size 1920x1080 a.yuvu
2. ffmpeg增加x264编码库

  * mingw，**vs2017**，ffmpeg4.0

  * mingw环境, 目录下的link.exe重命名;msys下msys.bat首行增加vs2017环境变量引用
> call "C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\bin\vcvars32.bat"  

  * x264编译

  ```
function build_x264
{
CC=cl ./configure \
--enable-shared \
--extra-cflags="-DNO_PREFIX" \
--output-def=libx264.def \
--disable-pthread
make -j4
make install-lib-shared
}
build_x264
```

  * ffmpeg config

  ```
function build_ff
{
./configure --toolchain=msvc \
--build-suffix=-ql \
--prefix=./mingw_build \
--enable-libx264 \
--enable-small \
--enable-version3 \
--enable-shared \
--disable-everything \
--enable-protocol=file \
--enable-protocol=rtmp \
--enable-protocol=http \
--enable-bsf=h264_mp4toannexb \
--enable-bsf=aac_adtstoasc \
--enable-avresample \
--enable-hwaccels \
--enable-parsers \
--enable-demuxers \
--enable-decoders \
--enable-filters \
--enable-muxers \
--enable-encoders \
--enable-gpl \
--disable-doc \
--disable-ffmpeg \
--disable-ffplay \
--disable-ffprobe \
--extra-cflags=-I/home/x264-bin/include \
--extra-ldflags="-LIBPATH:d:\\MinGW\\msys\\1.0\\local\\lib"
}
build_ff
```

  * make提示libx264找不到,msys.bat增加环境变量
> @set LIBPATH=D:\MinGW\msys\1.0\local\lib;%LIBPATH%
