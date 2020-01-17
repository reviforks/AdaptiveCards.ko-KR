---
title: CardRendererRegistration 클래스-Xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: 4254c1c3c0f275434fae2a92e20679b6fa136b16
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145987"
---
# <a name="cardrendererregistration"></a>CardRendererRegistration

```csharp
public class CardRendererRegistration : Java.Lang.Object
```

**Namespace**
```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.Renderer.Registration
```

### <a name="summary"></a>요약

| public 메서드 | |
| --- | ---- |
| ```void``` | [```RegisterFeatureRegistration (FeatureRegistration featureRegistration)```](#registerfeatureregistration) |

## <a name="public-methods"></a>공용 메서드

--- 

### <a id="registerfeatureregistration"></a>RegisterFeatureRegistration
<p style='text-align:right'>버전 0.1.0에 추가 됨</p>

```csharp
public void RegisterFeatureRegistration (FeatureRegistration featureRegistration)
```

사용할 카드 렌더러에 대 한 [```FeatureRegistration```](adaptivecards-rendering-xamarin-android-objectmodel-featureregistration.md) 개체를 등록 합니다.

| 매개 변수 | |
| --- | --- |
| featureRegistration | [```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.FeatureRegistration```](adaptivecards-rendering-xamarin-android-objectmodel-featureregistration.md) |

#### <a name="sample"></a>샘플

```csharp
FeatureRegistration featureRegistration = new FeatureRegistration();
featureRegistration.AddFeature("MyFeature", "1.2.0");
CardRendererRegistration.Instance.RegisterFeatureRegistration(featureRegistration);
```