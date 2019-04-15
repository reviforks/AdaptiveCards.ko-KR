---
title: UWP SDK 작업
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
# <a name="actions---uwp"></a><span data-ttu-id="0e935-102">UWP 작업</span><span class="sxs-lookup"><span data-stu-id="0e935-102">Actions - UWP</span></span>

<span data-ttu-id="0e935-103">모든 **동작** 카드 내에서 UWP로 렌더링 됩니다 **단추**의 사용자가 ShowCard 작업... (제외 누를 때 발생 하는 새로운 처리할 앱에 달려 있지만 자세한 내용은 용 코드 조각 참조).</span><span class="sxs-lookup"><span data-stu-id="0e935-103">Any **actions** within the card will render as UWP **Button**'s, but it's up to your app to handle what happens when a user presses them (except for ShowCard actions... see code snippet for more info).</span></span>

<span data-ttu-id="0e935-104">합니다 `RenderedAdaptiveCard` 개체를 제공는 `Action` 이 목적을 위해 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="0e935-104">The `RenderedAdaptiveCard` object provides an `Action` event for this purpose.</span></span>

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
