---
title: 템플릿 Sdk
author: matthidinger
ms.author: mahiding
ms.date: 08/01/2019
ms.topic: article
ms.openlocfilehash: 5f60a458af99f1b88e8ee428a8f29f1849be9b62
ms.sourcegitcommit: a16f53ba10a8607deacde5c8cc78927cac58657c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68878880"
---
# <a name="adaptive-card-templating-sdks"></a><span data-ttu-id="ca612-102">적응 카드 템플릿 Sdk</span><span class="sxs-lookup"><span data-stu-id="ca612-102">Adaptive Card Templating SDKs</span></span>

<span data-ttu-id="ca612-103">적응 카드 템플릿 Sdk를 사용 하면 지원 되는 플랫폼의 실제 데이터로 [카드 템플릿을](language.md) 쉽게 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca612-103">The Adaptive Card Templating SDKs make it easy to populate a [card template](language.md) with real data on any supported platform.</span></span>

> <span data-ttu-id="ca612-104">[적응 카드 템플릿 개요](index.md) 는이 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca612-104">Please read this for an [overview of Adaptive Card Templating](index.md)</span></span>

> [!IMPORTANT] 
> 
> <span data-ttu-id="ca612-105">이러한 기능은 **미리 보기 상태 이며 변경 될 수**있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca612-105">These features are **in preview and subject to change**.</span></span> <span data-ttu-id="ca612-106">사용자 의견은 환영 뿐만 아니라 필요한 기능을 제공 하기 위해 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca612-106">Your feedback is not only welcome, but  critical to ensure we deliver the features **you** need.</span></span>
> 
> <span data-ttu-id="ca612-107">초기 미리 보기 중에는 JavaScript SDK만 사용할 수 있지만 .NET SDK는 곧 도착할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca612-107">During the initial preview only the JavaScript SDK is available, but a .NET SDK should arrive shortly.</span></span>

## <a name="javascript"></a><span data-ttu-id="ca612-108">JavaScript</span><span class="sxs-lookup"><span data-stu-id="ca612-108">JavaScript</span></span>

<span data-ttu-id="ca612-109">[Adaptivecards](https://www.npmjs.com/package/adaptivecards-templating) 라이브러리는 NPM 및 CDN을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca612-109">The [adaptivecards-templating](https://www.npmjs.com/package/adaptivecards-templating) library is available on npm and via CDN.</span></span> <span data-ttu-id="ca612-110">전체 설명서는 패키지 링크를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca612-110">See the package link for full documentation.</span></span>

### <a name="npm"></a><span data-ttu-id="ca612-111">npm</span><span class="sxs-lookup"><span data-stu-id="ca612-111">npm</span></span>

```console
npm install adaptivecards-templating
```

### <a name="cdn"></a><span data-ttu-id="ca612-112">CDN</span><span class="sxs-lookup"><span data-stu-id="ca612-112">CDN</span></span>

```html
<script src="https://unpkg.com/adaptivecards-templating/dist/adaptivecards-templating.min.js"></script>
``` 

### <a name="usage"></a><span data-ttu-id="ca612-113">사용법</span><span class="sxs-lookup"><span data-stu-id="ca612-113">Usage</span></span>

<span data-ttu-id="ca612-114">아래 샘플에서는 카드를 렌더링 하기 위해 [adaptivecards](https://www.npmjs.com/package/adaptivecards) 라이브러리도 설치 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca612-114">The sample below assumes you've also installed the [adaptivecards](https://www.npmjs.com/package/adaptivecards) library in order to render the card.</span></span> 

<span data-ttu-id="ca612-115">카드 렌더링을 계획 하지 않은 경우 `parse` 및 `render` 코드를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca612-115">If you don't plan on rendering the card then you can remove the `parse` and `render` code.</span></span> 

```js
import * as ACData from "adaptivecards-templating";
import * as AdaptiveCards from "adaptivecards";
 
// Define a template payload
var templatePayload = {
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Hello {name}!"
        }
    ]
};
 
// Create a Template instamce from the template payload
var template = new ACData.Template(templatePayload);
 
// Create a data binding context, and set its $root property to the
// data object to bind the template to
var context = new ACData.EvaluationContext();
context.$root = {
    "name": "Mickey Mouse"
};
 
// "Expand" the template - this generates the final Adaptive Card,
// ready to render
var card = template.expand(context);
 
// Render the card
var adaptiveCard = new AdaptiveCards.AdaptiveCard();
adaptiveCard.parse(card);
 
var htmlElement = adaptiveCard.render();
```

## <a name="net-coming-soon"></a><span data-ttu-id="ca612-116">.NET (*출시*예정)</span><span class="sxs-lookup"><span data-stu-id="ca612-116">.NET (*coming soon*)</span></span>

<span data-ttu-id="ca612-117">아직 작동 하지 않음:</span><span class="sxs-lookup"><span data-stu-id="ca612-117">NOT WORKING YET:</span></span> 

```console
nuget install AdaptiveCards.Templating
```
