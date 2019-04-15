---
title: 확장성
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 9359db59201d3ddb27f7cb31bdf22985b73d29d1
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552575"
---
# <a name="extensibility"></a><span data-ttu-id="f9c67-102">확장성</span><span class="sxs-lookup"><span data-stu-id="f9c67-102">Extensibility</span></span>

<span data-ttu-id="f9c67-103">각 SDK를 사용 하면 모든 요소의 렌더링을 재정의 하거나 정의 하는 완전히 새로운 요소에 대 한 지원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9c67-103">Each SDK allows you to override the rendering of any element, or even add support for entirely new elements that you define.</span></span>  <span data-ttu-id="f9c67-104">예를 들어, 변경할 수 있습니다는 `Input.Date` 렌더러 렌더러의 출력의 나머지 부분을 유지 하면서 사용자 고유의 사용자 지정 컨트롤을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9c67-104">For example, you can change the `Input.Date` renderer to emit your own custom control while still retaining the rest of the output of the renderer.</span></span> <span data-ttu-id="f9c67-105">사용자 지정에 대 한 지원을 추가할 수 있습니다 또는 `Rating` 요소 수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c67-105">Or you can add support for a custom `Rating` element to you define.</span></span>