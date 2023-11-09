
## gdb的使用
### gdb运行程序需要传递参数
`gdb -ex run --args ffmpeg -i input.mp4 -vf "scale=640:480" output.mp4`
`gdb> set args -i input.mp4 -vf "scale=640:480" output.mp4`

### gdb dump对应地址的数据
`dump binary memory file start_addr end_addr `

`(gdb) x/10b ptr //这里，/10b表示以字节（byte）为单位dump 10个数据。`

`x/100xb 0x7fffcaffe020  // 打印100个字节每个字节是16进制数`