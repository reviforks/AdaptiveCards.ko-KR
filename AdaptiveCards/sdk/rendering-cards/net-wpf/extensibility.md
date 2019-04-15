---
title: 확장성-.NET WPF SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: af301ec4d73b6791c1d132b9df7040d71cf70d7b
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552625"
---
# <a name="extensibility---net-wpf"></a><span data-ttu-id="f3c78-102">확장성-.NET WPF</span><span class="sxs-lookup"><span data-stu-id="f3c78-102">Extensibility - .NET WPF</span></span>

## <a name="custom-element-rendering"></a><span data-ttu-id="f3c78-103">사용자 지정 요소 렌더링</span><span class="sxs-lookup"><span data-stu-id="f3c78-103">Custom Element Rendering</span></span>

<span data-ttu-id="f3c78-104">렌더러의 전체 컨트롤에 대해 사용할 수 있습니다 합니다 `ElementRenderers` 속성을 **추가**를 **제거**, 또는 **재정의** 렌더러 기본입니다.</span><span class="sxs-lookup"><span data-stu-id="f3c78-104">For full control of the renderer you can use the `ElementRenderers` property to **add**, **remove**, or **override** default renderers.</span></span>

<span data-ttu-id="f3c78-105">다음 예제에서는 사용자 지정을 정의 하는 방법을 보여 줍니다. `"type": "Rating"` 요소 및 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c78-105">The following example shows how you could define a custom `"type": "Rating"` element and render it.</span></span>

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
