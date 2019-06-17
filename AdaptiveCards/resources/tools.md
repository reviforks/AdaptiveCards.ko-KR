---
title: Adaptive Card 도구
author: matthidinger
ms.author: mahiding
ms.date: 03/14/2019
ms.topic: article
ms.openlocfilehash: ad520693224509deaf0ea1c2cd6a837089dbf2d5
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67137986"
---
# <a name="tools-and-samples"></a>도구 및 샘플

## <a name="card-designer"></a>카드 디자이너 

카드를 디자인 하는 도구에 대 한 필요 합니까? 브라우저 기반 적응 카드에 디자이너에 더 [https://adaptivecards.io/designer](https://adaptivecards.io/designer)

[![디자이너의 스크린 샷](media/tools/designer.jpg)](https://adaptivecards.io/designer)

### <a name="embed-the-designer-into-your-app"></a>앱에 디자이너를 포함 합니다.

그러나 가능한 경우 사용자가 있는 송신 하는 이유 **카드 디자이너 웹에 직접 포함** JavaScript 라이브러리를 사용 하 여 앱. 

체크 아웃 합니다 [adaptivecards 디자이너](https://npmjs.com/adaptivecards-designer) 패키지를 시작 합니다.

## <a name="schema-validation"></a>스키마 유효성 검사

스키마 유효성 검사는 쉽게 작성 하 고 도구를 사용 하도록 설정 하도록 하는 강력한 방법입니다.

전체 제공 했습니다 [JSON 스키마 파일](http://adaptivecards.io/schemas/1.2.0/adaptive-card.json) 편집 하 고 json에서 adaptive card의 유효성을 검사 합니다. 스키마 URL 버전으로 최신 버전의 Adaptive Card는 해당 URL을 갖게 됩니다.

Visual Studio 및 Visual Studio Code에서 포함 하 여 자동 Intellisense를 가져올 수 있습니다는 `$schema` 참조 합니다.

![잘못 된](media/tools/invalidjson1.png)

![자동 완성](media/tools/autocomplete.png)

## <a name="example"></a>예제

```json
{
    "$schema": "http://adaptivecards.io/schemas/1.2.0/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

## <a name="visual-studio-code-extension"></a>Visual Studio Code 확장

자체 편집기 내부에서 실시간으로 편집 하는 카드를 시각화할 수 있는 Visual Studio 코드 확장을 만들었습니다. 

![확장](media/tools/vscode-extension.png)

를 설치 하려면 확장 Marketplace 열고 검색할 **적응 카드 뷰어**합니다.

![marketplace](media/tools/vscode-extension-marketplace.png)

### <a name="usage"></a>사용법

Adaptive Card를 사용 하 여.json 파일을 편집할 때 `$schema` 속성을 사용 하 여 볼 수 있습니다 `Ctrl+Shift+V A`합니다.
```json
{
    "$schema": "http://adaptivecards.io/schemas/1.2.0/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

### <a name="options"></a>변수

다음 Visual Studio Code 설정은입니다 AdaptiveCards 뷰어를 사용할 수 있습니다. 사용자 설정 또는 작업 영역 설정을 설정할 수 있습니다.

```js
{
    // Open or not open the preview screen automatically
    "adaptivecardsviewer.enableautopreview": true,
}
```

## <a name="wpf-visualizer-sample"></a>WPF 시각화 도우미 샘플

합니다 [WPF 시각화 도우미 샘플 프로젝트](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) 사용 WPF/Xaml을 사용 하 여 Windows 컴퓨터에서 카드를 시각화할 수 있습니다.  `hostconfig` 호스트 구성 설정 보기 및 편집에 대 한 편집기 빌드됩니다. 응용 프로그램에서 렌더링에서 사용 하는 JSON으로 이러한 설정을 저장 합니다.

![wpf 시각화 도우미](media/tools/wpfvisualizer.png)

## <a name="wpf-imagerender-sample"></a>WPF ImageRender 샘플

합니다 [ImageRender 샘플 프로젝트](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/AdaptiveCards.Sample.ImageRender) WPF를 사용 하 여 명령줄에서 PNG 모든 카드가 바뀝니다. 
