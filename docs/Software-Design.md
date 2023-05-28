# 软件设计体系学习

> 把事物抽象和模块化
>
> 首先这个考试知识面很广，涵盖计算机各个方面

## 计算机系统体系结构

计算机硬件体系：CPU(运算器和控制器)、内存和硬盘(存储器)、键盘和显示器(输入输出设备)五大部件组层

- CPU(运算器和控制器) 获取指令、译码、处理

  功能：程序控制、操作控制、时间控制、数据处理(主要功能)

  组成：运算器、控制器、数据缓冲寄存器等

- 多核CPU：多任务处理，并行处理

数据表示：带符号数、无符号原码、反码、补码、移码、定点数和浮点数

校验码：提高数据传输后，对数据的正确性识别操作

- 奇偶校验码
- 海明码
- 循环冗余校验码

宏观计算机体系结构：单处理系统、并行多处理系统、分布式处理系统

微观计算机体系结构之Flynn分类法：M.J.Flynn提出的计算机系统结构分为四类，分别为单指令单数据流、单指令多数据流、多指令单数据流、多指令多数据流

指令分类：CISC和RISC

- CISC（Complex Instruction Set Computer 复杂指令集计算机），指令复杂、主要由微程序技术实现、完善的中断处理、该设计给芯片提高了研制难度和出错几率
- RISC（Reduced Instruction Set Computer 精简指令集计算机），指令简单、主要由

指令的流水线技术：

**存储系统：** CPU内部通用寄存器、Cache、主存储器、磁盘存储器

- RAM（Random Access Memory 读写存储器）

- ROM（Read Only Memory 只读存储器）内部固定的数据，存放系统程序BIOS和用于微程序控制

- PROM（Programmable Read Only Memory 可编程只读存储器）

- EPROM（Erasable Programmable Read Only Memory 可编程可擦除的只读存储器）

- EEPROM（Electrically Erasable Programmable Read Only Memory 电擦除可编程的只读存储器）

- Flash Memory 闪存存储器

  寻址方式不同的存储器

- RAM 随机存储器

- SAM（Sequentially Addressed Memory 顺序存储器）

- DAM（Direct Addressed Memory 直接存储器）介于上面两者之间，比如磁盘

**总线结构：**计算机中设备与设备之间数据传输的通道

- 数据总线（Data Bus，DB）传送数据，双向
- 地址总线（Address Bus，AB）传送CPU发出的地址信息，单向
- 控制总线（Control Bus，CB）传送控制、时序、状态数据信息

**可靠性：** 

- 串联系统计算 R~总~ = R~1~*R~2~*R~3~ * ... * R~n~
- 并联系统计算 R~总~ = 1- (1-R~1~)(1-R~2~)...(1-R~n~)
- N模混连 结合上面两个方式计算
- 可靠性：MTTF/(1-MTTF)

**计算机安全性：** 

- 安全等级从高到低：A1、B3、B2、B1、C2、C1、D
- 影响数据安全因素：内部和外部
- 加密技术：加密解密搭配密匙操作



## 程序设计语言

计算机使用的语言，从硬件使用的低级语言的机器语言和汇编，再到高级语言C、应用层更抽象的java、python等

程序设计语言倡导的就是更高的抽象机制和程序设计思想

解释源程序后，需要解释程序与源程序一起参与运行，解释程序占主要控制

编译源程序后，只需运行与源程序等价的编译后生成的目标程序

语言的发展路程：

- Fortran  用于科学与工程中数值计算领域的高级语言，程序设计语言的开端
- ALGOL  语言发展的重要节点，产出了局部性、动态、递归等思想
- PASCAL 过程式、结构化程序设计语言、功能强且使用简单
- C  具备高级语言与汇编语言的特点、高效的执行语句、能直接操控操作系统与底层硬件
- C++ 在C之上的面向对象设计语言
- C#  运行在.NET上的高级设计语言
- Objective-C  扩充C的面向对象设计语言，MAC系统的主要开发语言
- Java  目前通用的程序设计语言，有C++面向对象特点，更简单抽象
- Ruby  解释性、面向对象、动态脚本语言，语言的使用和思想和现在的Kotlin相似，任何都是对象等
- PHP  服务器端执行的嵌入HTML的脚本语言，语言风格相似C，兼容很多数据库和操作系统
- Python  解释型操作语言、能结合C、C++、Java等设计脚本和程序，支持操作系统的访问
- JavaScript  WEB开发网页动态效果的脚本语言

## 数据结构

数据在计算机中的不同组织方式 线性结构、数组、广义表、树、图和基本算法

[数据结构与算法](../Data-Structure.md)

## 操作系统

