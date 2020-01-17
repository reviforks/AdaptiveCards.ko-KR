---
title: AdaptiveCardRenderer 클래스-Xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: c90fb22f60fa75a37b6372c2660f8599535fd961
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76146067"
---
# <a name="adaptivecardrenderer"></a><span data-ttu-id="16dda-102">AdaptiveCardRenderer</span><span class="sxs-lookup"><span data-stu-id="16dda-102">AdaptiveCardRenderer</span></span>

```csharp
public class AdaptiveCardRenderer : global::Java.Lang.Object
```

<span data-ttu-id="16dda-103">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="16dda-103">**Namespace**</span></span>
```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.Renderer
```

### <a name="summary"></a><span data-ttu-id="16dda-104">요약</span><span class="sxs-lookup"><span data-stu-id="16dda-104">Summary</span></span>

| <span data-ttu-id="16dda-105">public 메서드</span><span class="sxs-lookup"><span data-stu-id="16dda-105">Public methods</span></span> | |
| --- | ---- |
| ```RenderedAdaptiveCard``` | [```Render (Context context, FragmentManager fragmentManager, AdaptiveCard adaptiveCard, ICardActionHandler cardActionHandler)```](#render0) |
| ```RenderedAdaptiveCard``` | [```Render (Context context, FragmentManager fragmentManager, AdaptiveCard adaptiveCard, ICardActionHandler cardActionHandler, HostConfig hostConfig)```](#render1) |

## <a name="public-methods"></a><span data-ttu-id="16dda-106">공용 메서드</span><span class="sxs-lookup"><span data-stu-id="16dda-106">Public Methods</span></span>

---

### <a id="render0"></a><span data-ttu-id="16dda-107">못하게</span><span class="sxs-lookup"><span data-stu-id="16dda-107">Render</span></span>
<p style='text-align:right'><span data-ttu-id="16dda-108">버전 0.1.0에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="16dda-108">Added in version 0.1.0</span></span></p>

```csharp
public RenderedAdaptiveCard Render (Context context, 
                                    FragmentManager fragmentManager, 
                                    AdaptiveCard adaptiveCard,
                                    ICardActionHandler cardActionHandler)
```

<span data-ttu-id="16dda-109">호스트 구성에 대 한 기본값을 사용 하 여 지정 된 적응 카드를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="16dda-109">Renders the specified adaptive card with default values for the host config.</span></span>

| <span data-ttu-id="16dda-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="16dda-110">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="16dda-111">컨텍스트</span><span class="sxs-lookup"><span data-stu-id="16dda-111">context</span></span> | ```Android.Content.Context``` |
| <span data-ttu-id="16dda-112">fragmentManager</span><span class="sxs-lookup"><span data-stu-id="16dda-112">fragmentManager</span></span> | ```Android.Support.V4.App.FragmentManager``` |
| <span data-ttu-id="16dda-113">adaptiveCard</span><span class="sxs-lookup"><span data-stu-id="16dda-113">adaptiveCard</span></span> | [```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.AdaptiveCard```](adaptivecards-rendering-xamarin-android-objectmodel-adaptivecard.md) |
| <span data-ttu-id="16dda-114">가 나 Actionhandler</span><span class="sxs-lookup"><span data-stu-id="16dda-114">cardActionHandler</span></span> | [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.ActionHandler.ICardActionHandler```](adaptivecards-renderin-xamarin-android-renderer-actionhandler-icardactionhandler.md) |

| <span data-ttu-id="16dda-115">Returns</span><span class="sxs-lookup"><span data-stu-id="16dda-115">Returns</span></span> |
| --- | --- |
| [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.RenderedAdaptiveCard```](adaptivecards-rendering-xamarin-android-renderer-renderedadaptivecard.md) | |

#### <a name="sample"></a><span data-ttu-id="16dda-116">샘플</span><span class="sxs-lookup"><span data-stu-id="16dda-116">Sample</span></span>

```csharp
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version);
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.Instance.Render(context, SupportFragmentManager, parseResult.AdaptiveCard, cardActionHandler);
```

---

### <a id="render1"></a><span data-ttu-id="16dda-117">못하게</span><span class="sxs-lookup"><span data-stu-id="16dda-117">Render</span></span>
<p style='text-align:right'><span data-ttu-id="16dda-118">버전 0.1.0에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="16dda-118">Added in version 0.1.0</span></span></p>

```csharp
RenderedAdaptiveCard Render (Context context, 
                            FragmentManager fragmentManager, 
                            AdaptiveCard adaptiveCard, 
                            ICardActionHandler cardActionHandler, 
                            HostConfig hostConfig)
```

<span data-ttu-id="16dda-119">지정 된 호스트 구성을 사용 하 여 지정 된 적응 카드를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="16dda-119">Renders the specified adaptive card with using the given host config.</span></span>

| <span data-ttu-id="16dda-120">매개 변수</span><span class="sxs-lookup"><span data-stu-id="16dda-120">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="16dda-121">컨텍스트</span><span class="sxs-lookup"><span data-stu-id="16dda-121">context</span></span> | ```Android.Content.Context``` |
| <span data-ttu-id="16dda-122">fragmentManager</span><span class="sxs-lookup"><span data-stu-id="16dda-122">fragmentManager</span></span> | ```Android.Support.V4.App.FragmentManager``` |
| <span data-ttu-id="16dda-123">adaptiveCard</span><span class="sxs-lookup"><span data-stu-id="16dda-123">adaptiveCard</span></span> | [```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.AdaptiveCard```](adaptivecards-rendering-xamarin-android-objectmodel-adaptivecard.md) |
| <span data-ttu-id="16dda-124">가 나 Actionhandler</span><span class="sxs-lookup"><span data-stu-id="16dda-124">cardActionHandler</span></span> | [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.ActionHandler.ICardActionHandler```](adaptivecards-renderin-xamarin-android-renderer-actionhandler-icardactionhandler.md) |
| <span data-ttu-id="16dda-125">hostConfig</span><span class="sxs-lookup"><span data-stu-id="16dda-125">hostConfig</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HostConfig``` |

| <span data-ttu-id="16dda-126">Returns</span><span class="sxs-lookup"><span data-stu-id="16dda-126">Returns</span></span> | |
| --- | --- |
| [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.RenderedAdaptiveCard```](adaptivecards-rendering-xamarin-android-renderer-renderedadaptivecard.md) | |

#### <a name="sample"></a><span data-ttu-id="16dda-127">샘플</span><span class="sxs-lookup"><span data-stu-id="16dda-127">Sample</span></span>

```csharp
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version);
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.Instance.Render(context, SupportFragmentManager, parseResult.AdaptiveCard, cardActionHandler, hostConfig);
```