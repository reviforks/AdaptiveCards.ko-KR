---
title: 시작하기
author: matthidinger
ms.author: mahiding
ms.date: 11/9/2017
ms.topic: article
ms.openlocfilehash: 9d363da0c10b242e23d2594984292fcc1f31382f
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552685"
---
# <a name="getting-started"></a><span data-ttu-id="0820b-102">시작하기</span><span class="sxs-lookup"><span data-stu-id="0820b-102">Getting Started</span></span> 

<span data-ttu-id="0820b-103">Adaptive Card는 카드 JSON 직렬화 된 개체 모델.</span><span class="sxs-lookup"><span data-stu-id="0820b-103">An Adaptive Card is a JSON-serialized card object model.</span></span>

## <a name="adaptive-card-structure"></a><span data-ttu-id="0820b-104">적응 카드 구조</span><span class="sxs-lookup"><span data-stu-id="0820b-104">Adaptive Card structure</span></span>

<span data-ttu-id="0820b-105">카드의 기본 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-105">The basic structure of a card is as follows:</span></span>

* <span data-ttu-id="0820b-106">`AdaptiveCard` 해당 요소 구성을, 해당 작업, 어떻게 해당 음성으로 변환 되어야 합니다 및 렌더링 하는 데 필요한 스키마 버전 포함 한 AdaptiveCard 자체를 설명 하는-루트 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-106">`AdaptiveCard` - The root object describes the AdaptiveCard itself, including its element makeup, its actions, how it should be spoken, and the schema version required to render it.</span></span>
* <span data-ttu-id="0820b-107">`body` -카드의 본문으로 이루어집니다 빌딩 블록으로 알려진 `elements`합니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-107">`body` - The body of the card is made up of building-blocks known as `elements`.</span></span> <span data-ttu-id="0820b-108">다양 한 유형의 카드를 만들려면 거의 무한에 요소를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-108">Elements can be composed in nearly infinite arrangements to create many types of cards.</span></span> 
* <span data-ttu-id="0820b-109">`actions` -많은 카드는 일련의 작업에 사용자가 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-109">`actions` - Many cards have a set of actions a user may take on it.</span></span> <span data-ttu-id="0820b-110">이 속성의 맨 아래에서 "작업 모음" 렌더링 일반적으로 이러한 작업을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-110">This property describes those actions which typically get rendered in an "action bar" at the bottom.</span></span>

### <a name="example-card"></a><span data-ttu-id="0820b-111">예제에서는 카드</span><span class="sxs-lookup"><span data-stu-id="0820b-111">Example Card</span></span>

<span data-ttu-id="0820b-112">이미지 뒤에 텍스트 한 줄을 포함 하는이 샘플 카드.</span><span class="sxs-lookup"><span data-stu-id="0820b-112">This sample card which includes a single line of text followed by an image.</span></span>

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

## <a name="type-property"></a><span data-ttu-id="0820b-113">`Type` 속성</span><span class="sxs-lookup"><span data-stu-id="0820b-113">`Type` property</span></span>

<span data-ttu-id="0820b-114">모든 요소에는 `type` 해당 개체의 종류를 식별 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-114">Every element has a `type` property which identifies what kind of object it is.</span></span> <span data-ttu-id="0820b-115">위의 카드를 살펴보면 보면 두 가지 요소인 것을 `TextBlock` 및 `Image`합니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-115">Looking at the above card, you can see we have two elements, a `TextBlock` and an `Image`.</span></span>

<span data-ttu-id="0820b-116">모든 Adaptive Card 요소 **세로로** 하 고 **는 부모의 너비를 확장 하 고** (생각 `display: block` html에서).</span><span class="sxs-lookup"><span data-stu-id="0820b-116">All Adaptive Card elements **stack vertically** and **expand to the width of their parent** (think `display: block` in HTML).</span></span> <span data-ttu-id="0820b-117">사용할 수 있습니다는 `ColumnSet` 컨테이너의 side-by-side-열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-117">However, you can use a `ColumnSet` to create side-by-side columns of containers.</span></span>

## <a name="adaptive-elements"></a><span data-ttu-id="0820b-118">적응 요소</span><span class="sxs-lookup"><span data-stu-id="0820b-118">Adaptive Elements</span></span>

<span data-ttu-id="0820b-119">가장 기본적인 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-119">The most fundamental elements are:</span></span>

* <span data-ttu-id="0820b-120">**TextBlock** -텍스트의 모양을 제어 하는 속성을 사용 하 여 텍스트 블록을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-120">**TextBlock** - adds a block of text with properties to control what the text looks like</span></span>
* <span data-ttu-id="0820b-121">**이미지** -이미지의 모양을 제어 하는 속성을 사용 하 여 이미지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-121">**Image** - adds an image with properties to control what the image looks like</span></span>

## <a name="container-elements"></a><span data-ttu-id="0820b-122">컨테이너 요소</span><span class="sxs-lookup"><span data-stu-id="0820b-122">Container elements</span></span>

<span data-ttu-id="0820b-123">카드는 자식 요소의 컬렉션을 정렬 하는 컨테이너를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-123">Cards can also have containers, which arrange a collection of child elements.</span></span>

