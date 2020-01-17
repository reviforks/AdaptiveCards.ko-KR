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
# <a name="adaptivecardrenderer"></a>AdaptiveCardRenderer

```csharp
public class AdaptiveCardRenderer : global::Java.Lang.Object
```

**Namespace**
```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.Renderer
```

### <a name="summary"></a>요약

| public 메서드 | |
| --- | ---- |
| ```RenderedAdaptiveCard``` | [```Render (Context context, FragmentManager fragmentManager, AdaptiveCard adaptiveCard, ICardActionHandler cardActionHandler)```](#render0) |
| ```RenderedAdaptiveCard``` | [```Render (Context context, FragmentManager fragmentManager, AdaptiveCard adaptiveCard, ICardActionHandler cardActionHandler, HostConfig hostConfig)```](#render1) |

## <a name="public-methods"></a>공용 메서드

---

### <a id="render0"></a>못하게
<p style='text-align:right'>버전 0.1.0에 추가 됨</p>

```csharp
public RenderedAdaptiveCard Render (Context context, 
                                    FragmentManager fragmentManager, 
                                    AdaptiveCard adaptiveCard,
                                    ICardActionHandler cardActionHandler)
```

호스트 구성에 대 한 기본값을 사용 하 여 지정 된 적응 카드를 렌더링 합니다.

| 매개 변수 | |
| --- | --- |
| 컨텍스트 | ```Android.Content.Context``` |
| fragmentManager | ```Android.Support.V4.App.FragmentManager``` |
| adaptiveCard | [```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.AdaptiveCard```](adaptivecards-rendering-xamarin-android-objectmodel-adaptivecard.md) |
| 가 나 Actionhandler | [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.ActionHandler.ICardActionHandler```](adaptivecards-renderin-xamarin-android-renderer-actionhandler-icardactionhandler.md) |

| Returns |
| --- | --- |
| [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.RenderedAdaptiveCard```](adaptivecards-rendering-xamarin-android-renderer-renderedadaptivecard.md) | |

#### <a name="sample"></a>샘플

```csharp
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version);
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.Instance.Render(context, SupportFragmentManager, parseResult.AdaptiveCard, cardActionHandler);
```

---

### <a id="render1"></a>못하게
<p style='text-align:right'>버전 0.1.0에 추가 됨</p>

```csharp
RenderedAdaptiveCard Render (Context context, 
                            FragmentManager fragmentManager, 
                            AdaptiveCard adaptiveCard, 
                            ICardActionHandler cardActionHandler, 
                            HostConfig hostConfig)
```

지정 된 호스트 구성을 사용 하 여 지정 된 적응 카드를 렌더링 합니다.

| 매개 변수 | |
| --- | --- |
| 컨텍스트 | ```Android.Content.Context``` |
| fragmentManager | ```Android.Support.V4.App.FragmentManager``` |
| adaptiveCard | [```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.AdaptiveCard```](adaptivecards-rendering-xamarin-android-objectmodel-adaptivecard.md) |
| 가 나 Actionhandler | [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.ActionHandler.ICardActionHandler```](adaptivecards-renderin-xamarin-android-renderer-actionhandler-icardactionhandler.md) |
| hostConfig | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HostConfig``` |

| Returns | |
| --- | --- |
| [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.RenderedAdaptiveCard```](adaptivecards-rendering-xamarin-android-renderer-renderedadaptivecard.md) | |

#### <a name="sample"></a>샘플

```csharp
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version);
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.Instance.Render(context, SupportFragmentManager, parseResult.AdaptiveCard, cardActionHandler, hostConfig);
```