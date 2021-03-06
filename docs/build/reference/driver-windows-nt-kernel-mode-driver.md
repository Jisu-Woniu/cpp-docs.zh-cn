---
title: /DRIVER（Windows NT 内核模式驱动程序）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.driver
- /driver
helpviewer_keywords:
- kernel mode driver
- -DRIVER linker option
- DRIVER linker option
- /DRIVER linker option
ms.assetid: aeee8e28-5d97-40f5-ba16-9f370fe8a1b8
ms.openlocfilehash: c935c20d6c1c009cff64d48e0c0122c8b91bbba3
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041154"
---
# <a name="driver-windows-nt-kernel-mode-driver"></a>/DRIVER（Windows NT 内核模式驱动程序）

>/DRIVER [： UPONLY |： WDM]

## <a name="remarks"></a>备注

使用 **/DRIVER** 链接器选项可生成 Windows NT 内核模式驱动程序。

**/DRIVER： UPONLY** 导致链接器将 **IMAGE_FILE_UP_SYSTEM_ONLY** 位添加到 output 标头中的特性，以指定它是一个单处理器 () 驱动程序。 操作系统将拒绝在多处理器 (MP) 系统上加载 UP 驱动程序。

**/DRIVER： WDM** 使链接器在可选标头的 DLLCHARACTERISTICS 字段中设置 **IMAGE_DLLCHARACTERISTICS_WDM_DRIVER** 位。

如果未指定 **/DRIVER** ，链接器不会设置这些位。

如果指定 **/DRIVER** ：

- **/FIXED： NO** 无效。 有关详细信息，请参阅 [/FIXED (固定基址) ](fixed-fixed-base-address.md)。

- 输出文件的扩展名设置为 .sys。 使用 **/out** 更改默认文件名和扩展名。 有关详细信息，请参阅 [/out (输出文件名) ](out-output-file-name.md)。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹****。

1. 单击 " **系统** " 属性页。

1. 修改 **Driver** 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 [VCLinkerTool 属性](/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.driver)。

## <a name="see-also"></a>另请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
