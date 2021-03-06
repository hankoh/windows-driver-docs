---
title: KsStreamPointerClone rule ()
description: The KsStreamPointerClone rule specifies that a kernel-stream (KS) miniport driver correctly uses the KsStreamPointerClone and KsStreamPointerDelete functions.
ms.assetid: 5ECF0070-0E36-4A91-B9FA-AA0DB7636B0E
ms.author: windowsdriverdev
ms.date: 5/21/2018
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
keywords: ["KsStreamPointerClone rule ()"]
topic_type:
- apiref
api_name:
- KsStreamPointerClone
api_type:
- NA
---

# KsStreamPointerClone rule ()


The KsStreamPointerClone rule specifies that a kernel-stream (KS) miniport driver correctly uses the [**KsStreamPointerClone**](https://msdn.microsoft.com/library/windows/hardware/ff567129) and [**KsStreamPointerDelete**](https://msdn.microsoft.com/library/windows/hardware/ff567130) functions.

|              |     |
|--------------|-----|
| Driver model | KS  |

|                                   |                                                                                                                                       |
|-----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Bug check(s) found with this rule | [**Bug Check 0xC4: DRIVER\_VERIFIER\_DETECTED\_VIOLATION**](https://msdn.microsoft.com/library/windows/hardware/ff560187) (0x00081002) |

How to test
-----------

<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">At run time</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>To verify this rule, open a Command Prompt window. Enter a Driver Verifier command and specify <strong>/domain ks</strong>.</p>
<p>For example:</p>
<p><strong>verifier /domain ks</strong> [<em>options</em>] <strong>/driver</strong> <em>&lt;yourdriver&gt;</em></p>
<p>For more information, see [Driver Verifier](https://msdn.microsoft.com/library/windows/hardware/ff545448).</p></td>
</tr>
</tbody>
</table>

 

 

 





