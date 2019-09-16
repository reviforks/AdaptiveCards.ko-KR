---
title: 적응형 카드 도구
author: matthidinger
ms.author: mahiding
ms.date: 03/14/2019
ms.topic: article
ms.openlocfilehash: ad520693224509deaf0ea1c2cd6a837089dbf2d5
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67137986"
---
# <a name="tools-and-samples"></a>도구 및 샘플

## <a name="card-designer"></a>카드 디자이너 

카드를 디자인하려면 도구가 필요한가요? [https://adaptivecards.io/designer](https://adaptivecards.io/designer)에서 브라우저 기반 적응형 카드 디자이너만 찾으면 됩니다.

[![디자이너 스크린샷](media/tools/designer.jpg)](https://adaptivecards.io/designer)

### <a name="embed-the-designer-into-your-app"></a>앱에 디자이너 포함

그러나 JavaScript 라이브러리를 사용하여 **웹앱에 직접 카드 디자이너를 포함**할 수 있을 때 사용자를 해당 위치로 보내는 이유입니다. 

시작하려면 [adaptivecards-designer](https://npmjs.com/adaptivecards-designer) 패키지를 체크 아웃합니다.

## <a name="schema-validation"></a>스키마 유효성 검사

스키마 유효성 검사는 쉽게 작성하고 도구를 사용할 수 있는 강력한 방법입니다.

json에서 적응형 카드를 편집하고 유효성 검사하는 데 필요한 전체 [JSON 스키마 파일](http://adaptivecards.io/schemas/1.2.0/adaptive-card.json)을 제공했습니다. 스키마 URL의 버전이 지정되었으므로 최신 버전의 적응형 카드에 해당 URL이 포함됩니다.

Visual Studio 및 Visual Studio Code에서 `$schema` 참조를 포함하여 자동 IntelliSense를 가져올 수 있습니다.

![불량](media/tools/invalidjson1.png)

![자동 완성](media/tools/autocomplete.png)

## <a name="example"></a>예

```json
{
    "$schema": "http://adaptivecards.io/schemas/1.2.0/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

## <a name="visual-studio-code-extension"></a>Visual Studio Code 확장

편집기 자체에서 실시간으로 편집 중인 카드를 시각화할 수 있는 Visual Studio Code 확장을 만들었습니다. 

![확장](media/tools/vscode-extension.png)

설치하려면 확장 Marketplace를 열고 **적응형 카드 뷰어**를 검색합니다.

![marketplace](media/tools/vscode-extension-marketplace.png)

### <a name="usage"></a>사용

적응형 카드 `$schema` 속성으로 .json 파일을 편집하는 경우 `Ctrl+Shift+V A`를 사용하여 볼 수 있습니다.
```json
{
    "$schema": "http://adaptivecards.io/schemas/1.2.0/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

### <a name="options"></a>옵션

다음 Visual Studio Code 설정은 AdaptiveCards 뷰어에 사용할 수 있습니다. 이는 사용자 설정 또는 작업 영역 설정에서 설정할 수 있습니다.

```js
{
    // Open or not open the preview screen automatically
    "adaptivecardsviewer.enableautopreview": true,
}
```

## <a name="wpf-visualizer-sample"></a>WPF 시각화 도우미 샘플

[WPF 시각화 도우미 샘플 프로젝트](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer)를 사용하면 Windows 머신에서 WPF/Xaml을 사용하여 카드를 시각화할 수 있습니다.  호스트 구성 설정을 편집하고 볼 수 있도록 `hostconfig` 편집기가 기본 제공됩니다. 이 설정을 JSON으로 저장하여 애플리케이션의 렌더링에 사용합니다.

![WPF 시각화 도우미](media/tools/wpfvisualizer.png)

## <a name="wpf-imagerender-sample"></a>WPF ImageRender 샘플

[ImageRender 샘플 프로젝트](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/AdaptiveCards.Sample.ImageRender)는 WPF를 사용하여 명령줄에서 카드를 PNG로 변환합니다. 
