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
# <a name="render-a-card---net-wpf"></a>카드 렌더링 - .NET WPF

.NET WPF SDK를 사용하여 카드를 렌더링하는 방법은 다음과 같습니다.

> [!NOTE]
> HTTPS URL을 사용하는 **`Media`는 WPF**에서 작동하지 않습니다.
> 
> [WPF MediaElement 컨트롤의 버그](https://stackoverflow.com/questions/30702505/playing-media-from-https-site-in-media-element-throwing-null-reference-exception) 때문에 HTTPS를 통해 제공되는 미디어를 렌더링할 수 없습니다. 이 버그가 해결될 때까지 `Media` 요소에 HTTP URL을 사용해야 합니다.  

## <a name="instantiate-a-renderer"></a>렌더러 인스턴스화

렌더러 라이브러리의 인스턴스를 만듭니다. 

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

## <a name="render-a-card-to-xaml"></a>카드를 XAML로 렌더링

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

