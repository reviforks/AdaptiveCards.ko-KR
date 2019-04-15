---
title: .NET HTML SDK-카드를 렌더링 합니다.
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 8dc1baffb91f0755f1955ee02b8a3e820b0d34e4
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553105"
---
# <a name="render-a-card---net-html"></a><span data-ttu-id="fc358-102">카드-.NET HTML 렌더링</span><span class="sxs-lookup"><span data-stu-id="fc358-102">Render a card - .NET HTML</span></span>

<span data-ttu-id="fc358-103">HTML.NET SDK를 사용 하 여 카드를 렌더링 하는 방법을 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fc358-103">Here's how to render a card using the .NET HTML SDK.</span></span>

## <a name="instantiate-a-renderer"></a><span data-ttu-id="fc358-104">렌더러를 인스턴스화하십시오.</span><span class="sxs-lookup"><span data-stu-id="fc358-104">Instantiate a renderer</span></span>

<span data-ttu-id="fc358-105">다음 단계는 렌더러의 인스턴스를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fc358-105">The next step is to create an instance of the renderer.</span></span> 

```csharp
using AdaptiveCards;
using AdaptiveCards.Rendering;
using AdaptiveCards.Rendering.Html;
// ... 

// Create a card renderer
AdaptiveCardRenderer renderer = new AdaptiveCardRenderer();

// For fun, check the schema version this renderer supports
AdaptiveSchemaVersion schemaVersion = renderer.SupportedSchemaVersion; // 1.0
```

## <a name="render-a-card-to-html"></a><span data-ttu-id="fc358-106">카드를 HTML로 렌더링</span><span class="sxs-lookup"><span data-stu-id="fc358-106">Render a card to HTML</span></span>

```csharp
// Build a simple card
// In the real world this would probably be provided as JSON
AdaptiveCard card = new AdaptiveCard()
{
    Body = { new AdaptiveTextBlock() { Text = "Hello World" } }
};

try
{
    // Render the card
    RenderedAdaptiveCard renderedCard = renderer.RenderCard(card);

    // Get the output HTML 
    HtmlTag html = renderedCard.Html;

    // (Optional) Check for any renderer warnings
    // This includes things like an unknown element type found in the card
    // Or the card exceeded the maxmimum number of supported actions, etc
    IList<AdaptiveWarning> warnings = renderedCard.Warnings;
}
catch(AdaptiveException ex)
{
    // Failed rendering
}
```
