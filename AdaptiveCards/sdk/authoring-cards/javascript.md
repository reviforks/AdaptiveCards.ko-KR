---
title: Adaptive Card 용 JavaScript SDK
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 6372f2f23a817ecc4d07d950d6513d14357547b7
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552665"
---
# <a name="javascript-sdk-for-creating-cards"></a>카드를 만들기 위한 JavaScript SDK

> [!IMPORTANT]
> JSON 직렬화 라이브러리는 아직 개발 및 사용자 milage 다를 수 있습니다.

에 설명 된 것 처럼 섹션을 시작 하기를 adaptive card 뿐 다음 카드 개체 모델의 serialize 된 json 개체.  개체 모델을 조작할 수 있도록 하려면 json 직렬화/역직렬화 하기 쉬운 강력한 형식의 클래스 계층 구조를 정의 하는 일부 라이브러리 정의 했습니다.

적응 카드 json 만들려면 어떤 도구를 사용할 수 있습니다.

`adaptivecards` javascript에서 adaptive card를 사용 하 여 작업에 대 한 라이브러리를 정의 하는 npm 패키지

## <a name="to-install"></a>설치 하려면
```console
npm install adaptivecards
```

## <a name="example-creating"></a>예제 만들기 
에 대 한 인터페이스 정의가 `schema.d.ts` 스키마의 모양을 설명 하는

```typescript
let card = {
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "Container",
            "items": [
                {
                    "type": "TextBlock",
                    "text": "Meow!"
                },
                {
                    "type": "Image",
                    "url": "http://adaptivecards.io/content/cats/1.png"
                }
            ]
        }
    ]
};
```

카드를 만들기 위한 개체 모델 이기도 합니다.


```typescript
let card :IAdaptiveCard =  new AdaptiveCard();
card.body.add(new TextBlock() 
{
    text = "hello world"
});
```
