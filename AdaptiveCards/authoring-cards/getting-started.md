---
title: 시작
author: matthidinger
ms.author: mahiding
ms.date: 11/9/2017
ms.topic: article
ms.openlocfilehash: 9d363da0c10b242e23d2594984292fcc1f31382f
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2019
ms.locfileid: "59552685"
---
# <a name="getting-started"></a><span data-ttu-id="b0ffe-102">시작</span><span class="sxs-lookup"><span data-stu-id="b0ffe-102">Getting Started</span></span> 

<span data-ttu-id="b0ffe-103">적응형 카드는 JSON 직렬화된 카드 개체 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-103">An Adaptive Card is a JSON-serialized card object model.</span></span>

## <a name="adaptive-card-structure"></a><span data-ttu-id="b0ffe-104">적응형 카드 구조</span><span class="sxs-lookup"><span data-stu-id="b0ffe-104">Adaptive Card structure</span></span>

<span data-ttu-id="b0ffe-105">카드의 기본 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-105">The basic structure of a card is as follows:</span></span>

* <span data-ttu-id="b0ffe-106">`AdaptiveCard` - 루트 개체는 적응형 카드의 요소 구성, 동작, 말하기 방식, 렌더링하는 데 필요한 스키마 버전을 포함한 적응형 카드 자체를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-106">`AdaptiveCard` - The root object describes the AdaptiveCard itself, including its element makeup, its actions, how it should be spoken, and the schema version required to render it.</span></span>
* <span data-ttu-id="b0ffe-107">`body` - 카드의 본문은 `elements`로 알려진 빌딩 블록으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-107">`body` - The body of the card is made up of building-blocks known as `elements`.</span></span> <span data-ttu-id="b0ffe-108">요소를 거의 무한의 정렬로 구성하여 여러 종류의 카드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-108">Elements can be composed in nearly infinite arrangements to create many types of cards.</span></span> 
* <span data-ttu-id="b0ffe-109">`actions` - 여러 카드에 사용자가 취할 수 있는 일련의 동작이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-109">`actions` - Many cards have a set of actions a user may take on it.</span></span> <span data-ttu-id="b0ffe-110">이 속성은 일반적으로 하단의 "작업 모음"에서 렌더링되는 작업을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-110">This property describes those actions which typically get rendered in an "action bar" at the bottom.</span></span>

### <a name="example-card"></a><span data-ttu-id="b0ffe-111">카드 예</span><span class="sxs-lookup"><span data-stu-id="b0ffe-111">Example Card</span></span>

<span data-ttu-id="b0ffe-112">텍스트 한 줄 다음에 이미지가 오는 이 샘플 카드입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-112">This sample card which includes a single line of text followed by an image.</span></span>

```json
{
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Here is a ninja cat"
        },
        {
            "type": "Image",
            "url": "http://adaptivecards.io/content/cats/1.png"
        }
    ]
}
```

## <a name="type-property"></a><span data-ttu-id="b0ffe-113">`Type` 속성</span><span class="sxs-lookup"><span data-stu-id="b0ffe-113">`Type` property</span></span>

<span data-ttu-id="b0ffe-114">각 요소에는 개체의 유형을 식별하는 `type` 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-114">Every element has a `type` property which identifies what kind of object it is.</span></span> <span data-ttu-id="b0ffe-115">위의 카드를 보면 `TextBlock` 및 `Image`라는 두 가지 요소가 있는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-115">Looking at the above card, you can see we have two elements, a `TextBlock` and an `Image`.</span></span>

<span data-ttu-id="b0ffe-116">모든 적응형 카드 요소는 **가로로 스택되며** **부모 항목의 너비에 맞게 확장**됩니다(예: HTML의 `display: block`).</span><span class="sxs-lookup"><span data-stu-id="b0ffe-116">All Adaptive Card elements **stack vertically** and **expand to the width of their parent** (think `display: block` in HTML).</span></span> <span data-ttu-id="b0ffe-117">하지만 `ColumnSet`를 사용하여 컨테이너 열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-117">However, you can use a `ColumnSet` to create side-by-side columns of containers.</span></span>

## <a name="adaptive-elements"></a><span data-ttu-id="b0ffe-118">적응형 요소</span><span class="sxs-lookup"><span data-stu-id="b0ffe-118">Adaptive Elements</span></span>

<span data-ttu-id="b0ffe-119">가장 기본적인 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-119">The most fundamental elements are:</span></span>

* <span data-ttu-id="b0ffe-120">**TextBlock** - 텍스트의 모양을 제어하는 속성을 사용하여 텍스트 블록을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-120">**TextBlock** - adds a block of text with properties to control what the text looks like</span></span>
* <span data-ttu-id="b0ffe-121">**Image** - 이미지의 모양을 제어하는 속성을 사용하여 이미지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-121">**Image** - adds an image with properties to control what the image looks like</span></span>

## <a name="container-elements"></a><span data-ttu-id="b0ffe-122">컨테이너 요소</span><span class="sxs-lookup"><span data-stu-id="b0ffe-122">Container elements</span></span>

<span data-ttu-id="b0ffe-123">카드에 자식 요소의 컬렉션을 정렬하는 컨테이너가 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-123">Cards can also have containers, which arrange a collection of child elements.</span></span>

