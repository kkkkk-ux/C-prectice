1.十六进制字符串转十进制字符串。
char *end_ptr;  // 定义一个指针变量来存储未处理部分的起始地址
int decimal = (int)strtol(hex_str, &end_ptr, 16);
2.不安全函数和安全函数替换。
以下列出了部分内存操作类不安全函数：
内存拷贝函数：memcpy(), wmemcpy(), memmove(), wmemmove()

内存初始化函数：memset()

字符串拷贝函数：strcpy(), wcscpy(), strncpy(), wcsncpy()
安全：strncpy_s(char *dest, rsize_t dest_size, const char *src, rsize_t count);

字符串拼接函数：strcat(), wcscat(), strncat(), wcsncat()

字符串格式化输出函数：sprintf(), swprintf(), vsprintf(), vswprintf(), snprintf(), vsnprintf()
安全：int snprintf_s(char *str, rsize_t size, const char *format, ...); 用例：snprintf_s(TotalLength, sizeof(TotalLength), "%ld", DecimalLong)

字符串格式化输入函数：scanf(), wscanf(), vscanf(), vwscanf(), fscanf(), fwscanf(), vfscanf(),vfwscanf(), sscanf(), swscanf(), vsscanf(), vswscanf()

stdin流输入函数：gets()

3.十进制数据转字符串snprintf_s(TotalLength, sizeof(TotalLength), "%ld", DecimalLong); %X %o分别是转十六和八进制。
