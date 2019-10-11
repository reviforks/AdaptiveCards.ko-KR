---
title: 템플릿 개요
author: matthidinger
ms.author: mahiding
ms.date: 07/29/2019
ms.topic: article
ms.openlocfilehash: fdfe7b46614f046155ab84a5a487105d55afd7cb
ms.sourcegitcommit: ef03c0eff3272a36cfa88daf99c4d57e4bae9599
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2019
ms.locfileid: "72042544"
---
# <a name="adaptive-cards-templating-preview"></a><span data-ttu-id="39509-102">적응형 카드 템플릿(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="39509-102">Adaptive Cards Templating (Preview)</span></span>

<span data-ttu-id="39509-103">적응형 카드를 **생성**, **재사용**, **공유**하는 데 도움이 되는 새로운 도구의 미리 보기를 공유하게 되어 기쁩니다.</span><span class="sxs-lookup"><span data-stu-id="39509-103">We're excited to share a preview of new tools that will help you **create**, **reuse**, and **share** Adaptive Cards.</span></span> 

> [!IMPORTANT] 
> 
> <span data-ttu-id="39509-104">이러한 기능은 **미리 보기 상태이며 변경될 수 있습니다**.</span><span class="sxs-lookup"><span data-stu-id="39509-104">These features are **in preview and subject to change**.</span></span> <span data-ttu-id="39509-105">사용자 의견은 언제나 환영이며, **사용자**에게 필요한 기능을 제공하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="39509-105">Your feedback is not only welcome, but  critical to ensure we deliver the features **you** need.</span></span>

## <a name="how-can-templating-help-you"></a><span data-ttu-id="39509-106">템플릿을 어떻게 활용할 수 있을까요?</span><span class="sxs-lookup"><span data-stu-id="39509-106">How can templating help you?</span></span>

<span data-ttu-id="39509-107">템플릿을 사용하면 적응형 카드에서 **레이아웃**과 **데이터**를 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39509-107">Templating enables the separation of **data** from the **layout** in an Adaptive Card.</span></span> 

### <a name="it-helps-design-a-card-once-and-then-populate-it-with-real-data"></a><span data-ttu-id="39509-108">카드를 한 번 디자인하고 실제 데이터로 채우는 데 유용</span><span class="sxs-lookup"><span data-stu-id="39509-108">It helps design a card once, and then populate it with real data</span></span>

