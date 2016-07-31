# Mesos与Yarn的对比


## 总体对比

然而在长远来说都不是，并且我相信在通用的技术支持上，如网络和IO资源管理、容器支持、服务管理等功能上没有太大区别。

YARN的调度是一层资源管理，而Mesos的调度是二层资源管理，因此理论上YARN能提供全局最优的资源分配策略，资源利用率比Mesos高；而Mesos能比YARN的资源分配策略更加灵活。
YARN的调度是以数据为中心，而Mesos的调度是以资源为中心
就实现来讲，YARN对于Hadoop上的框架支持很好，但对于其他计算框架支持很少；而Mesos作为通用的框架，能灵活的支持第三方的各种框架。
## 具体
| 0:0 | 1:0 | 2:0 | 3:0 |
| -- | -- | -- | -- |
| 0:2 | 1:2 | 2:2 | 3:2 |

## Hadoop支持

### Spark
在整个Hadoop技术栈中，Spark的地位又比较特殊。它与Mesos同出生自Berkeley大学的AMP实验室，Matei Zaharia和Benjamin Hindman既是Spark项目也是Mesos项目的核心创始人，前者后来出去创办了DataBrick公司用于推广Spark技术，而后者作为创始人之一组建了Mesosphere公司，旨在提供基于Mesos技术的商业产品和服务。

Spark的第一个实现就是基于Mesos，后来才有YARN的实现。然而，2015年的[一项调查](http://cdn2.hubspot.net/hubfs/438089/DataBricks_Surveys_-_Content/Spark-Survey-2015-Infographic.pdf?t=1443116345933)显示实际运行在YARN上的Spark部署是Mesos的4倍。


## 未来的可能
### Mesos and YARN
### Mesos over YARN

现在还有很多技术上的

与无状态服务不同，Hadoop上应用很多是以数据为中心，不仅对于数据的访问效率有要求，而且有些还是有状态的。
数据位置
部署代价：
### YARN over Mesos
