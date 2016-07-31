# DC/OS概念

DC/OS是Data Center Operation System的缩写，首次出现自2011年Matei Zaharia等的论文《[The Datacenter Needs an Operating System](http://dl.acm.org/citation.cfm?id=2170461)》，灵感也许来自于2009年Google的一篇文章《The Datacenter as a Computer》（2011年出了[第二版](http://web.eecs.umich.edu/~mosharaf/Readings/DC-Computer.pdf)），其目的是让用户就像使用一个现代操作系统来管理单个计算机一样，将数据中心抽象为逻辑上的一台计算机，屏蔽掉底层的细节，并提供一个友好的界面供管理和使用。

> By datacenter OS, we mean a software stack providing functionality for the overall datacenter that is analogous to what a traditional OS provides on one machine. We are not calling for a new host OS to be run in datacenters, though such a change may also prove beneficial.

以前的简称为DCOS，后来为了防止被读作[di'k^s]，在中间加了一个斜线。
## DC/OS的功能

既然叫OS，那功能和我们熟悉的单机OS应该非常类似。因此我们从通用操作系统的功能出发，对DC/OS得出要求：

资源管理
调度管理
任务管理
安全管理
存储管理(文件系统)
系统监控

## DC/OS的架构
### 系统层
这里的系统层是一套与服务器本地系统进行交互的程序，同于将独立的不同服务器所拥有的本地资源抽象统一为通用的、可供其他DC/OS进行管理的接口，并将DC/OS下达的管理指令翻译为本地的实现。

其实现的一种方式是重新编写或改写一个特有的本地操作系统，根据DC/OS要求进行裁剪和深度定制，但这个在与底层兼容性、本地管理性和通用性；另外一种更通用更常见的方式是一个驻留的守护进程和与本地环境相关的调用库，实现完全使用现有的第三方操作系统。

资源抽象的难点在于既要保证资源的标准化和通用性，又不要损失其独特性。如位置信息、有某种特殊硬件等，基于attribute或者tag的方式进行简单Key-Value键值记录，具体管理和使用由操作员和应用来维护和实现。
### 平台层要求
这是DC/OS最为
### 应用层要求



## DC/OS与普通单机OS的区别
相对于单机的OS（也称Host OS），无论是桌面版或者是服务器版，DC/OS都有显著的区别。首先，在定位上，DC/OS通常是一组分布式的软件，运行在每台服务器本地的操作系统之上，
此次，在功能定位上，DC/OS更加关注一下的能力指标：
### 可扩展性
### 并发度
### 异构环境兼容度
异构包括了
* 硬件
* 底层软件：操作系统
* 上层应用：与传统单机用于指定用途不同，数据中心通常承载着各式各样的服务和应用，有的对延时要求高，有的对吞吐要求高。导致通用数据中心平台软件的实现很难为某种应用场景进行特地特别优化。

### 错误容忍度
### 无宕机运维能力




## DC/OS与Cloud OS的区别
DC/OS与Cloudera OS的区别更多的在功能要求一节中提到的系统层。这里，“Data Center”更多注重的是主流服务器（commodity server）的管理，而“Cloud”底层会关注如何将不同的硬件虚拟化成标准或定制的服务器。

另外的是Cloud更多关心的是计算的弹性，能“无限”的动态增加和减少资源，

devops

