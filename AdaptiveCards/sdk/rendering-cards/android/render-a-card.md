---
title: 카드 렌더링 - Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: a4eeda54a80c959ff9a1246371240954b4c3fb12
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67134284"
---
# <a name="render-a-card---android"></a>카드 렌더링 - Android

Android SDK를 사용하여 카드를 렌더링하는 방법은 다음과 같습니다.

## <a name="create-adaptive-card-object-instance-from-json-text"></a>JSON 텍스트에서 적응형 카드 개체 인스턴스 만들기

```java
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, elementParserRegistration);
AdaptiveCard adaptiveCard = parseResult.GetAdaptiveCard();
```
> [!IMPORTANT]
> **v1.2의 주요 변경 내용**
> 
> 1. ElementParserRegistration 매개 변수는 ElementParserRegistration 및 ActionRegistration 개체를 포함하는 ParseContext로 변경되었습니다.
> ```java
> ParseContext context = new ParseContext(elementParserRegistration, actionParserRegistration);
> ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, context);
> ```

## <a name="render-a-card"></a>카드 렌더링

```java
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, getSupportFragmentManager(), adaptiveCard, cardActionHandler, new HostConfig());
View v = renderedCard.getView();
```
