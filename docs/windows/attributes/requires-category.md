---
title: 'requires_category (c + + COM 特性) '
ms.date: 10/02/2018
f1_keywords:
- vc-attr.requires_category
helpviewer_keywords:
- requires_category attribute
ms.assetid: a645fdc6-1ef5-414d-8c56-5fe2686d4687
ms.openlocfilehash: d566e74a9019259e526fa27aec26500e9ef3e1c1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845999"
---
# <a name="requires_category"></a>requires_category

指定目标类的必需组件类别。

## <a name="syntax"></a>语法

```cpp
[ requires_category(
  requires_category) ]
```

### <a name="parameters"></a>参数

*requires_category*<br/>
所需类别的 ID。

## <a name="remarks"></a>注解

**Requires_category** c + + 特性指定目标类所需的组件类别。 有关详细信息，请参阅 [REQUIRED_CATEGORY](../../atl/reference/category-macros.md#required_category)。

此属性要求 [coclass](coclass.md)、 [progid](progid.md)或 [vi_progid](vi-progid.md) 属性（或隐含这些属性之一的其他属性）也应用于同一个元素。

## <a name="example"></a>示例

下面的代码要求对象实现控件类别。

```cpp
// cpp_attr_ref_requires_category.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="MyLibrary")];

[ coclass, requires_category("CATID_Control"),
  uuid("1e1a2436-f3ea-4ff3-80bf-5409370e8144")]
class CMyClass {};
```

## <a name="requirements"></a>要求

| 特性上下文 | 值 |
|-|-|
|**适用于**|**`class`**, **`struct`**|
|**且**|否|
|**必需属性**|以下一项或多项操作： `coclass` 、 `progid` 或 `vi_progid` 。|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[COM 特性](com-attributes.md)<br/>
[implements_category](implements-category.md)
