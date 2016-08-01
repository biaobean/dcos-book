# DC/OS概念

DC/OS是Data Center Operation System的缩写，首次出现自2011年Matei Zaharia等的论文《[The Datacenter Needs an Operating System](http://dl.acm.org/citation.cfm?id=2170461)》，

“Sixty-four cores or 128 cores on a single chip looks a lot like 64 machines or 128 machines in a data center”“We wanted people to be able to program for the data center just like they program for their laptop.”

灵感也许来自于2009年Google的一篇文章《The Datacenter as a Computer》（2011年出了[第二版](http://web.eecs.umich.edu/~mosharaf/Readings/DC-Computer.pdf)），IaaC Infrastructure as a computer 其目的是让用户就像使用一个现代操作系统来管理单个计算机一样，将数据中心抽象为逻辑上的一台计算机，屏蔽掉底层的细节，并提供一个友好的界面供管理和使用。

> By datacenter OS, we mean a software stack providing functionality for the overall datacenter that is analogous to what a traditional OS provides on one machine. We are not calling for a new host OS to be run in datacenters, though such a change may also prove beneficial.

以前的简称为DCOS，后来为了防止被读作[di'k^s]，在中间加了一个斜线。
## DC/OS的功能

既然叫OS，那功能和我们熟悉的单机OS应该非常类似。因此我们从通用操作系统的功能出发，对DC/OS提出要求。通常开源社区中很多不同组件都能实现部分集群功能，值得注意的是，**DC/OS不应该只是一堆组件的堆积和组合，也不应该只是文档描述的解决方案，而是集成各个功能组件以后，并在其之上屏蔽组件细节的整套一站式服务的管理软件。**

### 资源管理
资源管理包括
设备管理：现代计算机系统中都配备了许多设备，每台设备的性能和操作方式都不相同，操作系统设备管理的主要任务就是对CPU和内存以外的各种硬件资源进行有效地管理，为用户提供方便的操作，从而提高设备的利用率。 除此之外，操作系统还提供一些服务管理的功能，如提供系统设置、错误检测、网络连接等其他基本的系统功能，为使用者提供方便管理和使用计算机的工具。 

登记、分配、启动、完成和回收；

除此之外，DC/OS还提供一些服务管理的功能，对于资源有效性、配置和错误的监测，如网络连接，

### 任务管理
通常来说，任务的生命周期包括：资源分配->任务启动->资源再分配->任务监控->任务结束->资源回收这几个周期，
启动管理：
系统驻留
计划启动
用户提交
调度管理：将什么资源分配给什么任务让其在什么时间运行
任务监控
FailOver管理

接口管理
UI
CLI：通常作为运维和调试用。
API：要求编程接口尽量简单，屏蔽掉底层如何分布式。虽然这个很难，十年前C++界的大师级人物[Herb Sutter](https://herbsutter.com/about/)就发表了一篇文章《[并发软件的免费午餐结束了](http://www.gotw.ca/publications/concurrency-ddj.htm)》，如何到利用多core、多cpu、多server来进行不同层级的并发，又不将细节暴露给上层接口是一个难点。

服务管理
服务生命周期管理
服务发现
配置管理

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

> “Everything fails all the time.” —— Werner Vogels, CTO of Amazon



### 无宕机运维能力




## DC/OS与Cloud OS的区别
DC/OS与Cloudera OS的区别更多的在功能要求一节中提到的系统层。这里，“Data Center”更多注重的是主流服务器（commodity server）的管理，而“Cloud”底层会关注如何将不同的硬件虚拟化成标准或定制的服务器。

Opentstack独立的machine
Mesos独立的application


另外的是Cloud更多关心的是计算的弹性，能“无限”的动态增加和减少资源，

devops

