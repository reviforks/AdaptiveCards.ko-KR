---
title: 렌더러 상태
author: matthidinger
ms.author: mahiding
ms.date: 10/12/2018
ms.topic: article
ms.openlocfilehash: bffa49012a8ebe686fc033f98b2438d2e9e959cc
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67138036"
---
# <a name="renderer-status"></a>렌더러 상태
다음 표에서 해당 공용 게시 된 버전에 따라 각 렌더러의 현재 상태를 보여 줍니다.

### <a name="parsing"></a>구문 분석

|기능 | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|유효성 검사 오류를 반환 합니다. | ✅ | ✅ | ✅ | ✅ | ✅ |
|알 수 없는 속성을 구문 분석 | ✅ | ✅ | ✅ | ✅ | ✅ |

### <a name="card-rendering"></a>카드 렌더링

|기능 | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|지원 되는 버전 확인 | ✅ | ✅ | ✅ | ✅ | ✅  |
|전체 스키마를 렌더링 합니다. | ✅ | ✅ | ✅ | ✅ | ✅ |
|작업 표시줄 렌더링 | ✅ | ✅ | ✅ | ✅ | ✅ |
|알 수 없는 요소를 무시 합니다. | ✅ | ✅ | ✅ | ✅ | ✅ |
|호스트 구성 지원 | ✅ | ✅ | ✅ | ✅ | ✅ |
|네이티브 플랫폼 스타일 지정 | ✅ | ✅ | ✅ | ✅ | ✅ |

### <a name="element-rendering"></a>요소 렌더링

|기능 | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|간격 및 구분 기호 | ✅ | ✅ | ✅ | ✅ | ✅ |
|[TextBlock의 날짜/시간 형식](../authoring-cards/text-features.md#datetime-formatting-and-localization) | ✅ | ✅ | ✅ | ✅ | ✅ |
|[TextBlock Markdown 지원](../authoring-cards/text-features.md#markdown) | ✅* | ✅ | ✅ | ✅ | ✅ |
|전체 입력 지원 | ✅ | ✅ | ✅ | ✅ | ✅ |

\* HTML 렌더러 라이브러리의 크기를 최소화 하 고 해당 기본 Markdown 프로세서를 사용 하는 응용 프로그램이 수 있도록 기본 Markdown 지원을 포함 되지 않습니다. 그러나 자동으로 HTML 렌더러는 로드 되 면 It Markdown을 사용 합니다.

### <a name="extensibility"></a>확장성

|기능 | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|요소 렌더러를 재정의 합니다. | ✅ | ✅ | ✅ | ✅ | ✅ |
|새 요소 렌더러를 추가 합니다. | ✅ | ✅ | ✅ | ✅ | ✅ |
|요소 렌더러를 제거 합니다. | ✅ | ✅ | ✅ | ✅ | ✅ |
|[재정의/추가/제거 작업 렌더러](https://github.com/Microsoft/AdaptiveCards/issues/1671) | ✅ | ✅ | ❌ | ✅ | ✅ |

### <a name="actions"></a>동작

| 기능 | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
| Action.OpenUrl 지원 | ✅ | ✅ | ✅ | ✅ | ✅  |
| Action.ShowCard 지원  | ✅ | ✅ | ✅ | ✅ | ✅ |
| Action.Submit 지원  | ✅ | ✅ | ✅ | ✅ | ✅  |
| selectAction 지원 | ✅ | ✅ | ✅ | ✅ | ✅ |

### <a name="events"></a>이벤트

|       기능        | HTML | .NET | UWP | iOS | Android | 
|----------------------------|------|------|-----|-----|---------|
| 요소 표시 유형 변경 |  ✅   |  ❌   |  ❌  |  ❌  | ❌ |

