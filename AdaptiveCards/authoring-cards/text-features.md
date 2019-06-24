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
# <a name="text-features"></a><span data-ttu-id="7f4b7-102">텍스트 기능</span><span class="sxs-lookup"><span data-stu-id="7f4b7-102">Text features</span></span>

<span data-ttu-id="7f4b7-103">`TextBlock`은 텍스트의 서식을 지정하고 텍스트를 현지화할 수 있는 몇 가지 고급 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4b7-103">`TextBlock` offers some advanced features for formatting and localizing the text.</span></span>

## <a name="markdown"></a><span data-ttu-id="7f4b7-104">Markdown</span><span class="sxs-lookup"><span data-stu-id="7f4b7-104">Markdown</span></span>
<span data-ttu-id="7f4b7-105">적응형 카드는 인라인 변경 내용을 지원하기 위해 Markdown 구문의 **하위 집합**을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4b7-105">To support inline markup, Adaptive Cards support a **subset** of Markdown syntax.</span></span>

<span data-ttu-id="7f4b7-106">_지원됨_</span><span class="sxs-lookup"><span data-stu-id="7f4b7-106">_Supported_</span></span>

| <span data-ttu-id="7f4b7-107">텍스트 스타일</span><span class="sxs-lookup"><span data-stu-id="7f4b7-107">Text Style</span></span>      | <span data-ttu-id="7f4b7-108">Markdown</span><span class="sxs-lookup"><span data-stu-id="7f4b7-108">Markdown</span></span> |
|-----------------|-----|
| <span data-ttu-id="7f4b7-109">**굵게**</span><span class="sxs-lookup"><span data-stu-id="7f4b7-109">**Bold**</span></span>        | ```**Bold**``` |
| <span data-ttu-id="7f4b7-110">_기울임꼴_</span><span class="sxs-lookup"><span data-stu-id="7f4b7-110">_Italic_</span></span>        | ```_Italic_``` |
| <span data-ttu-id="7f4b7-111">글머리 기호 목록</span><span class="sxs-lookup"><span data-stu-id="7f4b7-111">Bullet list</span></span>     | ```- Item 1\r- Item 2\r- Item 3``` | 
| <span data-ttu-id="7f4b7-112">번호가 매겨진 목록</span><span class="sxs-lookup"><span data-stu-id="7f4b7-112">Numbered list</span></span>   | ```1. Green\r2. Orange\r3. Blue``` |
| <span data-ttu-id="7f4b7-113">하이퍼링크</span><span class="sxs-lookup"><span data-stu-id="7f4b7-113">Hyperlinks</span></span>      | ```[Title](url)``` |

<span data-ttu-id="7f4b7-114">_지원 안 됨_</span><span class="sxs-lookup"><span data-stu-id="7f4b7-114">_Not supported_</span></span>

* <span data-ttu-id="7f4b7-115">헤더</span><span class="sxs-lookup"><span data-stu-id="7f4b7-115">Headers</span></span>
* <span data-ttu-id="7f4b7-116">표</span><span class="sxs-lookup"><span data-stu-id="7f4b7-116">Tables</span></span>
* <span data-ttu-id="7f4b7-117">이미지</span><span class="sxs-lookup"><span data-stu-id="7f4b7-117">Images</span></span>
* <span data-ttu-id="7f4b7-118">위의 표에 없는 항목</span><span class="sxs-lookup"><span data-stu-id="7f4b7-118">Anything not in the table above</span></span>

### <a name="markdown-example"></a><span data-ttu-id="7f4b7-119">Markdown 예제</span><span class="sxs-lookup"><span data-stu-id="7f4b7-119">Markdown Example</span></span>

<span data-ttu-id="7f4b7-120">아래 페이로드는 다음과 같은 항목을 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4b7-120">The below payload would render something like this:</span></span>

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

## <a name="datetime-formatting-and-localization"></a><span data-ttu-id="7f4b7-122">날짜/시간 형식 지정 및 지역화</span><span class="sxs-lookup"><span data-stu-id="7f4b7-122">Date/Time formatting and localization</span></span>

<span data-ttu-id="7f4b7-123">카드를 수신하는 사용자의 표준 시간대를 모르는 경우가 있으므로 적응형 카드는 대상 디바이스의 시간을 자동으로 현지화하는 `DATE()` 및 `TIME()` 형식 지정 함수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4b7-123">Sometimes you won't know the timezone of the user receiving the card, so Adaptive Cards offers `DATE()` and `TIME()` formatting functions to automatically localize the time on the target device.</span></span>

