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
# <a name="text-features"></a><span data-ttu-id="50fd2-102">텍스트 기능</span><span class="sxs-lookup"><span data-stu-id="50fd2-102">Text features</span></span>

<span data-ttu-id="50fd2-103">`TextBlock` 서식 지정 및 텍스트를 지역화에 대 한 몇 가지 고급 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="50fd2-103">`TextBlock` offers some advanced features for formatting and localizing the text.</span></span>

## <a name="markdown"></a><span data-ttu-id="50fd2-104">Markdown</span><span class="sxs-lookup"><span data-stu-id="50fd2-104">Markdown</span></span>
<span data-ttu-id="50fd2-105">Adaptive Card 지원를 지원 하기 위해 인라인 태그를 **하위 집합** Markdown 구문의 합니다.</span><span class="sxs-lookup"><span data-stu-id="50fd2-105">To support inline markup, Adaptive Cards support a **subset** of Markdown syntax.</span></span>

<span data-ttu-id="50fd2-106">_지원_</span><span class="sxs-lookup"><span data-stu-id="50fd2-106">_Supported_</span></span>

| <span data-ttu-id="50fd2-107">텍스트 스타일</span><span class="sxs-lookup"><span data-stu-id="50fd2-107">Text Style</span></span>      | <span data-ttu-id="50fd2-108">Markdown</span><span class="sxs-lookup"><span data-stu-id="50fd2-108">Markdown</span></span> |
|-----------------|-----|
| <span data-ttu-id="50fd2-109">**굵게**</span><span class="sxs-lookup"><span data-stu-id="50fd2-109">**Bold**</span></span>        | ```**Bold**``` |
| <span data-ttu-id="50fd2-110">_기울임꼴_</span><span class="sxs-lookup"><span data-stu-id="50fd2-110">_Italic_</span></span>        | ```_Italic_``` |
| <span data-ttu-id="50fd2-111">글머리 기호 목록</span><span class="sxs-lookup"><span data-stu-id="50fd2-111">Bullet list</span></span>     | ```- Item 1\r- Item 2\r- Item 3``` | 
| <span data-ttu-id="50fd2-112">번호가 매겨진 목록</span><span class="sxs-lookup"><span data-stu-id="50fd2-112">Numbered list</span></span>   | ```1. Green\r2. Orange\r3. Blue``` |
| <span data-ttu-id="50fd2-113">하이퍼링크</span><span class="sxs-lookup"><span data-stu-id="50fd2-113">Hyperlinks</span></span>      | ```[Title](url)``` |

<span data-ttu-id="50fd2-114">_지원 되지 않음_</span><span class="sxs-lookup"><span data-stu-id="50fd2-114">_Not supported_</span></span>

* <span data-ttu-id="50fd2-115">헤더</span><span class="sxs-lookup"><span data-stu-id="50fd2-115">Headers</span></span>
* <span data-ttu-id="50fd2-116">테이블</span><span class="sxs-lookup"><span data-stu-id="50fd2-116">Tables</span></span>
* <span data-ttu-id="50fd2-117">이미지</span><span class="sxs-lookup"><span data-stu-id="50fd2-117">Images</span></span>
* <span data-ttu-id="50fd2-118">위의 테이블에 없는 항목</span><span class="sxs-lookup"><span data-stu-id="50fd2-118">Anything not in the table above</span></span>

### <a name="markdown-example"></a><span data-ttu-id="50fd2-119">Markdown 예제</span><span class="sxs-lookup"><span data-stu-id="50fd2-119">Markdown Example</span></span>

<span data-ttu-id="50fd2-120">페이로드 아래은 다음과 같이 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50fd2-120">The below payload would render something like this:</span></span>

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

## <a name="datetime-formatting-and-localization"></a><span data-ttu-id="50fd2-122">날짜/시간 형식 및 지역화</span><span class="sxs-lookup"><span data-stu-id="50fd2-122">Date/Time formatting and localization</span></span>

<span data-ttu-id="50fd2-123">Adaptive Card 제공 되므로 카드를 수신 하는 사용자의 표준 시간대를 알 수 없습니다 경우에 따라 `DATE()` 고 `TIME()` 자동으로 대상 장치에서 시간을 지역화 하는 함수를 서식 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="50fd2-123">Sometimes you won't know the timezone of the user receiving the card, so Adaptive Cards offers `DATE()` and `TIME()` formatting functions to automatically localize the time on the target device.</span></span>

