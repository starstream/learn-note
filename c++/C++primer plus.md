# 第2章 开始学习C++

- 2.1 进入C++
- C++对大小写敏感
  
- main()函数
  
  - int main()叫做函数头，{}包含的部分叫做函数体
  
  - main()函数中最后一条语句叫做返回语句，如果编译器到达main()函数末尾时没有遇到返回语句，则认为main函数以 return 0；结尾。
  
- C++注释
  
  - C++注释以//打头，到行尾结束
  
  - C++也能识别C注释，即/* ...*/
  
- C++预处理器和iostream文件
    - 若程序要使用C++输入或输出工具，则须提供以下两行代码： # include <iostream>； # using namespace std ; 该编译指令导致预处理器将iostream文件的内容添加到程序中。iostream中的io指的是输入（进入程序的信息）和输出（从程序中发送出去的信息），# include编译指令导致iostream文件的内容随源代码的内容一起被发送给编译器，实际上，iostream文件的内容将取代代码行# include<iostream>，但原始文件没有被修改，而是将源代码和iostream组合成一个复合文件，编译的下一阶段将使用该文件。
  
- 头文件名 
  
  - 像iostrean这样的文件叫做包含文件（由于它们被包含在其他文件中），也叫头文件（由于它们被包含在文件起始处）。
  
  - C++新式风格不使用扩展名
  
- 名称空间
  
  - 如果使用iostream而不是iostream.h，则应使用下面的名称空间来使iostream中的定义对文件可用：using namespace std; ，这叫做using编译指令。
  
  - 类、函数、和变量是C++编译器的标准组件，它们都被放置在名称空间std中（当头文件没有扩展名h时），这意味着在iostream中定义的用于输出的cout变量实际上是std::cout，而endl实际上是std::endl。
  
  - 使用std名称空间中定义的名称，可以不必使用std::前缀，即using namespace std; 这个using编译指令使得std名称空间中所有名称可用，更好的方法是只使所需的名称可用，即 using std ::cout；
  
- cout进行输出
  
  - cout << "string"; <<符号表示该语句将把这个字符串发送给cout，该符号指出了信息流动的路径。cout是一个预定义的对象，它的对象属性包括一个插入运算符（<<），可以将右侧的信息插入到流中。
  
  - 控制符endl：重起一行
  
  - 换行符\n
  
- C++源代码的格式化
  
  - 标记和空白
  
  - C++源代码风格
  
- 2.2 C++语句

  - 声明语句和变量
    - 对于声明变量，C++的做法是在首次使用该变量前声明它

  - 赋值语句

- 2.3 其他C++语句

  - cin << carrots ; >>运算符从输入流中抽取字符。

  - 使用cout进行拼接

  - 类简介

- 2.4 函数

  - 有返回值的函数

  - 函数的变体
    - 在C++中，函数调用必须包括括号，即使没有参数。

  - 自定义函数

    - main函数返回一个int值，程序要求它返回整数0。main()的返回值不是返回给程序的其他部分，而是返回给操作系统，操作系统测试程序的返回值（通常叫做退出值），退出值为0则意味着程序运行成功。

    - 在多函数程序中使用using编译指令

# 第3章 处理数据

- 3.1 简单变量

  - 整型

    - short、int、long、long long

      - sizeof运算符返回类型或变量的长度，如sizeof(int)的值为4，说明在使用8位字节的系统中，int的长度为4个字节。

      - climits头文件定义了符号常量来表示类型的限制。如INT_MAX表示类型int能够存储的最大值，LONG_MIN表示long的最小值。

      - int被设置为对目标计算机而言最为自然的长度，即计算机处理起来效率最高的长度。

    - 无符号类型

      - 使用关键字 unsigned声明无符号类型。

      - 如果值溢出，其值将为范围另一端的取值。（图3.1）

    - 整型字面值（常量）

      - 第一位是1~9，则基数为10；第一位是0，第二位是1~7，则基数为8；前两位是0x或0X，则基数为16。

      - cout以十进制格式显示整数，同时提供了控制符dec、hec和oct分别用于指示cout以十进制、十六进制和八进制格式显示整数。

      - C++默认将整型常量存储为int类型，当整数后面的后缀为l或L时，表示该整数为long常量；u或U后缀表示unsigned int常量。

  - char类型：字符和小整数

    - char类型是另一种整型

    - cin将输入的字符转换为字符编码并存储到char类型中，cout反之。 如，输入时cin将键盘输入的M转换为77，输出时cout将值77转换为字符M；如果将77存储在Int变量中，则cout将把它显示为77，即cout显示两个字符7

    - 由于char实际上是一个整数，因此可以进行整数操作。如ch=ch+1

    - cout.put()函数显示一个字符

    - 转义序列

      - 有些字符具有特殊的含义，或者不能从键盘输入。如回车键为在代码中开始新的一行，双引号用来分隔字符串字面值。

      - 应该像处理常规字符一样处理转义序列，即将它们视作字符常量时，用单引号括起，将它们放在字符串中时，不要使用单引号。

      - 可以以字符常量表示法‘\n’或字符串方式“\n”使用换行符，如cout << '\n' 

    - 通用字符名

    - 有符号char和无符号char

      - 与Int类型不同，char在默认情况下既不是没有符号，也不是有符号。

      - 无符号char的表示范围通常为0~255，而有符号char的表示范围为-128~127。

    - wcha_t（宽字符类型）
      - wcin和wcout可用于处理wchar_t流

    - char16_t和char32_t

  - bool类型

    - 值为true或flase

    - 字面值true和flase都可以通过提升转化为Int类型，true被转换为1，flase被转换为0。

- 3.2 const限定符

  - 常量被const关键字初始化后，其值就被固定，编译器不再允许修改该常量的值。

  - 常见的做法是将名称的首字母大写，如Months

- 3.3 浮点数

  - 书写浮点数的方法：标准小数法、E表示法

  - 浮点数类型

    - float 32位

    - double 64位

    - long double 80、96、128

  - setf()方法迫使输出使用定点表示法，防止程序把较大的值切换为E表示法，并使程序显示到小数点后6位

  - 浮点常量
    - 在默认情况下，浮点常量为double类型

- 3.4 C++算术运算符

  - 运算符优先级和结合性

  - 除法运算符
    - 其中一个操作数是浮点数，则结果为浮点数

  - 求模运算符

  - 类型转换