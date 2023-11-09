# FFmpeg
<!-- TOC -->

1. [FFmpeg](#ffmpeg)
   1. [Get the FFmpeg source package](#get-the-ffmpeg-source-package)
   2. [install and compile](#install-and-compile)

<!-- /TOC -->
## Get the FFmpeg source package
1. Linux executes download and decompression commands
```shell
[root@localhost]# wget http://www.ffmpeg.org/releases/ffmpeg-3.4.4.tar.gz
[root@localhost]#tar -zxvf ffmpeg-3.4.4.tar.gz
```
2. github open source community address: http://git.videolan.org/?p=ffmpeg.git

## install and compile
1. install yasm
   ```shell
   sudo apt install yasm
   #configure可以用于配置需编译的模块
   ./configure --enable-ffplay --enable-ffserver

   make clean;
   make -j8;
   sudo make install;
   ./configure --prefix=PREFIX //安装到指定目录
    ```
## ffmpeg cmd
```shell
#argb 2 gif
ffmpeg -f rawvideo -pix_fmt argb -s 560x1280 -i argb_w560_h1280.argb output.gif

ffmpeg_g -f rawvideo -pix_fmt argb -s 560x1280 -i w560_h1280.argb -f rawvideo -pix_fmt rgb8 test.rgb8 -loglevel debug

ffmpeg -i source.mp4 -vf \
       scale=[width in px]:-1,format=rgb8,format=rgb24 \
       -r [framerate] \
       destination.gif

```