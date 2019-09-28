---
title: 적응 카드용 .NET SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/01/2017
ms.topic: article
ms.openlocfilehash: 10400d5db3aac8ea60e5f03f5ab5d9b013211954
ms.sourcegitcommit: 4dd40521cd39313657f1dab642f49ff04098ba35
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71343731"
---
# <a name="net-sdk-for-authoring-cards"></a><span data-ttu-id="0d409-102">제작 카드용 .NET SDK</span><span class="sxs-lookup"><span data-stu-id="0d409-102">.NET SDK for Authoring Cards</span></span>

<span data-ttu-id="0d409-103">[시작](../../authoring-cards/getting-started.md) 페이지에서 설명한 대로 적응 카드는 JSON 개체 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="0d409-103">As we described in the [Getting Started](../../authoring-cards/getting-started.md) page, an Adaptive Card is a JSON object model.</span></span> <span data-ttu-id="0d409-104">.NET 라이브러리를 사용 하면 해당 JSON을 훨씬 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d409-104">The .NET library makes working with that JSON much easier.</span></span>


## <a name="nuget-install"></a><span data-ttu-id="0d409-105">NuGet 설치</span><span class="sxs-lookup"><span data-stu-id="0d409-105">NuGet Install</span></span>
<span data-ttu-id="0d409-106">NuGet `AdaptiveCards` 패키지는 .net에서 적응 카드로 작업 하기 위한 형식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d409-106">The `AdaptiveCards` NuGet package provides types for working with adaptive cards in .NET</span></span>

<span data-ttu-id="0d409-107">[![NuGet 설치](https://img.shields.io/nuget/vpre/AdaptiveCards.svg)](https://www.nuget.org/packages/AdaptiveCards)</span><span class="sxs-lookup"><span data-stu-id="0d409-107">[![Nuget install](https://img.shields.io/nuget/vpre/AdaptiveCards.svg)](https://www.nuget.org/packages/AdaptiveCards)</span></span>

```console
Install-Package AdaptiveCards
```

## <a name="example-create-an-adaptivecard-and-serialize-to-json"></a><span data-ttu-id="0d409-108">예: AdaptiveCard 만들기 및 JSON으로 직렬화</span><span class="sxs-lookup"><span data-stu-id="0d409-108">Example: Create an AdaptiveCard and serialize to JSON</span></span>

<span data-ttu-id="0d409-109">이 예제에서는 표준 C# 개체를 사용 하 여 적응 카드를 빌드한 다음 네트워크를 통해 전송 하기 위해 JSON으로 serialize 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d409-109">This example demonstrates how to build an Adaptive Card using standard C# objects and then serialize it to JSON for transport over the wire.</span></span>

```csharp
using AdaptiveCards;
// ...

AdaptiveCard card = new AdaptiveCard(new AdaptiveSchemaVersion(1, 0));

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

## <a name="example-parse-an-adaptivecard-from-json"></a><span data-ttu-id="0d409-110">예: JSON에서 AdaptiveCard 구문 분석</span><span class="sxs-lookup"><span data-stu-id="0d409-110">Example: Parse an AdaptiveCard from JSON</span></span>

<span data-ttu-id="0d409-111">이 예제에서는 JSON 페이로드를 적응 카드로 구문 분석 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d409-111">This example demonstrates how to parse a JSON payload into an Adaptive Card.</span></span> <span data-ttu-id="0d409-112">이렇게 하면 개체 모델을 쉽게 조작 하거나 [렌더러 sdk](../../rendering-cards/getting-started.md)를 사용 하 여 앱 내에서 적응 카드를 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d409-112">This makes it easy to manipulate the object model or even render Adaptive Cards inside your app by using our [renderer SDKs](../../rendering-cards/getting-started.md).</span></span>

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
