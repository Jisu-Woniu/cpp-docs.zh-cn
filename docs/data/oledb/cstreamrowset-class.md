---
title: CStreamRowset 类
ms.date: 11/04/2016
f1_keywords:
- ATL::CStreamRowset<TAccessor>
- ATL::CStreamRowset
- CStreamRowset
- ATL.CStreamRowset<TAccessor>
- ATL.CStreamRowset
- CStreamRowset::CStreamRowset
- CStreamRowset.CStreamRowset
- ATL.CStreamRowset.CStreamRowset
- ATL::CStreamRowset::CStreamRowset
- CStreamRowset<TAccessor>::CStreamRowset
- ATL::CStreamRowset<TAccessor>::CStreamRowset
- CStreamRowset<TAccessor>.Close
- ATL.CStreamRowset<TAccessor>.Close
- CStreamRowset::Close
- CStreamRowset<TAccessor>::Close
- ATL::CStreamRowset::Close
- ATL.CStreamRowset.Close
- ATL::CStreamRowset<TAccessor>::Close
- CStreamRowset.Close
helpviewer_keywords:
- CStreamRowset class
- CStreamRowset class, constructor
- Close method
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
ms.openlocfilehash: 304dfe0e026a9fbba899c1ef17c06cf1baf1529b
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841046"
---
# <a name="cstreamrowset-class"></a>CStreamRowset 类

在 `CCommand` 或声明中使用 `CTable` 。

## <a name="syntax"></a>语法

```cpp
template <class TAccessor = CAccessorBase>
class CStreamRowset
```

### <a name="parameters"></a>参数

*TAccessor*<br/>
一个访问器类。

## <a name="requirements"></a>要求

**标头:** atldbcli.h

## <a name="members"></a>成员

### <a name="methods"></a>方法

| 名称 | 说明 |
|-|-|
|[CStreamRowset](#cstreamrowset)|构造函数。 实例化并初始化 `CStreamRowset` 对象。|
|[关闭](#close)|释放类中的 [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) 接口指针。|

## <a name="remarks"></a>注解

`CStreamRowset`在 `CCommand` 或声明中使用 `CTable` ，例如：

[!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]

或

[!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]

`ICommand::Execute` 返回 `ISequentialStream` 存储在中的指针 `m_spStream` 。 然后，使用 `Read` 方法检索 XML 格式的 (Unicode 字符串) 数据。 例如：

[!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]

SQL Server 2000 执行 XML 格式设置，并将行集的所有列和所有行作为一个 XML 字符串返回。

> [!NOTE]
> 此功能仅适用于 SQL Server 2000。

## <a name="cstreamrowsetcstreamrowset"></a><a name="cstreamrowset"></a> CStreamRowset：： CStreamRowset

实例化并初始化 `CStreamRowset` 对象。

### <a name="syntax"></a>语法

```cpp
CStreamRowset();
```

## <a name="cstreamrowsetclose"></a><a name="close"></a> CStreamRowset：： Close

释放类中的 [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) 接口指针。

### <a name="syntax"></a>语法

```cpp
void Close();
```

## <a name="see-also"></a>另请参阅

[OLE DB 使用者模板](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 使用者模板参考](../../data/oledb/ole-db-consumer-templates-reference.md)
