---
title: Platform::Exception 类
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception::Exception
- VCCORLIB/Platform::Exception::CreateException
- VCCORLIB/Platform::Exception::HResult
- VCCORLIB/Platform::Exception::Message
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: ca1d5a67-3a5a-48fe-8099-f9c38a2d2dce
ms.openlocfilehash: bfdd8b3df720073e6b4a19cdb5b34db23e659fd0
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90741964"
---
# <a name="platformexception-class"></a>Platform::Exception 类

表示在应用程序执行期间出现的错误。 自定义异常类不能从 `Platform::Exception`派生。 如果需要自定义异常，可以使用 `Platform::COMException` 并指定应用程序特定的 HRESULT。

## <a name="syntax"></a>语法

```cpp
public ref class Exception : Object,    IException,    IPrintable,    IEquatable
```

### <a name="members"></a>成员

`Exception` 类继承自 `Object` 类、 `IException`、 `IPrintable`和 `IEquatable` 接口。

`Exception` 还具有以下类型的成员。

### <a name="constructors"></a>构造函数

|成员|描述|
|------------|-----------------|
|[Exception：： Exception](#ctor)|初始化 `Exception` 类的新实例。|

### <a name="methods"></a>方法

`Exception`类 `Equals()` `Finalize()` `GetHashCode()` `GetType()` `MemberwiseClose()` `ToString()` 从[Platform：： Object 类](../cppcx/platform-object-class.md)继承、、、、和方法。 `Exception` 类还具有以下方法。

|成员|描述|
|------------|-----------------|
|[Exception：： CreateException](#createexception)|创建表示指定 HRESULT 值的异常。|

### <a name="properties"></a>属性

此异常类还具有以下属性。

|成员|描述|
|------------|-----------------|
|[Exception：： HResult](#hresult)|与异常相对应的 HRESULT。|
|[Exception：： Message](#message)|描述异常的消息。 此值是只读的，在构造 `Exception` 后不能修改。|

### <a name="requirements"></a>要求

**支持的最低客户端：** Windows 8

**支持的最低服务器：** Windows Server 2012

**命名空间：** Platform

**Metadata：** platform.string

## <a name="exceptioncreateexception-method"></a><a name="createexception"></a> Exception：： CreateException 方法

基于指定的 HRESULT 值创建 Platform::Exception^。

### <a name="syntax"></a>语法

```cpp
Exception^ CreateException(int32 hr);
Exception^ CreateException(int32 hr, Platform::String^ message);
```

### <a name="parameters"></a>参数

*小时*<br/>
调用 COM 方法时通常获取的 HRESULT 值。 如果该值为0（等于 S_OK），则此方法将引发 [Platform：： InvalidArgumentException](../cppcx/platform-invalidargumentexception-class.md) ，因为成功的 COM 方法不应引发异常。

*message*<br/>
描述错误的字符串。

### <a name="return-value"></a>返回值

表示错误 HRESULT 的异常。

### <a name="remarks"></a>备注

使用此方法可基于返回的 HRESULT（例如，调用 COM 接口方法时返回的 HRESULT）创建异常。 您可以使用带 String^ 参数的重载提供自定义消息。

强烈建议使用 CreateException 创建强类型的异常，而不是创建仅包含 HRESULT 的 [Platform：： COMException](../cppcx/platform-comexception-class.md) 。

## <a name="exceptionexception-constructor"></a><a name="ctor"></a> Exception：： Exception 构造函数

初始化 Exception 类的新实例。

### <a name="syntax"></a>语法

```cpp
Exception(int32 hresult);
Exception(int32 hresult, ::Platform::String^ message);
```

### <a name="parameters"></a>参数

*hresult*<br/>
由异常表示的错误 HRESULT。

*message*<br/>
用户指定的与异常相关联的消息，例如指导性文本。 一般情况下，您应该会希望使用第二个重载，以便就错误的发生方式和原因提供尽可能具体的描述性消息。

## <a name="exceptionhresult-property"></a><a name="hresult"></a> Exception：： HResult 属性

与异常相对应的 HRESULT。

### <a name="syntax"></a>语法

```cpp
public:
    property int HResult { int get(); }
```

### <a name="property-value"></a>属性值

HRESULT 值。

### <a name="remarks"></a>备注

大多数异常都以 COM 错误形式出现，这类错误会返回为 HRESULT 值。 C++/CX 会将这些值转换为 Platform::Exception^ 对象，此属性则存储原始错误代码的值。

## <a name="exceptionmessage-property"></a><a name="message"></a> Exception：： Message 属性

描述错误的消息。

### <a name="syntax"></a>语法

```cpp
public:property String^ Message;
```

### <a name="property-value"></a>属性值

对于 Windows 运行时中出现的异常，这是系统提供的错误描述。

### <a name="remarks"></a>备注

在 Windows 8 中，此属性是只读的，因为该版本的 Windows 运行时中的异常只在 HRESULT 上传输。 在 Windows 8.1 中，可跨 ABI 传输更加丰富的异常信息，你可以提供自定义消息，供其他组件以编程方式进行访问。 有关详细信息，请参阅 [异常 (c + +/cx) ](../cppcx/exceptions-c-cx.md)。

## <a name="see-also"></a>请参阅

[Platform 命名空间](../cppcx/platform-namespace-c-cx.md)
