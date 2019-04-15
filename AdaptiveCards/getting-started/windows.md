---
title: Windows 개발자를 위한 adaptive Card
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 20b324c12cd7cec10f2142fc2cf76039b5c329de
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552855"
---
# <a name="adaptive-cards-for-windows-developers"></a>Windows 개발자를 위한 adaptive Card



## <a name="timeline"></a>타임라인

첫 번째 Windows 환경을 Adaptive Card는 타임 라인을 Windows 10 1803에서에서 처음 도입 된 새로운 경험을 지원 합니다. 

![타임라인](media/windows/timeline.png)

### <a name="useractivity-api"></a>UserActivity API

합니다 [ `Windows.ApplicationModel.UserActivities.UserActivity` ](https://docs.microsoft.com/en-us/uwp/api/windows.applicationmodel.useractivities.useractivity) API는 새로운 타임 라인으로 채웁니다.

Adaptive Card를 통해 제공 합니다 `Content` 속성의 `VisualElement`아래와 같이:

```csharp
UserActivity userActivity = await channel.GetOrCreateUserActivityAsync(activityId, new HostName("contoso.com"));
userActivity.ActivationUri = new Uri("rss-reader:article?" + article.Link);
userActivity.DisplayText = article.Title; //used for details tile text
userActivity.VisualElements.Content = AdaptiveCardBuilder.CreateAdaptiveCardFromJson(jsonString);
await userActivity.SaveAsync();
```

### <a name="learn-more"></a>자세한 내용

Build 2017이 세션에서는 detial에서 사용자 동작을 설명합니다.

<iframe src="https://channel9.msdn.com/Events/Build/2017/B8108/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

## <a name="other-windows-surfaces"></a>다른 Windows 화면
아직 공유에 아무것도 없기 있지만 Adaptive Card 자세한 Windows 환경에 통합에 최선을 다하고 있습니다.

## <a name="dive-in"></a>시작 해 보겠습니다!

했습니다 극히 일부만이 자습서에서는, 따라서 곧 다시 확인 하 고 적응 카드에 대 한 다른 기능을 탐색 하려면 아래 링크를 찾아보십시오.

* [샘플 카드 찾아보기](http://adaptivecards.io/samples/) 영감
* 사용 된 [스키마 탐색기](http://adaptivecards.io/explorer) 사용 가능한 요소를 알아보려면
* 카드를 통해 빌드를 [대화형 시각화 도우미](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)
* [연락](http://adaptivecards.io/connect) 피드백을 사용 하 여
