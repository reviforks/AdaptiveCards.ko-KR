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

호스트 구성 것입니다 얻게 하면 대부분의 정도 각 플랫폼에서 가능성이 각 플랫폼에서 몇 가지 기본 스타일 지정을 수행 해야 합니다. 

WPF 쉽게이 세분화 된 스타일, 동작, 애니메이션 등 ResourceDictionary를 전달할 수 있도록 하 여 합니다.

| 요소 | 유형 이름 |
|---|---|
| AdaptiveCard | Adaptive.Card| 
| Action.OpenUrl  | Adaptive.Action.OpenUrl  |
| Action.ShowCard | Adaptive.Action.ShowCard |
| Action.Submit  | Adaptive.Action.Submit  |
| Column | Adaptive.Column, Adaptive.Action.Tap |
| ColumnSet | Adaptive.ColumnSet, Adaptive.VerticalSeparator |
| 컨테이너 | Adaptive.Container|
| Input.ChoiceSet | Adaptive.Input.ChoiceSet,  Adaptive.Input.ChoiceSet.ComboBox, Adaptive.Input.ChoiceSet.CheckBox,  Adaptive.Input.ChoiceSet.Radio,  Adaptive.Input.ChoiceSet.ComboBoxItem |
| Input.Date | Adaptive.Input.Text.Date
| Input.Number | Adaptive.Input.Text.Number |
| Input.Text | Adaptive.Input.Text |
| Input.Time | Adaptive.Input.Text.Time |
| Input.Toggle| Adaptive.Input.Toggle|
| image  | Adaptive.Image |
| ImageSet  | Adaptive.ImageSet |
| FactSet | Adaptive.FactSet, Adaptive.Fact.Title, Adaptive.Fact.Value |
| TextBlock  | Adaptive.TextBlock |

모든 Textblock의 배경색을 바다색으로 설정 된이 샘플 XAML 리소스 사전입니다. 싶을 것이 보다 고급 항목 😁

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
> **서버 쪽 이미지 생성에 대 한 메모** The WPF 렌더러는 제공을 `RenderCardToImageAsync` 서버 쪽 이미지 생성에 사용할 수 있는 메서드. 만 사용 해야 합니다는 `ResourcesPath` 이 환경에서 사용 하는 경우에 속성입니다. 참조 된 [이미지 렌더링](../net-image/getting-started.md) 자세한 docs