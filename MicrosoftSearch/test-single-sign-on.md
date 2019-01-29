---
title: シングル サインオンのテスト
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: a220c1bf-7cee-448a-90a3-310284d03e81
description: Microsoft Search と Office 365 にサインインするのには、Windows の 10 人のユーザーが表示されたら、時間の数を減らす
ms.openlocfilehash: 55d359edac36020ec8cf2aad6b64ca9737ee1066
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612359"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="08801-103">シングル サインオンのテスト</span><span class="sxs-lookup"><span data-stu-id="08801-103">Test single sign-on</span></span>

<span data-ttu-id="08801-p101">シングル サインオンのユーザーがサインインするように求められます回数が減少します。シングル サインオンのユーザーの小さなグループでテストすると、ブロック構成に関する問題を識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="08801-p101">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="08801-106">Windows 10 には、クロムのユーザーのシングル サインオンが機能する、Windows 10 と AAD 符号拡張であるクロムがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="08801-106">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="08801-107">クロムの Windows 10 と AAD 符号の拡張機能をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="08801-107">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="08801-108">この拡張機能を自動的にインストールするのにはグループ ポリシーを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="08801-108">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="08801-109">Microsoft 検索の管理ポータルに移動します。</span><span class="sxs-lookup"><span data-stu-id="08801-109">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="08801-110">ナビゲーション ウィンドウで [**ツール**] をクリックします</span><span class="sxs-lookup"><span data-stu-id="08801-110">In the navigation pane, click **Tools**</span></span>
    
3. <span data-ttu-id="08801-111">ツールの一覧ダウンロード**Windows 10 とクロムのサインイン用の拡張子を AAD**</span><span class="sxs-lookup"><span data-stu-id="08801-111">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="08801-112">クロム 10 の Windows ユーザーと拡張機能を共有します。</span><span class="sxs-lookup"><span data-stu-id="08801-112">Share the extension with Chrome users on Windows 10</span></span>

  

