---
title: 템플릿 생성용 SDK
author: matthidinger
ms.author: mahiding
ms.date: 08/01/2019
ms.topic: article
ms.openlocfilehash: 3a9bfcd1bf8f87959a747997e04f5c5ad2a79980
ms.sourcegitcommit: 90afb3729931b0e4cae19b17ef9e49453c2d2bf6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2019
ms.locfileid: "72163616"
---
# <a name="adaptive-card-templating-sdks"></a>적응 카드 템플릿 Sdk

적응 카드 템플릿 Sdk를 사용 하면 지원 되는 플랫폼의 실제 데이터로 [카드 템플릿을](language.md) 쉽게 채울 수 있습니다.

> [적응 카드 템플릿 개요](index.md) 는이 내용을 참조 하세요.

> [!IMPORTANT] 
> 
> 이러한 기능은 **미리 보기 상태이며 변경될 수 있습니다**. 사용자 의견은 언제나 환영이며, **사용자**에게 필요한 기능을 제공하는 데 중요합니다.
> 
> 초기 미리 보기 중에는 JavaScript SDK만 사용할 수 있지만 .NET SDK는 곧 도착할 것입니다.

## <a name="javascript"></a>JavaScript

[Adaptivecards](https://www.npmjs.com/package/adaptivecards-templating) 라이브러리는 NPM 및 CDN을 통해 사용할 수 있습니다. 전체 설명서는 패키지 링크를 참조 하세요.

### <a name="npm"></a>npm

```console
npm install adaptivecards-templating
```

### <a name="cdn"></a>CDN

```html
<script src="https://unpkg.com/adaptivecards-templating/dist/adaptivecards-templating.min.js"></script>
``` 

### <a name="usage"></a>사용법

아래 샘플에서는 카드를 렌더링 하기 위해 [adaptivecards](https://www.npmjs.com/package/adaptivecards) 라이브러리도 설치 했다고 가정 합니다. 

카드 렌더링을 계획 하지 않은 경우 `parse` 및 `render` 코드를 제거할 수 있습니다. 

```js
import * as ACData from "adaptivecards-templating";
import * as AdaptiveCards from "adaptivecards";
 
// Define a template payload
var templatePayload = {
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Hello {name}!"
        }
    ]
};
 
// Create a Template instamce from the template payload
var template = new ACData.Template(templatePayload);
 
// Create a data binding context, and set its $root property to the
// data object to bind the template to
var context = new ACData.EvaluationContext();
context.$root = {
    "name": "Mickey Mouse"
};
 
// "Expand" the template - this generates the final Adaptive Card,
// ready to render
var card = template.expand(context);
 
// Render the card
var adaptiveCard = new AdaptiveCards.AdaptiveCard();
adaptiveCard.parse(card);
 
var htmlElement = adaptiveCard.render();
```

## <a name="net"></a>.NET 

```console
dotnet add package AdaptiveCards.Templating --version 0.1.0-alpha1
```

> [!NOTE]
>
> 위의 버전을 최신 게시 된 버전으로 변경 하는 것이 좋습니다.

라이브러리 가져오기 

```cs
using AdaptiveCards.Templating
```

템플릿 JSON 및 데이터 JSON을 전달 하 여 템플릿 엔진을 사용 합니다.

```cs
var templateJson = @"
{
    ""type"": ""AdaptiveCard"",
    ""version"": ""1.0"",
    ""body"": [
        {
            ""type"": ""TextBlock"",
            ""text"": ""Hello {name}""
        }
    ]
}";

var dataJson = @"
{
    ""name"": ""Mickey Mouse""
}";

var transformer = new AdaptiveTransformer();
var cardJson = transformer.Transform(templateJson, dataJson);
```
