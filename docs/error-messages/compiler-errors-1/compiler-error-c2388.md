---
title: 编译器错误 C2388
ms.date: 11/04/2016
f1_keywords:
- C2388
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
ms.openlocfilehash: 50148f4fb5c3af33d8de8b005f75f491b0540271
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225496"
---
# <a name="compiler-error-c2388"></a>编译器错误 C2388

"symbol"：不能同时使用 __declspec （appdomain）和 \_ _declspec （进程）声明符号

`appdomain`和 `process` **`__declspec`** 修饰符不能用于相同的符号。 变量的存储空间按进程或按应用程序域存在。

有关详细信息，请参见 [应用程序域](../../cpp/appdomain.md) 和 [过程](../../cpp/process.md)。

以下示例生成 C2388：

```cpp
// C2388.cpp
// compile with: /clr /c
__declspec(process) __declspec(appdomain) int i;   // C2388
__declspec(appdomain) int i;   // OK
```
