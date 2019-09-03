---
title: 렌더러 상태
author: matthidinger
ms.author: mahiding
ms.date: 10/12/2018
ms.topic: article
ms.openlocfilehash: bffa49012a8ebe686fc033f98b2438d2e9e959cc
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67138036"
---
# <a name="renderer-status"></a>렌더러 상태
아래 표에서는 공개 게시된 버전을 기반으로 각 렌더러의 현재 상태를 보여 줍니다.

### <a name="parsing"></a>구문 분석

|기능 | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|유효성 검사 실패 반환 | ✅ | ✅ | ✅ | ✅ | ✅ |
|알 수 없는 속성 구문 분석 | ✅ | ✅ | ✅ | ✅ | ✅ |

### <a name="card-rendering"></a>카드 렌더링

|기능 | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|지원되는 버전 확인 | ✅ | ✅ | ✅ | ✅ | ✅  |
|전체 스키마 렌더링 | ✅ | ✅ | ✅ | ✅ | ✅ |
|작업 모음 렌더링 | ✅ | ✅ | ✅ | ✅ | ✅ |
|알 수 없는 요소 무시 | ✅ | ✅ | ✅ | ✅ | ✅ |
|호스트 구성 지원 | ✅ | ✅ | ✅ | ✅ | ✅ |
|네이티브 플랫폼 스타일 지정 | ✅ | ✅ | ✅ | ✅ | ✅ |

### <a name="element-rendering"></a>요소 렌더링

|기능 | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|간격 및 구분 기호 | ✅ | ✅ | ✅ | ✅ | ✅ |
|[TextBlock 날짜/시간 형식](../authoring-cards/text-features.md#datetime-formatting-and-localization) | ✅ | ✅ | ✅ | ✅ | ✅ |
|[TextBlock Markdown 지원](../authoring-cards/text-features.md#markdown) | ✅* | ✅ | ✅ | ✅ | ✅ |
|전체 입력 지원 | ✅ | ✅ | ✅ | ✅ | ✅ |

\* HTML 렌더러는 라이브러리의 크기를 최소화하고 소비하는 애플리케이션이 선호하는 Markdown 프로세서를 사용하도록 하기 위해 기본 제공 Markdown 지원을 포함하지 않습니다. 그러나 HTML 렌더러는 로드되는 경우 자동으로 Markdown-It을 사용합니다.

### <a name="extensibility"></a>확장성

|기능 | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|요소 렌더러 재정의 | ✅ | ✅ | ✅ | ✅ | ✅ |
|새 요소 렌더러 추가 | ✅ | ✅ | ✅ | ✅ | ✅ |
|요소 렌더러 제거 | ✅ | ✅ | ✅ | ✅ | ✅ |
|[작업 렌더러 재정의/추가/제거](https://github.com/Microsoft/AdaptiveCards/issues/1671) | ✅ | ✅ | ❌ | ✅ | ✅ |

### <a name="actions"></a>조치

| 기능 | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
| Action.OpenUrl 지원 | ✅ | ✅ | ✅ | ✅ | ✅  |
| Action.ShowCard 지원  | ✅ | ✅ | ✅ | ✅ | ✅ |
| Action.Submit 지원  | ✅ | ✅ | ✅ | ✅ | ✅  |
| selectAction 지원 | ✅ | ✅ | ✅ | ✅ | ✅ |

### <a name="events"></a>이벤트

|       기능        | HTML | .NET | UWP | iOS | Android | 
|----------------------------|------|------|-----|-----|---------|
| 요소 표시 여부 변경됨 |  ✅   |  ❌   |  ❌  |  ❌  | ❌ |

