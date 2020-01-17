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

1. ElementParserRegistration 매개 변수가 ElementParserRegistration 및 ActionParserRegistration 개체를 포함 하는 ParseContext로 변경 되었습니다.

```java
ParseContext context = new ParseContext(); // Empty parseContext so only known elements up to v1.2 will be parsed
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, context);
```

또는

```java
ParseContext context = new ParseContext(elementParserRegistration, actionParserRegistration);
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, context);
```

## <a name="render-a-card"></a>카드 렌더링

```java
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, fragmentManager, adaptiveCard, cardActionHandler, hostConfig);
View v = renderedCard.getView();
```
