---
title: 目录控制
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], directory
- directory control routines
ms.assetid: a72dcf6f-f366-4d20-8850-0e19cc53ca18
ms.openlocfilehash: 640ce8a8665936b604c6e8e6270e358a200c880a
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438533"
---
# <a name="directory-control"></a>目录控制

这些例程可访问、修改和获取目录结构的相关信息。

## <a name="directory-control-routines"></a>目录控制例程

|例程|使用|
|-------------|---------|
|[_chdir、_wchdir](../c-runtime-library/reference/chdir-wchdir.md)|更改当前工作目录|
|[_chdrive](../c-runtime-library/reference/chdrive.md)|更改当前驱动器|
|[_getcwd、_wgetcwd](../c-runtime-library/reference/getcwd-wgetcwd.md)|获取默认驱动器的当前工作目录|
|[_getdcwd、_wgetdcwd](../c-runtime-library/reference/getdcwd-wgetdcwd.md)|获取指定驱动器的当前工作目录|
|[_getdiskfree](../c-runtime-library/reference/getdiskfree.md)|使用磁盘驱动器的相关信息填充 _diskfree_t 结构。|
|[_getdrive](../c-runtime-library/reference/getdrive.md)|获取当前（默认）驱动器|
|[_getdrives](../c-runtime-library/reference/getdrives.md)|返回一个表示当前可用磁盘驱动器的位掩码。|
|[_mkdir、_wmkdir](../c-runtime-library/reference/mkdir-wmkdir.md)|创建新目录|
|[_rmdir、_wrmdir](../c-runtime-library/reference/rmdir-wrmdir.md)|移除目录|
|[_searchenv、_wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md)、[_searchenv_s、_wsearchenv_s](../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)|在指定路径中搜索给定的文件|

## <a name="see-also"></a>另请参阅

[按类别分的通用 C 运行时例程](../c-runtime-library/run-time-routines-by-category.md)<br/>
[文件处理](../c-runtime-library/file-handling.md)<br/>
[系统调用](../c-runtime-library/system-calls.md)<br/>
