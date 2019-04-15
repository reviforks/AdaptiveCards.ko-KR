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
# <a name="render-a-card---net-wpf"></a>카드-.NET WPF 렌더링

.NET WPF SDK를 사용 하 여 카드를 렌더링 하는 방법을 다음과 같습니다.

> [!NOTE]
> **`Media` HTTPS Url을 사용 하 여에서 작동 하지 않습니다 WPF**
> 
> 로 인해를 [WPF MediaElement 컨트롤의 버그](https://stackoverflow.com/questions/30702505/playing-media-from-https-site-in-media-element-throwing-null-reference-exception) HTTPS를 통해 제공 되는 미디어를 렌더링할 수 없습니다. HTTP Url에서 사용 해야는 `Media` 이 해결 될 때까지 요소입니다.  

## <a name="instantiate-a-renderer"></a>렌더러를 인스턴스화하십시오.

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

## <a name="render-a-card-to-xaml"></a>XAML에 카드를 렌더링 합니다.

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

