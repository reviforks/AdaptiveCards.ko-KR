---
title: 조치
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 42ba1ca4ba2ecd508bdee2f04061293d48349aab
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553375"
---
# <a name="actions"></a><span data-ttu-id="7ca7e-102">조치</span><span class="sxs-lookup"><span data-stu-id="7ca7e-102">Actions</span></span>

<span data-ttu-id="7ca7e-103">기본적으로 작업은 카드에 단추로 렌더링되지만 앱에서 사용자가 원하는 대로 작동하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ca7e-103">By default, the actions will render as buttons on the card, but it's up to your app to make them behave as you expect.</span></span> <span data-ttu-id="7ca7e-104">각 SDK에는 처리해야 하는 `OnAction` 이벤트에 해당하는 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ca7e-104">Each SDK has the equivalent of an `OnAction` event that you must handle.</span></span>

* <span data-ttu-id="7ca7e-105">**Action.OpenUrl** - 지정된 `url`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7ca7e-105">**Action.OpenUrl** - open the specified `url`.</span></span>  
* <span data-ttu-id="7ca7e-106">**Action.Submit** - 제출 결과를 가져오고 원본으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="7ca7e-106">**Action.Submit** - take the result of the submit and send it to the source.</span></span> <span data-ttu-id="7ca7e-107">카드 원본으로 보내는 방법은 사용자가 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ca7e-107">How you send it to the source of the card is entirely up to you.</span></span>
* <span data-ttu-id="7ca7e-108">**Action.ShowCard** - 대화 상자를 호출하고 해당 대화 상자에 하위 카드를 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca7e-108">**Action.ShowCard** - invokes a dialog and renders the sub-card into that dialog.</span></span> <span data-ttu-id="7ca7e-109">`ShowCardActionMode`가 `popup`으로 설정되는 경우에만 이 항목을 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca7e-109">Note that you only need to handle this if `ShowCardActionMode` is set to `popup`.</span></span>