---
title: sinh、sinhf、sinhl
description: 用于计算浮点值的双曲正弦值的 API 参考。
ms.date: 08/31/2020
api_name:
- sinh
- sinhl
- sinhf
- sinhl
- _o_sinh
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- sinh
- sinhf
- sinhl
helpviewer_keywords:
- sinh function
- sinhl function
- sinhf function
- calculating hyperbolic sines
- trigonometric functions
- sinhf function
- sinhl function
- hyperbolic functions
ms.openlocfilehash: 6a8c9c4195eab66a46230e7a3baf6194e17c4519
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556172"
---
# <a name="sinh-sinhf-sinhl"></a>sinh、sinhf、sinhl

计算双曲正弦值。

## <a name="syntax"></a>语法

```C
double sinh(double x);
float sinhf(float x);
long double sinhl(long double x);
#define sinh(x) // Requires C11 or higher

float sinh(float x);  // C++ only
long double sinh(long double x);  // C++ only
```

### <a name="parameters"></a>参数

*x-blade*\
角度（以弧度为单位）。

## <a name="return-value"></a>返回值

**Sinh**函数返回*x*的双曲正弦值。 默认情况下，如果结果太大， **sinh** 会将 **Errno** 设置为 **ERANGE** 并返回±**HUGE_VAL**。

|输入|SEH 异常|Matherr 异常|
|-----------|-------------------|-----------------------|
|± QNAN，IND|无|_DOMAIN|
|&#124;x&#124; ≥ 7.104760 e + 002|溢出 + 不准确|OVERFLOW|

有关返回代码的详细信息，请参阅 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此可以调用 **sinh** 的重载，该重载采用和返回 **`float`** 或 **`long double`** 值。 在 C 程序中，除非使用 \<tgmath.h> 宏来调用此函数，否则 **sinh** 始终采用并返回 **`double`** 。

如果使用 \<tgmath.h> `sinh()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头 (C)|必需的标头 (C++)|
|-|-|-|
|**sinh**、 **sinhf**、 **sinhl**|\<math.h>|\<cmath> 或 \<math.h>|
|**sinh ( # B1 ** 宏 | \<tgmath.h> ||

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_sinhcosh.c
// This program displays the hyperbolic
// sine and hyperbolic cosine of pi / 2.
// Compile by using: cl /W4 crt_sinhcosh.c

#include <math.h>
#include <stdio.h>

int main( void)
{
   double pi = 3.1415926535;
   double x, y;

   x = pi / 2;
   y = sinh( x );
   printf( "sinh( %f ) = %f\n",x, y );
   y = cosh( x );
   printf( "cosh( %f ) = %f\n",x, y );
}
```

```Output
sinh( 1.570796 ) = 2.301299
cosh( 1.570796 ) = 2.509178
```

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)<br/>
[acosh、acoshf、acoshl](acosh-acoshf-acoshl.md)<br/>
[asinh、asinhf、asinhl](asinh-asinhf-asinhl.md)<br/>
[atanh、atanhf、atanhl](atanh-atanhf-atanhl.md)<br/>
[cosh、coshf、coshl](cosh-coshf-coshl.md)<br/>
[tanh、tanhf、tanhl](tanh-tanhf-tanhl.md)<br/>
