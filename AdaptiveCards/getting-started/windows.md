---
title: Windows 개발자용 적응형 카드
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 20b324c12cd7cec10f2142fc2cf76039b5c329de
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2019
ms.locfileid: "59552855"
---
# <a name="adaptive-cards-for-windows-developers"></a><span data-ttu-id="6f8a9-102">Windows 개발자용 적응형 카드</span><span class="sxs-lookup"><span data-stu-id="6f8a9-102">Adaptive Cards for Windows Developers</span></span>



## <a name="timeline"></a><span data-ttu-id="6f8a9-103">타임라인</span><span class="sxs-lookup"><span data-stu-id="6f8a9-103">Timeline</span></span>

<span data-ttu-id="6f8a9-104">적응형 카드를 지원한 첫 번째 Windows 환경은 Timeline으로, Windows 10 1803에 처음 도입된 완전히 새로운 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="6f8a9-104">The first Windows experience to supports Adaptive Cards is Timeline, a brand new experience first introduced in Windows 10 1803.</span></span> 

![타임라인](media/windows/timeline.png)

### <a name="useractivity-api"></a><span data-ttu-id="6f8a9-106">UserActivity API</span><span class="sxs-lookup"><span data-stu-id="6f8a9-106">UserActivity API</span></span>

<span data-ttu-id="6f8a9-107">[`Windows.ApplicationModel.UserActivities.UserActivity`](https://docs.microsoft.com/en-us/uwp/api/windows.applicationmodel.useractivities.useractivity) API는 Timeline에 활동을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="6f8a9-107">The [`Windows.ApplicationModel.UserActivities.UserActivity`](https://docs.microsoft.com/en-us/uwp/api/windows.applicationmodel.useractivities.useractivity) API is what populates an Activity into Timeline.</span></span>

<span data-ttu-id="6f8a9-108">적응형 카드는 아래에 표시된 것처럼 `VisualElement`의 `Content` 속성을 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f8a9-108">The Adaptive Card will be supplied via the `Content` property of `VisualElement`, as seen below:</span></span>

```csharp
UserActivity userActivity = await channel.GetOrCreateUserActivityAsync(activityId, new HostName("contoso.com"));
userActivity.ActivationUri = new Uri("rss-reader:article?" + article.Link);
userActivity.DisplayText = article.Title; //used for details tile text
userActivity.VisualElements.Content = AdaptiveCardBuilder.CreateAdaptiveCardFromJson(jsonString);
await userActivity.SaveAsync();
```

### <a name="learn-more"></a><span data-ttu-id="6f8a9-109">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="6f8a9-109">Learn more</span></span>

<span data-ttu-id="6f8a9-110">빌드 2017의 이 세션에서는 사용자 활동을 자세히 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="6f8a9-110">This session at Build 2017 covers User Activities in detial.</span></span>

<iframe src="https://channel9.msdn.com/Events/Build/2017/B8108/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

## <a name="other-windows-surfaces"></a><span data-ttu-id="6f8a9-111">기타 Windows 화면</span><span class="sxs-lookup"><span data-stu-id="6f8a9-111">Other Windows Surfaces</span></span>
<span data-ttu-id="6f8a9-112">아직 공유할 내용은 없지만 더 많은 Windows 환경에 적응형 카드를 통합하기 위해 노력하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f8a9-112">We don't have anything to share just yet, but we're working on incorporating Adaptive Cards into more Windows experiences.</span></span>

## <a name="dive-in"></a><span data-ttu-id="6f8a9-113">자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="6f8a9-113">Dive in!</span></span>

<span data-ttu-id="6f8a9-114">이 자습서에서는 극히 일부만 다루었으므로 곧 다시 방문해서 아래의 링크로 이동하여 적응형 카드에 대해 자세히 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="6f8a9-114">We've barely scratched the surface in this tutorial, so check back soon and browse the links below to explore more about Adaptive Cards.</span></span>

* <span data-ttu-id="6f8a9-115">영감을 얻기 위해 [샘플 카드 찾아보기](http://adaptivecards.io/samples/)</span><span class="sxs-lookup"><span data-stu-id="6f8a9-115">[Browse Sample cards](http://adaptivecards.io/samples/) for inspiration</span></span>
* <span data-ttu-id="6f8a9-116">[스키마 탐색기](http://adaptivecards.io/explorer)를 사용하여 사용 가능한 요소 알아보기</span><span class="sxs-lookup"><span data-stu-id="6f8a9-116">Use the [Schema Explorer](http://adaptivecards.io/explorer) to learn the available elements</span></span>
* <span data-ttu-id="6f8a9-117">[대화형 비주얼라이저](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)를 사용하여 카드 작성</span><span class="sxs-lookup"><span data-stu-id="6f8a9-117">Build a card using the [Interactive Visualizer](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)</span></span>
* <span data-ttu-id="6f8a9-118">모든 피드백과 [연결 유지](http://adaptivecards.io/connect)</span><span class="sxs-lookup"><span data-stu-id="6f8a9-118">[Get in touch](http://adaptivecards.io/connect) with any feedback you have</span></span>
