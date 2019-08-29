---
title: 기본 스타일 지정-.NET WPF SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: ee5bec1a11f39ad69d40e57410c105b50ba45981
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552725"
---
# <a name="native-styling---net-wpf"></a>기본 스타일 지정-.NET WPF

호스트 구성에는 각 플랫폼에 대 한 대부분의 방법이 있지만 각 플랫폼에서 기본 스타일 지정을 수행 해야 할 가능성이 있습니다. 

WPF를 사용 하면 세분화 된 스타일, 동작, 애니메이션 등에 대해 ResourceDictionary를 전달할 수 있으므로이를 쉽게 수행할 수 있습니다.

| 요소 | 스타일 이름 |
|---|---|
| AdaptiveCard | 적응 카드| 
| 작업. OpenUrl  | 적응. Action. OpenUrl  |
| 작업. ShowCard | 적응. 작업 ... ShowCard |
| 작업. 제출  | 적응. 작업. 제출  |
| Column | 적응형 열, 적응. 동작 탭 |
| ColumnSet | ColumnSet, VerticalSeparator |
| 컨테이너 | 적응 컨테이너|
| ChoiceSet | ChoiceSet, ChoiceSet, ChoiceSet, ChoiceSet, ComboBoxItem,, .입니다. .입니다. |
| 입력. 날짜 | 적응형. 텍스트. 날짜
| 입력. Number | 적응형. 텍스트 번호 |
| 입력. 텍스트 | 적응형. 입력. 텍스트 |
| 입력. 시간 | 적응. 텍스트. 시간 |
| 입력. 전환| 적응형. 입력. 전환|
| 이미지  | 적응. 이미지 |
| ImageSet  | 적응 ImageSet |
| FactSet | FactSet, 적응. fact.-Value |
| TextBlock  | 적응형. TextBlock |

이 샘플 XAML 리소스 사전은 모든 Textblock의 배경을 바다색으로 설정 합니다. 이 작업 보다 더 고급 작업을 원하는 경우😁

```xml
<ResourceDictionary
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" 
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
    <Style x:Key="Adaptive.TextBlock" TargetType="TextBlock">
        <Setter Property="Background" Value="Aqua"></Setter>
    </Style>
</ResourceDictionary>
```
```csharp
// Use a ResourceDictionary instance
// DON'T use this property if rendering from a server
renderer.Resources = myResourceDictionary;

// ... or load it from a file path
// USE this if rendering from a server
renderer.ResourcesPath = <path-to-my-resource-dictionary.xaml>;
```

> [!IMPORTANT]
> **서버 쪽 이미지 생성에 대 한 참고 사항** WPF 렌더러는 서버측 이미지 `RenderCardToImageAsync` 생성에 사용할 수 있는 메서드를 제공 합니다. 이 환경에서 사용 하 `ResourcesPath` 는 경우에만 속성을 사용 해야 합니다. 자세한 내용은 [이미지 렌더링](../net-image/getting-started.md) 문서를 참조 하세요.