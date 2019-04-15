---
title: 작업-HTML.NET SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 99bf6121489391c207a71b45264dc68aa2c6116e
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553315"
---
# <a name="actions---net-html"></a><span data-ttu-id="236ad-102">작업을.NET HTML</span><span class="sxs-lookup"><span data-stu-id="236ad-102">Actions - .NET HTML</span></span>

<span data-ttu-id="236ad-103">최상위 카드 `actions` 는 HTML로 렌더링 될 `<button>`합니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-103">Top-level card `actions` will render as an HTML `<button>`.</span></span> <span data-ttu-id="236ad-104">서버 쪽 라이브러리 이기 때문에 달려 단추를 누르면 클라이언트 쪽 이벤트 처리기를 연결 하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-104">Since this is a server-side library it's up to you to wire up client-side event handlers when buttons are pressed.</span></span> <span data-ttu-id="236ad-105">각 `<button>` HTML의 특성을 갖습니다 사용할 수 있는 적절 한 동작을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-105">Each `<button>` in the HTML will have attributes that you can use to wire up the proper behavior.</span></span>

<span data-ttu-id="236ad-106">일부 요소는 `selectAction` 호출 되도록 하는 속성 (열, 컨테이너 이미지).</span><span class="sxs-lookup"><span data-stu-id="236ad-106">Some elements have a `selectAction` property (Container, Columns, Image) which makes them invokable.</span></span> <span data-ttu-id="236ad-107">요소에 있는 경우는 `selectAction` 렌더러의 CSS 클래스를 추가 합니다 `ac-selectable`, 함께 특성 아래.</span><span class="sxs-lookup"><span data-stu-id="236ad-107">If an element has a `selectAction` the renderer will add a CSS class of `ac-selectable`, along with the below attributes.</span></span>

<span data-ttu-id="236ad-108">동작 유형</span><span class="sxs-lookup"><span data-stu-id="236ad-108">Action Type</span></span> | <span data-ttu-id="236ad-109">CSS 클래스</span><span class="sxs-lookup"><span data-stu-id="236ad-109">CSS class</span></span> | <span data-ttu-id="236ad-110">추가 특성</span><span class="sxs-lookup"><span data-stu-id="236ad-110">Additional attributes</span></span>
---|---|---
`Action.OpenUrl` | `ac-action-openUrl` | <span data-ttu-id="236ad-111">`data-ac-url` (의 `url` 카드에서 속성)</span><span class="sxs-lookup"><span data-stu-id="236ad-111">`data-ac-url` (the `url` property from the card)</span></span>
`Action.Submit` | `ac-action-submit` | <span data-ttu-id="236ad-112">`data-ac-data` (의 `data` 카드에서 속성)</span><span class="sxs-lookup"><span data-stu-id="236ad-112">`data-ac-data` (the `data` property from the card)</span></span>
`Action.ShowCard` | `ac-action-showCard` | <span data-ttu-id="236ad-113">`data-ac-showcardid` (합니다 `id` 의 `<div>` 내부 카드 포함)</span><span class="sxs-lookup"><span data-stu-id="236ad-113">`data-ac-showcardid` (the `id` of the `<div>` containing the inner card)</span></span>