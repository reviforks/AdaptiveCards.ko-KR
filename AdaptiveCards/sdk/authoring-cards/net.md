---
title: 적응 카드용 .NET SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/01/2017
ms.topic: article
ms.openlocfilehash: fa86d83a8f20490ec286b69653099ac8cd81b8ef
ms.sourcegitcommit: 4d80c553ab574befa8c84706fd85d22077915745
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68387351"
---
# <a name="net-sdk-for-authoring-cards"></a>제작 카드용 .NET SDK

[시작](../../authoring-cards/getting-started.md) 페이지에서 설명한 대로 적응 카드는 JSON 개체 모델입니다. .NET 라이브러리를 사용 하면 해당 JSON을 훨씬 쉽게 사용할 수 있습니다.

> [!IMPORTANT]
> **V 0.5의 주요 변경 내용**
> 
> 1. 에서 `Microsoft.AdaptiveCards` 로 이름이 바뀐 패키지`AdaptiveCards`
> 1. 프레임 워크 유형과 자주 이름이 충돌 하기 때문에 모든 모델 클래스에는 "적응" 접두사가 붙습니다. `TextBlock` 예: 이제`AdaptiveTextBlock`
> 1. 모든 "uri" 속성이 형식 `string` 에서로 변경 되었습니다.`Uri`
> 1. [여기에 설명](https://github.com/Microsoft/AdaptiveCards/pull/633) 된 v 0.5 미리 보기의 일부 스키마도 변경 되었습니다.


## <a name="nuget-install"></a>NuGet 설치
NuGet `AdaptiveCards` 패키지는 .net에서 적응 카드로 작업 하기 위한 형식을 제공 합니다.

[![Nuget 설치](https://img.shields.io/nuget/vpre/AdaptiveCards.svg)](https://www.nuget.org/packages/AdaptiveCards)

```console
Install-Package AdaptiveCards -IncludePrerelease
```

## <a name="example-create-an-adaptivecard-and-serialize-to-json"></a>예: AdaptiveCard 만들기 및 JSON으로 직렬화

이 예제에서는 표준 C# 개체를 사용 하 여 적응 카드를 빌드한 다음 네트워크를 통해 전송 하기 위해 JSON으로 serialize 하는 방법을 보여 줍니다.

```csharp
using AdaptiveCards;
// ...

AdaptiveCard card = new AdaptiveCard();

card.Body.Add(new AdaptiveTextBlock() 
{
    Text = "Hello",
    Size = AdaptiveTextSize.ExtraLarge
});

card.Body.Add(new AdaptiveImage() 
{
    Url = new Uri("http://adaptivecards.io/content/cats/1.png")
});

// serialize the card to JSON
string json = card.ToJson();
```

## <a name="example-parse-an-adaptivecard-from-json"></a>예: JSON에서 AdaptiveCard 구문 분석

이 예제에서는 JSON 페이로드를 적응 카드로 구문 분석 하는 방법을 보여 줍니다. 이렇게 하면 개체 모델을 쉽게 조작 하거나 [렌더러 sdk](../../rendering-cards/getting-started.md)를 사용 하 여 앱 내에서 적응 카드를 렌더링할 수 있습니다.

```csharp
try
{
    // Get a JSON-serialized payload
    // Your app will probably get cards from somewhere else :)
    var client = new HttpClient();
    var response = await client.GetAsync("http://adaptivecards.io/payloads/ActivityUpdate.json");
    var json = await response.Content.ReadAsStringAsync();

    // Parse the JSON 
    AdaptiveCardParseResult result = AdaptiveCard.FromJson(json);

    // Get card from result
    AdaptiveCard card = result.Card;

    // Optional: check for any parse warnings
    // This includes things like unknown element "type"
    // or unknown properties on element
    IList<AdaptiveWarning> warnings = result.Warnings;
}
catch(AdaptiveSerializationException ex)
{
    // Failed to deserialize card 
    // This occurs from malformed JSON
    // or schema violations like required properties missing 
}
```
