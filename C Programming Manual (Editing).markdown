# 实验室C语言编程规范
版本号/Version|制定者/Writer|更新日期/Update Date|备注/Note
--|--|--|--
0.0.1|ArvinSC|2017-04-29|First Draft Doc.  <br />Any ERROR or MISTAKE, Please contact <a href="mailto:arvinsc@foxmail.com?subject=FeedBackAtCProgrammingManual">arvinsc@foxmail.com</a>
# 1. 项目组织规范
项目命名,一个工程项目应当存放在同一个文件中,项目名应当和实际开发作用相联系,主程序文件名和输出文件名应当与项目名一致.  
```
eg. Project: LED
. // Represent Current Directory
├── BoeBot.h
├── LED
├── LED.build_log.htm
├── LED.c // LED Main souce
├── LED.hex // OUTPUT file, sometimes may be *.exe file
├── LED.lnp
├── LED.LST
├── LED.M51
├── LED.OBJ
├── LED.uvgui.Administrator
├── LED.uvopt
├── LED.uvproj  // Project File
└── LED_uvproj.bak
```

# 2. 命名规范
## 2.1. 项目命名规范
- 项目命名应当与实际功用相匹配对应,如:  
  对于一个小车运行S型曲线的项目,可采用“SShapeMove”作为项目名.
- 项目命名时采用UpperCamelCase命名法,名称起止不应为任何的标点符号.
- 项目源文件文件应当以小写'c'为后缀, 形如:"\*.c".
- 项目采用的头文件应当以小写'h'为后缀, 形如:"\*.h".
## 2.2. 文件命名规范
- 文件命名应采用UpperCamelCase命名法,后缀名采用小写,如:"ThisIsAFile.txt".
## 2.3. 变量命名的规范
- 变量命名采用lowerCamelCase命名法,命名时应当见明知义,如存放数字的变量A:"numberA".
## 2.4. 函数命名规范
- 函数命名时,函数名应当与其所抽象的功能对应并采用lowerCamelCase方式命名,如:
  ```
  int addAAndB(int numberA, int numberB){
    return A + B;
  }
  ```
# 3. 代码书写规范
## 3.1. 引用库文件的规范
- 引用库文件时,引用文件应当遵循原文件命名规范,如果是最通用性地头文件,可以按照使用最多的形式引用.引用时,按照"#include <header.h>"的形式引用,在"include"后添加一个空格,如:
    ```
      // 原库文件: STDIO.H  MotorDriver.h
      // 引用时如下:
      #include <stdio.h>  
      // 而不应当是 #include <STDIO.H>
      #include <MotorDriver.h>
      // 而不应当是 #include <motordriver.H>
    ```
- 引用库文件时,如果库文件存在于当前目录,则应当使用"#include "header.h""的形式,如果存在于编译器默认目录,应当使用"#include <header.h>"的形式,如:
  ```
  #include <header.h> // Default include path
  #include "header.h" // Current project path
  ```
## 3.2. 函数的写法
- 在书写普通函数时,应当在命名上符合函数命名规范.
- 函数书写时,应当明确输入与输出,输入参数命名应当符合变量命名规范.
- main函数的写法,依照C/C++11标准,如下所示:
  ```
  int main(){
    // Your code here.
    return 0;
  }
  ```
## 3.3. 缩进规范
- 代码缩进,可以采用一个TAB占位符或者两个空格.
## 3.4. 注释规范
- 单行注释应当在"//"语法标记后添加一个空格
- 尽量采用英文的注释,尤其在对于中文或非ASCII编码敏感的编辑器中
