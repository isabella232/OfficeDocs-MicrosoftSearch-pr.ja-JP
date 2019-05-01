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
description: Windows 10 ユーザーに対して Microsoft Search と Office 365 にサインインを求めるメッセージが表示される回数を減らします
ms.openlocfilehash: 55d359edac36020ec8cf2aad6b64ca9737ee1066
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508931"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="efe93-103">シングル サインオンのテスト</span><span class="sxs-lookup"><span data-stu-id="efe93-103">Test single sign-on</span></span>

<span data-ttu-id="efe93-p101">シングル サインオンによって、サインインを求めるメッセージがユーザーに表示される回数を減らします。少人数のユーザー グループでシングル サインオンをテストすると、構成を妨げている問題を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="efe93-p101">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="efe93-106">Windows 10 における Chrome ユーザーの場合、シングル サインオンが機能するのは、Chrome 向けの Windows 10 と AAD サインイン拡張機能がインストールされている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="efe93-106">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="efe93-107">Chrome 向けの Windows 10 と AAD サインイン拡張機能をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="efe93-107">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="efe93-108">この拡張機能を自動インストールするためのグループ ポリシーを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="efe93-108">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="efe93-109">Microsoft Search 管理ポータルに移動します</span><span class="sxs-lookup"><span data-stu-id="efe93-109">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="efe93-110">ナビゲーション ウィンドウで、**[ツール]** をクリックします</span><span class="sxs-lookup"><span data-stu-id="efe93-110">In the navigation pane, click **Tools**</span></span>
    
3. <span data-ttu-id="efe93-111">ツールの一覧で、**[Chrome 向けの Windows 10 と AAD サインイン拡張機能]** をダウンロードします</span><span class="sxs-lookup"><span data-stu-id="efe93-111">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="efe93-112">Windows 10 の Chrome ユーザーと拡張機能を共有します</span><span class="sxs-lookup"><span data-stu-id="efe93-112">Share the extension with Chrome users on Windows 10</span></span>

  

