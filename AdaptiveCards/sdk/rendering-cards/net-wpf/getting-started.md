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
# <a name="getting-started---net-wpf"></a>시작 하기-.NET WPF

[시작](../../../authoring-cards/getting-started.md) 페이지에서 설명한 대로 적응 카드는 JSON 직렬화 카드 개체 모델입니다. 이 라이브러리를 사용 하면 응용 프로그램 내에서 사용할 수 있는 WPF UI로 해당 JSON을 쉽게 렌더링할 수 있습니다.

## <a name="nuget-install"></a>NuGet 설치

[![Nuget 설치](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf)

```console
Install-Package AdaptiveCards.Rendering.Wpf
```

### <a name="xceed-enhanced-input-package"></a>Xceed 고급 입력 패키지

이 선택적 패키지는 WPF에서 제공 하는 것 이상의 기능을 제공 합니다. 다음에 대 한 종속성이 있습니다.`Extended.Wpf.Toolkit`

[![Nuget 설치](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.Xceed.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf.Xceed)

```console
Install-Package AdaptiveCards.Rendering.Wpf.Xceed
```

## <a name="wpf-visualizer-sample"></a>WPF 시각화 도우미 샘플

![시각화 도우미 스크린샷](../../../resources/media/tools/wpfvisualizer.png)

[Wpf 시각화 도우미 샘플](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) 에서는 wpf를 사용 하 여 카드를 시각화할 수 있습니다.  호스트 구성 설정을 편집 하 고 볼 수 있는 편집기가기본제공됩니다.`Host Config` 응용 프로그램에서 렌더링 하는 데 사용할 수 있도록 이러한 설정을 JSON으로 저장 합니다.

## <a name="next-steps"></a>다음 단계

[카드 렌더링](render-a-card.md)에서 다음 단계를 확인합니다.
