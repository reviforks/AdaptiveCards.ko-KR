---
title: 카드 렌더링 - Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: c9fbfa788af0b0c7f16824bf9c369fa59a1b80f5
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145473"
---
# <a name="render-a-card---android"></a><span data-ttu-id="cbdd5-102">카드 렌더링 - Android</span><span class="sxs-lookup"><span data-stu-id="cbdd5-102">Render a card - Android</span></span>

<span data-ttu-id="cbdd5-103">Android SDK를 사용하여 카드를 렌더링하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-103">Here's how to render a card using the Android SDK.</span></span>

## <a name="create-adaptive-card-object-instance-from-json-text"></a><span data-ttu-id="cbdd5-104">JSON 텍스트에서 적응형 카드 개체 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="cbdd5-104">Create Adaptive Card Object Instance from JSON Text</span></span>

```java
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, elementParserRegistration);
AdaptiveCard adaptiveCard = parseResult.GetAdaptiveCard();
```
> [!IMPORTANT]
> <span data-ttu-id="cbdd5-105">**v1.2의 주요 변경 내용**</span><span class="sxs-lookup"><span data-stu-id="cbdd5-105">**Breaking changes for v1.2**</span></span>
> 

1. <span data-ttu-id="cbdd5-106">ElementParserRegistration 매개 변수가 ElementParserRegistration 및 ActionParserRegistration 개체를 포함 하는 ParseContext로 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-106">ElementParserRegistration parameter changed to ParseContext which includes an ElementParserRegistration and an ActionParserRegistration object</span></span>

```java
ParseContext context = new ParseContext(); // Empty parseContext so only known elements up to v1.2 will be parsed
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, context);
```

<span data-ttu-id="cbdd5-107">또는</span><span class="sxs-lookup"><span data-stu-id="cbdd5-107">or</span></span>

```java
ParseContext context = new ParseContext(elementParserRegistration, actionParserRegistration);
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, context);
```

## <a name="render-a-card"></a><span data-ttu-id="cbdd5-108">카드 렌더링</span><span class="sxs-lookup"><span data-stu-id="cbdd5-108">Render a card</span></span>

```java
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, fragmentManager, adaptiveCard, cardActionHandler, hostConfig);
View v = renderedCard.getView();
```
