---
title: 확장성
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: b6d303e15f8d51aa3f1f944304b1fa4f11f9c206
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67138116"
---
# <a name="extensibility"></a><span data-ttu-id="a90d2-102">확장성</span><span class="sxs-lookup"><span data-stu-id="a90d2-102">Extensibility</span></span>

<span data-ttu-id="a90d2-103">각 SDK를 사용하여 요소의 렌더링을 재정의하거나, 사용자가 정의하는 완전히 새로운 요소의 지원을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a90d2-103">Each SDK allows you to override the rendering of any element, or even add support for entirely new elements that you define.</span></span>  <span data-ttu-id="a90d2-104">예를 들어 렌더러의 나머지 출력을 계속 유지하면서 고유한 사용자 지정 컨트롤을 내보내도록 `Input.Date` 렌더러를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a90d2-104">For example, you can change the `Input.Date` renderer to emit your own custom control while still retaining the rest of the output of the renderer.</span></span> <span data-ttu-id="a90d2-105">또는 사용자가 정의한 사용자 지정 `Rating` 요소의 지원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a90d2-105">Or you can add support for a custom `Rating` element to you define.</span></span>

<span data-ttu-id="a90d2-106">예제 코드를 보려면 왼쪽의 **SDK** 노드를 확장한 후 **카드 렌더링** -> **사용할 SDK** -> **확장성**으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="a90d2-106">For example code, please expand the **SDK** node on the left -> **Rendering Cards** -> **the SDK you'd like to use** -> **Extensibility**</span></span>
