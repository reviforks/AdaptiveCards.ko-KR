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
# <a name="getting-started---net-wpf"></a><span data-ttu-id="a9904-102">가져오기 시작-.NET WPF</span><span class="sxs-lookup"><span data-stu-id="a9904-102">Getting started - .NET WPF</span></span>

<span data-ttu-id="a9904-103">설명 했 듯이 [Getting Started](../../../authoring-cards/getting-started.md) 페이지 Adaptive Card는 JSON 직렬화 된 카드 개체 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="a9904-103">As we described in [Getting Started](../../../authoring-cards/getting-started.md) page, an Adaptive Card is a JSON-serialized card object model.</span></span> <span data-ttu-id="a9904-104">이 라이브러리 쉽게 앱 내에서 사용할 수 있는 WPF UI에는 JSON을 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9904-104">This library makes it easy to render that JSON into WPF UI that you can use within your app.</span></span>

## <a name="nuget-install"></a><span data-ttu-id="a9904-105">NuGet 설치</span><span class="sxs-lookup"><span data-stu-id="a9904-105">NuGet install</span></span>

<span data-ttu-id="a9904-106">[![Nuget 설치](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf)</span><span class="sxs-lookup"><span data-stu-id="a9904-106">[![Nuget install](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf)</span></span>

```console
Install-Package AdaptiveCards.Rendering.Wpf
```

### <a name="xceed-enhanced-input-package"></a><span data-ttu-id="a9904-107">Xceed 입력된 패키지 향상</span><span class="sxs-lookup"><span data-stu-id="a9904-107">Xceed enhanced input package</span></span>

<span data-ttu-id="a9904-108">이 선택적 패키지 즉시 WPF 제공 하는 것 이상의 적응 카드 입력 제어를 강화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9904-108">This optional package enhances the Adaptive Card Input controls beyond what WPF provides out of the box.</span></span> <span data-ttu-id="a9904-109">에 대 한 종속성 `Extended.Wpf.Toolkit`</span><span class="sxs-lookup"><span data-stu-id="a9904-109">It has a dependency on `Extended.Wpf.Toolkit`</span></span>

<span data-ttu-id="a9904-110">[![Nuget 설치](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.Xceed.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf.Xceed)</span><span class="sxs-lookup"><span data-stu-id="a9904-110">[![Nuget install](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.Xceed.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf.Xceed)</span></span>

```console
Install-Package AdaptiveCards.Rendering.Wpf.Xceed
```

## <a name="wpf-visualizer-sample"></a><span data-ttu-id="a9904-111">WPF 시각화 도우미 샘플</span><span class="sxs-lookup"><span data-stu-id="a9904-111">WPF Visualizer Sample</span></span>

![시각화 도우미 스크린 샷](../../../resources/media/tools/wpfvisualizer.png)

<span data-ttu-id="a9904-113">합니다 [WPF 시각화 도우미 샘플](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) 사용 WPF를 사용 하 여 카드를 시각화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9904-113">The [WPF Visualizer sample](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) lets you visualize cards using WPF.</span></span>  <span data-ttu-id="a9904-114">`Host Config` 호스트 구성 설정 보기 및 편집에 대 한 편집기 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9904-114">A `Host Config` editor is built in for editing and viewing host config settings.</span></span> <span data-ttu-id="a9904-115">응용 프로그램에서 렌더링에서 사용 하는 JSON으로 이러한 설정을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9904-115">Save these settings as a JSON to use them in rendering in your application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a9904-116">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a9904-116">Next steps</span></span>

<span data-ttu-id="a9904-117">참조 [카드를 렌더링할](render-a-card.md) 다음 단계!</span><span class="sxs-lookup"><span data-stu-id="a9904-117">See [Render a card](render-a-card.md) for the next steps!</span></span>
