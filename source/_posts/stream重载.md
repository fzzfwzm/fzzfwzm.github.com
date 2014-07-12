title: IStream重载
date: 2014-07-10 07:14:29 
categories: 实习记录 
---
### 流的相关基本知识

读和写类型打开文件时：注意事项：
* 如果中间没有fflush，fseek，fsetpos，rewind，则在输出后面不能直接跟输入
* 如果中间没有fseek，fsetpos，rewind，或者一个输入操作没有到达文件尾，则在输入之后不能跟输出

### 流与缓冲区


### 高级IO
#### 字节范围锁
#### 异步