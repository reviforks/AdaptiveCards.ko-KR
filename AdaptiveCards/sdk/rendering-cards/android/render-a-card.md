---
title: 카드 렌더링 - Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: 55e0fa828abf3b9af857d1deb7ecd3744b5a7280
ms.sourcegitcommit: 8c8067206f283d97a5aa4ec65ba23d3fe18962f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299531"
---
# <a name="render-a-card---android"></a><span data-ttu-id="5a61b-102">카드 렌더링 - Android</span><span class="sxs-lookup"><span data-stu-id="5a61b-102">Render a card - Android</span></span>

<span data-ttu-id="5a61b-103">Android SDK를 사용하여 카드를 렌더링하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5a61b-103">Here's how to render a card using the Android SDK.</span></span>

## <a name="create-adaptive-card-object-instance-from-json-text"></a><span data-ttu-id="5a61b-104">JSON 텍스트에서 적응형 카드 개체 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="5a61b-104">Create Adaptive Card Object Instance from JSON Text</span></span>

```java
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, elementParserRegistration);
AdaptiveCard adaptiveCard = parseResult.GetAdaptiveCard();
```
> [!IMPORTANT]
> <span data-ttu-id="5a61b-105">**v1.2의 주요 변경 내용**</span><span class="sxs-lookup"><span data-stu-id="5a61b-105">**Breaking changes for v1.2**</span></span>
> 

1. <span data-ttu-id="5a61b-106">ElementParserRegistration 매개 변수가 ElementParserRegistration 및 ActionParserRegistration 개체를 포함 하는 ParseContext로 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5a61b-106">ElementParserRegistration parameter changed to ParseContext which includes an ElementParserRegistration and an ActionParserRegistration object</span></span>

```java
ParseContext context = new ParseContext(); // Empty parseContext so only known elements up to v1.2 will be parsed
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, context);
```

<span data-ttu-id="5a61b-107">로 구분하거나 여러</span><span class="sxs-lookup"><span data-stu-id="5a61b-107">or</span></span>

```java
ParseContext context = new ParseContext(elementParserRegistration, actionParserRegistration);
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, context);
```

## <a name="render-a-card"></a><span data-ttu-id="5a61b-108">카드 렌더링</span><span class="sxs-lookup"><span data-stu-id="5a61b-108">Render a card</span></span>

```java
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, fragmentManager, adaptiveCard, cardActionHandler, hostConfig);
View v = renderedCard.getView();
```
