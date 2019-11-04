---
title: 적응 카드 템플릿 언어
author: matthidinger
ms.author: mahiding
ms.date: 08/01/2019
ms.topic: article
ms.openlocfilehash: b99a2905fb000653b7ee75204221b832a2b5a907
ms.sourcegitcommit: ce044dc969d9b9c47a52bd361bfe2b746071913b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72917130"
---
# <a name="adaptive-cards-template-language"></a><span data-ttu-id="0ab11-102">적응 카드 템플릿 언어</span><span class="sxs-lookup"><span data-stu-id="0ab11-102">Adaptive Cards Template Language</span></span>

<span data-ttu-id="0ab11-103">템플릿을 사용 하면 적응 카드의 **레이아웃** 에서 **데이터** 를 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-103">Templating enables the separation of **data** from **layout** in your Adaptive Card.</span></span> <span data-ttu-id="0ab11-104">템플릿 언어는 템플릿을 작성 하는 데 사용 되는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-104">The template langauge is the syntax used to author a template.</span></span> 

> <span data-ttu-id="0ab11-105">[적응 카드 템플릿 개요](index.md) 는이 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ab11-105">Please read this for an [overview of Adaptive Card Templating](index.md)</span></span>

> [!IMPORTANT] 
> 
> <span data-ttu-id="0ab11-106">이러한 기능은 **미리 보기 상태이며 변경될 수 있습니다**.</span><span class="sxs-lookup"><span data-stu-id="0ab11-106">These features are **in preview and subject to change**.</span></span> <span data-ttu-id="0ab11-107">사용자 의견은 언제나 환영이며, **사용자**에게 필요한 기능을 제공하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-107">Your feedback is not only welcome, but  critical to ensure we deliver the features **you** need.</span></span>

<span data-ttu-id="0ab11-108">템플릿을 제작할 때 템플릿 [sdk](sdk.md)를 사용 하 여 `AdaptiveCard` 페이로드를 사용 하거나 런타임에 데이터를 인라인으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-108">When authoring a template you can specify the data inline with the `AdaptiveCard` payload, or at runtime using the [Templating SDKs](sdk.md).</span></span>

## <a name="specify-data-within-the-card"></a><span data-ttu-id="0ab11-109">카드 내에서 데이터 지정</span><span class="sxs-lookup"><span data-stu-id="0ab11-109">Specify data within the card</span></span>

<span data-ttu-id="0ab11-110">카드 페이로드 내에서 직접 데이터를 제공 하려면 `AdaptiveCard`에 `$data` 특성을 추가 하면 됩니다 (아래 참조).</span><span class="sxs-lookup"><span data-stu-id="0ab11-110">To provide data directly within the card payload, simply add a `$data` attribute to your `AdaptiveCard` (seen below).</span></span>

## <a name="binding-to-the-data"></a><span data-ttu-id="0ab11-111">데이터에 바인딩</span><span class="sxs-lookup"><span data-stu-id="0ab11-111">Binding to the data</span></span>

<span data-ttu-id="0ab11-112">카드의 `body` 또는 `actions` 내에서 데이터에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-112">You can bind to the data within the `body` or `actions` of the card.</span></span>

* <span data-ttu-id="0ab11-113">바인딩 구문은 `{` 시작 하 여 `}`로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-113">Binding syntax starts with `{` and ends with `}`.</span></span> <span data-ttu-id="0ab11-114">예: `{myProperty}`</span><span class="sxs-lookup"><span data-stu-id="0ab11-114">E.g., `{myProperty}`</span></span>
* <span data-ttu-id="0ab11-115">하위 개체에 액세스 하는 점 표기법</span><span class="sxs-lookup"><span data-stu-id="0ab11-115">Dot-notation to access sub-objects</span></span>
* <span data-ttu-id="0ab11-116">배열에서 키 또는 항목으로 속성을 검색 하는 인덱서 구문</span><span class="sxs-lookup"><span data-stu-id="0ab11-116">Indexer syntax to retrieve properties by key or items in an array</span></span>
* <span data-ttu-id="0ab11-117">딥 계층에 대 한 정상적인 null 처리</span><span class="sxs-lookup"><span data-stu-id="0ab11-117">Graceful null handling for deep hierarchies</span></span>
* <span data-ttu-id="0ab11-118">*곧 제공 될 이스케이프 구문 설명서*</span><span class="sxs-lookup"><span data-stu-id="0ab11-118">*Escape syntax documentation to come soon*</span></span>