### <a name="datetime-example"></a><span data-ttu-id="7f4b7-124">날짜/시간 예</span><span class="sxs-lookup"><span data-stu-id="7f4b7-124">Date/Time Example</span></span>

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

<span data-ttu-id="7f4b7-125">위의 카드는 다음을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4b7-125">The above card will display:</span></span> 

> <span data-ttu-id="7f4b7-126">**택배가 2017년 2월 14일 화요일 오전 6:00에 도착할 예정입니다.**</span><span class="sxs-lookup"><span data-stu-id="7f4b7-126">**Your package will arrive on Tue, Feb 14th, 2017 at 6:00 AM**</span></span>

### <a name="datetime-function-rules"></a><span data-ttu-id="7f4b7-127">날짜/시간 함수 규칙</span><span class="sxs-lookup"><span data-stu-id="7f4b7-127">Date/Time function rules</span></span>

<span data-ttu-id="7f4b7-128">모든 플랫폼에서 날짜/시간 함수를 올바르게 해석하기 위한 몇 가지 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4b7-128">There are some rules to properly interpret the the date/time functions on every platform.</span></span> <span data-ttu-id="7f4b7-129">규칙이 충족되지 않으면 사용자에게 원시 문자열이 표시됩니다. 누구도 원치 않는 상황일 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7f4b7-129">If the rules aren't met then the raw string will be displayed to the user, and no one wants that.</span></span>

1. <span data-ttu-id="7f4b7-130">**대/소문자 구분**(모두 대문자여야 함)</span><span class="sxs-lookup"><span data-stu-id="7f4b7-130">**CASE SENSITIVE** (must be all caps)</span></span>
1. <span data-ttu-id="7f4b7-131">`{{`, `}}` 또는 괄호 사이에 **공백 없음**</span><span class="sxs-lookup"><span data-stu-id="7f4b7-131">**NO SPACES** between the `{{`, `}}`, or parentheses</span></span>
1. <span data-ttu-id="7f4b7-132">**엄격한 [RFC 3389](https://tools.ietf.org/html/rfc3339) 형식 지정**(아래의 예 참조)</span><span class="sxs-lookup"><span data-stu-id="7f4b7-132">**STRICT [RFC 3389](https://tools.ietf.org/html/rfc3339) FORMATTING** (See examples below)</span></span>
1. <span data-ttu-id="7f4b7-133">**유효한 날짜 및 시간**이어야 함</span><span class="sxs-lookup"><span data-stu-id="7f4b7-133">**MUST BE** a valid date and time</span></span>

### <a name="valid-formats"></a><span data-ttu-id="7f4b7-134">유효한 형식</span><span class="sxs-lookup"><span data-stu-id="7f4b7-134">Valid formats</span></span>

* `2017-02-14T06:08:00Z`
* `2017-02-14T06:08:00-07:00`
* `2017-02-14T06:08:00+07:00`

### <a name="date-formatting-param"></a><span data-ttu-id="7f4b7-135">날짜 형식 지정 매개 변수</span><span class="sxs-lookup"><span data-stu-id="7f4b7-135">Date formatting param</span></span>

<span data-ttu-id="7f4b7-136">날짜의 경우 선택적 매개 변수를 지정하여 출력 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4b7-136">For dates, an optional param may be specified to format the output.</span></span>


|       <span data-ttu-id="7f4b7-137">형식</span><span class="sxs-lookup"><span data-stu-id="7f4b7-137">Format</span></span>        |            <span data-ttu-id="7f4b7-138">예</span><span class="sxs-lookup"><span data-stu-id="7f4b7-138">Example</span></span>            |
|---------------------|-------------------------------|
| <span data-ttu-id="7f4b7-139">`COMPACT`(기본값)</span><span class="sxs-lookup"><span data-stu-id="7f4b7-139">`COMPACT` (Default)</span></span> |          <span data-ttu-id="7f4b7-140">"2017/2/13"</span><span class="sxs-lookup"><span data-stu-id="7f4b7-140">"2/13/2017"</span></span>          |
|       `SHORT`       |     <span data-ttu-id="7f4b7-141">"2017년 2월 13일 월"</span><span class="sxs-lookup"><span data-stu-id="7f4b7-141">"Mon, Feb 13th, 2017"</span></span>     |
|       `LONG`        | <span data-ttu-id="7f4b7-142">"2017년 2월 13일 월요일"</span><span class="sxs-lookup"><span data-stu-id="7f4b7-142">"Monday, February 13th, 2017"</span></span> |

