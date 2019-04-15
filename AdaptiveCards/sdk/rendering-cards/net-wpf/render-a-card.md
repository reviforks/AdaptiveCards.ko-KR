---
title: .NET WPF SDK-카드를 렌더링 합니다.
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 6bc476c79c6d06c7ecb770fb1c3e89eb55e81b9a
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553475"
---
# <a name="render-a-card---net-wpf"></a><span data-ttu-id="0f24d-102">카드-.NET WPF 렌더링</span><span class="sxs-lookup"><span data-stu-id="0f24d-102">Render a card - .NET WPF</span></span>

<span data-ttu-id="0f24d-103">.NET WPF SDK를 사용 하 여 카드를 렌더링 하는 방법을 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0f24d-103">Here's how to render a card using the .NET WPF SDK.</span></span>

> [!NOTE]
> <span data-ttu-id="0f24d-104">**`Media` HTTPS Url을 사용 하 여에서 작동 하지 않습니다 WPF**</span><span class="sxs-lookup"><span data-stu-id="0f24d-104">**`Media` with HTTPS URLs will not work in WPF**</span></span>
> 
> <span data-ttu-id="0f24d-105">로 인해를 [WPF MediaElement 컨트롤의 버그](https://stackoverflow.com/questions/30702505/playing-media-from-https-site-in-media-element-throwing-null-reference-exception) HTTPS를 통해 제공 되는 미디어를 렌더링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f24d-105">Due to a [bug in the WPF MediaElement control](https://stackoverflow.com/questions/30702505/playing-media-from-https-site-in-media-element-throwing-null-reference-exception) we aren't able to render media that is served via HTTPS.</span></span> <span data-ttu-id="0f24d-106">HTTP Url에서 사용 해야는 `Media` 이 해결 될 때까지 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0f24d-106">You should use HTTP URLs in the `Media` element until this is addressed.</span></span>  

## <a name="instantiate-a-renderer"></a><span data-ttu-id="0f24d-107">렌더러를 인스턴스화하십시오.</span><span class="sxs-lookup"><span data-stu-id="0f24d-107">Instantiate a renderer</span></span>

<span data-ttu-id="0f24d-108">렌더러 라이브러리의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f24d-108">Create an instance of the renderer library.</span></span> 

```csharp
using AdaptiveCards;
using AdaptiveCards.Rendering;
using AdaptiveCards.Rendering.Wpf;
// ...

// Create a card renderer
AdaptiveCardRenderer renderer = new AdaptiveCardRenderer();

// If using the Xceed package, enable the enhanced input
renderer.UseXceedElementRenderers();

// For fun, check the schema version this renderer supports
AdaptiveSchemaVersion schemaVersion = renderer.SupportedSchemaVersion;
```

## <a name="render-a-card-to-xaml"></a><span data-ttu-id="0f24d-109">XAML에 카드를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f24d-109">Render a card to XAML</span></span>

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

    // Get the FrameworkElement
    // Add this to your app's UI somewhere
    FrameworkElement fe = renderedCard.FrameworkElement;

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

