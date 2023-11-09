# 函数解析之：avformat_find_stream_info()

## 函数功能
函数解析：avformat_find_stream_info()，用于获取媒体文件中的流信息。
该函数主要用于给每个媒体流（音频/视频）的AVStream结构体赋值
## 函数声明
```C    
int avformat_find_stream_info(AVFormatContext *ic, AVDictionary **options);
```
