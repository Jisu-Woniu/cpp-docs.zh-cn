---
title: 服务映射宏
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_SERVICE_MAP
- atlcom/ATL::END_SERVICE_MAP
- atlcom/ATL::SERVICE_ENTRY
- atlcom/ATL::SERVICE_ENTRY_CHAIN
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
ms.openlocfilehash: 1fa163098d89dd949c17ee7cd5e4ddc46cd2a091
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835202"
---
# <a name="service-map-macros"></a>服务映射宏

这些宏定义服务映射和条目。

|名称|说明|
|-|-|
|[BEGIN_SERVICE_MAP](#begin_service_map)|标记 ATL 服务映射的开头。|
|[END_SERVICE_MAP](#end_service_map)|标记 ATL 服务映射的结尾。|
|[SERVICE_ENTRY](#service_entry)|指示对象支持特定服务 ID。|
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|指示 [IServiceProviderImpl：： QueryService](#queryservice) 链接到指定的对象。|

## <a name="requirements"></a>要求

**标头：** atlcom。h

## <a name="begin_service_map"></a><a name="begin_service_map"></a> BEGIN_SERVICE_MAP

标记服务映射的开头。

```
BEGIN_SERVICE_MAP(theClass)
```

### <a name="parameters"></a>参数

*类*<br/>
中指定包含服务映射的类。

### <a name="remarks"></a>注解

使用服务映射在 COM 对象上实现服务提供程序功能。 首先，必须从 [IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md)派生类。 有两种类型的条目：

- [SERVICE_ENTRY](#service_entry)   指示 (SID) 支持指定的服务 ID。

- [SERVICE_ENTRY_CHAIN](#service_entry_chain)   指示 [IServiceProviderImpl：： QueryService](#queryservice) 链接到另一个指定的对象。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_COM#57](../../atl/codesnippet/cpp/service-map-macros_1.h)]

## <a name="end_service_map"></a><a name="end_service_map"></a> END_SERVICE_MAP

标记服务映射的结尾。

```
END_SERVICE_MAP()
```

### <a name="example"></a>示例

请参阅 [BEGIN_SERVICE_MAP](#begin_service_map)的示例。

## <a name="service_entry"></a><a name="service_entry"></a> SERVICE_ENTRY

指示对象支持 *SID*指定的服务 id。

```
SERVICE_ENTRY( SID )
```

### <a name="parameters"></a>参数

*SID*<br/>
服务 ID。

### <a name="example"></a>示例

请参阅 [BEGIN_SERVICE_MAP](#begin_service_map)的示例。

## <a name="service_entry_chain"></a><a name="service_entry_chain"></a> SERVICE_ENTRY_CHAIN

指示 [IServiceProviderImpl：： QueryService](#queryservice) 链接到 *punk*指定的对象。

```
SERVICE_ENTRY_CHAIN( punk )
```

### <a name="parameters"></a>参数

*punk*<br/>
指向要链接到的 **IUnknown** 接口的指针。

### <a name="example"></a>示例

请参阅 [BEGIN_SERVICE_MAP](#begin_service_map)的示例。

## <a name="iserviceproviderimplqueryservice"></a><a name="queryservice"></a> IServiceProviderImpl：： QueryService

创建或访问指定的服务，并将接口指针返回到服务的指定接口。

```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>参数

*guidService*<br/>
中指向服务标识符 (SID) 的指针。

*riid*<br/>
中调用方要获取访问权限的接口的标识符。

*ppvObj*<br/>
弄指向所请求接口的间接指针。

### <a name="return-value"></a>返回值

返回的 HRESULT 值为下列值之一：

|返回值|含义|
|------------------|-------------|
|S_OK|已成功创建或检索服务。|
|E_INVALIDARG|一个或多个自变量无效。|
|E_OUTOFMEMORY|内存不足，无法创建服务。|
|E_UNEXPECTED|出现未知错误。|
|E_NOINTERFACE|请求的接口不是此服务的一部分，或者该服务是未知的。|

### <a name="remarks"></a>注解

`QueryService` 返回指向指定服务中所请求的接口的间接指针。 调用方负责在不再需要此指针时释放它。

调用时 `QueryService` ，会将服务标识符 () 并 (*guidService* *riid*) 传递接口标识符。 *GuidService*指定要访问的服务， *riid*会标识属于该服务的接口。 返回时，会收到指向接口的间接指针。

实现接口的对象还可以实现属于其他服务的接口。 考虑以下情况：

- 其中一些接口可能是可选的。 并非服务说明中定义的所有接口都必须存在于服务的每个实现或每个返回的对象上。

- 不同于对的调用 `QueryInterface` ，传递不同的服务标识符并不一定意味着返回不同的组件对象模型 (COM) 对象。

- 返回的对象可能包含不是该服务定义的一部分的其他接口。

两种不同的服务（如 SID_SMyService 和 SID_SYourService）都可以指定同一接口的使用，即使接口的实现在这两个服务之间可能没有任何共性。 这可行，因为对 `QueryService` (SID_SMyService、IID_IDispatch) 的调用返回的对象不同于 (SID_SYourService IID_IDispatch) `QueryService` 。 指定不同的服务标识符时，不会假定对象标识。

## <a name="see-also"></a>另请参阅

[宏](../../atl/reference/atl-macros.md)