* <span data-ttu-id="0820b-124">**컨테이너** -정의 된 요소의 컬렉션</span><span class="sxs-lookup"><span data-stu-id="0820b-124">**Container** - Defines a a collection of elements</span></span>
* <span data-ttu-id="0820b-125">**ColumnSet/열** -컬렉션을 정의의 열을 각 열은 컨테이너</span><span class="sxs-lookup"><span data-stu-id="0820b-125">**ColumnSet/Column** - Defines a collection of columns, each column is a container</span></span>
* <span data-ttu-id="0820b-126">**FactSet** -팩트의 컨테이너</span><span class="sxs-lookup"><span data-stu-id="0820b-126">**FactSet** - Container of Facts</span></span>
* <span data-ttu-id="0820b-127">**ImageSet** -컨테이너의 이미지 해당 UI는 적절 한 표시할 수 있도록 사진 이미지의 컬렉션에 대 한 갤러리 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-127">**ImageSet** - Container of Images so that UI can show appropriate photo gallery experience for a collection of images.</span></span>

## <a name="input-elements"></a><span data-ttu-id="0820b-128">입력된 요소</span><span class="sxs-lookup"><span data-stu-id="0820b-128">Input elements</span></span>

<span data-ttu-id="0820b-129">입력된 요소를 사용 하면 간단한 양식을 작성 하는 네이티브 UI에 대 한 문의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-129">Input elements allow you to ask for native UI to build simple forms:</span></span>

* <span data-ttu-id="0820b-130">**Input.Text** -사용자의 텍스트 콘텐츠 가져오기</span><span class="sxs-lookup"><span data-stu-id="0820b-130">**Input.Text** - get text content from the user</span></span>
* <span data-ttu-id="0820b-131">**Input.Date** -사용자의 날짜 가져오기</span><span class="sxs-lookup"><span data-stu-id="0820b-131">**Input.Date** - get a Date from the user</span></span>
* <span data-ttu-id="0820b-132">**Input.Time** -사용자의 시간 가져오기</span><span class="sxs-lookup"><span data-stu-id="0820b-132">**Input.Time** - get a Time from the user</span></span>
* <span data-ttu-id="0820b-133">**Input.Number** -여러 사용자에서 가져오기</span><span class="sxs-lookup"><span data-stu-id="0820b-133">**Input.Number** - get a Number from the user</span></span>
* <span data-ttu-id="0820b-134">**Input.ChoiceSet** -선택 항목 집합이 사용자에 게 제공 하 고 선택</span><span class="sxs-lookup"><span data-stu-id="0820b-134">**Input.ChoiceSet** - Give the user a set of choices and have them pick</span></span>
* <span data-ttu-id="0820b-135">**Input.Toggle** -사용자에 게 두 항목 사이 단일 선택 항목을 제공 하 고 선택</span><span class="sxs-lookup"><span data-stu-id="0820b-135">**Input.Toggle** - Give the user a single choice between two items and have them pick</span></span>

## <a name="actions"></a><span data-ttu-id="0820b-136">동작</span><span class="sxs-lookup"><span data-stu-id="0820b-136">Actions</span></span>

<span data-ttu-id="0820b-137">카드에 단추를 추가 하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-137">Actions add buttons to the card.</span></span> <span data-ttu-id="0820b-138">이러한 다양 한 URL을 열거나 일부 데이터 전송 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-138">These can perform a variety of actions, like opening a URL or submitting some data.</span></span>

* <span data-ttu-id="0820b-139">**Action.OpenUrl** -보기에 대 한 외부 URL이 단추를 클릭</span><span class="sxs-lookup"><span data-stu-id="0820b-139">**Action.OpenUrl** - the button opens an external URL for viewing</span></span>
* <span data-ttu-id="0820b-140">**Action.ShowCard** -사용자에 게 표시할 하위 카드를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-140">**Action.ShowCard** - Requests a sub-card to be shown to the user.</span></span>
* <span data-ttu-id="0820b-141">**Action.Submit** -호스트 응용 프로그램에서 정의 된 몇 가지 메서드를 통해 다음에 전송 되는 개체로 수집의 모든 입력된 요소에 대 한 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-141">**Action.Submit** - Ask for all of the input elements to be gathered up into an object which is then sent to you through some method defined by the host application.</span></span>

> <span data-ttu-id="0820b-142">**예제 Action.Submit**: Skype를 사용 하 여는 Action.Submit는 보내기 Bot Framework 봇 활동 다시 사용 하 여 봇에 합니다 **값** 에 입력된 데이터의 모든 개체를 포함 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0820b-142">**Example Action.Submit**: With Skype, an Action.Submit will send a Bot Framework bot activity back to the bot with the **Value** property containing an object with all of the input data on it.</span></span>

## <a name="learn-more"></a><span data-ttu-id="0820b-143">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="0820b-143">Learn More</span></span>

* <span data-ttu-id="0820b-144">[샘플 카드 찾아보기](http://adaptivecards.io/samples/) 영감</span><span class="sxs-lookup"><span data-stu-id="0820b-144">[Browse Sample cards](http://adaptivecards.io/samples/) for inspiration</span></span>
* <span data-ttu-id="0820b-145">사용 된 [스키마 탐색기](http://adaptivecards.io/explorer) 사용 가능한 요소를 찾아보려면</span><span class="sxs-lookup"><span data-stu-id="0820b-145">Use the [Schema Explorer](http://adaptivecards.io/explorer) to browse the available elements</span></span>
* <span data-ttu-id="0820b-146">카드를 통해 빌드를 [대화형 시각화 도우미](http://adaptivecards.io/visualizer/)</span><span class="sxs-lookup"><span data-stu-id="0820b-146">Build a card using the [Interactive Visualizer](http://adaptivecards.io/visualizer/)</span></span>
* <span data-ttu-id="0820b-147">[연락](http://adaptivecards.io/connect) 피드백을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="0820b-147">[Get in touch](http://adaptivecards.io/connect) with any feedback you have</span></span>
