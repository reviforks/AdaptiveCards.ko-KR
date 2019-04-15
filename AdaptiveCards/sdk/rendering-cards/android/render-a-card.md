---
title: Android SDK-카드를 렌더링 합니다.
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: b93ce97a41152641892e6a69d5221842181fcb72
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552515"
---
# <a name="render-a-card---android"></a><span data-ttu-id="dacc3-102">Android-카드를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="dacc3-102">Render a card - Android</span></span>

<span data-ttu-id="dacc3-103">Android SDK를 사용 하 여 카드를 렌더링 하는 방법을 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dacc3-103">Here's how to render a card using the Android SDK.</span></span>

## <a name="create-adaptive-card-object-instance-from-json-text"></a><span data-ttu-id="dacc3-104">JSON 텍스트에서 Adaptive Card 개체 인스턴스를 만듭니다</span><span class="sxs-lookup"><span data-stu-id="dacc3-104">Create Adaptive Card Object Instance from JSON Text</span></span>

```java
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION);
AdaptiveCard adaptiveCard = parseResult.GetAdaptiveCard();
```

## <a name="render-a-card"></a><span data-ttu-id="dacc3-105">카드를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="dacc3-105">Render a card</span></span>

```java
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, getSupportFragmentManager(), adaptiveCard, cardActionHandler, new HostConfig());
View v = renderedCard.getView();
```