```json
{
    "type": "AdaptiveCard",
    "$data": {
        "employee": {
            "name": "Matt",
            "manager": { "name": "Thomas" },
            "peers": [{
                "name": "Andrew" 
            }, { 
                "name": "Lei"
            }, { 
                "name": "Mary Anne"
            }, { 
                "name": "Adam"
            }]
        }
    },
    "body": [
        {
            "type": "TextBlock",
            "text": "Hi {employee.name}! Here's a bit about your org..."
        },
        {
            "type": "TextBlock",
            "text": "Your manager is: {employee.manager.name}"
        },
        {
            "type": "TextBlock",
            "text": "3 of your peers are: {employee.peers[0].name}, {employee.peers[1].name}, {employee.peers[2].name}"
        }
    ]
}
```

## <a name="separating-the-template-from-the-data"></a><span data-ttu-id="0ab11-119">데이터에서 템플릿 구분</span><span class="sxs-lookup"><span data-stu-id="0ab11-119">Separating the template from the data</span></span>

<span data-ttu-id="0ab11-120">또는 데이터를 포함 하지 않고 다시 사용할 수 있는 카드 "템플릿"을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-120">Alternatively (and more likely), you will create a re-usable card "template" without including the data.</span></span> <span data-ttu-id="0ab11-121">이 템플릿을 파일로 저장 하 고 소스 제어에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-121">This template could be stored as a file and added to source control.</span></span>

<span data-ttu-id="0ab11-122">**EmployeeCardTemplate.json**</span><span class="sxs-lookup"><span data-stu-id="0ab11-122">**EmployeeCardTemplate.json**</span></span>

```json
{
    "type": "AdaptivCard",
    "body": [
        {
            "type": "TextBlock",
            "text": "Hi {employee.name}! Here's a bit about your org..."
        },
        {
            "type": "TextBlock",
            "text": "Your manager is: {employee.manager.name}"
        },
        {
            "type": "TextBlock",
            "text": "3 of your peers are: {employee.peers[0].name}, {employee.peers[1].name}, {employee.peers[2].name}"
        }
    ]
}
```

<span data-ttu-id="0ab11-123">그런 다음 [템플릿 sdk](sdk.md)를 사용 하 여 런타임에 데이터를 로드 하 고 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-123">Then load it up and provide the data at runtime using the [Templating SDKs](sdk.md).</span></span>

<span data-ttu-id="0ab11-124">**JavaScript 예제**</span><span class="sxs-lookup"><span data-stu-id="0ab11-124">**JavaScript example**</span></span>

