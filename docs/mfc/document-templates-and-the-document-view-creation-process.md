---
title: 文档模板和文档视图创建过程
ms.date: 11/19/2018
helpviewer_keywords:
- icons, for multiple document templates
- document templates [MFC], and views
- document/view architecture [MFC], creating document/view
- single document template
- MFC, document templates
- multiple document template
- CDocTemplate class [MFC]
- templates [MFC], document templates
ms.assetid: 311ce4cd-fbdf-4ea1-a51b-5bb043abbcee
ms.openlocfilehash: b96a11926927e89890ca268dcff7d347079b25fb
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615780"
---
# <a name="document-templates-and-the-documentview-creation-process"></a>文档模板和文档/视图创建过程

为了管理使用其关联的视图和框架窗口创建文档的复杂过程，框架使用了两个文档模板类：用于 SDI 应用程序的[CSingleDocTemplate](reference/csingledoctemplate-class.md)和用于 MDI 应用程序的[CMultiDocTemplate](reference/cmultidoctemplate-class.md) 。 `CSingleDocTemplate` 可以一次创建和存储一种类型的一个文档。 `CMultiDocTemplate` 保留一个类型的多个打开的文档的列表。

某些应用程序支持多种文档类型。 例如，一个应用程序可能支持文本文档和图形文档。 在此类应用程序中，当用户选择“文件”菜单上的“新建”命令时，一个对话框会显示可能要打开的新文档类型的列表。 对于每种受支持的文档类型，应用程序使用不同的文档模板对象。 下图阐释了支持两种文档类型和显示多个打开的文档的 MDI 应用程序的配置。

![具有两种文档类型的 MDI 应用程序](../mfc/media/vc387h1.gif "具有两种文档类型的 MDI 应用程序") <br/>
包含两个文档类型的 MDI 应用程序

文档模板由应用程序对象创建和维护。 在应用程序的 `InitInstance` 函数中执行的一个关键任务是构造一个或多个适当类型的文档模板。 此功能在[文档模板创建](document-template-creation.md)中进行了介绍。 应用程序对象存储指向其模板列表中的每个文件模板的指针，并提供一个用于添加文件模板的接口。

如果需要支持两种或多种文档类型，则必须为每个文档类型额外添加对[AddDocTemplate](reference/cwinapp-class.md#adddoctemplate)的调用。

根据文档模板在应用程序的文档模板列表中的位置，为每个文档模板注册一个图标。 文档模板的顺序由调用 `AddDocTemplate` 来添加它们的顺序决定。 MFC 假定应用程序中的第一个图标资源是应用程序图标，下一个图标资源是第一个文档图标，依此类推。

例如，文档模板是应用程序的三个图标资源中的第三个。 如果在应用程序中的索引 3 处有一个图标资源，则该图标用于文档模板。 否则，索引 0 处的图标则用作默认图标。

## <a name="see-also"></a>另请参阅

[常规 MFC 主题](general-mfc-topics.md)<br/>
[文档模板创建](document-template-creation.md)<br/>
[文档/视图创建](document-view-creation.md)<br/>
[MFC 对象之间的关系](relationships-among-mfc-objects.md)<br/>
[创建新文档、窗口和视图](creating-new-documents-windows-and-views.md)
