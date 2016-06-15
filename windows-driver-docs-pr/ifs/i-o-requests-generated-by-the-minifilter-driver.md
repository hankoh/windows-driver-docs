---
title: I/O Requests Generated by the Minifilter Driver
author: windows-driver-content
description: I/O Requests Generated by the Minifilter Driver
ms.assetid: cf06dcb9-58e2-4341-8229-8f172f37c176
keywords: ["filter manager WDK file system minifilter , I/O requests generated by driver", "I/O requests WDK file system", "IRPs WDK file system"]
---

# I/O Requests Generated by the Minifilter Driver


A minifilter driver can generate and send IRP-based I/O requests from one of the minifilter driver's own instances on the current volume or on another volume. The generated I/O is seen only by the minifilter driver instances and legacy filter drivers attached below the specified instance, and by the file system. This solves many problems related to recursive I/O in the legacy filter driver model, in which I/O requests generated by a legacy filter driver must travel through the entire file system stack, starting with the topmost driver.

The filter manager doesn't unload a minifilter driver until all of its outstanding I/O operations are completed.

### <span id="Filter_Manager_Routines_for_I_O_Requests_Generated_by_the_Minifilter_Driver"></span><span id="filter_manager_routines_for_i_o_requests_generated_by_the_minifilter_driver"></span><span id="FILTER_MANAGER_ROUTINES_FOR_I_O_REQUESTS_GENERATED_BY_THE_MINIFILTER_DRIVER"></span>Filter Manager Routines for I/O Requests Generated by the Minifilter Driver

The filter manager provides the following support routines for creating, opening, reading, and writing files:

[**FltClose**](https://msdn.microsoft.com/library/windows/hardware/ff541863)

[**FltCreateFile**](https://msdn.microsoft.com/library/windows/hardware/ff541935)

[**FltCreateFileEx**](https://msdn.microsoft.com/library/windows/hardware/ff541937)

[**FltReadFile**](https://msdn.microsoft.com/library/windows/hardware/ff544286)

[**FltWriteFile**](https://msdn.microsoft.com/library/windows/hardware/ff544610)

The following support routines are provided for setting and removing reparse points:

[**FltTagFile**](https://msdn.microsoft.com/library/windows/hardware/ff544589)

[**FltUntagFile**](https://msdn.microsoft.com/library/windows/hardware/ff544608)

The following support routines are provided for generating I/O requests:

[*FltAllocateCallbackData*](https://msdn.microsoft.com/library/windows/hardware/ff541703)

[**FltFreeCallbackData**](https://msdn.microsoft.com/library/windows/hardware/ff542949)

[**FltPerformAsynchronousIo**](https://msdn.microsoft.com/library/windows/hardware/ff543420)

[*FltPerformSynchronousIo*](https://msdn.microsoft.com/library/windows/hardware/ff543421)

[**FltReuseCallbackData**](https://msdn.microsoft.com/library/windows/hardware/ff544358)

The following support routines are provided for canceling a file open request and for reissuing an I/O request:

[**FltCancelFileOpen**](https://msdn.microsoft.com/library/windows/hardware/ff541784)

[**FltReissueSynchronousIo**](https://msdn.microsoft.com/library/windows/hardware/ff544311)

The filter manager also provides the following general-purpose routines:

[**FltDeviceIoControlFile**](https://msdn.microsoft.com/library/windows/hardware/ff542046)

[**FltFlushBuffers**](https://msdn.microsoft.com/library/windows/hardware/ff542099)

[**FltFsControlFile**](https://msdn.microsoft.com/library/windows/hardware/ff542988)

[**FltQueryInformationFile**](https://msdn.microsoft.com/library/windows/hardware/ff543439)

[**FltQuerySecurityObject**](https://msdn.microsoft.com/library/windows/hardware/ff543441)

[**FltQueryVolumeInformationFile**](https://msdn.microsoft.com/library/windows/hardware/ff543446)

[**FltSetInformationFile**](https://msdn.microsoft.com/library/windows/hardware/ff544516)

[**FltSetSecurityObject**](https://msdn.microsoft.com/library/windows/hardware/ff544538)

 

 


--------------------
[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20[ifsk\ifsk]:%20I/O%20Requests%20Generated%20by%20the%20Minifilter%20Driver%20%20RELEASE:%20%285/9/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")

