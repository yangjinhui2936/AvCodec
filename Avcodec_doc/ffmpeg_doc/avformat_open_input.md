## 函数详解：avformat_open_input()
### 函数功能
    打开一个输入流，并读取其头部信息,
    返回一个指向 AVFormatContext 的指针,
    成功后，需要调用 avformat_close_input()来关闭输入流,
    如果需要读取流中的数据，需要调用avformat_find_stream_info()来读取流中的信息。
### 函数原型
```c
/**
 * Open an input stream and read the header. The codecs are not opened.
 * The stream must be closed with avformat_close_input().
 *
 * @param ps Pointer to user-supplied AVFormatContext (allocated by avformat_alloc_context).
 *           May be a pointer to NULL, in which case an AVFormatContext is allocated by this
 *           function and written into ps.
 *           Note that a user-supplied AVFormatContext will be freed on failure.
 * @param filename Name of the stream to open.
 * @param fmt If non-NULL, this parameter forces a s    pecific input format.
 *            Otherwise the format is autodetected.
 * @param options  A dictionary filled with AVFormatContext and demuxer-private options.
 *                 On return this parameter will be destroyed and replaced with a dict containing
 *                 options that were not found. May be NULL.
 *
 * @return 0 on success, a negative AVERROR on failure.
 *
 * @note If you want to use custom IO, preallocate the format context and set its pb field.
 */
int avformat_open_input(AVFormatContext **ps, const char *filename, AVInputFormat *fmt, AVDictionary **options);
```


### 函数用法
```c
    // 打开输入文件
    AVFormatContext* input_format_ctx = NULL;
    if (avformat_open_input(&input_format_ctx, input_filename, NULL, NULL) != 0) {
        printf("cannot avformat_open_input\n");
        return -1;
    }
```

```mermaid
    graph LR
    A[avcodec_open2] -->B[avctx->codec->init]
```

### 函数详解
