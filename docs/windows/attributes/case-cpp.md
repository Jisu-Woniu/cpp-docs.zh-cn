---
title: 'c + + COM 特性 (情况) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.case
helpviewer_keywords:
- case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
ms.openlocfilehash: e1d3c113c42be99a8475c5a667b7ea6ed9583d92
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838901"
---
# <a name="case-c"></a>case (C++)

与中的 [switch_type](switch-type.md) 特性一起使用 **`union`** 。

## <a name="syntax"></a>语法

```cpp
[ case(value) ]
```

#### <a name="parameters"></a>参数

*value*<br/>
要为其提供处理的可能输入值。 **值**的类型可以是以下类型之一：

- **`int`**

- **`char`**

- `boolean`

- **`enum`**

或此类类型的标识符。

## <a name="remarks"></a>注解

C **+ + 属性与** **case** MIDL 特性具有相同的功能。 此属性仅与 [switch_type](switch-type.md) 特性一起使用。

## <a name="example"></a>示例

以下代码显示了 **case** 属性的用法：

```cpp
// cpp_attr_ref_case.cpp
// compile with: /LD
#include <unknwn.h>
[export]
struct SizedValue2 {
   [switch_type(char), switch_is(kind)] union {
      [case(1), string]
          wchar_t* wval;
      [default, string]
          char* val;
   };
    char kind;
};
[module(name="ATLFIRELib")];
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|或的成员 **`class`****`struct`**|
|**且**|否|
|**必需属性**|无|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[IDL 特性](idl-attributes.md)<br/>
[Typedef、Enum、Union 和 Struct 特性](typedef-enum-union-and-struct-attributes.md)<br/>
[类特性](class-attributes.md)
