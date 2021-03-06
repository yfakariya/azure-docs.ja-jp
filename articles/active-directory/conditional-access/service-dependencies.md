---
title: Azure Active Directory 条件付きアクセスのサービス依存関係の概要 | Microsoft Docs
description: Azure Active Directory の条件付きアクセスで条件を使用してポリシーをトリガーする方法について学習します。
services: active-directory
keywords: アプリへの条件付きアクセス, Azure AD での条件付きアクセス, 企業リソースへの安全なアクセス, 条件付きアクセス ポリシー
documentationcenter: ''
author: MicrosoftGuyJFlo
manager: daveba
editor: ''
ms.assetid: 8c1d978f-e80b-420e-853a-8bbddc4bcdad
ms.service: active-directory
ms.subservice: conditional-access
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: identity
ms.date: 03/18/2019
ms.author: joflore
ms.reviewer: calebb
ms.collection: M365-identity-device-management
ms.openlocfilehash: f727fc7133ebc9ee124e63253e8a266862b0d908
ms.sourcegitcommit: 6da4959d3a1ffcd8a781b709578668471ec6bf1b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "58522032"
---
# <a name="what-are-service-dependencies-in-azure-active-directory-conditional-access"></a>Azure Active Directory 条件付きアクセスのサービス依存関係の概要 


条件付きアクセス ポリシーを使用すると、Web サイトやサービスに対するアクセス要件を指定できます。 たとえば、アクセス要件に、Multi-Factor Authentication (MFA) または[マネージド デバイス](require-managed-devices.md)の要件を含めることができます。 


サイトまたはサービスに直接アクセスすると、通常、関連するポリシーの影響を簡単に確認できます。 たとえば、SharePoint Online 用の MFA を必要とするポリシーを構成すると、SharePoint Web ポータルにサインインするたびに MFA が適用されます。 ただし、他のクラウド アプリとの依存関係があるクラウド アプリがあるため、ポリシーの影響が常に簡単に確認できるとは限りません。 たとえば、Microsoft Teams は SharePoint オンラインを活用しています。 そのため、現在のシナリオで Microsoft Teams にアクセスすると、SharePoint MFA ポリシーの対象にもなります。   


## <a name="policy-enforcement"></a>ポリシーの適用 

サービス依存関係を構成している場合は、事前バインディングまたは遅延バインディングを使用してポリシーを適用できます。 

**事前バインディング ポリシー適用**では、ユーザーが呼び出し元のアプリにアクセスする前に依存サービス ポリシーを満たす必要があります。 たとえば、ユーザーが MS Teams にサインインする前に SharePoint ポリシーを満たす必要があります。 

**遅延バインディング ポリシー適用**は、ユーザーが呼び出し元アプリにサインインした後で行われます。 呼び出し元アプリがダウンストリーム サービスのトークンを要求するまで、適用が延期されます。 例としては、Planner にアクセスする MS Teams や SharePoint にアクセスする Office.com があります。 

次の図は、MS Teams のサービス依存関係を示しています。 実線矢印は事前バインディング適用を示し、Planner を指す破線矢印は遅延バインディング適用を示します。 



![MS Teams のサービス依存関係](./media/service-dependencies/01.png)



  

ベスト プラクティスとして、可能な場合には常に、関連するアプリおよびサービスに対して共通のポリシーを設定することをお勧めします。 一貫性のあるセキュリティ体制によって、最適なユーザー エクスペリエンスが実現します。 たとえば、業務のための Exchange Online、SharePoint Online、MS Teams、Skype に対して共通のポリシーを設定すると、ダウンストリーム サービスに適用されるさまざまなポリシーからのプロンプトが予期せずに生成される回数が大幅に減少します。 

次の表には、クライアント アプリが満たす必要があるその他のサービス依存関係を示します。  

| クライアント アプリ         | ダウン ストリーム サービス                          | 適用 |
| :--                 | :--                                         | ---         | 
| Azure Data Lake     | Microsoft Azure 管理 (ポータルおよび API) | 事前バインディング |
| Microsoft Classroom | Exchange                                    | 事前バインディング |
|                     | SharePoint                                  | 事前バインディング  |
| Microsoft Teams     | Exchange                                    | 事前バインディング |
|                     | MS Planner                                  | 遅延バインディング  |
|                     | SharePoint                                  | 事前バインディング |
|                     | Skype for Business Online                   | 事前バインディング |
| Office ポータル       | Exchange                                    | 遅延バインディング  |
|                     | SharePoint                                  | 遅延バインディング  |
| Outlook Groups      | Exchange                                    | 事前バインディング |
|                     | SharePoint                                  | 事前バインディング |
| PowerApps           | Microsoft Azure 管理 (ポータルおよび API) | 事前バインディング |
|                     | Windows Azure Active Directory              | 事前バインディング |
| Project             | Dynamics CRM                                | 事前バインディング |
| Skype for Business  | Exchange                                    | 事前バインディング |
| Visual Studio       | Microsoft Azure 管理 (ポータルおよび API) | 事前バインディング |



## <a name="next-steps"></a>次の手順

お使いの環境に条件付きアクセスを実装する方法については、「[Azure Active Directory の条件付きアクセスの展開を計画する](plan-conditional-access.md)」をご覧ください。
