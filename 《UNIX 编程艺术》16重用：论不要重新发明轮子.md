不言之教，无为之益，天下希及之。

- 不愿做不必要的工作是程序员的一大美德
他可能会被错解为：不编之码，天下希及之。
>事实上，近来的译者已经建议，传统上认为等价于“不作为”或是“节制行为”的中国专有名词“无为”，
或许应该解释成“最小行为”、“最有效行为”或是“按自然法则行为”，这更适合描述良好的工程实践。


牢记经济原则。每个新项目都从刀耕火种开始干起简直就是极端的浪费
>请想想：和其它耗在软件开发的花费比起来，时间无疑是最宝贵和最有价值的；所以相应地，应该耗费在解决新问题，而不是对那些已存在确切解决方案的问题老调重弹。


>发明轮子之所以糟糕不仅因为浪费时间，还因为它浪费的时间往往是平方级。
>走捷径往往产生粗糙、未经思考的版本，长期而言这是假性节约，但通过这种方式来节省重新发明时间的诱惑几乎总是无法抵抗的。—Henry Spencer

避免重新发明轮子的最有效方法是借用别人的设计和实现。换句话说，重用代码。

Unix的经验是，养成良好的习惯，尝试通过最少的新发明，组合现有组件以形成原型，而非匆忙地编写独立的、只能使用一次的代码
代码重用的品质是软件开发中如同苹果派和母爱般基本的主要美德。

## 16.1 猪小兵的故事
>程序员为什么会重新发明轮子？

从狭隘的技术原因到程序员心理状态，再到软件生产系统的经济学，方方面面都会导致如此行为，这种特有的顽疾正在肆虐。

自己造轮子的优点：
- 清晰

缺点：
- 局部优化，如果不能重用就没有价值
>在换工作时，他很可能发现带不走他的工具包。如果他带着在公司编写的代码走出公司大门，其旧雇主就有理由认为他侵犯了知识产权。如果承认重用了旧代码，新雇主如果知道了，也大有可能很不爽。



## 16.2 透明性是重用的关键
为什么需要源代码？

## 16.3 从重用到开源
- Unix程序员在几十年中学到了“只有变化才是永恒的”，经验是，源码可以永续，目标码则不行。
- 如果在尝试重用时，其源码可以被阅读或修改，那么代码重用失败的那种刺痛感要少得多。



>
>SourceForge＜http：//www.sourceforge.net＞
>是个软件的展示站点，这些软件明确地设计来支持合作开发，并拥有相关的项目管理服务。SourceForge不仅仅是个存放软件的地方，还提供自由的联合开发服务，在2003年中期，毫无疑问，是世界上最大的纯开源活动中心。在SourceForge之前，最大的站点是ibiblio＜http：//www.ibiblio.org＞的Linux归档。ibiblio 归档是被动的，仅仅是个发布软件包的地方。然而，它确实比起多数被动站点的网页界面都要好得多（创造其网页外观的程序，是我们在第14章讨论Perl时的一个实例分析）。这个站点也是Linux文档项目（Linux Documentation Project）的主页，维护着许多供Unix用户和开发者使用的优秀资源。Freshmeat＜http：//www.freshmeat.net＞是个专注于提供新软件以及已有软件新版本发布公告的系统。它允许用户和第三方给这些版本添加评审。


更一般地，阅读代码是为未来而投资。可以从中学到甚多——新技术、分解问题的新方法、不同的风格和手段.写之前先读；培养阅读代码的习惯。少有什么彻底全新的问题，所以几乎总是能够发现非常接近的代码，成为自己需要的一个良好起点。


## 16.6 使用开源软件的问题
使用或者重用开源软件存在三个主要问题；质量、文档以及许可证条款。