> 计算机软件分为系统软件和应用软件，系统软件就是操作系统、语言处理程序、数据库管理系统等
>
> 操作系统就是核心软件，其它软件都是建立在它的接口之上，从而可以操作硬件执行程序

操作系统的功能：进程、存储、设备、文件、作业管理

操作系统分类：

- 批处理操作系统  其实就是最古老的纸带打孔的程序，一条就是一个程序，称为单道批处理操作系统；后面出现了个多道批处理操作系统，就是一次运行多个程序，当操作系统调用CPU处理第一个程序的同时调用内存将第二个程序装入内存，实现宏观并行运行
- 分时操作系统  一个主计算机与多个终端设备连接，比如20个终端每个终端需要CPU运行50ms的时间片，那这二十个终端运行完就需要1S，缺点就是卡，优点就是节约钱，并且可以统一管理；多路、独立、交互
- 实时操作系统  用于武器控制，飞机订票等对新信息的快速处理的操作系统
- 网络操作系统   就是将每个主机利用网络连接起来，使相互之间能信息资源共享，能相互提供各种服务
- 分布式操作系统  网络操作系统的高级形式，将每个主机结合起来，这样可以实现同一管理，并且其中一台故障后不影响整体功能，在对任务的处理上更加快速，并且存储数据更分散，属于去中心化系统
- 微型计算机操作系统  用在一些微机上的操作系统，比如鼠标，路由器等上使用Linux等
- 嵌入式操作系统   嵌入芯片中的程序，芯片的功能和操作由它来提供，有微型、可定制、可靠、易移植等特点

**进程：** 合理地管理分配多道程序给CPU处理

进程的组成：程序、数据、进程控制块PCB

PCB内容：

| 信息       | 含义                                                         |
| ---------- | ------------------------------------------------------------ |
| 进程标识符 | 标识每个进程                                                 |
| 状态       | 当前进程状态                                                 |
| 位置       | 指明程序和数据在主存或外存的物理位置                         |
| 控制信息   | 参数、信号量、消息等                                         |
| 队列指针   | 连接相同状态的进程                                           |
| 优先级     | 进程调度的依据                                               |
| 保护现场   | 进程处理到哪块位置，并将这个位置和一些数据进行保存，用于再次调度继续运行 |

进程通信：多个进程之间的资源共享，信息共享

- 同步  进程间相互合作，协同工作的处理，在A进程处理完数据后将数据给B进程处理
- 互斥  进程间争用临界区后产生的互斥操作，一个临界区只能给一个进程使用
- 信号量  多个进程实现同步和互斥的工具，信号量主要就得知道S、P、V的含义和PV操作信号量S
  - S  如果S>=0代表资源的可用数，S<0代表进程阻塞的数量
  - P  申请资源
  - V  释放资源
  - 信号量实现同步  用S代表消息，进程调用P操作测试消息是否到达，调用V操作测试消息是否准备好
  - 信号量实现互斥  进入临界区执行P操作，退出临界区执行V操作

进程调度：如何分配高优先级的进程给CPU

- 可剥夺  更高优先级进程会占领CPU处理中的进程
- 不可剥夺  更高优先级的进程会等待占领CPU处理中的进程

调度算法：

- 先来先服务  FCFS 进程按照先后顺序排队处理，适用于处理频繁的作业
- 时间片轮转  给进程固定时间片，每个进程得到处理的概率相同；给进程可变时间片，每个进程处理的概率和时间可以设置
- 优先级调度  给每个进程一个优先级，优先级高的进程在调度时优先处理
- 多级反馈调度  结合时间片和优先级的调度管理

线程：线程的出现原因就是进程的创建、撤销、切换过于消耗系统开销，这样拥有资源的基本单位的进程不用频繁切换，转为切换线程实现程序的并发；线程是进程中一个实体，是被系统独立分配和调度的基本单位，它共享进程资源，如程序计数器和栈；进程的切换不需要内核调度，进程需要内核调度的参与才能实现切换或数据通信

**存储：** 对存储空间的分配、回收、地址映射管理

计算机中的存储结构：寄存器-缓存-主存-外存

存储管理目的是解决多用户使用主存问题，管理方案有分区存储管理、分页存储管理、分段存储管理、段页式存储管理、虚拟存储管理等

分区存储管理：就是把主存分为若干个区域，然后一个作业只能使用一块区域；

- 固定分区优点就是可以自定义每块区域大小，但是容易造成空间浪费
- 可变分区就是动态分区，在作业工作时动态分配区域大小，这种分配方式有很多，比如最佳适应法等

分页存储管理：首先是将进程的地址空间分成若干个页，然后将主存空间分成和页相同大小的块，在分配进程空间时将页装到主存的块中；操作系统实现，缺点是不易实现共享