<span data-ttu-id="0ab11-125">[Adaptivecards](https://npmjs.com/package/adaptivecards-templating) 패키지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-125">Using the [adaptivecards-templating](https://npmjs.com/package/adaptivecards-templating) package.</span></span>

```js
var template = new ACData.Template({ 
    // EmployeeCardTemplate goes here
});

// Specify data at runtime
var dataContext = new ACData.EvaluationContext();
dataContext.$root = {
    "employee": {
        "name": "Matt",
        "manager": { "name": "Thomas" },
        "peers": [{
            "name": "Andrew" 
        }, { 
            "name": "Lei"
        }, { 
            "name": "Mary Anne"
        }, { 
            "name": "Adam"
        }]
    }
};

var card = template.expand(dataContext);
// Now you have an AdaptiveCard ready to render!
```

## <a name="designer-support"></a><span data-ttu-id="0ab11-126">디자이너 지원</span><span class="sxs-lookup"><span data-stu-id="0ab11-126">Designer Support</span></span>

<span data-ttu-id="0ab11-127">적응 카드 디자이너가 템플릿을 지원 하도록 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-127">The Adaptive Card Designer has been updated to support templating.</span></span> 

> <span data-ttu-id="0ab11-128">https://vnext.adaptivecards.io/designer 에서 "vnext" 미리 보기를 사용해 보세요.  **[](https://vnext.adaptivecards.io/designer)**</span><span class="sxs-lookup"><span data-stu-id="0ab11-128">Try out a "vnext" preview at: **[https://vnext.adaptivecards.io/designer](https://vnext.adaptivecards.io/designer)**</span></span>

<span data-ttu-id="0ab11-129">[![이미지](https://user-images.githubusercontent.com/1432195/53214462-88d46980-3601-11e9-908d-253a1bb940a8.png)](http://vnext.adaptivecards.io/designer)</span><span class="sxs-lookup"><span data-stu-id="0ab11-129">[![image](https://user-images.githubusercontent.com/1432195/53214462-88d46980-3601-11e9-908d-253a1bb940a8.png)](http://vnext.adaptivecards.io/designer)</span></span>

 
<span data-ttu-id="0ab11-130">이 "vnext" URL은 버그를 포함 하 고 자주 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-130">This "vnext" URL is going to have bugs and will deploy frequently.</span></span> <span data-ttu-id="0ab11-131">**캐시를 지워** 최신이 있는지 확인 하 고, 버그를 찾았으면 알려 주세요.</span><span class="sxs-lookup"><span data-stu-id="0ab11-131">**Clear your cache** to make sure you have the latest, and if you find bugs please let us know!</span></span>

* <span data-ttu-id="0ab11-132">**샘플 데이터 편집기** -"미리 보기 모드"에 있는 경우 데이터 바인딩된 카드를 보려면 여기에 샘플 데이터를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-132">**Sample Data Editor** - Specify sample data here to view the data-bound card when in "Preview Mode."</span></span> <span data-ttu-id="0ab11-133">이 창에는 기존 샘플 데이터의 데이터 구조를 채우는 작은 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-133">There is a small button in this pane to populate the Data Structure from the existing sample data.</span></span>
* <span data-ttu-id="0ab11-134">**데이터 구조** -샘플 데이터의 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-134">**Data Structure** - This is the structure of your sample data.</span></span> <span data-ttu-id="0ab11-135">필드를 디자인 화면으로 끌어 해당 필드에 대 한 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-135">Fields can be dragged onto the design surface to create a binding to them</span></span> 
* <span data-ttu-id="0ab11-136">**미리 보기 모드** -도구 모음 단추를 눌러 편집 환경과 샘플 데이터 미리 보기 환경 사이를 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-136">**Preview Mode** - Press the toolbar button to toggle between the edit-experience and the sample-data-preview experience</span></span>
* <span data-ttu-id="0ab11-137">**샘플 열기** -이 단추를 클릭 하 여 다양 한 샘플 페이로드를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-137">**Open Sample** - click this button to open various sample payloads</span></span>

## <a name="advanced-binding"></a><span data-ttu-id="0ab11-138">고급 바인딩</span><span class="sxs-lookup"><span data-stu-id="0ab11-138">Advanced binding</span></span>

### <a name="binding-scopes"></a><span data-ttu-id="0ab11-139">바인딩 범위</span><span class="sxs-lookup"><span data-stu-id="0ab11-139">Binding scopes</span></span>

<span data-ttu-id="0ab11-140">다양 한 바인딩 범위에 액세스 하기 위한 몇 가지 예약 된 키워드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-140">There are a few reserved keywords to access various binding scopes.</span></span> 

<span data-ttu-id="0ab11-141">*참고:* 이러한 일부는 미리 보기에서 구현 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-141">*Note:* not all of these are implemented in the preview.</span></span>

```json
{
    "{<property>}": "Implicitly binds to `$data.<property>`",
    "$data": "The current data object",
    "$root": "The root data object. Useful when iterating to escape to parent object",
    "$index": "The current index when iterating",
    "$host": "Access properties of the host *(not working yet)*"
}
```

### <a name="assigning-a-data-context-to-elements"></a><span data-ttu-id="0ab11-142">요소에 데이터 컨텍스트 할당</span><span class="sxs-lookup"><span data-stu-id="0ab11-142">Assigning a data context to elements</span></span>

<span data-ttu-id="0ab11-143">모든 요소에 "데이터 컨텍스트"를 할당 하려면 `$data` 특성을 요소에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-143">To assign a "data context" to any element add a `$data` attribute to the element.</span></span>

```json
{
    "type": "Container",
    "$data": "{mySubObject}",
    "items": [
        {
            "type": "TextBlock",
            "text": "This TextBlock is now scoped directly to 'mySubObject': {mySubObjectProperty}"
        },
        {
            "type": "TextBlock",
            "text": "To break-out and access the root data, use: {$root}"
        }
    ]
}
```

## <a name="repeating-items-in-an-array"></a><span data-ttu-id="0ab11-144">배열의 반복 항목</span><span class="sxs-lookup"><span data-stu-id="0ab11-144">Repeating items in an array</span></span>

<span data-ttu-id="0ab11-145">이 부분은 약간의 "진한 매직"입니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-145">This part is a bit of "dark magic".</span></span> <span data-ttu-id="0ab11-146">사용자 의견을 환영 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-146">Feedback welcome.</span></span>

* <span data-ttu-id="0ab11-147">개체의 `$data` 속성이 **배열로**설정 되어 있으면 **배열의 각 항목에 대해 개체 자체가 반복 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="0ab11-147">If the objects' `$data` property is set to an **array**, then the **object itself will be repeated for each item in the array.**</span></span> 
* <span data-ttu-id="0ab11-148">반복 될 때 속성 바인딩에 사용 되는 `$data`는 배열 내의 **개별 항목** 으로 범위가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-148">As it is being repeated, `$data` used in property bindings are scoped to the **individual item** within the array.</span></span>

<span data-ttu-id="0ab11-149">예를 들어 아래 `TextBlock`는 배열 `$data` 이므로 3 번 반복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-149">For example, the `TextBlock` below will be repeated 3 times since it's `$data` is an array.</span></span> <span data-ttu-id="0ab11-150">`text` 속성이 배열 내 개별 개체의 `name` 속성에 바인딩되는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-150">Notice how the `text` property is bound to the `name` property of an individual object within the array.</span></span> 

```json
{
    "type": "Container",
    "items": [
        {
            "type": "TextBlock",
            "$data": [
                { "name": "Matt" }, 
                { "name": "David" }, 
                { "name": "Thomas" }
            ],
            "text": "{name}"
        }
    ]
}
```

<span data-ttu-id="0ab11-151">**결과:**</span><span class="sxs-lookup"><span data-stu-id="0ab11-151">**Resulting in:**</span></span>

```json
{
    "type": "Container",
    "items": [ 
        {
            "type": "TextBlock",
            "text": "Matt"
        },
        {
            "type": "TextBlock",
            "text": "David"
        }
        {
            "type": "TextBlock",
            "text": "Thomas"
        }
    ]
}
```

## <a name="functions"></a><span data-ttu-id="0ab11-152">함수</span><span class="sxs-lookup"><span data-stu-id="0ab11-152">Functions</span></span>

<span data-ttu-id="0ab11-153">일부 도우미 함수 없이 템플릿 언어가 완전 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-153">No templating language is complete without some helper functions.</span></span> <span data-ttu-id="0ab11-154">모든 SDK에서 작동 하는 표준 함수 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-154">We will provide a standard set of functions that work on every SDK.</span></span> 

<span data-ttu-id="0ab11-155">여기에 나와 있는 구문은 계속 해 서 계속 해 서 제공 될 것 이므로 곧 다시 확인 하세요. 여기서는 계획 중인 작업을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-155">The syntax here is still up in the air so please check back soon, but here's a start of what we're planning:</span></span>

### <a name="string-functions"></a><span data-ttu-id="0ab11-156">문자열 함수</span><span class="sxs-lookup"><span data-stu-id="0ab11-156">String functions</span></span>

* <span data-ttu-id="0ab11-157">substr</span><span class="sxs-lookup"><span data-stu-id="0ab11-157">substr</span></span>
* <span data-ttu-id="0ab11-158">indexOf *(아직 작동 하지 않음)*</span><span class="sxs-lookup"><span data-stu-id="0ab11-158">indexOf *(not working yet)*</span></span>
* <span data-ttu-id="0ab11-159">toUpper *(아직 작동 하지 않음)*</span><span class="sxs-lookup"><span data-stu-id="0ab11-159">toUpper *(not working yet)*</span></span>
* <span data-ttu-id="0ab11-160">toLower *(아직 작동 하지 않음)*</span><span class="sxs-lookup"><span data-stu-id="0ab11-160">toLower *(not working yet)*</span></span>

### <a name="number-functions"></a><span data-ttu-id="0ab11-161">Number 함수</span><span class="sxs-lookup"><span data-stu-id="0ab11-161">Number functions</span></span>

* <span data-ttu-id="0ab11-162">서식 (통화, 10 진수 등) *(아직 작동 하지 않음)*</span><span class="sxs-lookup"><span data-stu-id="0ab11-162">Formatting (currency, decimal, etc) *(not working yet)*</span></span>

### <a name="date-functions"></a><span data-ttu-id="0ab11-163">날짜 함수</span><span class="sxs-lookup"><span data-stu-id="0ab11-163">Date functions</span></span>

* <span data-ttu-id="0ab11-164">잘 알려진 날짜 문자열 형식 구문 분석 *(아직 작동 하지 않음)*</span><span class="sxs-lookup"><span data-stu-id="0ab11-164">Parsing well-known date string formats *(not working yet)*</span></span>
* <span data-ttu-id="0ab11-165">잘 알려진 날짜/시간 표현에 대 한 서식 지정 *(아직 작동 하지 않음)*</span><span class="sxs-lookup"><span data-stu-id="0ab11-165">Formatting for well-known date/time representations *(not working yet)*</span></span>

### <a name="conditional-functions"></a><span data-ttu-id="0ab11-166">조건부 함수</span><span class="sxs-lookup"><span data-stu-id="0ab11-166">Conditional functions</span></span>

* <span data-ttu-id="0ab11-167">if (*expression*, *trueValue*, *falseValue*)</span><span class="sxs-lookup"><span data-stu-id="0ab11-167">if(*expression*, *trueValue*, *falseValue*)</span></span>

<span data-ttu-id="0ab11-168">**`if` 예제**</span><span class="sxs-lookup"><span data-stu-id="0ab11-168">**`if` example**</span></span>

```json
{
    "type": "TextBlock",
    "color": "{if(priceChange >= 0, 'good', 'attention')}"
}
```

### <a name="data-manipulation"></a><span data-ttu-id="0ab11-169">데이터 조작</span><span class="sxs-lookup"><span data-stu-id="0ab11-169">Data manipulation</span></span>

* <span data-ttu-id="0ab11-170">JSON-JSON 문자열을 구문 분석 하는 기능</span><span class="sxs-lookup"><span data-stu-id="0ab11-170">JSON.parse - ability to parse a JSON string</span></span> 

<span data-ttu-id="0ab11-171">**`JSON.parse` 예제**</span><span class="sxs-lookup"><span data-stu-id="0ab11-171">**`JSON.parse` example**</span></span>

<span data-ttu-id="0ab11-172">이는 `message` 속성이 JSON 직렬화 문자열인 Azure DevOps 응답입니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-172">This is an Azure DevOps response where the `message` property is a JSON-serialized string.</span></span> <span data-ttu-id="0ab11-173">문자열 내의 값에 액세스 하려면 템플릿에서 `JSON.parse` 함수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-173">In order to access values within the string, we need to use the `JSON.parse` function in our template.</span></span>

<span data-ttu-id="0ab11-174">**데이터**</span><span class="sxs-lookup"><span data-stu-id="0ab11-174">**Data**</span></span> 

```json
{
    "id": "1291525457129548",
    "status": 4,
    "author": "Matt Hidinger",
    "message": "{\"type\":\"Deployment\",\"buildId\":\"9542982\",\"releaseId\":\"129\",\"buildNumber\":\"20180504.3\",\"releaseName\":\"Release-104\",\"repoProvider\":\"GitHub\"}",
    "start_time": "2018-05-04T18:05:33.3087147Z",
    "end_time": "2018-05-04T18:05:33.3087147Z"
}
```

<span data-ttu-id="0ab11-175">**보려면**</span><span class="sxs-lookup"><span data-stu-id="0ab11-175">**Usage**</span></span>

```json
{
    "type": "TextBlock",
    "text": "{JSON.parse(message).releaseName}"
}
```

<span data-ttu-id="0ab11-176">**결과**</span><span class="sxs-lookup"><span data-stu-id="0ab11-176">**Resulting In**</span></span>

```json
{
    "type": "TextBlock",
    "text": "Release-104"
}
```

### <a name="custom-functions"></a><span data-ttu-id="0ab11-177">사용자 지정 함수</span><span class="sxs-lookup"><span data-stu-id="0ab11-177">Custom functions</span></span>

<span data-ttu-id="0ab11-178">호스트가 사용자 지정 함수를 추가할 수 있는지 확인 하려고 합니다. 즉, 함수가 지원 되지 않는 경우에는 대체 지원이 강력 하 게 지원 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-178">We want to make sure Hosts can add custom functions, which means we need robust support for fallback support if a function isn't supported.</span></span> <span data-ttu-id="0ab11-179">계속 평가 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-179">We are still evaluating this.</span></span>

## <a name="conditional-layout"></a><span data-ttu-id="0ab11-180">조건부 레이아웃</span><span class="sxs-lookup"><span data-stu-id="0ab11-180">Conditional layout</span></span>

<span data-ttu-id="0ab11-181">조건이 충족 될 경우 전체 요소를 삭제 하려면 `$when` 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-181">To drop an entire element if a condition is met, use the `$when` property.</span></span> <span data-ttu-id="0ab11-182">`$when`이 `false`으로 계산 되 면 요소가 사용자에 게 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-182">If `$when` evaluates to `false` the element will not appear to the user.</span></span>

```json
{
    "type": "AdaptiveCard",
    "$data": {
        "price": "35"
    },
    "body": [
        {
            "type": "TextBlock",
            "$when": "{price > 30}",
            "text": "This thing is pricy!",
            "color": "attention",
        },
         {
            "type": "TextBlock",
            "$when": "{price <= 30}",
            "text": "Dang, this thing is cheap!",
            "color": "good"
        }
    ]
}
```

### <a name="composing-templates"></a><span data-ttu-id="0ab11-183">템플릿 작성</span><span class="sxs-lookup"><span data-stu-id="0ab11-183">Composing templates</span></span>

<span data-ttu-id="0ab11-184">현재는 템플릿 "파트"를 함께 작성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-184">Currently there is no support for composing template "parts" together.</span></span> <span data-ttu-id="0ab11-185">그러나이 옵션을 탐색 하 고 더 빨리 공유 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-185">But we are exploring options and hope to share more soon.</span></span> <span data-ttu-id="0ab11-186">여기에서 모든 생각을 환영 합니다!</span><span class="sxs-lookup"><span data-stu-id="0ab11-186">Any thoughts here welcome!</span></span>


## <a name="examples"></a><span data-ttu-id="0ab11-187">예</span><span class="sxs-lookup"><span data-stu-id="0ab11-187">Examples</span></span>

<span data-ttu-id="0ab11-188">지금까지 만든 제한 된 분량의 샘플만 있지만 시작 하려면 여기로 이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ab11-188">We only have a limited amount of samples created so far, but take a look here to get started.</span></span>

* <span data-ttu-id="0ab11-189">**샘플 열기** 를 클릭 하 여 [디자이너](http://vnext.adaptivecards.io/designer) 내에서 샘플 로드</span><span class="sxs-lookup"><span data-stu-id="0ab11-189">Load samples within the [designer](http://vnext.adaptivecards.io/designer) by clicking **Open Sample**</span></span>
* <span data-ttu-id="0ab11-190">또는 직접 [디렉터리를 검색](https://github.com/Microsoft/AdaptiveCards/tree/js/template-engine/samples/v2.0/Scenarios) 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab11-190">Or just [browse a directory of them](https://github.com/Microsoft/AdaptiveCards/tree/js/template-engine/samples/v2.0/Scenarios) directly</span></span>
