---
title: 기본 스타일링 - Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: ebb033c68b9aedcaacb1989ffb1bec48707a9026
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67134245"
---
# <a name="native-styling---android"></a>기본 스타일링 - Android

Android 렌더러는 기본 스타일링을 지원하지 않지만, v1.2에서는 일부 속성의 스타일링이 도입되었습니다.

## <a name="action-sentiment"></a>작업 감정

**v1.2**에는 작업 감정이 포함되어 있으며 다른 버전만큼 다양한 스타일을 지원하지는 않습니다. 유효한 스타일을 구현하고 다음 줄을 프로젝트의 styles.xml에 추가하여 *부정적* 또는 *긍정적* 감정이 포함된 작업을 스타일링할 수 있습니다.

```styles.xml
 <item name="adaptiveActionDestructive">@style/adaptiveActionDestructive</item>
 <item name="adaptiveActionPositive">@style/adaptiveActionPositive</item>
```

## <a name="inline-action"></a>인라인 작업

인라인 작업을 사용하는 텍스트 입력은 렌더링하려는 작업의 스타일링을 허용합니다. 이를 이용하여 작업을 단추(adaptiveInlineAction) 또는 이미지(adaptiveInlineActionImage)로 스타일링할 수 있습니다.

```styles.xml
 <item name="adaptiveInlineAction">@style/adaptiveInlineAction</item>
 <item name="adaptiveInlineActionImage">@style/adaptiveInlineActionImage</item>
```

> [!IMPORTANT]
> 렌더러는 항목의 정확한 이름을 검색하므로 모든 항목 이름을 여기에 보이는 것처럼 유지해야 합니다.
