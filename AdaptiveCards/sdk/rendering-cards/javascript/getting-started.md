---
title: JavaScript SDK
author: matthidinger
ms.author: mahiding
ms.date: 11/28/2017
ms.topic: article
ms.openlocfilehash: 4a6030dda12ab8d9a1e5c387cec63d45e84660d8
ms.sourcegitcommit: aa044167fd0b32b485ea2ce014afcf0b332bf1a2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69529838"
---
# <a name="getting-started---javascript"></a><span data-ttu-id="5d63d-102">시작 하기-JavaScript</span><span class="sxs-lookup"><span data-stu-id="5d63d-102">Getting started - JavaScript</span></span>

<span data-ttu-id="5d63d-103">[시작](../../../authoring-cards/getting-started.md) 페이지에서 설명한 대로 적응 카드는 JSON 직렬화 카드 개체 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="5d63d-103">As we described in [Getting Started](../../../authoring-cards/getting-started.md) page, an Adaptive Card is a JSON-serialized card object model.</span></span> <span data-ttu-id="5d63d-104">이는 브라우저에서 클라이언트 쪽 HTML을 생성 하기 위한 JavaScript SDK입니다.</span><span class="sxs-lookup"><span data-stu-id="5d63d-104">This is a JavaScript SDK for generating client-side HTML in the browser.</span></span>

## <a name="install"></a><span data-ttu-id="5d63d-105">Install</span><span class="sxs-lookup"><span data-stu-id="5d63d-105">Install</span></span>

### <a name="node"></a><span data-ttu-id="5d63d-106">노드</span><span class="sxs-lookup"><span data-stu-id="5d63d-106">Node</span></span>

<span data-ttu-id="5d63d-107">[![npm 설치](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards)</span><span class="sxs-lookup"><span data-stu-id="5d63d-107">[![npm install](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards)</span></span>

```console
npm install adaptivecards
```

### <a name="cdn"></a><span data-ttu-id="5d63d-108">CDN</span><span class="sxs-lookup"><span data-stu-id="5d63d-108">CDN</span></span>

```html
<script src="https://unpkg.com/adaptivecards/dist/adaptivecards.js"></script>
```

## <a name="usage"></a><span data-ttu-id="5d63d-109">사용법</span><span class="sxs-lookup"><span data-stu-id="5d63d-109">Usage</span></span>

### <a name="import-the-module"></a><span data-ttu-id="5d63d-110">모듈 가져오기</span><span class="sxs-lookup"><span data-stu-id="5d63d-110">Import the module</span></span>

```js
// import the module
import * as AdaptiveCards from "adaptivecards";

// or require it
var AdaptiveCards = require("adaptivecards");

// or use the global variable if loaded from CDN
AdaptiveCards.renderCard(...);
```

## <a name="next-steps"></a><span data-ttu-id="5d63d-111">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5d63d-111">Next steps</span></span>

<span data-ttu-id="5d63d-112">[카드 렌더링](render-a-card.md)에서 다음 단계를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5d63d-112">See [Render a card](render-a-card.md) for the next steps!</span></span>
