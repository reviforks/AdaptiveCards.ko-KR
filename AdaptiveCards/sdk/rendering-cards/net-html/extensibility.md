---
title: 확장성-.NET HTML SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 5aedc2b0bb19cb7a26caa16c8490d0d2f3c93282
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552535"
---
# <a name="extensibility---net-html"></a>확장성-.NET HTML

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
    public override string Type => "Rating";

    public double Rating { get; set; }

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
