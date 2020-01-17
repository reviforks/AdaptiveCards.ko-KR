---
title: 작업 - Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: 680aab595123ce35654d760f0e1dbbe406c8f29d
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145523"
---
# <a name="actions---android"></a><span data-ttu-id="bdcb6-102">작업 - Android</span><span class="sxs-lookup"><span data-stu-id="bdcb6-102">Actions - Android</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bdcb6-103">**주요 변경 내용 목록**</span><span class="sxs-lookup"><span data-stu-id="bdcb6-103">**List of Breaking changes**</span></span>
> 
> [<span data-ttu-id="bdcb6-104">V 1.1의 주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="bdcb6-104">Breaking changes in v1.1</span></span>](#breaking-changes-in-v11)
> 

<span data-ttu-id="bdcb6-105">카드 작업을 실행 하면 ```ICardActionHandler``` 인터페이스를 구현 하는 렌더링 호출에 전달 된 클래스가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdcb6-105">When a cards action is executed, the class that was passed to the render call that implements the ```ICardActionHandler``` interface gets invoked.</span></span> <span data-ttu-id="bdcb6-106">작업 처리기를 정의하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bdcb6-106">Here is how to define your action handler:</span></span>

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

## <a name="breaking-changes-in-v11"></a><span data-ttu-id="bdcb6-107">V 1.1의 주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="bdcb6-107">Breaking changes in v1.1</span></span>

<span data-ttu-id="bdcb6-108">이 버전에 포함 된 미디어 요소에는 ```ICardActionHandler```를 구현 하는 클래스에 의해 구현 되는 두 가지 새로운 메서드가 필요 합니다. 이러한 메서드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bdcb6-108">The media element included in this version requires two new methods to be implemented by the classes that implement ```ICardActionHandler```, these methods are:</span></span>

* <span data-ttu-id="bdcb6-109">```onMediaPlay```는 media 요소에서 재생 단추를 처음 누를 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdcb6-109">```onMediaPlay``` is invoked when the play button is pressed for the first time in any media element</span></span>
* <span data-ttu-id="bdcb6-110">미디어가 끝에 도달 하면 ```onMediaStop``` 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdcb6-110">```onMediaStop``` is invoked when the media reaches it's end</span></span>

<span data-ttu-id="bdcb6-111">이러한 메서드에 대 한 시그니처는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bdcb6-111">The signatures for these methods are:</span></span>

```java
public void onMediaPlay(BaseCardElement mediaElement, RenderedAdaptiveCard renderedAdaptiveCard)
public void onMediaStop(BaseCardElement mediaElement, RenderedAdaptiveCard renderedAdaptiveCard)
```

<span data-ttu-id="bdcb6-112">그리고 앞의 예제에서 ActionHandler에 대 한 구현은 이제 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdcb6-112">And the implementation for the ActionHandler from the previous example would now look similar to this:</span></span>

```java
public class ActionHandler implements ICardActionHandler
{
    @Override
    public void onAction(BaseActionElement actionElement, RenderedAdaptiveCard renderedCard)
    { }

    private void onSubmit(BaseActionElement actionElement, RenderedAdaptiveCard renderedAdaptiveCard) 
    { }

    private void onShowCard(BaseActionElement actionElement)
    { }

    private void onOpenUrl(BaseActionElement actionElement)
    { }

    @Override
    public void onMediaPlay(BaseCardElement mediaElement, RenderedAdaptiveCard renderedAdaptiveCard)
    {
        // Your logic here, i.e.
        showToast("Media started: " + mediaElement, Toast.LENGTH_LONG);
    }

    @Override
    public void onMediaStop(BaseCardElement mediaElement, RenderedAdaptiveCard renderedAdaptiveCard)
    {
        // Your logic here, i.e.
        showToast("Media ended playing: " + mediaElement, Toast.LENGTH_LONG);
    }
}
```
