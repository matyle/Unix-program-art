# Unix-program-art
unix编程艺术笔记，👍

>> 过早优化是万恶之源

- 阅读动机：
一开始并不知道这本书是讲的什么，以为更多的是讲述 UNIX 的历史和一些编程经验。对 Unix 感兴趣的原因之一本人也在越来越多的接触终端，vim。给我的感觉是vim的插件都是开源的，而且非常规范统一。其二，我现在更多的使用的是 golang，而 golang 的创始人之一正是 Unix c 语言 创始人 Rob Pike。因此在很多地方都看到了 Rob Pike 对 golang 思想的设计。这让我开始想了解 Unix的历史和编程艺术
>>Rob Pike，最伟大的C语言大师之一

## 开始阅读

第一部分整体讲述了 Unix 的哲学思想，历史和其他系统的哲学对比。
### 关于哲学

- 这个章节讲述了 Unix 设计的得失（灵活，开源软件，移植性，经验到处可用）
- 哲学基础
	- 一个程序做好一件事（一次做好一件事，做好就够了）
	- 尽早设计编译，投入试用（才能快速找到问题）
	- 恶劣代码扔掉重写
	- 优先使用工具
	 
- Rob Pike大师的原则（golang 发明者通用）
	- 原则1. 无法判断瓶颈位置，不要随便修改，除非已经证实（用数据说话，golang 使用 pprof）
	- 原则2. 没有用数据进行估量之前，不要优化速度（有可能只是我们自己主观臆断）
	- 原则3.不要轻易使用花哨的算法（常数复杂度大）（因为 n 往往不是很大，就算大也要考虑原则2）
	- 原则4.数据比算法更好把握，花哨的算法容易出 bug 更难实现。尽量使用简单算法配合简单数据结构。
	- 原则5：数据压倒一切，数据结构组织的清洗明了，正确算法不言自明。**编程的核心是数据结构，而不是算法**
- Ken Thompson 原则：
	- 强调原则4：拿不准就穷举
	
### 后面详细阐述的 Unix 原则（非常重要）！！

- **1. 模块原则：使用简洁的接口拼合简单的部件。**
- 2.清晰原则：清晰胜于机巧。
- 3.组合原则：设计时考虑拼接组合。
- **4.分离原则：策略同机制分离，接口同引擎分离。**
- 5.简洁原则：设计要简洁，复杂度能低则低。
- 6.吝啬原则：除非确无它法，不要编写庞大的程序。
[[《UNIX 编程艺术》4 第4章 模块性：保持清晰，保持简洁]]
- 7.透明性原则：设计要可见，以便审查和调试。
- 8.健壮原则：健壮源于透明与简洁。
- 9.表示原则：把知识叠入数据以求逻辑质朴而健壮。
- 10.通俗原则：接口设计避免标新立异。
- 11.缄默原则：如果一个程序没什么好说的，就沉默。
- 12.补救原则：出现异常时，马上退出并给出足够错误信息。
- 13.经济原则：宁花机器一分，不花程序员一秒。 

- 14.生成原则：避免手工hack，尽量编写程序去生成程序。
- 15.**优化原则：雕琢前先要有原型，跑之前先学会走。**
- 16.多样原则：决不相信所谓“不二法门”的断言。17.扩展原则：设计着眼未来，未来总比预想来得快。
## 总结

Unix 哲学是这本书的精华（也正是编程艺术的体现），特别是几大原则十分具有实践意义。
后面部分有对编程哲学的具体化讲解，以及实例分析。

---
#book 
[[《UNIX编程艺术》1 第一章 规范]]


[gitlab博客](www.matytan.gitlab.io)

[博客园博客](https://www.cnblogs.com/matytan/)

[github 博客](https://www.matyle.github.io)
