---
title: 텍스트 기능
author: matthidinger
ms.author: mahiding
ms.date: 11/09/2017
ms.topic: article
ms.openlocfilehash: ac8ec0c48e06377ebd17f1b31abe463c48809fe3
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2019
ms.locfileid: "59553615"
---
# <a name="text-features"></a>텍스트 기능

`TextBlock`은 텍스트의 서식을 지정하고 텍스트를 현지화할 수 있는 몇 가지 고급 기능을 제공합니다.

## <a name="markdown"></a>Markdown
적응형 카드는 인라인 변경 내용을 지원하기 위해 Markdown 구문의 **하위 집합**을 지원합니다.

_지원됨_

| 텍스트 스타일      | Markdown |
|-----------------|-----|
| **굵게**        | ```**Bold**``` |
| _기울임꼴_        | ```_Italic_``` |
| 글머리 기호 목록     | ```- Item 1\r- Item 2\r- Item 3``` | 
| 번호가 매겨진 목록   | ```1. Green\r2. Orange\r3. Blue``` |
| 하이퍼링크      | ```[Title](url)``` |

_지원 안 됨_

* 헤더
* 표
* 이미지
* 위의 표에 없는 항목

### <a name="markdown-example"></a>Markdown 예제

아래 페이로드는 다음과 같은 항목을 렌더링합니다.

![Markdown 스크린샷](media/text-features/markdown.png)

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

## <a name="datetime-formatting-and-localization"></a>날짜/시간 형식 지정 및 지역화

카드를 수신하는 사용자의 표준 시간대를 모르는 경우가 있으므로 적응형 카드는 대상 디바이스의 시간을 자동으로 현지화하는 `DATE()` 및 `TIME()` 형식 지정 함수를 제공합니다.

### <a name="datetime-example"></a>날짜/시간 예

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

위의 카드는 다음을 표시합니다. 

> **택배가 2017년 2월 14일 화요일 오전 6:00에 도착할 예정입니다.**

### <a name="datetime-function-rules"></a>날짜/시간 함수 규칙

모든 플랫폼에서 날짜/시간 함수를 올바르게 해석하기 위한 몇 가지 규칙이 있습니다. 규칙이 충족되지 않으면 사용자에게 원시 문자열이 표시됩니다. 누구도 원치 않는 상황일 것입니다.

1. **대/소문자 구분**(모두 대문자여야 함)
1. `{{`, `}}` 또는 괄호 사이에 **공백 없음**
1. **엄격한 [RFC 3389](https://tools.ietf.org/html/rfc3339) 형식 지정**(아래의 예 참조)
1. **유효한 날짜 및 시간**이어야 함

### <a name="valid-formats"></a>유효한 형식

* `2017-02-14T06:08:00Z`
* `2017-02-14T06:08:00-07:00`
* `2017-02-14T06:08:00+07:00`

### <a name="date-formatting-param"></a>날짜 형식 지정 매개 변수

날짜의 경우 선택적 매개 변수를 지정하여 출력 형식을 지정할 수 있습니다.


|       형식        |            예            |
|---------------------|-------------------------------|
| `COMPACT`(기본값) |          "2017/2/13"          |
|       `SHORT`       |     "2017년 2월 13일 월"     |
|       `LONG`        | "2017년 2월 13일 월요일" |

