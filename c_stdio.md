stdio: FILIE
## fopen() / fclose()
1. How many files at most can you open?
hint: ulimit -a
2. What's the user permission of file created by fopen?
0666 & ~umask

## fgetc / getputc / fgets / fputs
fgets: add terminating null byte('\0') to the end of s
fputs: without '\0'
puts: to stdout, with new line('\n')
no gets:

## fread / fwrite

## printf / scanf / fprintf / fscanf

fseek() / ftell() / no bigger than 2G-1
fseeko() / ftello(): off_t
perror() / strerror(errorno)
## getline

## tmpnam / tmpfile

=======================
I/O: base for all application.
stdio vs sysio
readable==> accurate ==>efficient
logic ==> no bug
有宏名用宏名，不要用宏值
谁打开谁关闭
谁申请谁释放
是资源就有上限
malloc
void ==> any type pointer

stack/ static zone/ 
localtime
getpwuid


函数和宏的区别
宏不占用调用时间
inline  define
内核/应用稳定 安全
没有内存泄漏　尾０
慎重使用%s
====
int fgetc(): stream
int getc(): kernel, macro, evaluate stream.
int getchar() : getc(stdin)
diff
once program error, you need to release resources via hook function
gets()
====
Don't create opportunities to make mistake.
atoi
sprintf==>"itoa"  
#define FILE_OFFSET_BITS 64 ==> off_t
makefile: CFLAGS+=-D_FILE_OFFSET_BITS=64  ==>
-D_GNU_SOURCE
cc -D_FILE_OFFSET_BITS=64 flen.c -o flen
空洞文件
行缓冲模式：换行/行满
缓冲区作用：合并系统调用
行缓冲
全缓冲
无缓冲：stderr
setvbuf
fopen

================
## execise:
1. use getline() to get a file's very line
2. realize getline() function by yourself.
3. 
