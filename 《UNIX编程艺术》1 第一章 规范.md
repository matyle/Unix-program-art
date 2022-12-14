#book 
[[UNIX编程艺术]] 微信划线
[[《UNIX编程艺术》2 第二章 历史]]
[[《UNIX 编程艺术》4 第4章 模块性：保持清晰，保持简洁]]



part 1

# 哲学

## 文化？什么文化
Unix确实有它自己的文化；有独特的编程艺术；有一套影响深远的设计哲学。理解这些传统，会使你写出更好的软件，即使你是在非 Unix 平台上开发。


## Unix生命力

性能—时间的指数曲线对软件开发过程所引发的结果，就是每过18个月，就有一半的知识会过时。Unix并不承诺让你免遭此劫，只是让你的知识投资更趋稳定。

## 反对学习Unix文化的理由
即使在 Unix 世界里，Unix 的通用性也一直受到怀疑，摇摆在危崖边。在持怀疑态度的外行人眼中，Unix很有用，不会消亡，只是登不了大雅之堂；注定只能是个小众的操作系统。
## UNIX 之失


Unix文件在字节层次以上再无结构可言。文件删除了就没法恢复。Unix的安全模型公认地太过原始。作业控制有欠精致。命名方式非常混乱。或许拥有文件系统本身就是一个错误。

#### 如何理解“机制”和“策略”？
X 致力于提供 一套“机制，而不是策略”，以支持一套极端通用的图形操作，从而把使用工具箱和界面的“观感”（策略）推后到应用层。

什么是机制和策略？ 应该分离
机制（mechanism）：更多偏抽象，和概念化（是否可以理解为接口）
策略（policy）：具体实施的方式（具体实现方式）

Unix其它系统级的服务也有类似的倾向：
行为的最终逻辑被尽可能推后到使用端。Unix用户可以在多种shell中进行选择。


这种倾向也反映出Unix的遗风：原本是为技术人员设计的操作系统；同时也表明设计的信念：**最终用户永远比操作系统设计人员更清楚他们究竟需要什么。**

贝尔实验室的Dick Hamming[3]在1950年代便树立了此信条：尽管计算机稀缺昂贵，但是开放式的计算模式，即客户可以为系统写出自己的应用程序，这一点势在必行，因为“用错误的方式解决正确的问题总比用正确的方法解决错误的问题好”。

## 1.5 Unix之得

1. 开源软件
2. 跨平台可移植性和开放标准
	1. Unix仍是唯一一个在不同种类的计算机、众多厂商、各种专用硬件上提供了一个一致的、文档齐全的应用程序接口（API）的操作系统
	2. Unix API几乎就可以作为编写真正可移植软件的硬件无关标准。
3. Internet和万维网
4. 开源社区
5. 从头到脚的灵活性
6. Unix Hack之趣：但是，确实如此，同Unix打交道，搞开发就是好玩；现在是，且一向如是。
	1. 对于程序员和开发人员来说，如果完成某项任务所需要付出的努力对他们是个挑战却又恰好还在力所能及的范围内，他们就会觉得很有乐趣。
	2. 就算 Unix 在其它各个方面都一无是处，Unix 的工程文化仍然值得学习，它使得开发过程充满乐趣。乐趣是一个符号，意味着效能、效率和高产。
7. Unix的经验别处也可适用


