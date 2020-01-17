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
# <a name="render-a-card---xamarinandroid"></a>카드 렌더링-Xamarin. Android

Android SDK를 사용 하 여 카드를 렌더링 하는 방법은 다음과 같습니다.

## <a name="create-adaptive-card-object-instance-from-json-text"></a>JSON 텍스트에서 적응형 카드 개체 인스턴스 만들기

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
// ...

ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version);
AdaptiveCard adaptiveCard = parseResult.AdaptiveCard;
```

또는 ```ParseContext``` 개체를 사용 하 여 다음과 같이 적응 카드에 포함 된 사용자 지정 요소를 deserialize 할 수도 있습니다.

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
// ...

ParseContext context = new ParseContext(); // Empty parseContext so only known elements up to v1.2 will be parsed
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version, context);
```

또는

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
// ...

ParseContext context = new ParseContext(elementParserRegistration, actionParserRegistration);
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version, context);
```

## <a name="render-a-card"></a>카드 렌더링

카드를 렌더링 하려면 일부 정보가 필요 합니다.
* 컨텍스트: 카드가 호스트 되는 활동에서 얻을 수 있습니다.
* fragmentManager: 호스팅 활동에서 검색할 수도 있습니다.
* 작업 동작을 관리 하는 [```ICardActionHandler```](adaptivecards-renderin-xamarin-android-renderer-actionhandler-icardactionhandler.md) 의 인스턴스

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
using AdaptiveCards.Rendering.Xamarin.Android.Renderer;
using AdaptiveCards.Rendering.Xamarin.Android.Renderer.ActionHandler;
// ...

var renderedCard = AdaptiveCardRenderer.Instance.Render(context, fragmentManager, adaptiveCard, cardActionHandler, hostConfig);
View v = renderedCard.View;
```
