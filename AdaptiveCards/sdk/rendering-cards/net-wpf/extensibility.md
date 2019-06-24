---
title: 확장성 - .NET WPF SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 4f89784f711727deb538b2ed2195007ca8e6aca1
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67134315"
---
# <a name="extensibility---net-wpf"></a>확장성 - .NET WPF

## <a name="custom-element-rendering"></a>사용자 지정 요소 렌더링

렌더러를 완벽하게 제어하려면 `ElementRenderers` 속성을 사용하여 기본 렌더러를 **추가**, **제거** 또는 **재정의**하면 됩니다.

다음 예제에서는 사용자 지정 `"type": "Rating"` 요소를 정의하고 렌더링하는 방법을 보여줍니다.

```csharp
// Register the new type with the JSON parser
AdaptiveTypedElementConverter.RegisterTypedElement<MyCustomRating>();

// Add the new type to the element renderer registry
renderer.ElementRenderers.Set<MyCustomRating>(MyCustomRating.Render);

// Define a custom Rating element type
public class MyCustomRating : AdaptiveElement
{
    public MyCustomRating() { Type = "Rating"; }

    public override string Type { get; set; }

    public AdaptiveTextSize Size { get; set; }

    public AdaptiveTextColor Color { get; set; }

    public static FrameworkElement Render(MyCustomRating rating, AdaptiveRenderContext context)
    {
        var textBlock = new AdaptiveTextBlock
        {
            Size = rating.Size,
            Color = rating.Color
        };
        for (int i = 0; i < rating.Rating; i++)
        {
            textBlock.Text += "\u2605";
        }
        textBlock.Text += $" ({rating.Rating})";
        return context.Render(textBlock);
    }
}
```
