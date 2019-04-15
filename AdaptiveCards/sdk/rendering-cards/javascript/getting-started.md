---
title: JavaScript SDK
author: matthidinger
ms.author: mahiding
ms.date: 11/28/2017
ms.topic: article
ms.openlocfilehash: 9684b96bba5168a1f07549468274ce5d74c01820
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553465"
---
# <a name="getting-started---javascript"></a><span data-ttu-id="05a68-102">가져오기 시작-JavaScript</span><span class="sxs-lookup"><span data-stu-id="05a68-102">Getting started - JavaScript</span></span>

<span data-ttu-id="05a68-103">설명 했 듯이 [Getting Started](../../../authoring-cards/getting-started.md) 페이지 Adaptive Card는 JSON 직렬화 된 카드 개체 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="05a68-103">As we described in [Getting Started](../../../authoring-cards/getting-started.md) page, an Adaptive Card is a JSON-serialized card object model.</span></span> <span data-ttu-id="05a68-104">이것이 브라우저에서 클라이언트 쪽 HTML을 생성 하는 것에 대 한 JavaScript SDK입니다.</span><span class="sxs-lookup"><span data-stu-id="05a68-104">This is a JavaScript SDK for generating client-side HTML in the browser.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05a68-105">**주요 v0.5에서 변경 내용**</span><span class="sxs-lookup"><span data-stu-id="05a68-105">**Breaking changes from v0.5**</span></span>
> 
> 1. <span data-ttu-id="05a68-106">패키지에서 이름이 `microsoft-adaptivecards` 를 `adaptivecards`</span><span class="sxs-lookup"><span data-stu-id="05a68-106">Package renamed from `microsoft-adaptivecards` to `adaptivecards`</span></span>
> 1. <span data-ttu-id="05a68-107">정적 `AdaptiveCards.setHostConfig()` 의 인스턴스 멤버를 이동 되었습니다 `AdaptiveCard`합니다.</span><span class="sxs-lookup"><span data-stu-id="05a68-107">The static `AdaptiveCards.setHostConfig()` has been moved to an instance member of `AdaptiveCard`.</span></span> <span data-ttu-id="05a68-108">예를 들어, `myCard.hostConfig = {}`</span><span class="sxs-lookup"><span data-stu-id="05a68-108">E.g., `myCard.hostConfig = {}`</span></span> 
> 1. <span data-ttu-id="05a68-109">`HostConfig` 다양 한 이름 바꾸기 및 이동 하지만 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="05a68-109">`HostConfig` has gone though various renames and moves.</span></span> <span data-ttu-id="05a68-110">참조 된 [sample.json](https://github.com/Microsoft/AdaptiveCards/blob/master/samples/HostConfig/sample.json) 현재 구조에 대 한 호스트 구성</span><span class="sxs-lookup"><span data-stu-id="05a68-110">See the [sample.json](https://github.com/Microsoft/AdaptiveCards/blob/master/samples/HostConfig/sample.json) Host Config for current structure</span></span>
> 1. <span data-ttu-id="05a68-111">또한 일부 스키마 변경 내용이 있었는지 v0.5 미리 보기에서는 [여기에 설명 된](https://github.com/Microsoft/AdaptiveCards/pull/633)</span><span class="sxs-lookup"><span data-stu-id="05a68-111">There have also been some schema changes from the v0.5 preview, which are [outlined here](https://github.com/Microsoft/AdaptiveCards/pull/633)</span></span>
> 1. <span data-ttu-id="05a68-112">정적 `renderCard()` 함수 처럼 클래스 메서드를 사용 하 여 중복 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="05a68-112">The static `renderCard()` function was removed as it was redundant with the class methods.</span></span> <span data-ttu-id="05a68-113">사용 하 여 `adaptiveCard.render()` 아래 설명 된 대로 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a68-113">Use `adaptiveCard.render()` as described below.</span></span> 


## <a name="install"></a><span data-ttu-id="05a68-114">Install</span><span class="sxs-lookup"><span data-stu-id="05a68-114">Install</span></span>

### <a name="node"></a><span data-ttu-id="05a68-115">노드</span><span class="sxs-lookup"><span data-stu-id="05a68-115">Node</span></span>

<span data-ttu-id="05a68-116">[![npm 설치](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards)</span><span class="sxs-lookup"><span data-stu-id="05a68-116">[![npm install](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards)</span></span>

```console
npm install adaptivecards --save
```

### <a name="cdn"></a><span data-ttu-id="05a68-117">CDN</span><span class="sxs-lookup"><span data-stu-id="05a68-117">CDN</span></span>

```html
<script src="https://unpkg.com/adaptivecards/dist/adaptivecards.js"></script>
```

## <a name="usage"></a><span data-ttu-id="05a68-118">사용법</span><span class="sxs-lookup"><span data-stu-id="05a68-118">Usage</span></span>

### <a name="import-the-module"></a><span data-ttu-id="05a68-119">모듈 가져오기</span><span class="sxs-lookup"><span data-stu-id="05a68-119">Import the module</span></span>

```js
// import the module
import * as AdaptiveCards from "adaptivecards";

// or require it
var AdaptiveCards = require("adaptivecards");

// or use the global variable if loaded from CDN
AdaptiveCards.renderCard(...);
```

## <a name="next-steps"></a><span data-ttu-id="05a68-120">다음 단계</span><span class="sxs-lookup"><span data-stu-id="05a68-120">Next steps</span></span>

<span data-ttu-id="05a68-121">참조 [카드를 렌더링할](render-a-card.md) 다음 단계!</span><span class="sxs-lookup"><span data-stu-id="05a68-121">See [Render a card](render-a-card.md) for the next steps!</span></span>
