## 需要预先准备的环境和可以预先了解的工具
- Windbg调试环境
	- [安装](https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/debugger-download-tools)
	- [配置Symbol](https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/symbol-path)
	- Extension
		- [Mex](https://www.microsoft.com/en-us/download/details.aspx?id=53304)
		- [Pykd](https://github.com/wu-wenxiang/Tool-Windbg-Pykd-Scripts)
	- [入门文档](https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/getting-started-with-windbg)
	- [进阶文档](https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/debugging-using-windbg)
- 自动化Dump分析工具`DebugDiag`
	- [安装](https://www.microsoft.com/en-us/download/details.aspx?id=49924)
	- 使用方法（案例）
		- [How to use the Debug Diagnostics tool to troubleshoot a process that has stopped responding in IIS](https://support.microsoft.com/en-us/help/919792/how-to-use-the-debug-diagnostics-tool-to-troubleshoot-a-process-that-h)
		- [How to use the Debug Diagnostics Tool to troubleshoot high CPU usage by a process in IIS](https://support.microsoft.com/en-us/help/919791/how-to-use-the-debug-diagnostics-tool-to-troubleshoot-high-cpu-usage-b)
- Sysinternals工具集
	- [安装](https://docs.microsoft.com/en-us/sysinternals/downloads/sysinternals-suite)
	- [使用文档](https://docs.microsoft.com/en-us/sysinternals/learn/troubleshooting-book)
	- [功能简介](http://blog.wuwenxiang.net/Windows-Sysinternals)
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
		- [What is MSDTC and why do I need to care about it?](https://blogs.msdn.microsoft.com/florinlazar/2004/03/04/what-is-msdtc-and-why-do-i-need-to-care-about-it/)
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

## 时间安排
- 8/22上午
	- .NET GC原理介绍
	- Server Mode和Workstation Mode的区别及适用场景
	- .NET GC问题排查步骤
- 8/22下午
	- GCHeap内存泄露问题排查
	- GC过频导致CPU冲高问题排查
	- DTC原理和应用场景
	- WCF中应如何使用DTC
- 8/23上午
	- WCF中DTC问题的Debug步骤
	- STA/MTA的原理
	- STA/MTA的应用场景
- 8/23下午
	- STA/MTA在真实场景中遇到的问题
	- .NET消息机制的原理
	- Demo：Windbg呈现消息机制的运作过程
	- RealCase：WinForm偶发性Hang住问题