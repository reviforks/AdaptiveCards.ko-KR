---
title: 동작
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 42ba1ca4ba2ecd508bdee2f04061293d48349aab
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553375"
---
# <a name="actions"></a><span data-ttu-id="db7f0-102">동작</span><span class="sxs-lookup"><span data-stu-id="db7f0-102">Actions</span></span>

<span data-ttu-id="db7f0-103">기본적으로 카드에서 단추도 렌더링 됩니다. 작업 되지만 예상 대로 작동 되도록 할 앱에 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db7f0-103">By default, the actions will render as buttons on the card, but it's up to your app to make them behave as you expect.</span></span> <span data-ttu-id="db7f0-104">각 SDK에 해당 하는 `OnAction` 처리 해야 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="db7f0-104">Each SDK has the equivalent of an `OnAction` event that you must handle.</span></span>

* <span data-ttu-id="db7f0-105">**Action.OpenUrl** -지정 된 열 `url`합니다.</span><span class="sxs-lookup"><span data-stu-id="db7f0-105">**Action.OpenUrl** - open the specified `url`.</span></span>  
* <span data-ttu-id="db7f0-106">**Action.Submit** -제출 결과 및 원본에 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="db7f0-106">**Action.Submit** - take the result of the submit and send it to the source.</span></span> <span data-ttu-id="db7f0-107">전적으로 사용자가 어떻게 보내기 카드의 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="db7f0-107">How you send it to the source of the card is entirely up to you.</span></span>
* <span data-ttu-id="db7f0-108">**Action.ShowCard** -대화 상자를 호출 하 고 해당 대화 상자에 하위 카드를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="db7f0-108">**Action.ShowCard** - invokes a dialog and renders the sub-card into that dialog.</span></span> <span data-ttu-id="db7f0-109">참고만 할 경우이 처리할 `ShowCardActionMode` 로 설정 된 `popup`합니다.</span><span class="sxs-lookup"><span data-stu-id="db7f0-109">Note that you only need to handle this if `ShowCardActionMode` is set to `popup`.</span></span>