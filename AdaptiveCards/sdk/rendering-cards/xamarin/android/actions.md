---
title: 작업-Xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: 6175bd4dc0709cc808a92e42f1b87d9a5f74ba0c
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76146077"
---
# <a name="actions---xamarinandroid"></a>작업-Xamarin Android

카드 작업을 실행 하면 [```ICardActionHandler```](adaptivecards-renderin-xamarin-android-renderer-actionhandler-icardactionhandler.md) 인터페이스를 구현 하는 렌더링 호출에 전달 된 클래스가 호출 됩니다. 작업 처리기를 정의하는 방법은 다음과 같습니다.

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
using AdaptiveCards.Rendering.Xamarin.Android.Renderer.ActionHandler;

// ...

public class CardActionHandlerImpl : ICardActionHandler
{

    public void OnAction(BaseActionElement element, RenderedAdaptiveCard renderedCard)
    {
        ActionType actionType = element.ElementType;
        if (actionType == ActionType.Submit)
        {
            var submitAction = SubmitAction.Dynamic_cast(element);
            var data = submitAction.DataJson;
            Toast.MakeText(this, data + "\n" + inputValues, ToastLength.Short).Show();
        }
        else if (actionType == ActionType.ShowCard)
        {           
            showCard(card);
        }
        else if (actionType == ActionType.OpenUrl)
        {
            openUrl(url);
        }
    }

    public void OnMediaPlay(BaseCardElement element, RenderedAdaptiveCard renderedCard) { }

    public void OnMediaStop(BaseCardElement element, RenderedAdaptiveCard renderedCard) { }
}
```