### <a name="datetime-example"></a><span data-ttu-id="50fd2-124">날짜/시간 예제</span><span class="sxs-lookup"><span data-stu-id="50fd2-124">Date/Time Example</span></span>

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

<span data-ttu-id="50fd2-125">위의 카드 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50fd2-125">The above card will display:</span></span> 

> <span data-ttu-id="50fd2-126">**2017 년 2 월 14, 화요일 오전 6 시에 패키지 도착**</span><span class="sxs-lookup"><span data-stu-id="50fd2-126">**Your package will arrive on Tue, Feb 14th, 2017 at 6:00 AM**</span></span>

### <a name="datetime-function-rules"></a><span data-ttu-id="50fd2-127">날짜/시간 함수 규칙</span><span class="sxs-lookup"><span data-stu-id="50fd2-127">Date/Time function rules</span></span>

<span data-ttu-id="50fd2-128">일부의 규칙이 제대로 해석 하는 모든 플랫폼에서 날짜/시간 함수.</span><span class="sxs-lookup"><span data-stu-id="50fd2-128">There are some rules to properly interpret the the date/time functions on every platform.</span></span> <span data-ttu-id="50fd2-129">원시 문자열 사용자에 게 표시 되 고 싶은는 다음 규칙을 충족 되지 않으면.</span><span class="sxs-lookup"><span data-stu-id="50fd2-129">If the rules aren't met then the raw string will be displayed to the user, and no one wants that.</span></span>

1. <span data-ttu-id="50fd2-130">**대/소문자 구분** (모두 대문자 여야 함)</span><span class="sxs-lookup"><span data-stu-id="50fd2-130">**CASE SENSITIVE** (must be all caps)</span></span>
1. <span data-ttu-id="50fd2-131">**공백이** 간의 합니다 `{{`, `}}`, 또는 괄호</span><span class="sxs-lookup"><span data-stu-id="50fd2-131">**NO SPACES** between the `{{`, `}}`, or parentheses</span></span>
1. <span data-ttu-id="50fd2-132">**엄격한 [RFC 3389](https://tools.ietf.org/html/rfc3339) 서식** (아래 예제 참조)</span><span class="sxs-lookup"><span data-stu-id="50fd2-132">**STRICT [RFC 3389](https://tools.ietf.org/html/rfc3339) FORMATTING** (See examples below)</span></span>
1. <span data-ttu-id="50fd2-133">**해야** 올바른 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="50fd2-133">**MUST BE** a valid date and time</span></span>

### <a name="valid-formats"></a><span data-ttu-id="50fd2-134">유효한 형식</span><span class="sxs-lookup"><span data-stu-id="50fd2-134">Valid formats</span></span>

* `2017-02-14T06:08:00Z`
* `2017-02-14T06:08:00-07:00`
* `2017-02-14T06:08:00+07:00`

### <a name="date-formatting-param"></a><span data-ttu-id="50fd2-135">날짜 매개 변수 형식 지정</span><span class="sxs-lookup"><span data-stu-id="50fd2-135">Date formatting param</span></span>

<span data-ttu-id="50fd2-136">날짜에 대 한 선택적 매개 변수는 출력의 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50fd2-136">For dates, an optional param may be specified to format the output.</span></span>


|       <span data-ttu-id="50fd2-137">형식</span><span class="sxs-lookup"><span data-stu-id="50fd2-137">Format</span></span>        |            <span data-ttu-id="50fd2-138">예제</span><span class="sxs-lookup"><span data-stu-id="50fd2-138">Example</span></span>            |
|---------------------|-------------------------------|
| <span data-ttu-id="50fd2-139">`COMPACT` (기본값)</span><span class="sxs-lookup"><span data-stu-id="50fd2-139">`COMPACT` (Default)</span></span> |          <span data-ttu-id="50fd2-140">"2/13/2017"</span><span class="sxs-lookup"><span data-stu-id="50fd2-140">"2/13/2017"</span></span>          |
|       `SHORT`       |     <span data-ttu-id="50fd2-141">"Mon, Feb 13th, 2017"</span><span class="sxs-lookup"><span data-stu-id="50fd2-141">"Mon, Feb 13th, 2017"</span></span>     |
|       `LONG`        | <span data-ttu-id="50fd2-142">"월요일, 2017 년 2 월 13"</span><span class="sxs-lookup"><span data-stu-id="50fd2-142">"Monday, February 13th, 2017"</span></span> |

