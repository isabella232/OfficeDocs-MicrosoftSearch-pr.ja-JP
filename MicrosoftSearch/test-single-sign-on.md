---
title: シングル サインオンをテストします。
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: a220c1bf-7cee-448a-90a3-310284d03e81
description: Microsoft Search と Office 365 にサインインするのには、Windows の 10 人のユーザーが表示されたら、時間の数を減らす
ms.openlocfilehash: 4157707d58ead304449805c8fd16578690ac01a6
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2019
ms.locfileid: "29379097"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="4050e-103">シングル サインオンをテストします。</span><span class="sxs-lookup"><span data-stu-id="4050e-103">Test single sign-on</span></span>

<span data-ttu-id="4050e-p101">シングル サインオンのユーザーがサインインするように求められます回数が減少します。シングル サインオンのユーザーの小さなグループでテストすると、ブロック構成に関する問題を識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4050e-p101">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="4050e-106">Windows 10 には、クロムのユーザーのシングル サインオンが機能する、Windows 10 と AAD 符号拡張であるクロムがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="4050e-106">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="4050e-107">クロムの Windows 10 と AAD 符号の拡張機能をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="4050e-107">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="4050e-108">この拡張機能を自動的にインストールするのにはグループ ポリシーを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4050e-108">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="4050e-109">Microsoft 検索の管理ポータルに移動します。</span><span class="sxs-lookup"><span data-stu-id="4050e-109">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="4050e-110">ナビゲーション ウィンドウで [**ツール**] をクリックします</span><span class="sxs-lookup"><span data-stu-id="4050e-110">In the navigation pane, click **Tools**</span></span>
    
3. <span data-ttu-id="4050e-111">ツールの一覧ダウンロード**Windows 10 とクロムのサインイン用の拡張子を AAD**</span><span class="sxs-lookup"><span data-stu-id="4050e-111">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="4050e-112">クロム 10 の Windows ユーザーと拡張機能を共有します。</span><span class="sxs-lookup"><span data-stu-id="4050e-112">Share the extension with Chrome users on Windows 10</span></span>

  

