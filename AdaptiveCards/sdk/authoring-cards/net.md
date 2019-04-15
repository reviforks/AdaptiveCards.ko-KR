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
# <a name="net-sdk-for-authoring-cards"></a><span data-ttu-id="1073e-102">카드를 작성 하는 것에 대 한.NET SDK</span><span class="sxs-lookup"><span data-stu-id="1073e-102">.NET SDK for Authoring Cards</span></span>

<span data-ttu-id="1073e-103">에 설명 된 것 처럼 합니다 [Getting Started](../../authoring-cards/getting-started.md) 페이지 Adaptive Card는 JSON 개체 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="1073e-103">As we described in the [Getting Started](../../authoring-cards/getting-started.md) page, an Adaptive Card is a JSON object model.</span></span> <span data-ttu-id="1073e-104">.NET 라이브러리는 JSON 사용 하 여 작업을 훨씬 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="1073e-104">The .NET library makes working with that JSON much easier.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1073e-105">**주요 v0.5에서 변경 내용**</span><span class="sxs-lookup"><span data-stu-id="1073e-105">**Breaking changes from v0.5**</span></span>
> 
> 1. <span data-ttu-id="1073e-106">패키지에서 이름이 `Microsoft.AdaptiveCards` 를 `AdaptiveCards`</span><span class="sxs-lookup"><span data-stu-id="1073e-106">Package renamed from `Microsoft.AdaptiveCards` to `AdaptiveCards`</span></span>
> 1. <span data-ttu-id="1073e-107">Framework 형식을 사용 하 여 자주 이름 충돌을 인해 "Adaptive"를 사용 하 여 모든 모델 클래스 앞입니다.</span><span class="sxs-lookup"><span data-stu-id="1073e-107">Due to frequent name collisions with framework types, all model classes have been prefixed with "Adaptive".</span></span> <span data-ttu-id="1073e-108">예를 들어 `TextBlock` 되었습니다 `AdaptiveTextBlock`</span><span class="sxs-lookup"><span data-stu-id="1073e-108">E.g., `TextBlock` is now `AdaptiveTextBlock`</span></span>
> 1. <span data-ttu-id="1073e-109">형식에서 모든 "uri" 속성이 변경 되었습니다 `string` 를 `Uri`</span><span class="sxs-lookup"><span data-stu-id="1073e-109">All "uri" properties were changed from type `string` to `Uri`</span></span>
> 1. <span data-ttu-id="1073e-110">또한 일부 스키마 변경 내용이 있었는지 v0.5 미리 보기에서는 [여기에 설명 된](https://github.com/Microsoft/AdaptiveCards/pull/633)</span><span class="sxs-lookup"><span data-stu-id="1073e-110">There have also been some schema changes from the v0.5 preview, which are [outlined here](https://github.com/Microsoft/AdaptiveCards/pull/633)</span></span>


## <a name="nuget-install"></a><span data-ttu-id="1073e-111">NuGet 설치</span><span class="sxs-lookup"><span data-stu-id="1073e-111">NuGet Install</span></span>
<span data-ttu-id="1073e-112">`AdaptiveCards` NuGet 패키지는.NET에서 adaptive card를 사용 하 여 작업에 대 한 형식 제공</span><span class="sxs-lookup"><span data-stu-id="1073e-112">The `AdaptiveCards` NuGet package provides types for working with adaptive cards in .NET</span></span>

<span data-ttu-id="1073e-113">[![Nuget 설치](https://img.shields.io/nuget/vpre/AdaptiveCards.svg)](https://www.nuget.org/packages/AdaptiveCards)</span><span class="sxs-lookup"><span data-stu-id="1073e-113">[![Nuget install](https://img.shields.io/nuget/vpre/AdaptiveCards.svg)](https://www.nuget.org/packages/AdaptiveCards)</span></span>

```console
Install-Package AdaptiveCards -IncludePrerelease
```

## <a name="example-create-an-adaptivecard-and-serialize-to-json"></a><span data-ttu-id="1073e-114">예: AdaptiveCard 만들고 JSON으로 serialize</span><span class="sxs-lookup"><span data-stu-id="1073e-114">Example: Create an AdaptiveCard and serialize to JSON</span></span>

<span data-ttu-id="1073e-115">이 예제에서는 표준을 사용 하 여 Adaptive Card를 빌드하는 방법 C# 개체를 serialize 한 다음이 JSON으로 전송에 대 한 연결을 통해.</span><span class="sxs-lookup"><span data-stu-id="1073e-115">This example demonstrates how to build an Adaptive Card using standard C# objects and then serialize it to JSON for transport over the wire.</span></span>

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

## <a name="example-parse-an-adaptivecard-from-json"></a><span data-ttu-id="1073e-116">예: JSON에서는 AdaptiveCard 구문 분석</span><span class="sxs-lookup"><span data-stu-id="1073e-116">Example: Parse an AdaptiveCard from JSON</span></span>

<span data-ttu-id="1073e-117">이 예제에서는 Adaptive Card JSON 페이로드를 구문 분석 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1073e-117">This example demonstrates how to parse a JSON payload into an Adaptive Card.</span></span> <span data-ttu-id="1073e-118">이렇게 하면 개체 모델을 조작 하거나 사용 하 여 앱 내에서 Adaptive Card를 렌더링도 쉽게 우리의 [렌더러 Sdk](../../rendering-cards/getting-started.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1073e-118">This makes it easy to manipulate the object model or even render Adaptive Cards inside your app by using our [renderer SDKs](../../rendering-cards/getting-started.md).</span></span>

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
