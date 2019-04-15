---
title: Adaptive Card 용.NET SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/01/2017
ms.topic: article
ms.openlocfilehash: 37dec7651a574194eb00d46014431dfb5764f9b7
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553745"
---
# <a name="net-sdk-for-authoring-cards"></a>카드를 작성 하는 것에 대 한.NET SDK

에 설명 된 것 처럼 합니다 [Getting Started](../../authoring-cards/getting-started.md) 페이지 Adaptive Card는 JSON 개체 모델입니다. .NET 라이브러리는 JSON 사용 하 여 작업을 훨씬 쉬워집니다.

> [!IMPORTANT]
> **주요 v0.5에서 변경 내용**
> 
> 1. 패키지에서 이름이 `Microsoft.AdaptiveCards` 를 `AdaptiveCards`
> 1. Framework 형식을 사용 하 여 자주 이름 충돌을 인해 "Adaptive"를 사용 하 여 모든 모델 클래스 앞입니다. 예를 들어 `TextBlock` 되었습니다 `AdaptiveTextBlock`
> 1. 형식에서 모든 "uri" 속성이 변경 되었습니다 `string` 를 `Uri`
> 1. 또한 일부 스키마 변경 내용이 있었는지 v0.5 미리 보기에서는 [여기에 설명 된](https://github.com/Microsoft/AdaptiveCards/pull/633)


## <a name="nuget-install"></a>NuGet 설치
`AdaptiveCards` NuGet 패키지는.NET에서 adaptive card를 사용 하 여 작업에 대 한 형식 제공

[![Nuget 설치](https://img.shields.io/nuget/vpre/AdaptiveCards.svg)](https://www.nuget.org/packages/AdaptiveCards)

```console
Install-Package AdaptiveCards -IncludePrerelease
```

## <a name="example-create-an-adaptivecard-and-serialize-to-json"></a>예: AdaptiveCard 만들고 JSON으로 serialize

이 예제에서는 표준을 사용 하 여 Adaptive Card를 빌드하는 방법 C# 개체를 serialize 한 다음이 JSON으로 전송에 대 한 연결을 통해.

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

## <a name="example-parse-an-adaptivecard-from-json"></a>예: JSON에서는 AdaptiveCard 구문 분석

이 예제에서는 Adaptive Card JSON 페이로드를 구문 분석 하는 방법에 설명 합니다. 이렇게 하면 개체 모델을 조작 하거나 사용 하 여 앱 내에서 Adaptive Card를 렌더링도 쉽게 우리의 [렌더러 Sdk](../../rendering-cards/getting-started.md)합니다.

```csharp
try
{
    // Get a JSON-serialized payload
    // Your app will probably get cards from somewhere else :)
    var client = new HttpClient("http://adaptivecards.io/payloads/ActivityUpdate.json");
    var response = await client.GetAsync(cardUrl);
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