* <span data-ttu-id="b0ffe-124">**Container** - 요소 컬렉션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-124">**Container** - Defines a a collection of elements</span></span>
* <span data-ttu-id="b0ffe-125">**ColumnSet/Column** - 열 컬렉션을 정의하며, 각 열이 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-125">**ColumnSet/Column** - Defines a collection of columns, each column is a container</span></span>
* <span data-ttu-id="b0ffe-126">**FactSet** - 팩트의 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-126">**FactSet** - Container of Facts</span></span>
* <span data-ttu-id="b0ffe-127">**ImageSet** - 이미지 컬렉션의 적절한 사진 갤러리 환경이 UI에 표시될 수 있도록 하는 이미지 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-127">**ImageSet** - Container of Images so that UI can show appropriate photo gallery experience for a collection of images.</span></span>

## <a name="input-elements"></a><span data-ttu-id="b0ffe-128">입력 요소</span><span class="sxs-lookup"><span data-stu-id="b0ffe-128">Input elements</span></span>

<span data-ttu-id="b0ffe-129">입력 요소를 사용하여 네이티브 UI에 간단한 양식을 빌드하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-129">Input elements allow you to ask for native UI to build simple forms:</span></span>

* <span data-ttu-id="b0ffe-130">**Input.Text** - 사용자로부터 텍스트 콘텐츠를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-130">**Input.Text** - get text content from the user</span></span>
* <span data-ttu-id="b0ffe-131">**Input.Date** - 사용자로부터 날짜를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-131">**Input.Date** - get a Date from the user</span></span>
* <span data-ttu-id="b0ffe-132">**Input.Time** - 사용자로부터 시간을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-132">**Input.Time** - get a Time from the user</span></span>
* <span data-ttu-id="b0ffe-133">**Input.Number** - 사용자로부터 숫자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-133">**Input.Number** - get a Number from the user</span></span>
* <span data-ttu-id="b0ffe-134">**Input.ChoiceSet** - 사용자에게 일련의 옵션을 제공하고 선택하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-134">**Input.ChoiceSet** - Give the user a set of choices and have them pick</span></span>
* <span data-ttu-id="b0ffe-135">**Input.Toggle** - 사용자에게 두 가지 옵션을 제공하고 선택하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-135">**Input.Toggle** - Give the user a single choice between two items and have them pick</span></span>

## <a name="actions"></a><span data-ttu-id="b0ffe-136">조치</span><span class="sxs-lookup"><span data-stu-id="b0ffe-136">Actions</span></span>

<span data-ttu-id="b0ffe-137">카드에 단추를 추가하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-137">Actions add buttons to the card.</span></span> <span data-ttu-id="b0ffe-138">URL 열기 또는 일부 데이터 제출과 같은 다양한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-138">These can perform a variety of actions, like opening a URL or submitting some data.</span></span>

* <span data-ttu-id="b0ffe-139">**Action.OpenUrl** - 단추를 누르면 외부 URL이 열리고 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-139">**Action.OpenUrl** - the button opens an external URL for viewing</span></span>
* <span data-ttu-id="b0ffe-140">**Action.ShowCard** - 사용자에게 표시할 하위 카드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-140">**Action.ShowCard** - Requests a sub-card to be shown to the user.</span></span>
* <span data-ttu-id="b0ffe-141">**Action.Submit** - 모든 입력 요소를 하나의 개체로 합친 후 호스트 애플리케이션이 정의한 일부 메서드를 통해 사용자에게 전송하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-141">**Action.Submit** - Ask for all of the input elements to be gathered up into an object which is then sent to you through some method defined by the host application.</span></span>

> <span data-ttu-id="b0ffe-142">**Example Action.Submit**: Action.Submit가 Skype를 통해 모든 입력 데이터가 합쳐진 개체가 포함된 **Value** 속성을 사용하여 Bot Framework 봇 활동 작업을 봇에 다시 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-142">**Example Action.Submit**: With Skype, an Action.Submit will send a Bot Framework bot activity back to the bot with the **Value** property containing an object with all of the input data on it.</span></span>

## <a name="learn-more"></a><span data-ttu-id="b0ffe-143">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="b0ffe-143">Learn More</span></span>

* <span data-ttu-id="b0ffe-144">영감을 얻기 위해 [샘플 카드 찾아보기](http://adaptivecards.io/samples/)</span><span class="sxs-lookup"><span data-stu-id="b0ffe-144">[Browse Sample cards](http://adaptivecards.io/samples/) for inspiration</span></span>
* <span data-ttu-id="b0ffe-145">[스키마 탐색기](http://adaptivecards.io/explorer)를 사용하여 사용 가능한 요소 찾아보기</span><span class="sxs-lookup"><span data-stu-id="b0ffe-145">Use the [Schema Explorer](http://adaptivecards.io/explorer) to browse the available elements</span></span>
* <span data-ttu-id="b0ffe-146">[대화형 비주얼라이저](http://adaptivecards.io/visualizer/)를 사용하여 카드 작성</span><span class="sxs-lookup"><span data-stu-id="b0ffe-146">Build a card using the [Interactive Visualizer](http://adaptivecards.io/visualizer/)</span></span>
* <span data-ttu-id="b0ffe-147">모든 피드백과 [연결 유지](http://adaptivecards.io/connect)</span><span class="sxs-lookup"><span data-stu-id="b0ffe-147">[Get in touch](http://adaptivecards.io/connect) with any feedback you have</span></span>
