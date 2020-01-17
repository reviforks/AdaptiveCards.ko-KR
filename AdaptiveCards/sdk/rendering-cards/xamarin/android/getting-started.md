---
title: Xamarin.Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: a7fd40ac7f026e2a325e7dc52e10defe550fd43a
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76146007"
---
# <a name="getting-started---xamarinandroid"></a><span data-ttu-id="40b5b-102">시작 하기-Xamarin Android</span><span class="sxs-lookup"><span data-stu-id="40b5b-102">Getting started - Xamarin.Android</span></span>

<span data-ttu-id="40b5b-103">이는 기본 xamarin android 응용 프로그램을 대상으로 하 고 [여기](../../android/getting-started.md)에서 찾을 수 있는 android 렌더러를 기반으로 하는 렌더러 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="40b5b-103">This is a renderer library which targets native xamarin android applications and is based on the Android renderer that you can find [here](../../android/getting-started.md).</span></span> 

## <a name="nuget-install"></a><span data-ttu-id="40b5b-104">NuGet 설치</span><span class="sxs-lookup"><span data-stu-id="40b5b-104">NuGet install</span></span>

<span data-ttu-id="40b5b-105">[![NuGet 설치](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Xamarin.Android.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Xamarin.Android)</span><span class="sxs-lookup"><span data-stu-id="40b5b-105">[![Nuget install](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Xamarin.Android.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Xamarin.Android)</span></span>

<span data-ttu-id="40b5b-106">게시 된 패키지는 [여기](http://nuget.org) 에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b5b-106">You can find the published packages [here](http://nuget.org)</span></span>

```console
Install-Package AdaptiveCards.Rendering.Xamarin.Android -Version 0.1.0-alpha
```

## <a name="namespace"></a><span data-ttu-id="40b5b-107">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="40b5b-107">Namespace</span></span>

<span data-ttu-id="40b5b-108">이 라이브러리를 사용 하는 데 필요한 네임 스페이스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="40b5b-108">The necessary namespaces for using this library are</span></span>
```csharp
// To import the base object model classes as AdaptiveCard, TextBlock, Column, ShowCardAction, ...
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;

// To import the AdaptiveCardRenderer class
using AdaptiveCards.Rendering.Xamarin.Android.Renderer;

// To import the ICardActionHandler interface
using AdaptiveCards.Rendering.Xamarin.Android.Renderer.ActionHandler;

// To use feature registration and register custom behaviour 
using AdaptiveCards.Rendering.Xamarin.Android.Renderer.Registration;
```

## <a name="xamarinandroid-visualizer-sample"></a><span data-ttu-id="40b5b-109">Xamarin Android 시각화 도우미 샘플</span><span class="sxs-lookup"><span data-stu-id="40b5b-109">Xamarin.Android Visualizer Sample</span></span>

<span data-ttu-id="40b5b-110">[Xamarin Android 시각화 도우미 샘플](https://github.com/Microsoft/AdaptiveCards/tree/master/source/xamarin/Xamarin.Droid.Sample) 을 사용 하면 Xamarin. android를 사용 하 여 카드를 시각화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b5b-110">The [Xamarin.Android Visualizer sample](https://github.com/Microsoft/AdaptiveCards/tree/master/source/xamarin/Xamarin.Droid.Sample) lets you visualize cards using Xamarin.Android.</span></span> <span data-ttu-id="40b5b-111">Android 샘플 응용 프로그램을 사용한 적이 있다면 매우 유사한 환경을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b5b-111">If you have ever used the Android sample application you'll find the experience to be really similar.</span></span>

## <a name="next-steps"></a><span data-ttu-id="40b5b-112">다음 단계</span><span class="sxs-lookup"><span data-stu-id="40b5b-112">Next steps</span></span>

<span data-ttu-id="40b5b-113">빠른 시작에서 다음 단계를 위해 [카드를 렌더링](render-a-card.md) 합니다 .를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b5b-113">For a quick start check [Render a card](render-a-card.md) for the next steps!</span></span>

<span data-ttu-id="40b5b-114">Xamarin.ios 렌더러 라이브러리에 대해 범주화 된 클래스를 자세히 보려면 아래를 클릭 하 여 바인딩된 클래스 중 일부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b5b-114">For a more in depth view of the classes that have been binded for the Xamarin.Android renderer library, you can check some of the binded classes by clicking on them below:</span></span>
* [```AdaptiveCard```](adaptivecards-rendering-xamarin-android-objectmodel-adaptivecard.md)
* [```AdaptiveCardRenderer```](adaptivecards-rendering-xamarin-android-renderer-adaptivecardrenderer.md)
* [```CardRendererRegistration```](adaptivecards-rendering-xamarin-android-renderer-cardrendererregistration.md)
* [```FeatureRegistration```](adaptivecards-rendering-xamarin-android-objectmodel-featureregistration.md)
* [```ICardActionHandler```](adaptivecards-renderin-xamarin-android-renderer-actionhandler-icardactionhandler.md)
* [```RenderedAdaptiveCard```](adaptivecards-rendering-xamarin-android-renderer-renderedadaptivecard.md)