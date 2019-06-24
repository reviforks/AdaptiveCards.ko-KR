---
title: 작업 - Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: e21c03e069e7ab29dd7d2724d49a2d439c67e5a1
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67134268"
---
# <a name="actions---android"></a><span data-ttu-id="64dd1-102">작업 - Android</span><span class="sxs-lookup"><span data-stu-id="64dd1-102">Actions - Android</span></span>

<span data-ttu-id="64dd1-103">카드 작업이 실행되면 ICardActionHandler 인터페이스를 구현하는 렌더링 호출로 전달된 클래스가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="64dd1-103">When a cards action is executed, the class that was passed to the render call that implements the ICardActionHandler interface gets invoked.</span></span> <span data-ttu-id="64dd1-104">작업 처리기를 정의하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="64dd1-104">Here is how to define your action handler:</span></span>

```java
public class ActionHandler implements ICardActionHandler
{
    @Override
    public void onAction(BaseActionElement actionElement, RenderedAdaptiveCard renderedCard)
    {
        ActionType actionType = actionElement.GetElementType();
        if (actionType == ActionType.Submit)
        {
            onSubmit(actionElement, renderedCard);
        }
        else if (actionType == ActionType.ShowCard)
        {
            onShowCard(actionElement);
        }
        else if (actionType == ActionType.OpenUrl)
        {
            onOpenUrl(actionElement);
        }
        else if (actionType == ActionType.Custom)
        {
            //Handle activation of custom actions
            ...
        }
    }

    private void onSubmit(BaseActionElement actionElement, RenderedAdaptiveCard renderedAdaptiveCard)
    {
        SubmitAction submitAction = null;
        if (actionElement instanceof SubmitAction)
        {
            submitAction = (SubmitAction) actionElement;
        }
        else if ((submitAction = SubmitAction.dynamic_cast(actionElement)) == null)
        {
            throw new InternalError("Unable to convert BaseActionElement to ShowCardAction object model.");
        }

        String data = submitAction.GetDataJson();
        Map<String, String> keyValueMap = renderedAdaptiveCard.getInputs();
        if (!data.isEmpty())
        {
            try
            {
                JSONObject object = new JSONObject(data);
                showToast("Submit data: " + object.toString() + "\nInput: " + keyValueMap.toString(), Toast.LENGTH_LONG);
            }
            catch (JSONException e)
            {
                showToast(e.toString(), Toast.LENGTH_LONG);
            }
        }
        else
        {
            showToast("Submit input: " + keyValueMap.toString(), Toast.LENGTH_LONG);
        }
    }

    private void onShowCard(BaseActionElement actionElement)
    {
        ShowCardAction showCardAction = null;
        if (actionElement instanceof ShowCardAction)
        {
            showCardAction = (ShowCardAction) actionElement;
        }
        else if ((showCardAction = ShowCardAction.dynamic_cast(actionElement)) == null)
        {
            throw new InternalError("Unable to convert BaseActionElement to ShowCardAction object model.");
        }

        //Get the card from show card and create a view
        RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, fragmentManager, showCardAction.GetCard(), cardActionHandler, hostConfig);

        ViewGroup viewGroup = (ViewGroup) renderedCard.getView();
        ...
    }

    private void onOpenUrl(BaseActionElement actionElement)
    {
        OpenUrlAction openUrlAction = null;
        if (actionElement instanceof ShowCardAction)
        {
            openUrlAction = (OpenUrlAction) actionElement;
        }
        else if ((openUrlAction = OpenUrlAction.dynamic_cast(actionElement)) == null)
        {
            throw new InternalError("Unable to convert BaseActionElement to ShowCardAction object model.");
        }

        Intent browserIntent = new Intent(Intent.ACTION_VIEW, Uri.parse(openUrlAction.GetUrl()));
        this.startActivity(browserIntent);
    }
}
```

> [!IMPORTANT]
> <span data-ttu-id="64dd1-105">**v1.1의 주요 변경 내용**</span><span class="sxs-lookup"><span data-stu-id="64dd1-105">**Breaking changes for v1.1**</span></span>
> 
> 1. <span data-ttu-id="64dd1-106">이 버전에 포함된 미디어 요소를 사용하려면 ICardActionHandler를 구현하는 클래스를 통해 다음과 같은 두 가지 새 메서드를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64dd1-106">The media element included in this version requires two new methods to be implemented by the classes that implement ICardActionHandler, these methods are</span></span>
>
> ```java
> public void onMediaPlay(BaseCardElement mediaElement, RenderedAdaptiveCard renderedAdaptiveCard)
> public void onMediaStop(BaseCardElement mediaElement, RenderedAdaptiveCard renderedAdaptiveCard)
> ```
>
> <span data-ttu-id="64dd1-107">onMediaPlay 메서드는 아무 미디어 요소에서 처음으로 재생 단추를 누를 때 호출되고, onMediaStop 메서드는 미디어가 끝부분에 도달할 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="64dd1-107">onMediaPlay is invoked when the play button is pressed for the first time in any media element, meanwhile onMediaStop is invoked when the media reaches it's end</span></span>
