---
title: ローカル ネットワーク ゲートウェイの IP アドレスのプレフィックスと VPN ゲートウェイの IP アドレスの変更 | Azure| CLI | Microsoft Docs
description: この記事では、Azure CLI を使用してローカル ネットワーク ゲートウェイの IP アドレスのプレフィックスを変更する手順について説明します。
services: vpn-gateway
documentationcenter: na
author: cherylmc
manager: timlt
editor: ''
tags: azure-resource-manager
ms.assetid: 8c7db48f-d09a-44e7-836f-1fb6930389df
ms.service: vpn-gateway
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: infrastructure-services
ms.date: 11/29/2017
ms.author: cherylmc
ms.openlocfilehash: a8f0c95acf872431fe7538acbd4ff1023c1496c0
ms.sourcegitcommit: 32d218f5bd74f1cd106f4248115985df631d0a8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2018
ms.locfileid: "46961231"
---
# <a name="modify-local-network-gateway-settings-using-the-azure-cli"></a>Azure CLI を使用したローカル ネットワーク ゲートウェイの設定の変更

ローカル ネットワーク ゲートウェイのアドレス プレフィックスまたはゲートウェイ IP アドレスの設定が変わることがあります。 この記事では、ローカル ネットワーク ゲートウェイの設定を変更する方法を説明します。 これらの設定は別の方法で変更することもできます。その場合は、次のボックスから別のオプションを選択してください。

> [!div class="op_single_selector"]
> * [Azure Portal](vpn-gateway-modify-local-network-gateway-portal.md)
> * [PowerShell](vpn-gateway-modify-local-network-gateway.md)
> * [Azure CLI](vpn-gateway-modify-local-network-gateway-cli.md)
>
>

## <a name="before"></a>開始する前に

最新バージョンの CLI コマンド (2.0 以降) をインストールします。 CLI コマンドのインストール方法については、「[Azure CLI 2.0 のインストール](https://docs.microsoft.com/cli/azure/install-azure-cli)」をご覧ください。

[!INCLUDE [CLI-login](../../includes/vpn-gateway-cli-login-include.md)]

## <a name="ipaddprefix"></a>IP アドレスのプレフィックスを変更する

[!INCLUDE [modify-prefix](../../includes/vpn-gateway-modify-ip-prefix-cli-include.md)]

## <a name="gwip"></a>ゲートウェイの IP アドレスを変更する

[!INCLUDE [modify-gateway-IP](../../includes/vpn-gateway-modify-lng-gateway-ip-cli-include.md)]

## <a name="next-steps"></a>次の手順

ゲートウェイの接続を確認することができます。 「 [Verify a gateway connection (ゲートウェイの接続を確認する)](vpn-gateway-verify-connection-resource-manager.md)」を参照してください。

