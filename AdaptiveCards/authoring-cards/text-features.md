---
title: 텍스트 기능
author: matthidinger
ms.author: mahiding
ms.date: 11/09/2017
ms.topic: article
ms.openlocfilehash: ac8ec0c48e06377ebd17f1b31abe463c48809fe3
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553615"
---
# <a name="text-features"></a>텍스트 기능

`TextBlock` 서식 지정 및 텍스트를 지역화에 대 한 몇 가지 고급 기능을 제공 합니다.

## <a name="markdown"></a>Markdown
Adaptive Card 지원를 지원 하기 위해 인라인 태그를 **하위 집합** Markdown 구문의 합니다.

_지원_

| 텍스트 스타일      | Markdown |
|-----------------|-----|
| **굵게**        | ```**Bold**``` |
| _기울임꼴_        | ```_Italic_``` |
| 글머리 기호 목록     | ```- Item 1\r- Item 2\r- Item 3``` | 
| 번호가 매겨진 목록   | ```1. Green\r2. Orange\r3. Blue``` |
| 하이퍼링크      | ```[Title](url)``` |

_지원 되지 않음_

* 헤더
* 테이블
* 이미지
* 위의 테이블에 없는 항목

### <a name="markdown-example"></a>Markdown 예제

페이로드 아래은 다음과 같이 렌더링 됩니다.

![markdown 스크린 샷](media/text-features/markdown.png)

```json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "This is some **bold** text"
        },
        {
            "type": "TextBlock",
            "text": "This is some _italic_ text"
        },
        {
            "type": "TextBlock",
            "text": "- Bullet \r- List \r",
            "wrap": true
        },
        {
            "type": "TextBlock",
            "text": "1. Numbered\r2. List\r",
            "wrap": true
        },
        {
            "type": "TextBlock",
            "text": "Check out [Adaptive Cards](http://adaptivecards.io)"
        }
    ]
}
```

## <a name="datetime-formatting-and-localization"></a>날짜/시간 형식 및 지역화

Adaptive Card 제공 되므로 카드를 수신 하는 사용자의 표준 시간대를 알 수 없습니다 경우에 따라 `DATE()` 고 `TIME()` 자동으로 대상 장치에서 시간을 지역화 하는 함수를 서식 지정 합니다.

### <a name="datetime-example"></a>날짜/시간 예제

```json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Your package will arrive on {{DATE(2017-02-14T06:00:00Z, SHORT)}} at {{TIME(2017-02-14T06:00:00Z)}}",
            "wrap": true
        }
    ]
}
```

위의 카드 표시 됩니다. 

> **2017 년 2 월 14, 화요일 오전 6 시에 패키지 도착**

### <a name="datetime-function-rules"></a>날짜/시간 함수 규칙

일부의 규칙이 제대로 해석 하는 모든 플랫폼에서 날짜/시간 함수. 원시 문자열 사용자에 게 표시 되 고 싶은는 다음 규칙을 충족 되지 않으면.

1. **대/소문자 구분** (모두 대문자 여야 함)
1. **공백이** 간의 합니다 `{{`, `}}`, 또는 괄호
1. **엄격한 [RFC 3389](https://tools.ietf.org/html/rfc3339) 서식** (아래 예제 참조)
1. **해야** 올바른 날짜 및 시간

### <a name="valid-formats"></a>유효한 형식

* `2017-02-14T06:08:00Z`
* `2017-02-14T06:08:00-07:00`
* `2017-02-14T06:08:00+07:00`

### <a name="date-formatting-param"></a>날짜 매개 변수 형식 지정

날짜에 대 한 선택적 매개 변수는 출력의 서식을 지정할 수 있습니다.


|       형식        |            예제            |
|---------------------|-------------------------------|
| `COMPACT` (기본값) |          "2/13/2017"          |
|       `SHORT`       |     "Mon, Feb 13th, 2017"     |
|       `LONG`        | "월요일, 2017 년 2 월 13" |

