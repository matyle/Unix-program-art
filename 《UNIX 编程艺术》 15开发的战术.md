#book 
[[14 语言：C还是非C《UNIX 编程艺术》]]
Unix is user-friendly—it's just choosy about who its friends are.
Unix对用户是友好的——只不过是挑剔的友好

## 15.1 开发者友好的操作系统
Unix提倡一种更灵活的风格，一种以编辑/编译/调试循环为中心、排它性更少的风格。
编译代码、管理代码配置、性能分析、调试以及自动完成各种脏活累活，而让人更专注于有趣的部分


## 编辑器

### vi
vi这个名字是“visual editor （可视编辑器）”的缩写，发音为/vee eye/（不是/vie/并且绝对不是/siks/！）。还有几个具有扩展功能的变种，著名的有vim（improved）


### 15.2.3 非虔诚的选择：两者兼用
许多人经常规则地使用vi和Emacs来做不同的事情，并且认为非常值得把两者都摸透。



## 15.3 专用代码生成器
### 15.3.1 yacc和lex
yacc和lex是用来生成语言词法分析器的工具


## 15.4 make：自动化编译
果使用C或C++进行开发，构建应用程序的一个重要部分是将源代码变成二进制可运行文件的编译和链接命令集合。Unix的make（1）程序，是所有这些程序的鼻祖，专门设计来帮助C程序员管理这些命令。

最开始是精细的依赖关系分析器，浓缩为更简单的东西后，周末就出炉了Make。
新兴工具的使用也是Unix文化的一个部分。Make文件都是文本的，不是神秘的二进制编码，因为这就是Unix的精神：可打印、可调试、可理解


### 15.4.2 非C/C++开发中的make

脚本语言可能并不要求传统的编译和链接步骤，但是也常常有其它的依赖关系，make（1）正好可以有帮助。

- all
- test
- clean

但是不要局限在这些通用目标上。一旦掌握make，就会越来越频繁地使用makefile机制来自动化那些依赖项目文件状态的小任务

makefile 就是一个方便存放完成这些小任务脚本的重要地方；而使用make可以在检视如何完成这些小任务时一目了然，并且避免了小脚本将项目工作空间弄得凌乱不堪。

### Makefile生成

1. Makedepend
2. atuoconf
3. Lmake
4. automake

## 版本控制系统

### 为什么需要版本控制
- 需要回归，回归到良好版本
- 如果回归是困难的或不可靠的，改变代码就太过冒险（有可能会崩掉整个项目，或者为自己凭空增加许多小时的痛苦工作）
- 稍后再看它们却很容易就忘记了改变的原因
- 如果项目存在合作者，又如何知道在自己不注意时合作者改变了什么，另外，每个修改该由谁负责？
- BUG 追踪

变化追踪的粒度也十分有限，而且细节经常丢失：比如变化次序、谁做的、为什么

[[我目前使用的开发工具]]