## 1.6 哲学基础
[[《UNIX 编程艺术》4 第4章 模块性：保持清晰，保持简洁]]
[[#哲学]]
- 让每个程序就做好一件事。如果有新任务，就重新开始，不要往原程序中加入新功能而搞得复杂
- 假定每个程序的输出都会成为另一个程序的输入，哪怕那个程序还是未知的。输出中不要有无关的信息干扰。避免使用严格的分栏格式和二进制格式输入。不要坚持使用交互式输入
- 尽可能早地将设计和编译的软件投入试用，哪怕是操作系统也不例外，理想情况下，应该是在几星期内。对拙劣的代码别犹豫，扔掉重写。
- 优先使用工具而不是拙劣的帮助来减轻编程任务的负担。工欲善其事，必先利其器。
Unix哲学是这样的：一个程序只做一件事，并做好。程序要能协作。程序要能处理文本流，因为这是最通用的接口。

Rob Pike，最伟大的C语言大师之一，在《Notes on C Programming》中从另一个稍微不同的角度表述了Unix的哲学[Pike]：

- 原则 1：**你无法断定程序会在什么地方耗费运行时间**。瓶颈经常出现在想不到的地方，所以别急于胡乱找个地方改代码，除非你已经证实那儿就是瓶颈所在。
- 原则 2：估量。在你没对代码进行估量，特别是没找到最耗时的那部分之前，别去优化速度。（优化要基于数据！！！）
- 原则3：**花哨的算法在n小时通常很慢，而n通常很小。**花哨算法的常数复杂度很大。除非你确定n总是很大，否则不要用花哨算法（即使n很大，也优先考虑原则2）。
- 原则4：**花哨的算法比简单算法更容易出bug、更难实现。**尽量使用简单的算法配合简单的数据结构。
- 原则 5：**数据压倒一切。**如果已经选择了正确的数据结构并且把一切都组织得井井有条，正确的算法也就不言自明。**编程的核心是数据结构，而不是算法[7]。**
- 原则6：没有原则6。


Ken Thompson——Unix最初版本的设计者和实现者，禅宗偈语般地对Pike的原则4作了强调：拿不准就穷举。
Unix哲学中更多的内容不是这些先哲们口头表述出来的，而是由他们所作的一切和Unix本身所作出的榜样体现出来的。从整体上来说，可以概括为以下几点：
1.模块原则：使用简洁的接口拼合简单的部件。
2.清晰原则：清晰胜于机巧。
3.组合原则：设计时考虑拼接组合。
**4.分离原则：策略同机制分离，接口同引擎分离。**
5.简洁原则：设计要简洁，复杂度能低则低。
6.吝啬原则：除非确无它法，不要编写庞大的程序。
7.透明性原则：设计要可见，以便审查和调试。
8.健壮原则：健壮源于透明与简洁。
9.表示原则：把知识叠入数据以求逻辑质朴而健壮。
10.通俗原则：接口设计避免标新立异。
11.缄默原则：如果一个程序没什么好说的，就沉默。
12.补救原则：出现异常时，马上退出并给出足够错误信息。
13.经济原则：宁花机器一分，不花程序员一秒。
14.生成原则：避免手工hack，尽量编写程序去生成程序。
15.**优化原则：雕琢前先要有原型，跑之前先学会走。**
16.多样原则：决不相信所谓“不二法门”的断言。17.扩展原则：设计着眼未来，未来总比预想来得快。


### 1.6.1 模块原则：使用简洁的接口拼合简单的部件
正如 Brian Kernighan 曾经说过的：“计算机编程的本质就是控制复杂度”[Kernighan-Plauger]。排错占用了大部分的开发时间，弄出一个拿得出手的可用系统，通常与其说出自才华横溢的设计成果，还不如说是跌跌撞撞的结果。

要编制复杂软件而又不至于一败涂地的唯一方法就是降低其整体复杂度——用清晰的接口把若干简单的模块组合成一个复杂软件。

### 1.6.2 清晰原则：清晰胜于机巧

维护如此重要而成本如此高昂；在写程序时，要想到你不是写给执行代码的计算机看的，而是给人——将来阅读维护源码的人，包括你自己——看的。

永远不要去吃力地解读一段晦涩的代码三次。第一次也许侥幸成功，但如果发现必须重新解读一遍——离第一次太久了，具体细节无从回想——那么你该注释代码了，这样第三次就相对不会那么痛苦了。


### 1.6.3 组合原则：设计时考虑拼接组合
在输入输出方面，Unix传统极力提倡采用简单、文本化、面向流、设备无关的格式
Unix中，文本流之于工具，就如同在面向对象环境中的消息之于对象。
要想让程序具有组合性，就要使程序彼此独立。（类也是如此，尽量用组合，而不是继承）

以一点点格式解析的代价，换得可以使用通用工具来构造或解读数据流的好处是值得的。


### 1.6.4 分离原则：策略同机制分离，接口同引擎分离
基本抉择是实行“机制，而不是策略”这种做法——使X成为一个通用图形引擎
策略和机制是按照不同的时间尺度变化的，**策略的变化要远远快于机制。**
GUI 工具包的观感时尚（策略）来去匆匆，而光栅操作和组合却是永恒的。（就像 MacOS，从初代到现在，gui 一直在变，而底层逻辑机制没有变）

把策略同机制揉成一团有两个负面影响：
1. 使策略变得死板，难以适应用户需求的改变，
2. 意味着任何策略的改变都极有可能动摇机制。

相反，将两者剥离，就有可能在探索新策略的时候不足以打破机制。
我们也可以更容易为机制写出较好的测试（因为策略太短命，不值得花太多精力在这上面）。

总而言之，这条准则告诉我们应该设法将接口和引擎剥离开来。

1. 将应用按照一个库来编写，这个库包含许多由内嵌脚本语言驱动的C服务程序，而至于整个应用的控制流程则用脚本来撰写而不是用C语言。
2. 将应用程序分成可以协作的前端和后端进程
前端实现策略，后端实现机制



### 简洁原则：设计要简洁，复杂度能低则低
来自多方面的压力常常会让程序变得复杂（由此代价更高，bug 更多），其中一种压力就是来自技术上的虚荣心理。程序员们都很聪明，常常以能玩转复杂东西和耍弄抽象概念的能力为傲，这一点也无可厚非。
但正因如此，他们常常会与同行们比试，看看谁能够鼓捣出最错综复杂的美妙事物.
正如我们经常所见，他们的设计能力大大超出他们的实现和排错能力，结果便是代价高昂的废品。

Unix程序员相互比的是谁能够做到“简洁而漂亮”并以此为荣!!!

要避免这些陷阱，唯一的方法就是鼓励另一种软件文化，以简洁为美，人人对庞大复杂的东西群起而攻之——这是一个非常看重简单解决方案的工程传统
总是设法将程序系统分解为几个能够协作的小部分，并本能地抵制任何用过多噱头来粉饰程序的企图。

>> 思考：简洁的意思不是说完全面向过程，有时候需要利用接口简化代码，复用逻辑（机制）。这也是为什么 go 语言提倡组合，小接口吧（不超过三个方法） Rob Pike 团队开发了 go 语言，同时他也是开发 Unix 的一员，所以有很多Unix设计理念 融合在了 golang 之中。
>
通用性和效率之间的抉择：例如昨天的 proto 和 json 解析（json 可以解析相应 interface{}


### 吝啬原则：除非确无它法，不要编写庞大的程序

“大”有两重含义：体积大，复杂程度高。程序大了，维护起来就困难。第13章就软件的最佳大小

### 1.6.7 透明性原则：设计要可见，以便审查和调试

软件系统的透明性是指：一眼就能够看出软件是在**做什么以及怎样做的**。（良好的规范）
显见性指：程序带有监视和显示内部状态的功能，这样程序不仅能够运行良好，而且还可以看得出它以何种方式运行。（日志）

至少，调试选项的设置应该尽量不要在事后，而应该在设计之初便考虑进去。
程序不但应该能够展示其正确性，也应该能够把原开发者解决问题的思维模型告诉后来者。

出于充分考虑透明性和显见性的目的，还应该提倡接口简洁（小接口），以方便其它程序对其进行操作——尤其是测试监视工具和调试脚本。

### 1.6.8 健壮原则：健壮源于透明与简洁
软件的健壮性指软件不仅能在正常情况下运行良好，而且在超出设计者设想的意外条件下也能够运行良好。
#### 为什么不健壮？
大多数软件禁不起磕碰，毛病很多，就是因为过于复杂，很难通盘考虑。如果不能够正确理解一个程序的逻辑，就不能确信其是否正确，也就不能在出错的时候修复它。

就带来了让程序健壮的方法，就是让程序的内部逻辑更易于理解。要做到这一点主要有两种方法：透明化和简洁化。

#### 透明性
软件的透明性就是指一眼就能够看出来是干什么以及怎么干的。
就健壮性而言，设计时要考虑到能承受极端大量的输入。

#### 如何判断简洁性？
如果“怎么回事”不算复杂，即不需要绞尽脑汁就能够推断出所有可能的情况，
那么这个程序就是简洁的。
模块性（代码简朴，接口简洁）是组织程序以达到更简洁目的的一个方法。
程序越简洁，越透明，也就越健壮.


### 表示原则：把知识叠入数据以求逻辑质朴而健壮

即使最简单的程序逻辑让人类来验证也很困难，但是就算是很复杂的数据，对人类来说，还是相对容易地就能够推导和建模的。

数据要比编程逻辑更容易驾驭。
如果要在复杂数据和复杂代码中选择一个，宁愿选择前者。更进一步：**在设计中，你应该主动将代码的复杂度转移到数据之中去。**


### 通俗原则：接口设计避免标新立异 最少惊奇原则
最易用的程序就是用户需要学习新东西最少的程序——或者，换句话说，最易用的程序就是最切合用户已有知识的程序。
而设计接口的时候，尽量按照用户最可能熟悉的同样功能接口和相似应用程序来进行建模。
‘+’应该永远表示加法

比如配置和运行控制文件的格式，命令行开关等等.这些惯例的存在有个极好的理由：缓和学习曲线。应该学会并使用这些惯例。

### 1.6.11 缄默原则：如果一个程序没什么好说的，就保持沉默(打印日志注意)
Unix中最古老最持久的设计原则之一就是：若程序没有什么特别之处可讲，就保持沉默。行为良好的程序应该默默工作，决不唠唠叨叨，碍手碍脚。沉默是金。

重要信息不应该混杂在冗长的程序内部行为信息中。如果显示的信息都是重要的，那就不用找了。

### 1.6.12 补救原则：出现异常时，马上退出并给出足量错误信息

同时也请注意Postel的规定：“宽容地收，谨慎地发”。
最初HTML文档推荐“宽容地接受数据”，结果因为每一种浏览器都只接受规范中一个不同的超集，使我们一直倍感无奈。要宽容的应该是规范而不是它们的解释工具。

### 1.6.13 经济原则：宁花机器一分，不花程序员一秒
不要过度优化，跟不值得花太多时间（当然有些是值得的，学习也是值得的）

### 避免手工hack，尽量编写程序去生成程序【
人类很不善于干辛苦的细节工作，程序中的任何手工hacking都是滋生错误和延误的温床。

程序中的任何手工hacking都是滋生错误和延误的温床。程序规格越简单越抽象，设计者就越容易做对。

由程序生成代码几乎（在各个层次）总是比手写代码廉价并且更值得信赖。我们都知道确实如此（毕竟这就是为什么会有编译器、解释器的原因），但我们却常常不去考虑其潜在的含义。

### 1.6.15 优化原则：雕琢前先得有原型，跑之前先学会走
原型设计最基本的原则最初来自于 Kernighan 和 Plauger 所说的“90%的功能现在能实现，比100%的功能永远实现不了强”。

Donald Knuth（程序设计领域中屈指可数的经典著作之一《计算机程序设计艺术》的作者）广为传播普及了这样的观点：“过早优化是万恶之源”。他是对的。

还不知道瓶颈所在就匆忙进行优化，这可能是唯一一个比乱加功能更损害设计的错误。
- 畸形的代码到杂乱无章的数据布局，牺牲透明性和简洁性而片面追求速度、内存或者磁盘使用的后果随处可见。滋生无数 bug，耗费以百万计的人时——这点芝麻大的好处，远不能抵消后续排错所付出的代价

- 过早的局部优化实际上会妨碍全局优化（从而降低整体性能）。


### 应该怎么优化？何时优化？
Ken Thompson：先制作原型，再精雕细琢。优化之前先确保能用
先能走，再学跑
>>先做一个初始版本（注意只是能用，并不是已经完成）
接着尝试理解，阅读自己代码,看有没有错误以及冗余，可优化点。

Donald Knuth：“过早优化是万恶之源”。
>> 以前在学校粗读这些书感觉非常复杂，还以为他们是推崇复杂性。其实那时候是理解不到位，也没有认真实践和理解。程序设计领域中屈指可数的经典著作之一 《计算机程序设计艺术》
[[计算机程序设计艺术]]

>>先给你的设计做个未优化的、运行缓慢、很耗内存但是正确的实现，然后进行系统地调整，牺牲最小局部简洁性而获得较大性能提升的点。

Ken Thompson:我最有成效的一天就是扔掉了1000行代码。。目前，最强大的优化工具恐怕就是delete键了。

### 1.6.16 多样原则：决不相信所谓“不二法门”的断言
即使最出色的软件也常常会受限于设计者的想象力.设计一个僵化、封闭、不愿与外界沟通的软件，简直就是一种病态的傲慢。

### 1.6.17 扩展原则：设计着眼未来，未来总比预想快
如果说相信别人所宣称的“不二法门”是不明智的话，那么坚信自己的设计是“不二法门”简直就是愚蠢了。决不要认为自己找到了最终答案。
因此，要为数据格式和代码留下扩展的空间，否则，就会发现自己常常被原先的不明智选择捆住了手脚，因为你无法既要改变它们又要维持对原来的兼容性。


#### 如何理解：设计协议或是文件格式时，应使其具有充分的自描述性以便可以扩展。
- 总是要么包含进一个版本号，
- 要么采用独立、自描述的语句，按照可以随时插入新的、换掉旧、
- 而不会搞乱格式读取代码的方法组织格式。

稍微增加一点让数据部署具有**自描述性**的开销，就可以在无需破坏整体的情况下进行扩展，你的付出也就得到了成千倍的回报。


## 所有的Unix哲学浓缩为一条铁律，那就是各地编程大师们奉为圭臬的“KISS”原则：
所有的Unix哲学浓缩为一条铁律，那就是各地编程大师们奉为圭臬的“KISS”原则：
Keep It Simple，Stupid！
![](https://cdn.jsdelivr.net/gh/matyle/tupic/img/20220813133452.png)


## 应用 Unix 哲学
- 如果可行，都应该使得程序与来源和目标无关的过滤器。
- 数据流应尽可能文本化（这样可以使用标准工具来查看和过滤）。
-  数据库部署和应用协议应尽可能文本化（让人可以阅读和编辑）。
-   过滤时，不需要丢弃的信息决不丢。
- 小就是美。在确保完成任务的基础上，程序功能尽可能少。


## 1.9 态度也要紧
看到该做的就去做——短期来看似乎是多做了，但从长期来看，这才是最佳捷径。
如果不能确定什么是对的，那么就只做最少量的工作，确保任务完成就行，至少直到明白什么是对的。
>>要良好的运用Unix哲学，你就应该不断追求卓越。你必须相信，软件设计是一门技艺，值得你付出所有的智慧、创造力和激情。
>>否则，你的视线就不会超越那些简单、老套的设计和实现；
>>你就会在应该思考的时候急急忙忙跑去编程。
>>你就会在该无情删繁就简的时候反而把问题复杂化——然后你还会反过来奇怪你的代码怎么会那么臃肿、那么难以调试。
>>好像现在还没有怎么思考，可能还是个新手小白吧，很多点 Get 不到。后面在开始编码的时候想好怎么写。因为都是在已有基础上编程，有类似代码可以学习，也需要利用框架做好自己的事情，还有更多的时间优化和修改

一旦某人已经解决了某个问题，就直接拿来利用，不要让骄傲或偏见拽住你又去重做一遍。
>>这个也是我之前喜欢犯的错，喜欢把别人实现的拿来再写一遍，应该直接用别人的。优化是后面的事情，应该要按上面的先完成跑通的原则。
>>永远不要蛮干；要多用巧劲，省下力气到需要的时候再用，好钢用在刀刃上。善用工具，尽可能将一切都自动化。（自动化非常重要）
>
软件设计和实现应该是一门充满快乐的艺术，一种高水平的游戏。如果这种态度对你来说听起来有些荒谬，或者令你隐约感到有些困窘，那么请停下来，想一想，问问自己是不是已经把什么给遗忘了。如果只是为了赚钱或是打发时间，你为什么要搞软件设计而不是别的什么呢？你肯定曾经也认为软件设计值得你付出激情……