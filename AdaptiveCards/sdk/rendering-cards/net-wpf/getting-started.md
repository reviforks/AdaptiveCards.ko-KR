---
title: .NET WPF SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: a3f63fc812c97014af06dd1a197b24c5d07361c2
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553625"
---
# <a name="getting-started---net-wpf"></a><span data-ttu-id="e4601-102">시작 하기-.NET WPF</span><span class="sxs-lookup"><span data-stu-id="e4601-102">Getting started - .NET WPF</span></span>

<span data-ttu-id="e4601-103">[시작](../../../authoring-cards/getting-started.md) 페이지에서 설명한 대로 적응 카드는 JSON 직렬화 카드 개체 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="e4601-103">As we described in [Getting Started](../../../authoring-cards/getting-started.md) page, an Adaptive Card is a JSON-serialized card object model.</span></span> <span data-ttu-id="e4601-104">이 라이브러리를 사용 하면 응용 프로그램 내에서 사용할 수 있는 WPF UI로 해당 JSON을 쉽게 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4601-104">This library makes it easy to render that JSON into WPF UI that you can use within your app.</span></span>

## <a name="nuget-install"></a><span data-ttu-id="e4601-105">NuGet 설치</span><span class="sxs-lookup"><span data-stu-id="e4601-105">NuGet install</span></span>

<span data-ttu-id="e4601-106">[![Nuget 설치](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf)</span><span class="sxs-lookup"><span data-stu-id="e4601-106">[![Nuget install](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf)</span></span>

```console
Install-Package AdaptiveCards.Rendering.Wpf
```

### <a name="xceed-enhanced-input-package"></a><span data-ttu-id="e4601-107">Xceed 고급 입력 패키지</span><span class="sxs-lookup"><span data-stu-id="e4601-107">Xceed enhanced input package</span></span>

<span data-ttu-id="e4601-108">이 선택적 패키지는 WPF에서 제공 하는 것 이상의 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4601-108">This optional package enhances the Adaptive Card Input controls beyond what WPF provides out of the box.</span></span> <span data-ttu-id="e4601-109">다음에 대 한 종속성이 있습니다.`Extended.Wpf.Toolkit`</span><span class="sxs-lookup"><span data-stu-id="e4601-109">It has a dependency on `Extended.Wpf.Toolkit`</span></span>

<span data-ttu-id="e4601-110">[![Nuget 설치](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.Xceed.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf.Xceed)</span><span class="sxs-lookup"><span data-stu-id="e4601-110">[![Nuget install](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.Xceed.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf.Xceed)</span></span>

```console
Install-Package AdaptiveCards.Rendering.Wpf.Xceed
```

## <a name="wpf-visualizer-sample"></a><span data-ttu-id="e4601-111">WPF 시각화 도우미 샘플</span><span class="sxs-lookup"><span data-stu-id="e4601-111">WPF Visualizer Sample</span></span>

![시각화 도우미 스크린샷](../../../resources/media/tools/wpfvisualizer.png)

<span data-ttu-id="e4601-113">[Wpf 시각화 도우미 샘플](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) 에서는 wpf를 사용 하 여 카드를 시각화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4601-113">The [WPF Visualizer sample](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) lets you visualize cards using WPF.</span></span>  <span data-ttu-id="e4601-114">호스트 구성 설정을 편집 하 고 볼 수 있는 편집기가기본제공됩니다.`Host Config`</span><span class="sxs-lookup"><span data-stu-id="e4601-114">A `Host Config` editor is built in for editing and viewing host config settings.</span></span> <span data-ttu-id="e4601-115">응용 프로그램에서 렌더링 하는 데 사용할 수 있도록 이러한 설정을 JSON으로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4601-115">Save these settings as a JSON to use them in rendering in your application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e4601-116">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e4601-116">Next steps</span></span>

<span data-ttu-id="e4601-117">[카드 렌더링](render-a-card.md)에서 다음 단계를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e4601-117">See [Render a card](render-a-card.md) for the next steps!</span></span>
