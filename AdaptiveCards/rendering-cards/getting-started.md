---
title: 애플리케이션 내에서 카드 렌더링
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 0a5f99268ce483fddd99f4493b386db796c3e9d2
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67138096"
---
# <a name="rendering-cards-inside-your-application"></a>애플리케이션 내에서 카드 렌더링

애플리케이션 내에서 적응형 카드를 쉽게 렌더링할 수 있습니다. 모든 일반적인 플랫폼용 SDK를 제공하며 고유한 적응형 카드 렌더러를 만드는 데 필요한 [자세한 사양](implement-a-renderer.md)을 제공합니다.

1. **렌더러 SDK 설치** - 대상 플랫폼에 해당합니다.
2. **렌더러 인스턴스 만들기** - 앱 스타일, 규칙 및 작업 이벤트 처리기를 사용하여 구성됩니다.
3. **카드를 네이티브 UI로 렌더링** - 자동으로 앱에 맞게 스타일이 지정됩니다.

## <a name="adaptive-cards-sdks"></a>적응형 카드 SDK

|플랫폼|설치|빌드|문서|상태|
|---|---|---|---|---|
| JavaScript | [![npm 설치](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards) | [원본](https://github.com/Microsoft/AdaptiveCards/tree/master/source/nodejs)| [문서](../sdk/rendering-cards/javascript/getting-started.md) | ![빌드 상태](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20564.svg) |
| .NET WPF | [![NuGet 설치](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf) | [원본](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet)| [문서](../sdk/rendering-cards/net-wpf/getting-started.md) | ![빌드 상태](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20596.svg) |
| .NET HTML | [![NuGet 설치](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Html.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Html) | [원본](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet) | [문서](../sdk/rendering-cards/net-html/getting-started.md) | ![빌드 상태](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20596.svg) |
| Windows UWP | [![NuGet 설치](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Uwp.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Uwp) | [원본](https://github.com/Microsoft/AdaptiveCards/tree/master/source/uwp) | [문서](../sdk/rendering-cards/uwp/getting-started.md) | ![빌드 상태](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20583.svg) |
| Android | [![Maven Central](https://img.shields.io/maven-central/v/io.adaptivecards/adaptivecards-android.svg)](https://search.maven.org/#search%7Cga%7C1%7Ca%3A%22adaptivecards-android%22) | [원본](https://github.com/Microsoft/AdaptiveCards/tree/master/source/android) | [문서](../sdk/rendering-cards/android/getting-started.md) | ![빌드 상태](https://img.shields.io/vso/build/Microsoft/8d47e068-03c8-4cdc-aa9b-fc6929290322/17651.svg)
| iOS | [![CocoaPods](https://img.shields.io/cocoapods/v/AdaptiveCards.svg)](https://cocoapods.org/pods/AdaptiveCards) | [원본](https://github.com/Microsoft/AdaptiveCards/tree/master/source/ios) | [문서](../sdk/rendering-cards/ios/getting-started.md) |  ![빌드 상태](https://img.shields.io/vso/build/Microsoft/8d47e068-03c8-4cdc-aa9b-fc6929290322/16990.svg) |

## <a name="create-an-instance-of-the-renderer"></a>렌더러 인스턴스 만들기

다음 단계는 `AdaptiveCardRenderer` 인스턴스를 만드는 것입니다. 

### <a name="hook-up-action-events"></a>작업 이벤트 연결

기본적으로 작업은 카드에 단추로 렌더링되지만 앱에서 사용자가 원하는 대로 작동하도록 설정할 수 있습니다. 각 SDK에는 처리해야 하는 `OnAction` 이벤트에 해당하는 항목이 있습니다.

* **Action.OpenUrl** - 지정된 `url`을 엽니다.  
* **Action.Submit** - 제출 결과를 가져오고 원본으로 보냅니다. 카드 원본으로 보내는 방법은 사용자가 결정할 수 있습니다.
* **Action.ShowCard** - 대화 상자를 호출하고 해당 대화 상자에 하위 카드를 렌더링합니다. `ShowCardActionMode`가 `popup`으로 설정되는 경우에만 이 항목을 처리해야 합니다.

## <a name="render-a-card"></a>카드 렌더링

카드 페이로드를 얻은 후 렌더러를 호출하고 카드에 전달하세요. 그러면 카드 콘텐츠로 구성된 네이티브 UI 개체를 다시 얻게 됩니다. 이제 이 UI를 앱 내에 배치합니다.

## <a name="customization"></a>사용자 지정

렌더링되는 항목을 사용자 지정할 수 있는 여러 가지 방법이 있습니다. 

### <a name="hostconfig"></a>HostConfig

[HostConfig](host-config.md)는 앱 내에서 카드의 기본 스타일과 동작을 제어하는 플랫폼 간 공유 구성 개체입니다. 글꼴 크기, 요소 간의 간격, 색, 지원되는 작업 수 등의 항목을 정의합니다. 

### <a name="native-platform-styling"></a>네이티브 플랫폼 스타일 지정

대부분의 UI 프레임워크에서는 네이티브 UI 프레임워크 스타일을 사용하여 렌더링된 카드의 스타일을 지정할 수 있습니다. 예를 들어 HTML에서는 HTML의 CSS 클래스를 지정할 수 있고, XAML에서는 출력을 세밀하게 제어하기 위한 사용자 지정 ResourceDictionary에 전달할 수 있습니다.

### <a name="customize-per-element-rendering"></a>요소별 렌더링 사용자 지정

각 SDK를 사용하여 요소의 렌더링을 재정의하거나, 사용자가 정의하는 완전히 새로운 요소의 지원을 추가할 수도 있습니다.  예를 들어 렌더러의 나머지 출력을 계속 유지하면서 고유한 사용자 지정 컨트롤을 내보내도록 `Input.Date` 렌더러를 변경할 수 있습니다. 또는 사용자가 정의한 사용자 지정 `Rating` 요소의 지원을 추가할 수 있습니다.



