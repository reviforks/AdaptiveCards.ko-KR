---
title: ICardActionHandler 클래스-Xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: 8b526ccb66be3a261384d6c4f68a850558e2549e
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76146157"
---
# <a name="icardactionhandler"></a><span data-ttu-id="fc70a-102">ICardActionHandler</span><span class="sxs-lookup"><span data-stu-id="fc70a-102">ICardActionHandler</span></span>

```csharp
public interface ICardActionHandler : IJavaObject 
```

<span data-ttu-id="fc70a-103">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="fc70a-103">**Namespace**</span></span>
```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.Renderer.ActionHandler
```

### <a name="summary"></a><span data-ttu-id="fc70a-104">요약</span><span class="sxs-lookup"><span data-stu-id="fc70a-104">Summary</span></span>

| <span data-ttu-id="fc70a-105">public 메서드</span><span class="sxs-lookup"><span data-stu-id="fc70a-105">Public methods</span></span> | |
| --- | ---- |
| ```abstract void``` | [```OnAction (BaseActionElement p0, RenderedAdaptiveCard p1)```](#onaction) |
| ```abstract void``` | [```OnMediaPlay (BaseCardElement p0, RenderedAdaptiveCard p1)```](#onmediaplay) |
| ```abstract void``` | [```OnMediaStop (BaseCardElement p0, RenderedAdaptiveCard p1)```](#onmediastop) |

## <a name="public-methods"></a><span data-ttu-id="fc70a-106">공용 메서드</span><span class="sxs-lookup"><span data-stu-id="fc70a-106">Public Methods</span></span>
--- 
### <a id="onaction"></a><span data-ttu-id="fc70a-107">OnAction</span><span class="sxs-lookup"><span data-stu-id="fc70a-107">OnAction</span></span>
<p style='text-align:right'><span data-ttu-id="fc70a-108">버전 0.1.0에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="fc70a-108">Added in version 0.1.0</span></span></p>

```csharp
void OnAction (BaseActionElement p0, RenderedAdaptiveCard p1)
```

<span data-ttu-id="fc70a-109">OpenUrlAction, SubmitAction 또는 ShowCardAction (인라인이 아닌 경우)를 클릭할 때 호출 되는 수신기입니다.</span><span class="sxs-lookup"><span data-stu-id="fc70a-109">Listener called when a OpenUrlAction, SubmitAction or ShowCardAction (if not inline) are clicked.</span></span>

| <span data-ttu-id="fc70a-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc70a-110">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="fc70a-111">p0</span><span class="sxs-lookup"><span data-stu-id="fc70a-111">p0</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseActionElement``` |
| <span data-ttu-id="fc70a-112">p1</span><span class="sxs-lookup"><span data-stu-id="fc70a-112">p1</span></span> | [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.RenderedAdaptiveCard```](adaptivecards-rendering-xamarin-android-renderer-renderedadaptivecard.md) |

#### <a name="sample"></a><span data-ttu-id="fc70a-113">샘플</span><span class="sxs-lookup"><span data-stu-id="fc70a-113">Sample</span></span>

```csharp
public class MyCardActionHandler : ICardActionHandler
{

    public void OnAction(BaseActionElement element, RenderedAdaptiveCard renderedCard)
    {
        ActionType actionType = element.ElementType;
        if (actionType == ActionType.Submit)
        {
            var inputs = renderedCard.Inputs;
            string inputValues = string.Empty;
            foreach (var inputString in inputs)
            {
                inputValues += $"{{{inputString.Key} : {inputString.Value}}}\n";
            }
            submitData(inputValues);
        }
        else if (actionType == ActionType.ShowCard)
        {
            var showcardAction = ShowCardAction.Dynamic_cast(element);
            showCard(showcardAction.Card)
        }
        else if (actionType == ActionType.OpenUrl)
        {
            var openUrlAction = OpenUrlAction.Dynamic_cast(element);
            openUrl(openUrlAction.Url);
        }
    }
}
```

---
### <a id="onmediaplay"></a><span data-ttu-id="fc70a-114">OnMediaPlay</span><span class="sxs-lookup"><span data-stu-id="fc70a-114">OnMediaPlay</span></span>
<p style='text-align:right'><span data-ttu-id="fc70a-115">버전 0.1에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="fc70a-115">Added in version 0.1</span></span></p>

```csharp
void OnMediaPlay (BaseCardElement p0, RenderedAdaptiveCard p1)
```

<span data-ttu-id="fc70a-116">미디어 요소의 재생을 시작할 때 호출 되는 수신기입니다.</span><span class="sxs-lookup"><span data-stu-id="fc70a-116">Listener called when the media element starts playing.</span></span>

| <span data-ttu-id="fc70a-117">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc70a-117">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="fc70a-118">p0</span><span class="sxs-lookup"><span data-stu-id="fc70a-118">p0</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseCardElement``` |
| <span data-ttu-id="fc70a-119">p1</span><span class="sxs-lookup"><span data-stu-id="fc70a-119">p1</span></span> | [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.RenderedAdaptiveCard```](adaptivecards-rendering-xamarin-android-renderer-renderedadaptivecard.md) |

#### <a name="sample"></a><span data-ttu-id="fc70a-120">샘플</span><span class="sxs-lookup"><span data-stu-id="fc70a-120">Sample</span></span>

```csharp
public class MyCardActionHandler : ICardActionHandler
{
    public void OnMediaPlay(BaseCardElement element, RenderedAdaptiveCard renderedCard)
    {
    }
}
```

--- 

### <a id="onmediastop"></a><span data-ttu-id="fc70a-121">OnMediaStop</span><span class="sxs-lookup"><span data-stu-id="fc70a-121">OnMediaStop</span></span>
<p style='text-align:right'><span data-ttu-id="fc70a-122">버전 0.1에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="fc70a-122">Added in version 0.1</span></span></p>

```csharp
void OnMediaStop (BaseCardElement p0, RenderedAdaptiveCard p1)
```

<span data-ttu-id="fc70a-123">미디어 요소가 재생을 중지할 때 호출 되는 수신기입니다.</span><span class="sxs-lookup"><span data-stu-id="fc70a-123">Listener called when the media element stops playing.</span></span>

| <span data-ttu-id="fc70a-124">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc70a-124">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="fc70a-125">p0</span><span class="sxs-lookup"><span data-stu-id="fc70a-125">p0</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseCardElement``` |
| <span data-ttu-id="fc70a-126">p1</span><span class="sxs-lookup"><span data-stu-id="fc70a-126">p1</span></span> | [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.RenderedAdaptiveCard```](adaptivecards-rendering-xamarin-android-renderer-renderedadaptivecard.md) |

#### <a name="sample"></a><span data-ttu-id="fc70a-127">샘플</span><span class="sxs-lookup"><span data-stu-id="fc70a-127">Sample</span></span>

```csharp
public class MyCardActionHandler : ICardActionHandler
{
    public void OnMediaStop(BaseCardElement element, RenderedAdaptiveCard renderedCard)
    {
    }
}
```