---
title: 카드 렌더링-UWP SDK
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 1a72cb9ba72811d4e98a48116fa08245e13a6392
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552435"
---
# <a name="render-a-card---uwp"></a><span data-ttu-id="f3539-102">카드 렌더링-UWP</span><span class="sxs-lookup"><span data-stu-id="f3539-102">Render a card - UWP</span></span>

<span data-ttu-id="f3539-103">UWP SDK를 사용 하 여 카드를 렌더링 하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f3539-103">Here's how to render a card using the UWP SDK.</span></span>

## <a name="create-an-instance-of-your-renderer"></a><span data-ttu-id="f3539-104">렌더러의 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="f3539-104">Create an instance of your renderer</span></span>

<span data-ttu-id="f3539-105">렌더러 라이브러리의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3539-105">Create an instance of the renderer library.</span></span> 

```csharp
using AdaptiveCards.Rendering.Uwp;
// ...

var renderer = new AdaptiveCardRenderer();
```

## <a name="create-a-card-from-a-json-string"></a><span data-ttu-id="f3539-106">JSON 문자열에서 카드 만들기</span><span class="sxs-lookup"><span data-stu-id="f3539-106">Create a card from a JSON string</span></span>

```csharp
var card = AdaptiveCard.FromJsonString(jsonString);
```

## <a name="create-a-card-from-a-json-object"></a><span data-ttu-id="f3539-107">JSON 개체에서 카드 만들기</span><span class="sxs-lookup"><span data-stu-id="f3539-107">Create a card from a JSON object</span></span>

```csharp
var card = AdaptiveCard.FromJson(jsonObject);
```

## <a name="render-a-card"></a><span data-ttu-id="f3539-108">카드 렌더링</span><span class="sxs-lookup"><span data-stu-id="f3539-108">Render a card</span></span>

<span data-ttu-id="f3539-109">원본에서 카드를 획득 하 여 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3539-109">Acquire a card from a source and render it.</span></span>

```csharp
RenderedAdaptiveCard renderedAdaptiveCard =  renderer.RenderAdaptiveCard(card);

// Check if the render was successful
if (renderedAdaptiveCard.FrameworkElement != null)
{
    // Get the framework element
    var uiCard = renderedAdaptiveCard.FrameworkElement;

    // Add it to your UI
    myGrid.Children.Add(uiCard);
}
```

## <a name="example"></a><span data-ttu-id="f3539-110">예제</span><span class="sxs-lookup"><span data-stu-id="f3539-110">Example</span></span>

<span data-ttu-id="f3539-111">UWP 렌더러의 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f3539-111">Here is an example from the UWP renderer.</span></span>

```csharp
var renderer = new AdaptiveCardRenderer();
var card = AdaptiveCard.FromJsonString(jsonString);
var renderedAdaptiveCard = renderer.RenderAdaptiveCard(card.AdaptiveCard);
if (renderedAdaptiveCard.FrameworkElement != null)
{
    myGrid.Children.Add(renderedAdaptiveCard.FrameworkElement);
}
...
```