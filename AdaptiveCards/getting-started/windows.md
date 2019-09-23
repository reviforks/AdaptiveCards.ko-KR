---
title: Windows 개발자용 적응형 카드
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 65494ed437303d26a202c9a5b95f88255147cbd0
ms.sourcegitcommit: 48838a50b5f0316e15b48d740a7dd0a5f96ebae4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70923079"
---
# <a name="adaptive-cards-for-windows-developers"></a><span data-ttu-id="34877-102">Windows 개발자용 적응형 카드</span><span class="sxs-lookup"><span data-stu-id="34877-102">Adaptive Cards for Windows Developers</span></span>

## <a name="timeline"></a><span data-ttu-id="34877-103">타임라인</span><span class="sxs-lookup"><span data-stu-id="34877-103">Timeline</span></span>

<span data-ttu-id="34877-104">적응형 카드를 지원한 첫 번째 Windows 환경은 Timeline으로, Windows 10 1803에 처음 도입된 완전히 새로운 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="34877-104">The first Windows experience to supports Adaptive Cards is Timeline, a brand new experience first introduced in Windows 10 1803.</span></span> 

![타임라인](media/windows/timeline.png)

### <a name="useractivity-api"></a><span data-ttu-id="34877-106">UserActivity API</span><span class="sxs-lookup"><span data-stu-id="34877-106">UserActivity API</span></span>

<span data-ttu-id="34877-107">[`Windows.ApplicationModel.UserActivities.UserActivity`](https://docs.microsoft.com/en-us/uwp/api/windows.applicationmodel.useractivities.useractivity) API는 Timeline에 활동을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="34877-107">The [`Windows.ApplicationModel.UserActivities.UserActivity`](https://docs.microsoft.com/en-us/uwp/api/windows.applicationmodel.useractivities.useractivity) API is what populates an Activity into Timeline.</span></span>

<span data-ttu-id="34877-108">적응형 카드는 아래에 표시된 것처럼 `VisualElement`의 `Content` 속성을 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="34877-108">The Adaptive Card will be supplied via the `Content` property of `VisualElement`, as seen below:</span></span>

```csharp
UserActivity userActivity = await channel.GetOrCreateUserActivityAsync(activityId, new HostName("contoso.com"));
userActivity.ActivationUri = new Uri("rss-reader:article?" + article.Link);
userActivity.DisplayText = article.Title; //used for details tile text
userActivity.VisualElements.Content = AdaptiveCardBuilder.CreateAdaptiveCardFromJson(jsonString);
await userActivity.SaveAsync();
```

### <a name="learning-module"></a><span data-ttu-id="34877-109">학습 모듈</span><span class="sxs-lookup"><span data-stu-id="34877-109">Learning Module</span></span>

<span data-ttu-id="34877-110">이러한 단계를 모두 학습하는 데 유용한 45분 학습 모듈이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34877-110">There is a great 45-min learn module that covers these steps end-to-end.</span></span>

[<span data-ttu-id="34877-111">적응형 카드를 Windows 10 타임라인에 통합</span><span class="sxs-lookup"><span data-stu-id="34877-111">Integrate adaptive cards into Windows 10 Timeline</span></span>](https://docs.microsoft.com/en-us/learn/modules/integrate-app-into-windows-10-timeline/)

### <a name="learn-more"></a><span data-ttu-id="34877-112">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="34877-112">Learn more</span></span>

<span data-ttu-id="34877-113">빌드 2017의 이 세션에서는 사용자 활동을 자세히 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="34877-113">This session at Build 2017 covers User Activities in detial.</span></span>

<iframe src="https://channel9.msdn.com/Events/Build/2017/B8108/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

## <a name="other-windows-surfaces"></a><span data-ttu-id="34877-114">기타 Windows 화면</span><span class="sxs-lookup"><span data-stu-id="34877-114">Other Windows Surfaces</span></span>
<span data-ttu-id="34877-115">아직 공유할 내용은 없지만 더 많은 Windows 환경에 적응형 카드를 통합하기 위해 노력하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34877-115">We don't have anything to share just yet, but we're working on incorporating Adaptive Cards into more Windows experiences.</span></span>

## <a name="dive-in"></a><span data-ttu-id="34877-116">자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="34877-116">Dive in!</span></span>

<span data-ttu-id="34877-117">이 자습서에서는 극히 일부만 다루었으므로 곧 다시 방문해서 아래의 링크로 이동하여 적응형 카드에 대해 자세히 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="34877-117">We've barely scratched the surface in this tutorial, so check back soon and browse the links below to explore more about Adaptive Cards.</span></span>

* <span data-ttu-id="34877-118">영감을 얻기 위해 [샘플 카드 찾아보기](http://adaptivecards.io/samples/)</span><span class="sxs-lookup"><span data-stu-id="34877-118">[Browse Sample cards](http://adaptivecards.io/samples/) for inspiration</span></span>
* <span data-ttu-id="34877-119">[스키마 탐색기](http://adaptivecards.io/explorer)를 사용하여 사용 가능한 요소 알아보기</span><span class="sxs-lookup"><span data-stu-id="34877-119">Use the [Schema Explorer](http://adaptivecards.io/explorer) to learn the available elements</span></span>
* <span data-ttu-id="34877-120">[대화형 비주얼라이저](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)를 사용하여 카드 작성</span><span class="sxs-lookup"><span data-stu-id="34877-120">Build a card using the [Interactive Visualizer](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)</span></span>
* <span data-ttu-id="34877-121">모든 피드백과 [연결 유지](http://adaptivecards.io/connect)</span><span class="sxs-lookup"><span data-stu-id="34877-121">[Get in touch](http://adaptivecards.io/connect) with any feedback you have</span></span>
