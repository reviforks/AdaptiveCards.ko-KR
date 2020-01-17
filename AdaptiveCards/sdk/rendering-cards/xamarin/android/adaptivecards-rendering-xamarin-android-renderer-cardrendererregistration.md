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
# <a name="cardrendererregistration"></a><span data-ttu-id="a7d49-102">CardRendererRegistration</span><span class="sxs-lookup"><span data-stu-id="a7d49-102">CardRendererRegistration</span></span>

```csharp
public class CardRendererRegistration : Java.Lang.Object
```

<span data-ttu-id="a7d49-103">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="a7d49-103">**Namespace**</span></span>
```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.Renderer.Registration
```

### <a name="summary"></a><span data-ttu-id="a7d49-104">요약</span><span class="sxs-lookup"><span data-stu-id="a7d49-104">Summary</span></span>

| <span data-ttu-id="a7d49-105">public 메서드</span><span class="sxs-lookup"><span data-stu-id="a7d49-105">Public methods</span></span> | |
| --- | ---- |
| ```void``` | [```RegisterFeatureRegistration (FeatureRegistration featureRegistration)```](#registerfeatureregistration) |

## <a name="public-methods"></a><span data-ttu-id="a7d49-106">공용 메서드</span><span class="sxs-lookup"><span data-stu-id="a7d49-106">Public Methods</span></span>

--- 

### <a id="registerfeatureregistration"></a><span data-ttu-id="a7d49-107">RegisterFeatureRegistration</span><span class="sxs-lookup"><span data-stu-id="a7d49-107">RegisterFeatureRegistration</span></span>
<p style='text-align:right'><span data-ttu-id="a7d49-108">버전 0.1.0에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="a7d49-108">Added in version 0.1.0</span></span></p>

```csharp
public void RegisterFeatureRegistration (FeatureRegistration featureRegistration)
```

<span data-ttu-id="a7d49-109">사용할 카드 렌더러에 대 한 [```FeatureRegistration```](adaptivecards-rendering-xamarin-android-objectmodel-featureregistration.md) 개체를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7d49-109">Registers a [```FeatureRegistration```](adaptivecards-rendering-xamarin-android-objectmodel-featureregistration.md) object for the card renderer to use.</span></span>

| <span data-ttu-id="a7d49-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7d49-110">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="a7d49-111">featureRegistration</span><span class="sxs-lookup"><span data-stu-id="a7d49-111">featureRegistration</span></span> | [```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.FeatureRegistration```](adaptivecards-rendering-xamarin-android-objectmodel-featureregistration.md) |

#### <a name="sample"></a><span data-ttu-id="a7d49-112">샘플</span><span class="sxs-lookup"><span data-stu-id="a7d49-112">Sample</span></span>

```csharp
FeatureRegistration featureRegistration = new FeatureRegistration();
featureRegistration.AddFeature("MyFeature", "1.2.0");
CardRendererRegistration.Instance.RegisterFeatureRegistration(featureRegistration);
```