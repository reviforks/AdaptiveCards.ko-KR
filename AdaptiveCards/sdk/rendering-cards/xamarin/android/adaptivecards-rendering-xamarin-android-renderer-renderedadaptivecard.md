---
title: RenderedAdaptiveCard 클래스-Xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: 608b28638ce6ed0a218cfc8dbbe73f22de1ab8cb
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145997"
---
# <a name="renderedadaptivecard"></a>RenderedAdaptiveCard

```csharp
public class RenderedAdaptiveCard : Java.Lang.Object
```

**Namespace**

```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.Renderer
```

### <a name="summary"></a>요약

| 특성 | |
| ---- | --- |
| AdaptiveCard | 렌더링 된 적응 카드의 논리적 표현입니다. |
| 입력 | 사용자가 추가한 입력 요소의 사전 및 정보입니다. |
| &gt; | 렌더링 프로세스의 시각적 결과입니다. |
| 경고 | 렌더링 프로세스에서 생성 된 경고 목록입니다. |

&nbsp;

| public 메서드 | |
| --- | ---- |
| ```void``` | [```AddWarning AdaptiveCards.Rendering.Xamarin.Android.Renderer.AdaptiveWarning warning)```](#addwarning) |

## <a name="public-methods"></a>공용 메서드

---

### <a id="addwarning"></a>AddWarning
<p style='text-align:right'>버전 0.1에 추가 됨</p>

```csharp
public void AddWarning (AdaptiveWarning warning)

```

경고 목록에 경고를 추가 합니다.

| 매개 변수 | |
| --- | --- |
| 경고 | ```AdaptiveCards.Rendering.Xamarin.Android.Renderer.AdaptiveWarning``` |
