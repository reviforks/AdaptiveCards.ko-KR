---
title: 카드 렌더링 - .NET WPF SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: f847b83a17456dbf80f869ef8ef0df699e57f50e
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67134293"
---
# <a name="render-a-card---net-wpf"></a><span data-ttu-id="0dde5-102">카드 렌더링 - .NET WPF</span><span class="sxs-lookup"><span data-stu-id="0dde5-102">Render a card - .NET WPF</span></span>

<span data-ttu-id="0dde5-103">.NET WPF SDK를 사용하여 카드를 렌더링하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0dde5-103">Here's how to render a card using the .NET WPF SDK.</span></span>

> [!NOTE]
> <span data-ttu-id="0dde5-104">HTTPS URL을 사용하는 **`Media`는 WPF**에서 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0dde5-104">**`Media` with HTTPS URLs will not work in WPF**</span></span>
> 
> <span data-ttu-id="0dde5-105">[WPF MediaElement 컨트롤의 버그](https://stackoverflow.com/questions/30702505/playing-media-from-https-site-in-media-element-throwing-null-reference-exception) 때문에 HTTPS를 통해 제공되는 미디어를 렌더링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0dde5-105">Due to a [bug in the WPF MediaElement control](https://stackoverflow.com/questions/30702505/playing-media-from-https-site-in-media-element-throwing-null-reference-exception) we aren't able to render media that is served via HTTPS.</span></span> <span data-ttu-id="0dde5-106">이 버그가 해결될 때까지 `Media` 요소에 HTTP URL을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dde5-106">You should use HTTP URLs in the `Media` element until this is addressed.</span></span>  

## <a name="instantiate-a-renderer"></a><span data-ttu-id="0dde5-107">렌더러 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="0dde5-107">Instantiate a renderer</span></span>

<span data-ttu-id="0dde5-108">렌더러 라이브러리의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0dde5-108">Create an instance of the renderer library.</span></span> 

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

## <a name="render-a-card-to-xaml"></a><span data-ttu-id="0dde5-109">카드를 XAML로 렌더링</span><span class="sxs-lookup"><span data-stu-id="0dde5-109">Render a card to XAML</span></span>

```csharp
// Build a simple card
// In the real world this would probably be provided as JSON
AdaptiveCard card = new AdaptiveCard("1.0")
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
    // Or the card exceeded the maximum number of supported actions, etc
    IList<AdaptiveWarning> warnings = renderedCard.Warnings;
}
catch(AdaptiveException ex)
{
    // Failed rendering
}
```

