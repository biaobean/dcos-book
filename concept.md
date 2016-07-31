# DCOS概念

Data Center Operation System的概念首次出现自2011年Matei Zaharia等的论文《[The Datacenter Needs an Operating System](http://dl.acm.org/citation.cfm?id=2170461)》

> By datacenter OS, we mean a software stack providing functionality for the overall datacenter that is analogous to what a traditional OS provides on one machine. We are not calling for a new host OS to be run in datacenters, though such a change may also prove beneficial.

也许来源自2009年Google的一篇文章《The Datacenter as a Computer》（2011年出了[第二版](http://web.eecs.umich.edu/~mosharaf/Readings/DC-Computer.pdf)）。

## DC/OS的功能要求
## DC/OS与普通单机OS的区别
相对于单机的OS（也称Host OS），无论是桌面版或者是服务器版，DC/OS都有显著的区别。首先，在定位上，DC/OS通常是一组分布式的软件，运行在每台服务器本地的操作系统之上，
此次，在功能定位上，DC/OS更加关注一下的能力指标：
* 可扩展性
* 并发度
* 异构环境兼容度
这种异构包括了
硬件
底层软件：操作系统
上层应用：与传统单机用于指定用途不同，数据中心通常承载着各式各样的服务和应用，有的对延时要求高，有的对吞吐要求高。导致通用数据中心平台软件的实现很难为某种应用场景进行特地特别优化。
* 错误容忍度
* 无宕机运维能力




## DC/OS与Cloud OS的区别
Data Center更多注重的是主流服务器（commodity server）的管理，而Cloud底层会关注如何将不同的硬件虚拟化成标准或定制的服务器。

devops

