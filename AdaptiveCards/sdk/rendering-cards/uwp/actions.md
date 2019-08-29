---
title: 작업-UWP SDK
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: d1d3410b19071f601b31e14882f2cccb4d1e6ccb
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552975"
---
# <a name="actions---uwp"></a>작업-UWP

카드 내의 모든 **작업** 은 UWP **단추로**렌더링 되지만 사용자가 해당 작업을 누를 때 발생 하는 상황을 처리 하기 위해 앱에 있습니다 (showcard 작업 ... 자세한 내용은 코드 조각을 참조 하세요.

`RenderedAdaptiveCard` 개체는 이 용도를 위한 `Action` 이벤트를 제공합니다.

```csharp
// Render a card (as previously shown)
RenderedAdaptiveCard renderedAdaptiveCard =  renderer.RenderAdaptiveCard(card);

// ...

// Attach the event handler for action click events
renderedAdaptiveCard.Action += RenderedAdaptiveCard_Action;

private async void RenderedAdaptiveCard_Action(RenderedAdaptiveCard sender, AdaptiveActionEventArgs args)
{
    if (args.Action is AdaptiveOpenUrlAction openUrlAction)
    {
        await Launcher.LaunchUriAsync(openUrlAction.Url);
    }

    else if (args.Action is AdaptiveShowCardAction showCardAction)
    {
        // This is only fired if, in HostConfig, you set the ShowCard ActionMode to Popup.
        // Otherwise, the renderer will automatically display the card inline without firing this event.
    }

    else if (args.Action is AdaptiveSubmitAction submitAction)
    {
        // Get the data and inputs
        string data = submitAction.DataJson.Stringify();
        string inputs = args.Inputs.AsJson().Stringify();

        // Process them as desired
    }
}
```
