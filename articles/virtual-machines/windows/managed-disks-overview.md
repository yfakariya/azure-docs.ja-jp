---
title: Windows VM 向け Azure Disk Storage マネージド ディスクの概要 | Microsoft Docs
description: Azure Windows VM を使用するときにストレージ アカウントを管理する Azure マネージド ディスクの概要
services: virtual-machines-windows,storage
author: roygara
ms.service: virtual-machines-windows
ms.workload: storage
ms.tgt_pltfrm: vm-windows
ms.topic: article
ms.date: 02/11/2019
ms.author: rogarana
ms.subservice: disks
ms.openlocfilehash: 85b2dcb73024ce786b78436b7070ad2e9a96e1d4
ms.sourcegitcommit: d2329d88f5ecabbe3e6da8a820faba9b26cb8a02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2019
ms.locfileid: "56328472"
---
# <a name="introduction-to-azure-managed-disks"></a>Azure マネージド ディスクの概要

Azure マネージド ディスクは仮想ハード ディスク (VHD) です。 オンプレミス サーバーの物理ディスクと似ていますが、仮想化されたディスクと考えることができます。 Azure マネージド ディスクは、Azure のランダム IO ストレージ オブジェクトであるページ BLOB として格納されます。 マネージド ディスクを "マネージド" と呼ぶ理由は、ページ BLOB、BLOB コンテナー、および Azure ストレージ アカウントを抽象化したものであるためです。 マネージド ディスクでは、ディスクをプロビジョニングするだけで、後の管理は Azure が実行します。

ワークロードに Azure マネージド ディスクを使用することを選択した場合、Azure で自動的にディスクが作成され、管理されます。 使用できるディスクの種類は、Ultra ソリッド ステート ドライブ (SSD)、Premium SSD、Standard SSD、Standard ハード ディスク ドライブ (HDD) です。 各ディスクの種類の詳細については、[IaaS VM 用のディスクの種類の選択](disks-types.md)に関するページを参照してください。

[!INCLUDE [virtual-machines-managed-disks-overview.md](../../../includes/virtual-machines-managed-disks-overview.md)]

> [!div class="nextstepaction"]
> [IaaS VM 用のディスクの種類の選択](disks-types.md)