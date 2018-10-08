## 需要预先准备的环境和可以预先了解的工具
- [Windbg调试环境](https://github.com/wu-wenxiang/Training-Debug-Windows/blob/master/doc/Debug-Environment.md)
- .NET版本：4.5.2+

## Demo资料
- 链接：[https://share.weiyun.com/5hHlmMZ](https://share.weiyun.com/5hHlmMZ)

## 内容安排
- .Net垃圾回收性能调优
	- [.Net GC原理介绍](https://docs.microsoft.com/en-us/dotnet/standard/garbage-collection/)
	- [GC Server Mode和Workstation Mode的区别及适用场景](https://blogs.msdn.microsoft.com/seteplia/2017/01/05/understanding-different-gc-modes-with-concurrency-visualizer/)
	- Windbg+Demo，呈现基本的GC Debug步骤
	- RealCase：GCHeap内存泄露问题排查
	- RealCase：GC过频导致CPU冲高问题排查
- WCF的DTC分布式事务的介绍
	- DTC原理和应用场景
		- [DTC Config Overview](https://docs.microsoft.com/en-us/previous-versions/windows/desktop/ms680182(v=vs.85))
		- [Windows MSDTC Setting](https://dotblogs.com.tw/echo/2017/08/24/windows_msdtc_setting)
		- [What is MSDTC and why do I need to care about it?](https://blogs.msdn.microsoft.com/florinlazar/2004/03/04/what-is-msdtc-and-why-do-i-need-to-care-about-it/)
	- 整理一些概念：
		- MSDTC is used by SQL Server and other applications when they want to make a **distributed transaction** between more than one machine.
		- A distributed transaction is simple a **transactions which spans between two or more machines**. The basic concept is that machine 1 starts a transaction, and does some work. It then connects to machine 2 and does some work. The work on machine 2 fails, and is cancled.  The work on machine 1 needs to then be rolled back.
		- DTC is for the most part a **black box**. It just sort of works without much interaction exept for the initial setup.
		- The only time that DTC needs to be used is when **more than one physical computer** is going to be involved in a distributed transaction. If you are going from one instance to another on the same server DTC will not be needed. If you are going from one instance to another within a cluster you will want to have DTC available as you may have to go between nodes of the cluster as you have no guarantee that the instances will be on the same physical node.
	- [Implementing an Implicit Transaction using Transaction Scope](https://docs.microsoft.com/en-us/dotnet/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope)
	- [Implementing an Explicit Transaction using CommittableTransaction](https://docs.microsoft.com/en-us/dotnet/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction)
	- [Transaction Promotion](https://docs.microsoft.com/en-us/sql/relational-databases/clr-integration-data-access-transactions/transaction-promotion?view=sql-server-2017)
	- [Demo：WCF中应如何使用DTC](https://docs.microsoft.com/en-us/dotnet/framework/wcf/samples/ws-transaction-flow)
	- Demo：WCF中DTC问题的Debug步骤
- STA,MTA线程之间的区别，使用场景？
	- STA/MTA的原理
		- [Understanding and Using COM Threading Models](https://msdn.microsoft.com/en-us/library/ms809971.aspx)
		- [What are these “Threading Models” and why do I care?](https://blogs.msdn.microsoft.com/larryosterman/2004/04/28/what-are-these-threading-models-and-why-do-i-care/)
	- Demo：STA/MTA的应用场景
	- RealCase：STA/MTA在真实场景中遇到的问题
- UI线程内部消息循环与Dispatcher.BeginInvoke调用原理
	- [.NET消息机制的原理](https://docs.microsoft.com/en-us/dotnet/framework/wpf/advanced/threading-model)
	- Demo：Windbg呈现消息机制的运作过程
	- RealCase：WinForm偶发性Hang住问题
