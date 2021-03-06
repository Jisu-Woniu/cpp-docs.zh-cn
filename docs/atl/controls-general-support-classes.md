---
title: ATL 控件：常规支持类
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- controls [ATL]
- general support classes
ms.assetid: cf73f1d2-7542-48e3-b8c8-9d3abf29f85b
ms.openlocfilehash: 3f00348ab0c9f25bdd4f6b7a2b05cd4b82ea48e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262809"
---
# <a name="controls-general-support-classes"></a>控件:常规支持类

以下类的 ATL 控件提供常规支持：

- [CComControl](../atl/reference/ccomcontrol-class.md)对 ATL 控件非常重要的帮助器函数和数据成员组成。

- [IOleControlImpl](../atl/reference/iolecontrolimpl-class.md)提供所需控件的方法。

- [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md)为通过该容器进行通信的主要方法提供了一个控件。 管理激活和停用的就地控件。

- [IQuickActivateImpl](../atl/reference/iquickactivateimpl-class.md)将合并到一个调用，以帮助避免延迟加载控件时的容器的初始化。

- [IPointerInactiveImpl](../atl/reference/ipointerinactiveimpl-class.md)提供最少的鼠标交互，否则为处于非活动状态的控件。

## <a name="sample-program"></a>示例程序

[ATLFire](../overview/visual-cpp-samples.md)

## <a name="related-articles"></a>相关文章

[ATL 教程](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>请参阅

[类概述](../atl/atl-class-overview.md)
