## 需要预先准备的环境
- Windbg调试环境
- .NET版本：4.5.2+

## 教学大纲
- .Net垃圾回收性能调优
	- .Net GC原理介绍
	- GC Server Mode和Workstation Mode的区别及适用场景
	- Windbg+Demo，呈现基本的GC Debug步骤
	- RealCase1-GCHeap内存泄露问题排查
	- RealCase2-GC过频导致CPU冲高问题排查
- WCF的DTC分布式事务的介绍
	- DTC原理和应用场景
	- Demo：WCF中应如何使用DTC
	- Demo：WCF中DTC问题的Debug步骤
- STA,MTA线程之间的区别，使用场景？
	- STA/MTA的原理
	- Demo：STA/MTA的应用场景
	- RealCase-1：STA/MTA在真实场景中遇到的问题
- UI线程内部消息循环与Dispatcher.BeginInvoke调用原理
	- .NET消息机制的原理
	- Demo：Windbg呈现消息机制的运作过程
	- RealCase：WinForm偶发性Hang住问题