<span data-ttu-id="39509-109">현재 [적응형 카드 디자이너](https://adaptivecards.io/designer)를 사용하여 카드를 만든 다음, 해당 JSON을 사용하여 **동적 콘텐츠**로 페이로드를 채울 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39509-109">Today it's impossible to create a card using the [Adaptive Card Designer](https://adaptivecards.io/designer) and use that JSON to populate the payload with **dynamic content**.</span></span> <span data-ttu-id="39509-110">이 작업을 수행하려면 사용자 지정 코드를 작성하여 JSON 문자열을 빌드하거나 개체 모델 SDK를 사용하여 카드를 나타내는 OM을 빌드하고 JSON으로 직렬화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39509-110">In order to achieve this you must write custom code to build a JSON string, or use the Object Model SDKs to build an OM representing your card and serialize it to JSON.</span></span> <span data-ttu-id="39509-111">어떤 경우든 디자이너는 일회성 단방향 작업이며 나중에 코드로 변환한 후에는 카드 디자인을 쉽게 조정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39509-111">In either case the Designer is a one-time one-way operation and doesn't make it easy to tweak the card design later once you've converted it to code.</span></span>

### <a name="it-makes-tranmissions-over-the-wire-smaller"></a><span data-ttu-id="39509-112">유선 전송 간소화</span><span class="sxs-lookup"><span data-stu-id="39509-112">It makes tranmissions over the wire smaller</span></span>

<span data-ttu-id="39509-113">템플릿과 데이터를 **클라이언트에서 직접** 결합할 수 있는 환경을 생각해 보세요.</span><span class="sxs-lookup"><span data-stu-id="39509-113">Imagine a world where a template and data can be combined **directly on the client**.</span></span> <span data-ttu-id="39509-114">즉, 동일한 템플릿을 여러 번 사용하거나 새 데이터를 사용하여 업데이트하려는 경우 새 데이터를 디바이스에 전송하기만 하면 동일한 템플릿을 계속 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39509-114">This means if you use the same template multiple times, or want to update it with new data, you just need to send new data to the device and it can re-use the same template over and over.</span></span>

### <a name="it-helps-you-create-a-great-looking-card-from-just-the-data-you-provide"></a><span data-ttu-id="39509-115">자신이 제공하는 데이터로만 멋진 카드를 만드는 데 유용</span><span class="sxs-lookup"><span data-stu-id="39509-115">It helps you create a great looking card from just the data you provide</span></span>

<span data-ttu-id="39509-116">적응형 카드도 좋지만 사용자에게 표시하려는 모든 항목에 대한 적응형 카드를 작성할 필요가 없다면 어떨까요?</span><span class="sxs-lookup"><span data-stu-id="39509-116">We think Adaptive Cards are great, but what if you didn't have to write an Adaptive Card for everything you want to display to a user?</span></span> <span data-ttu-id="39509-117">아래에 설명된 템플릿 서비스를 사용하면 모든 사용자가 모든 유형의 데이터에 대한 템플릿을 기고, 검색 및 공유할 수 있는 환경을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39509-117">With a template service (described below) we can create a world where everyone can contribute, discover, and share templates over any type of data.</span></span> 

<span data-ttu-id="39509-118">자체 프로젝트, 조직 내에서 또는 전체 인터넷과 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39509-118">Share within your own projects, your organization, or with the entire internet.</span></span>

### <a name="ai-and-other-services-could-improve-user-experiences"></a><span data-ttu-id="39509-119">AI 및 기타 서비스를 통해 사용자 환경 개선 가능</span><span class="sxs-lookup"><span data-stu-id="39509-119">AI and other services could improve user experiences</span></span>

<span data-ttu-id="39509-120">콘텐츠와 데이터를 분리하여 AI 및 기타 서비스가 카드에 표시되는 데이터를 "추론"할 수 있게 해주고, 사용자 생산성을 개선하거나 항목을 검색할 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="39509-120">By separating data from content it opens a door for AI and other services to  "reason" over the data in the cards we see and enhance user productivity or help us find things.</span></span>

## <a name="what-is-adaptive-cards-templating"></a><span data-ttu-id="39509-121">적응형 카드 템플릿이란?</span><span class="sxs-lookup"><span data-stu-id="39509-121">What is Adaptive Cards Templating?</span></span>

<span data-ttu-id="39509-122">3가지 주요 구성 요소로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39509-122">It's comprised of 3 major components:</span></span>

1. <span data-ttu-id="39509-123">**[템플릿 언어](language.md)** 는 템플릿을 작성하는 데 사용되는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="39509-123">The **[Template Language](language.md)** is the syntax used for authoring a template.</span></span> <span data-ttu-id="39509-124">디자이너를 사용하여 디자인 타임에 "샘플 데이터"를 포함하여 템플릿을 미리 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39509-124">The Designer even lets you preview your templates at design time by including "sample data".</span></span>
2. <span data-ttu-id="39509-125">**[템플릿 SDK](sdk.md)** 는 지원되는 모든 적응형 카드 플랫폼에 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="39509-125">The **[Templating SDK's](sdk.md)** will exist on all supported Adaptive Card platforms.</span></span> <span data-ttu-id="39509-126">이러한 SDK를 사용하여 백 엔드에서 또는 클라이언트에서 직접 실제 데이터로 템플릿을 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39509-126">These SDKs allow you to populate a template with real data, on the back-end or directly on the client.</span></span> 
3. <span data-ttu-id="39509-127">**[템플릿 서비스](service.md)** 는 누구나 잘 알려진 템플릿 세트를 찾고, 기고하고, 공유할 수 있게 해주는 개념 증명 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="39509-127">The **[Template Service](service.md)** is a proof-of-concept service that allows anyone to find, contribute to, and share a set of well-known templates.</span></span>

## <a name="template-language"></a><span data-ttu-id="39509-128">템플릿 언어</span><span class="sxs-lookup"><span data-stu-id="39509-128">Template Language</span></span>

<span data-ttu-id="39509-129">템플릿 언어는 적응형 카드 템플릿을 작성하는 데 사용되는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="39509-129">The template langauge is the syntax used to author an Adaptive Card template.</span></span> 

> [!NOTE]
> 
> <span data-ttu-id="39509-130">다음 링크를 새 탭에서 열고 아래 예를 따라 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="39509-130">Follow along with the example below by opening up a new tab to</span></span>
>
> **https://vnext.adaptivecards.io/designer**
> 
> <span data-ttu-id="39509-131">디자인 모드와 미리 보기 모드 간에 전환하려면 **미리 보기 모드** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="39509-131">Click the **Preview Mode** button to toggle between design-mode and preview-mode.</span></span>

![디자이너 스크린샷](content/2019-08-01-13-58-27.png)

<span data-ttu-id="39509-133">["vNext Designer](https://vnext.adaptivecards.io/designer)"는 템플릿을 작성하고 디자인 타임에 카드를 미리 볼 수 있게 **샘플 데이터**를 제공하는 지원 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="39509-133">The ["vNext Designer"](https://vnext.adaptivecards.io/designer) adds support for authoring templates and providing **Sample Data** to preview the card at design-time.</span></span>

<span data-ttu-id="39509-134">아래 예를 **카드 페이로드 편집기** 창에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="39509-134">Paste the example below into the **Card Payload Editor** pane:</span></span> 

<span data-ttu-id="39509-135">**EmployeeCardTemplate.json**</span><span class="sxs-lookup"><span data-stu-id="39509-135">**EmployeeCardTemplate.json**</span></span>

```json
{
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "ColumnSet",
            "style": "accent",
            "bleed": true,
            "columns": [
                {
                    "type": "Column",
                    "width": "auto",
                    "items": [
                        {
                            "type": "Image",
                            "url": "{photo}",
                            "altText": "Profile picture",
                            "size": "Small",
                            "style": "Person"
                        }
                    ]
                },
                {
                    "type": "Column",
                    "width": "stretch",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Hi {name}!",
                            "size": "Medium"
                        },
                        {
                            "type": "TextBlock",
                            "text": "Here's a bit about your org...",
                            "spacing": "None"
                        }
                    ]
                }
            ]
        },
        {
            "type": "TextBlock",
            "text": "Your manager is: **{manager.name}**"
        },
        {
            "type": "TextBlock",
            "text": "Your peers are:"
        },
        {
            "type": "FactSet",
            "facts": [
                {
                    "$data": "{peers}",
                    "title": "{name}",
                    "value": "{title}"
                }
            ]
        }
    ]
}
```

<span data-ttu-id="39509-136">그런 다음, 아래의 JSON 데이터를 **샘플 데이터 편집기**에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="39509-136">Then paste the JSON data below into the **Sample Data Editor**.</span></span> 

<span data-ttu-id="39509-137">**샘플 데이터**를 사용하면 실제 데이터를 전달할 때 런타임에 카드가 어떻게 표시되는지 정확하게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39509-137">**Sample Data** helps you see exactly how your card will appear at runtime when passed actual data.</span></span>

<span data-ttu-id="39509-138">**EmployeeData**</span><span class="sxs-lookup"><span data-stu-id="39509-138">**EmployeeData**</span></span>

```json
{
    "name": "Matt",
    "photo": "https://pbs.twimg.com/profile_images/3647943215/d7f12830b3c17a5a9e4afcc370e3a37e_400x400.jpeg",
    "manager": {
        "name": "Thomas",
        "title": "PM Lead"
    },
    "peers": [
        {
            "name": "Lei",
            "title": "Sr Program Manager"
        },
        {
            "name": "Andrew",
            "title": "Program Manager II"
        },
        {
            "name": "Mary Anne",
            "title": "Program Manager"
        }
    ]
}
```

<span data-ttu-id="39509-139">**미리 보기 모드** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="39509-139">Click the **Preview Mode** button.</span></span> <span data-ttu-id="39509-140">위에서 제공한 샘플 데이터에 따라 카드가 렌더링되는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39509-140">You should see the card render according to the sample data provided above.</span></span> <span data-ttu-id="39509-141">자유롭게 샘플 데이터를 조정하고 실시간으로 카드 업데이트를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="39509-141">Feel free to make tweaks to the sample data and watch the card update in realtime.</span></span>

<span data-ttu-id="39509-142">**축하합니다.** 첫 번째 적응형 카드 템플릿을 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="39509-142">**Congratulations**, you just authored your first Adaptive Card Template!</span></span> <span data-ttu-id="39509-143">다음에는 템플릿을 실제 데이터로 채우는 방법을 알아보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="39509-143">Next let's learn how to populate the template with real data.</span></span>

> <span data-ttu-id="39509-144">[템플릿 언어](language.md)에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="39509-144">Learn more about the [template language](language.md)</span></span>

## <a name="sdk-support"></a><span data-ttu-id="39509-145">SDK 지원</span><span class="sxs-lookup"><span data-stu-id="39509-145">SDK support</span></span>

<span data-ttu-id="39509-146">템플릿 SDK를 사용하여 템플릿을 실제 데이터로 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39509-146">The Templating SDKs make it possible to populate a template with real-data.</span></span>

> [!NOTE]
>
> <span data-ttu-id="39509-147">초기 미리 보기 중에는 제한된 SDK 세트만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39509-147">During the initial preview we only have a limited set of SDKs available.</span></span> <span data-ttu-id="39509-148">출시 후에는 지원되는 모든 적응형 카드 플랫폼에 대한 템플릿 라이브러리가 제공될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="39509-148">When we release there will be templating libraries for every supported Adaptive Cards platform.</span></span>

<span data-ttu-id="39509-149">플랫폼</span><span class="sxs-lookup"><span data-stu-id="39509-149">Platform</span></span> | <span data-ttu-id="39509-150">설치</span><span class="sxs-lookup"><span data-stu-id="39509-150">Install</span></span> | <span data-ttu-id="39509-151">설명서</span><span class="sxs-lookup"><span data-stu-id="39509-151">Documentation</span></span>
--- | --- | ---
<span data-ttu-id="39509-152">JavaScript</span><span class="sxs-lookup"><span data-stu-id="39509-152">JavaScript</span></span> | `npm install adaptivecards-templating` | [<span data-ttu-id="39509-153">설명서</span><span class="sxs-lookup"><span data-stu-id="39509-153">Documentation</span></span>](https://www.npmjs.com/package/adaptivecards-templating)
<span data-ttu-id="39509-154">.NET</span><span class="sxs-lookup"><span data-stu-id="39509-154">.NET</span></span> | `nuget install AdaptiveCards.Templating` | [<span data-ttu-id="39509-155">설명서</span><span class="sxs-lookup"><span data-stu-id="39509-155">Documentation</span></span>](https://docs.microsoft.com/en-us/adaptive-cards/templating/sdk#net)

### <a name="javascript-example"></a><span data-ttu-id="39509-156">JavaScript 예</span><span class="sxs-lookup"><span data-stu-id="39509-156">JavaScript Example</span></span>

<span data-ttu-id="39509-157">아래 JavaScript는 템플릿을 데이터로 채우는 데 사용되는 일반적인 패턴을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="39509-157">The JavaScript below shows the general pattern that will be used to populate a template with data.</span></span>

```js
var template = new ACData.Template({ 
    // EmployeeCardTemplate goes here
});

var dataContext = new ACData.EvaluationContext();
dataContext.$root = {
    // Data goes here
};

var card = template.expand(dataContext);
// Now you have an AdaptiveCard ready to render!
```

> <span data-ttu-id="39509-158">[템플릿 SDK](sdk.md)에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="39509-158">Learn more about the [templating SDKs](sdk.md)</span></span>

## <a name="template-service"></a><span data-ttu-id="39509-159">템플릿 서비스</span><span class="sxs-lookup"><span data-stu-id="39509-159">Template Service</span></span>

<span data-ttu-id="39509-160">적응형 카드 템플릿 서비스는 누구나 잘 알려진 템플릿 세트를 찾고, 기고하고, 공유할 수 있게 해주는 개념 증명 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="39509-160">The Adaptive Cards Template Service is a proof-of-concept service that allows anyone to find, contribute to, and share a set of well-known templates.</span></span>

<span data-ttu-id="39509-161">일부 데이터를 표시하되, 사용자 지정 적응형 카드를 작성하지 않으려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="39509-161">It's useful if you want to display some data but don't want to bother writing a custom Adaptive Card for it.</span></span>

<span data-ttu-id="39509-162">템플릿을 가져오는 API는 간단하게 사용할 수 있지만, 실제로 서비스는 데이터를 분석하고 사용자가 사용할 수 있는 템플릿을 찾는 기능을 포함하여 훨씬 더 많은 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="39509-162">The API to get a template is straight-forward enough, but the service actually offers much more, including the ability to analyze your data and find a template that might work for you.</span></span>

`HTTP GET https://templates.adaptivecards.io/graph.microsoft.com/Profile.json`

<span data-ttu-id="39509-163">모든 템플릿은 다른 오픈 소스 코드처럼 사용자가 참여할 수 있도록 GitHub 리포지토리에 저장된 일반 JSON 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="39509-163">All templates are flat JSON files stored in a GitHub repo so anyone can contribute to them like any other open source code.</span></span>

> <span data-ttu-id="39509-164">[카드 템플릿 서비스](service.md)에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="39509-164">Learn more about the [card template Service](service.md)</span></span>

## <a name="whats-next-and-sending-feedback"></a><span data-ttu-id="39509-165">다음 단계 및 피드백 보내기</span><span class="sxs-lookup"><span data-stu-id="39509-165">What's next and sending feedback</span></span>

<span data-ttu-id="39509-166">템플릿과 데이터와 프레젠테이션 분리는 "일반적이고 일관된 방식으로 카드 콘텐츠를 교환하는 에코시스템"이라는 사명에 성큼 다가갈 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="39509-166">Templating and the separation of presentation from data takes us a whole lot closer toward our mission: "an ecosystem for exchanging card content in a common and consistent way".</span></span>

<span data-ttu-id="39509-167">최대한 빨리 더 많은 것을 공유하고 싶습니다.</span><span class="sxs-lookup"><span data-stu-id="39509-167">We're eager to share more as soon as we can.</span></span> <span data-ttu-id="39509-168">그동안 [GitHub](https://github.com/microsoft/AdaptiveCards) 또는 Twitter **[@MattHidinger](https://twitter.com/matthidinger)** / **#AdaptiveCards**에 피드백을 보내 주세요.</span><span class="sxs-lookup"><span data-stu-id="39509-168">In the meantime please give feedback here, [GitHub](https://github.com/microsoft/AdaptiveCards), or Twitter **[@MattHidinger](https://twitter.com/matthidinger)**/**#AdaptiveCards**.</span></span> 
