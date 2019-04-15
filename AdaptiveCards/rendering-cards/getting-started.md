---
title: 응용 프로그램 내에서 카드를 렌더링합니다.
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 0a9507c56a8bae9f038c220cdf55e34b2c3b0829
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552925"
---
# <a name="rendering-cards-inside-your-application"></a>응용 프로그램 내에서 카드를 렌더링합니다.

응용 프로그램 내에서 Adaptive Card를 렌더링 하는 것이 쉽습니다. 에서는 모든 일반적인 플랫폼용 Sdk를 제공 합니다. 뿐만 아니라 제공을 [사양 자세한](implement-a-renderer.md) 고유한 Adaptive Card 렌더러를 만들기 위한 합니다.

1. **렌더러를 SDK 설치** -대상 플랫폼에 대 한 합니다.
2. **렌더러 인스턴스를 만들고** -앱의 스타일, 규칙 및 작업 이벤트 처리기를 사용 하 여 구성 합니다.
3. **카드와 네이티브 UI 렌더링** -앱에 스타일이 자동으로 적용 합니다.

## <a name="adaptive-cards-sdks"></a>Adaptive Card Sdk

|플랫폼|Install|빌드|문서|상태|
|---|---|---|---|---|
| JavaScript | [![npm 설치](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards) | [원본](https://github.com/Microsoft/AdaptiveCards/tree/master/source/nodejs)| [Docs](../sdk/rendering-cards/javascript/getting-started.md) | ![빌드 상태](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20564.svg) |
| .NET WPF | [![Nuget 설치](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf) | [원본](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet)| [Docs](../sdk/rendering-cards/net-wpf/getting-started.md) | ![빌드 상태](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20596.svg) |
| .NET HTML | [![Nuget 설치](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Html.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Html) | [원본](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet) | [Docs](../sdk/rendering-cards/net-html/getting-started.md) | ![빌드 상태](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20596.svg) |
| Windows UWP | [![Nuget 설치](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Uwp.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Uwp) | [원본](https://github.com/Microsoft/AdaptiveCards/tree/master/source/uwp) | [Docs](../sdk/rendering-cards/uwp/getting-started.md) | ![빌드 상태](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20583.svg) |
| Android | [![Maven Central](https://img.shields.io/maven-central/v/io.adaptivecards/adaptivecards-android.svg)](https://search.maven.org/#search%7Cga%7C1%7Ca%3A%22adaptivecards-android%22) | [원본](https://github.com/Microsoft/AdaptiveCards/tree/master/source/android) | [Docs](../sdk/rendering-cards/android/getting-started.md) | ![빌드 상태](https://img.shields.io/vso/build/Microsoft/8d47e068-03c8-4cdc-aa9b-fc6929290322/17651.svg)
| iOS | [![CocoaPods](https://img.shields.io/cocoapods/v/AdaptiveCards.svg)](https://cocoapods.org/pods/AdaptiveCards) | [원본](https://github.com/Microsoft/AdaptiveCards/tree/master/source/ios) | [Docs](../sdk/rendering-cards/ios/getting-started.md) |  ![빌드 상태](https://img.shields.io/vso/build/Microsoft/8d47e068-03c8-4cdc-aa9b-fc6929290322/16990.svg) |

## <a name="create-an-instance-of-the-renderer"></a>렌더러의 인스턴스를 만듭니다

인스턴스를 만들려면 다음 단계는는 `AdaptiveCardRenderer`합니다. 

### <a name="hook-up-action-events"></a>작업 이벤트 후크

기본적으로 카드에서 단추도 렌더링 됩니다. 작업 되지만 예상 대로 작동 되도록 할 앱에 달려 있습니다. 각 SDK에 해당 하는 `OnAction` 처리 해야 하는 이벤트입니다.

* **Action.OpenUrl** -지정 된 열 `url`합니다.  
* **Action.Submit** -제출 결과 및 원본에 전송 합니다. 전적으로 사용자가 어떻게 보내기 카드의 원본입니다.
* **Action.ShowCard** -대화 상자를 호출 하 고 해당 대화 상자에 하위 카드를 렌더링 합니다. 참고만 할 경우이 처리할 `ShowCardActionMode` 로 설정 된 `popup`합니다.

## <a name="render-a-card"></a>카드를 렌더링 합니다.

카드 페이로드를 획득 한 후 렌더러를 호출 하 고 카드의 전달 하기만 하면 됩니다. 카드 내용을 이루어져 네이티브 UI를 얻게 됩니다. 이제 방금 어딘가에이 UI 앱에서.

## <a name="customization"></a>사용자 지정

여러 가지 방법으로 렌더링할 대상을 사용자 지정할 수 있습니다. 

### <a name="hostconfig"></a>HostConfig

A [HostConfig](host-config.md) 은 기본 스타일 지정 및 앱 내에서 카드의 동작을 제어 하는 공유 되는 플랫폼 간 구성 개체입니다. 글꼴 크기, 요소, 색, 수 등 지원 되는 작업 간의 간격 등을 정의 합니다. 

### <a name="native-platform-styling"></a>네이티브 플랫폼 스타일 지정

대부분의 UI 프레임 워크를 사용 하면 네이티브 UI 프레임 워크 스타일을 사용 하 여 렌더링 된 카드 스타일을 수 있습니다. 예를 들어 HTML에서 html, CSS 클래스를 지정할 수 있습니다 또는 XAML에서 전달할 수 있습니다 ResourceDictionary를 사용자 지정에서 출력의 세분화 된 컨트롤에 대 한 합니다.

### <a name="customize-per-element-rendering"></a>요소 마다 렌더링을 사용자 지정

각 SDK를 사용 하면 모든 요소의 렌더링을 재정의 하거나 정의 하는 완전히 새로운 요소에 대 한 지원을 추가할 수 있습니다.  예를 들어, 변경할 수 있습니다는 `Input.Date` 렌더러 렌더러의 출력의 나머지 부분을 유지 하면서 사용자 고유의 사용자 지정 컨트롤을 내보낼 수 있습니다. 사용자 지정에 대 한 지원을 추가할 수 있습니다 또는 `Rating` 요소 수를 정의 합니다.



