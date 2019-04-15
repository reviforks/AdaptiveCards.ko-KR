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
# <a name="render-a-card---android"></a>Android-카드를 렌더링 합니다.

Android SDK를 사용 하 여 카드를 렌더링 하는 방법을 다음과 같습니다.

## <a name="create-adaptive-card-object-instance-from-json-text"></a>JSON 텍스트에서 Adaptive Card 개체 인스턴스를 만듭니다

```java
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION);
AdaptiveCard adaptiveCard = parseResult.GetAdaptiveCard();
```

## <a name="render-a-card"></a>카드를 렌더링 합니다.

```java
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, getSupportFragmentManager(), adaptiveCard, cardActionHandler, new HostConfig());
View v = renderedCard.getView();
```