- 将程序的页分为页号和页内地址(逻辑地址)
- 将主存的块分为块号和块内地址(物理地址)
- 在映射时有个叫页表的东西，然后查它得到页号，页内地址就对应块内地址，找到块内地址后就是实际程序存放的地方，完成从逻辑地址到物理地址的转变

分段存储管理：将进程的地址空间分成若干个段，也即将程序分为主程序段、子程序段、数据段等；一个作业最多64kb个段，每个段的最大长度为64kb

- 和页相似，也是将段分为段号和段内地址(逻辑地址)
- 剩下的和上面差不多

段页式存储：结合上面两个，有分页的高效主存利用率优点，也有分段满足用户需要的优点；原理：

- 将主存分为大小相等的块
- 将程序按程序的逻辑关系分为若干个段，每个段有个段名
- 再将段分为若干个页   就是               段号s+段内页号p+页内地址w
- 为实现逻辑地址和物理地址映射，必须有段表和页表
- 映射原理就是先在段表查找段号s，然后由段内号查找物理块b；再结合段号和段内页号得到的页内地址W这样就得到物理地址bW

**文件：** 文件存储空间、目录、文件读写管理

**设备：** 管理硬件设备的启动、回收以及输入输出设备分配

磁盘调度：就是多个进程同时需要把自身数据放到磁盘中时，对磁盘存访问的管理方式，让各进程对磁盘的平均寻道时间最小，磁盘在寻道时是先移臂再旋转调度

调度算法之先来先服务，就是哪个进程先来就对该进程处理，这样的平均寻道时间最长；调度算法之最短寻道时间优先，这样的调度要求访问磁道和当前磁头距离最近才能使平均寻道最短

- 旋转调度算法  懂磁道和扇区就行，然后旋转调度有下面三种情况
  - 进程访问的是同一磁道上不同编号的扇区
  - 进程访问的是不同磁道的不同编号扇区
  - 进程访问的是不同磁道的相同扇区
- 在分析访问时间时注意扇区处理时间就行

**作业：** 

## 软件工程的分析、设计、管理、工具

需求分析、系统设计、系统测试、系统运行维护、项目管理、质量、工具与开发环境

一个软件的生命周期中，其实开发阶段的重要性占比较小，主要是在需求分析与系统概要详细设计上得花大部分精力，它们才是主导产品的重要过程，当然每个阶段都必不可少

软件设计师主要的作用就是将需求转换为软件设计，将每个功能模块设计出来，再细化，最终在编码阶段实施

软件过程模型(软件开发模型)：描述软件开发的全部活动，用不同方式描述软件开发生命周期(需求分析、设计、编码、测试、发布、运行、维护)

- 瀑布模型：就像瀑布一样，将软件开发生命周期一次性流完，这就导致一开始就得有完整且详细的需求文档结果开启后面的活动，而且后一个阶段必须等前一个阶段完成才能展开，这样容易延期，项目风险难以控制
- 增量模型：将瀑布分成多个瀑布，就是把软件的实现分成若干次，第一次实现可以实现，最后一个实现才是最终软件；这样看起来比瀑布模型好，但是也有风险，就是前期的项目管理得一个很有经验的项目经理把控整个流程，管理的成本过大，每一次软件实现都容易产生重新发布的风险
- 上面模型属于软件一次成型，但是商业软件实际上是最初就开发完成，但是后面不断的新需求和环境变化导致软件不得不出现迭代，这就是软件开发的演化模型(原型模型、螺旋模型)
- 原型模型：它的出现主要是为了软件迭代，开发初期的需求说明不完整，后面会不断的补充且经常变化，使产品一边使用一边功能完善
- 螺旋模型：适用于复杂大型软件，将瀑布和演化模型结合起来不断螺旋发展，并在其中加入风险分析



测试策略：

- 单元测试：模块测试，完成一个模块后对这个模块的各方面进行测试，比如模块接口上数据的流入流出是否正常；局部值是否使用正确；模块的执行路径是否会产生问题；对有可能出错的地方是否进行预处理；
- 集成测试：测试所有模块一起工作是否会出现问题，模块之间的数据流是否出现丢失、积累问题；其中自顶向下集成测试是从主模块开始测试，直达全部模块测试结束；自底向上集成测试
- 确认测试：
- 系统测试：

## 面向对象的分析设计、UML、设计模式

## 算法

数据的处理方法即思想

## 数据库

基础、SQL、事务

## 网络与信息安全

## 软件的标准与产权

## 软件分析设计

结构化分析与设计、面向对象的分析与设计、数据库的分析与设计、算法的分析与设计