---
title: 카드 렌더링-Xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: dc1d48e05e99d6254b9253efa7145cefeb2ed17c
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145977"
---
# <a name="render-a-card---xamarinandroid"></a><span data-ttu-id="94847-102">카드 렌더링-Xamarin. Android</span><span class="sxs-lookup"><span data-stu-id="94847-102">Render a card - Xamarin.Android</span></span>

<span data-ttu-id="94847-103">Android SDK를 사용 하 여 카드를 렌더링 하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94847-103">Here's how to render a card using the Xamarin.Android SDK.</span></span>

## <a name="create-adaptive-card-object-instance-from-json-text"></a><span data-ttu-id="94847-104">JSON 텍스트에서 적응형 카드 개체 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="94847-104">Create Adaptive Card Object Instance from JSON Text</span></span>

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
// ...

ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version);
AdaptiveCard adaptiveCard = parseResult.AdaptiveCard;
```

<span data-ttu-id="94847-105">또는 ```ParseContext``` 개체를 사용 하 여 다음과 같이 적응 카드에 포함 된 사용자 지정 요소를 deserialize 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94847-105">or you can also use a ```ParseContext``` object to be able to deserialize custom elements that are included in your adaptive card like this:</span></span>

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
// ...

ParseContext context = new ParseContext(); // Empty parseContext so only known elements up to v1.2 will be parsed
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version, context);
```

<span data-ttu-id="94847-106">또는</span><span class="sxs-lookup"><span data-stu-id="94847-106">or</span></span>

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
// ...

ParseContext context = new ParseContext(elementParserRegistration, actionParserRegistration);
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version, context);
```

## <a name="render-a-card"></a><span data-ttu-id="94847-107">카드 렌더링</span><span class="sxs-lookup"><span data-stu-id="94847-107">Render a card</span></span>

<span data-ttu-id="94847-108">카드를 렌더링 하려면 일부 정보가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="94847-108">To be able to render a card you'll need some information</span></span>
* <span data-ttu-id="94847-109">컨텍스트: 카드가 호스트 되는 활동에서 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94847-109">context: Obtainable from the Activity the card is hosted in</span></span>
* <span data-ttu-id="94847-110">fragmentManager: 호스팅 활동에서 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94847-110">fragmentManager: can also be retrieved from the hosting activity</span></span>
* <span data-ttu-id="94847-111">작업 동작을 관리 하는 [```ICardActionHandler```](adaptivecards-renderin-xamarin-android-renderer-actionhandler-icardactionhandler.md) 의 인스턴스</span><span class="sxs-lookup"><span data-stu-id="94847-111">cardActionHandler: instance of [```ICardActionHandler```](adaptivecards-renderin-xamarin-android-renderer-actionhandler-icardactionhandler.md) to manage the action behaviour</span></span>

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
using AdaptiveCards.Rendering.Xamarin.Android.Renderer;
using AdaptiveCards.Rendering.Xamarin.Android.Renderer.ActionHandler;
// ...

var renderedCard = AdaptiveCardRenderer.Instance.Render(context, fragmentManager, adaptiveCard, cardActionHandler, hostConfig);
View v = renderedCard.View;
```
