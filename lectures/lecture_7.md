# 第7讲 COM 原理与技术

refs:

- [Component Object Model](https://learn.microsoft.com/en-us/windows/win32/com/component-object-model--com--portal)
- <https://learn.microsoft.com/en-us/windows/win32/com/the-component-object-model>
- [COM+ Programming Overview](https://learn.microsoft.com/en-us/windows/win32/cossdk/com--programming-overview)


**********************************


## 目录 <span id="index"> </span>

7.1  [COM 原理与技术简介](#introduction) \
7.2  [COM 创建与调用实例](#creation) \
7.3  [COM 技术与 OFFICE 对象](#office) \
7.4  [COM 技术操作 WORD 对象](#word) \
7.5  [COM 技术操作 EXCEL 对象](#excel) \
7.6  [相关技术发展及变迁](#history) 


## 7.1 COM 原理与技术简介 <span id="introduction"></span>

COM (Common Object Model) 被国际标准化组织称为公共对象模型，微软官方则称之为组件对象模型(Component Object Model)
COM 亦是关于如何建立组件以及如何通过组件建立应用程序的一个规范，说明了如何可动态交替更新组件。

COM is a platform-independent, distributed, object-oriented system for creating binary 
software components that can interact. COM is the foundation technology for Microsoft's 
OLE (compound documents) and ActiveX (Internet-enabled components) technologies.

开发人员开始将单个的应用程序分隔成单独多个独立的部分，也即组件。
这种做法的好处是可以随着技术的不断发展而用新的组件取代已有的组件。
此时的应用程序可以随新组件不断取代旧的组件而渐趋完善。
而且利用已有的组件，用户还可以快速的建立全新的应用。

传统的做法是将应用程序分割成文件，模块或类，然后将它们编译并链接成一个单模应用程序。
它与组件建立应用程序的过程（称为组件构架）有很大的不同。
一个组件同一个微型应用程序类似，即都是已经编译链接好并可以使用的二进制代码，应用程序就是由多个这样的组件打包而得到的。
单模应用程序只有一个二进制代码模块。自定义组件则可以在运行时刻同其他的组件连接起来以构成某个应用程序。
在需要对应用程序进行修改或改进时，只需要将构成此应用程序的组件中的某个用新的版本替换掉即可。

COM objects can be created with a variety of programming languages. Object-oriented 
languages, such as C++, provide programming mechanisms that simplify the implementation 
of COM objects. These objects can be within a single process, in other processes, even 
on remote computers.

历史知识：
COM is dead, Long live COM. CoderGears Team, November 30, 2014. https://javadepend.com/Blog/?p=950

Object Linking and Embedding


[返回到目录](#index)


## 7.2 COM 创建与调用实例 <span id="creation"></span>



[返回到目录](#index)


## 7.3 COM 技术与 OFFICE 对象 <span id="office"></span>



[返回到目录](#index)


## 7.4 COM 技术操作 WORD 对象 <span id="word"></span>



[返回到目录](#index)


## 7.5 COM 技术操作 EXCEL 对象 <span id="excel"></span>



[返回到目录](#index)


## 7.6 相关技术发展及变迁 <span id="history"></span>

- [Communication in a microservice architecture](https://learn.microsoft.com/en-us/dotnet/architecture/microservices/architect-microservice-container-applications/communication-in-microservice-architecture)
- [Microservices and the First Law of Distributed Objects](https://martinfowler.com/articles/distributed-objects-microservices.html)
- [Difference between COM and DCOM](https://www.geeksforgeeks.org/difference-between-com-and-dcom/)
- <https://learn.microsoft.com/en-us/archive/msdn-magazine/2002/february/advanced-basics-com-and-mts-dcom-and-msmq-serialization-in-net>
- <https://learn.microsoft.com/en-us/windows/win32/midl/com-dcom-and-type-libraries>
- [Top 10 Microservices Design Principles](https://www.developer.com/design/microservices-design-principles/)
- [What is SOA? Service-Oriented Architecture Principles](https://www.guru99.com/soa-principles.html)
- <https://www.goland.org/soarpcencoded/>
- <https://blog.katastros.com/a?ID=01000-3a26435f-7537-4ba2-bba2-9ab2ff16ab61>
- <https://www.ibm.com/cloud/blog/soa-vs-microservices>
- [踢开绊脚石：微服务难点之服务调用的解决方案](https://www.ydisp.cn/server/116052.html)
- [微服务架构概念](https://www.likecs.com/show-203367714.html)
- <http://www.3qphp.com/java/framework/3633.html>
- <https://www.csdn.net/tags/MtjaMg5sNDQ4OTMtYmxvZwO0O0OO0O0O.html>
- <https://www.zhangshilong.cn/work/35636.html>
- <https://www.csdn.net/tags/Mtzakg3sMzEyNDUtYmxvZwO0O0OO0O0O.html>

*********************************

COM (Component Object Model) is Microsoft's component software architecture developed 
primarily for Windows. It is the foundation upon which OLE and ActiveX are based, and 
provides a means to re-use code without requiring re-compilation. In COM, a component 
is a platform-specific binary file that compliant applications and other components 
can utilize. Programs incorporating a component's services never have access to its 
internal data structure, but instead include pointers to its standardized interface. 
Thus, it is possible for components to interact with each other regardless of how they 
work or what language they are written in.

COM+ is an enhanced version of COM that provides better security and improved 
performance. DCOM (Distributed Component Object Model) is an extension of COM that 
allows applications and components to communicate with each other over a network.


### 7.6.1 Difference between COM and DCOM

DCOM is the acronym for the Distributed Component Object Model, an extension of the 
Component Object Model (COM). DCOM was introduced in 1996 and is designed for use 
across multiple network transports, including Internet protocols such as HTTP. DCOM 
is based on the Open Software Foundation's DCE-RPC spec and will work with both Java 
applets and ActiveX components through its use of the Component Object Model (COM). 
It works primarily with Microsoft Windows.


1. Component Object Model (COM) : 
Component object model was introduced by Microsoft in the year 1993. It is an 
interface standard designed for software components. It helps for the inter process 
communication irrespective of the programming language to be used. COM is termed as 
a software architecture that allows systems to be built from the different software 
vendors. It is also called as a set of binary standards which helps in the creation 
of a dynamic object. COM can also be termed as the standard for the effective 
communication between the components. 

The benefits of using COM are it can be used with any programming language which is 
capable of creating objects and pointer. 

2. Distributed Component Object Model (DCOM) : 
The distributed component object model is specifically designed for distributed 
applications. Before DCOM was known as “Network OLE”. The applications designed with 
COM was not able to serve the need of distributed computing as a result DCOM came 
into the picture. This supports the need in which the component needs to communicate 
across networked supported computers. 

The benefits of using are it provides distributed computing, it has a distributed 
garbage collector that enhances the CPU utilization. 


[返回到目录](#index)
