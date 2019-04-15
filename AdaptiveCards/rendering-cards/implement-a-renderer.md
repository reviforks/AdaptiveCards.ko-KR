---
title: 렌더러 구현
author: matthidinger
ms.author: mahiding
ms.date: 09/15/2017
ms.topic: article
ms.openlocfilehash: 3c79d768d5c979626b66614a1856ad6c2e390805
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552555"
---
# <a name="adaptive-card-renderer-specification"></a>Adaptive Card 렌더러 사양

다음 사양에 설명 모든 UI 플랫폼에서 Adaptive Card 렌더러를 구현 하는 방법을 합니다.

> [!IMPORTANT]
> 
> 이 콘텐츠는 완료 되지 않았습니다. 잠시 후 확인해보세요.

## <a name="sdk-versioning"></a>SDK 버전 관리

1. SDK 주 및 부 버전 **SHOULD** 일치는 `schema` 버전입니다. 
1. 패치/build **SHOULD** 스키마 변경 되지 않은 렌더러 업데이트에 사용할 수 있습니다.

## <a name="parsing-json"></a>JSON 구문 분석

### <a name="error-conditions"></a>오류 조건
1. 파서가 **해야** 유효한 JSON 콘텐츠가 있는지 확인
1. 파서가 **해야** 스키마 (필수 속성 등)에 대해 유효성 검사
1. 위의 오류 **해야** 호스트 앱 (예외 또는 이와 동등한)에 게 보고

### <a name="unknown-types"></a>알 수 없는 형식
1. 알 수 없는 "형식" 발생 하는 경우 이러한 **없어지면** 결과에서
1. 위에서 같이 페이로드의 영향 **SHOULD** 호스트 앱에는 경고로 보고

### <a name="unknown-properties"></a>알 수 없는 속성
1. 파서가 **해야 합니다** 포함 **추가** 요소 속성

### <a name="additional-considerations"></a>추가 고려 사항
1. `speak` 속성 SSML 태그를 포함할 수 있습니다 하 고 **해야** 로 지정 된 호스트 응용 프로그램에 반환할

## <a name="parsing-host-config"></a>호스트 구성 구문 분석
1. TODO

## <a name="versioning"></a>버전 관리

1. 렌더러 **해야** 스키마의 특정 버전을 구현 합니다. 
1. `AdaptiveCard` 생성자 **해야 합니다** 제공 된 `version` 현재 스키마 버전에 따라 기본 값 속성 
1. 렌더러를 발견 하는 경우는 `version` 속성에는 `AdaptiveCard` 지원 되는 버전 보다 높은 것 **해야 합니다** 반환는 `fallbackText` 대신 합니다.

## <a name="rendering"></a>렌더링

`AdaptiveCard` 이루어져를 `body` 고 `actions`입니다. `body` 컬렉션인 `CardElement`의렌더러를 열거 하 고 순서 대로 렌더링 됩니다. 

1. 요소당 **해야 합니다** 부모의 너비를 확장 (생각 `display: block` html에서).
1. 렌더러 **해야** , 알 수 없는 요소 형식을 무시 하 고 페이로드의 나머지 부분 렌더링을 계속 합니다.

### <a name="spacing-and-separators"></a>간격 및 구분 기호

1. `spacing` 모든 요소에 대해 속성 사이의 공간 크기에 영향을 줍니다 합니다 **현재** 요소와 **BEFORE** 것입니다.
1. 간격 **만 해야** 있으면 실제로 앞에 요소를 적용 합니다. (예: 적용 되지 않습니다 배열에서 첫 번째 항목으로)
1. 렌더러 **해야 합니다** 에서 사용 하는 공간의 양을 조회를 `hostConfig` 현재 요소에 적용 되는 열거형 값에 대 한 간격입니다.
1. 요소에는 `separator` 값 `true`, 표시 줄 다음 **해야** 현재 요소 및 하기 전에 하나를 그릴 합니다.
1. 구분선 **해야 합니다** 수를 사용 하 여는 `container.style.default.foregroundColor`합니다.
1. 구분 기호 **만 해야** 경우 그릴 항목 **IS NOT** 배열의 첫 번째입니다.

### <a name="columns"></a>열

1. `Column` `width` **해야** "auto", "stretch" 또는 중된 비율로 해석 합니다.

### <a name="textblock"></a>TextBlock

1. TextBlock **해야 합니다** 하지 않으면 한 줄을 차지 합니다 `wrap` 속성이 `true`합니다. 
1. 텍스트 블록 **SHOULD** 줄임표 (...)를 사용 하 여 과도 한 모든 텍스트를 잘라내지

#### <a name="markdown"></a>Markdown

1. Adaptive Card Markdown의 하위 집합을 허용 하 고 **SHOULD** 지원 `TextBlock`합니다. 
1. 전체 참조 [markdown 요구 사항](../authoring-cards/text-features.md)

#### <a name="formatting-functions"></a>서식 지정 함수

1. `TextBlock` 허용 [날짜/시간 함수를 서식 지정](../authoring-cards/text-features.md) 하는 **해야** 모든 렌더러에서 지원 합니다.
1. **모든 실패 해야** 카드의 원시 문자열을 표시 합니다. 친숙 한 메시지를 시도 되지 않습니다. (개발자가 있는 즉시 인식할 수 있도록 되 목적은 문제)

1. TODO: Regex를 포함 합니다.

### <a name="images"></a>이미지

1. 렌더러 **SHOULD** 알고 있어야 모든 HTTP 이미지 다운로드 된 경우 호스트 앱 허용 및 카드가 "완벽 하 게 rendererd"
1. 렌더러 **해야 합니다** 호스트 구성 검사 `maxImageSize` HTTP 이미지를 다운로드 하는 경우 매개 변수
1. 렌더러 **해야 합니다** 지원 `.png` 및 `.jpeg`
1. 렌더러 **SHOULD** 지원 `.gif` 이미지

### <a name="host-config"></a>호스트 구성

* TODO: 기본값은 무엇을 해야 합니까? 모두 공유 합니까? 일반적인 hostConfig.json 파일 이진 파일에 포함할 해야?
* TODO: 생각해 HostConfig 구문 분석에 대해서는 물론 버전을 관리 해야 하나요?

[`HostConfig`](host-config.md) 적응 카드 렌더러는 UI를 생성 하는 방법을 지정 하는 공유 구성 개체가입니다.  

이렇게 하면 다양 한 플랫폼 및 장치에서 렌더러를 공유할 수 있도록 플랫폼을 알 수 없는 속성입니다. 또한 제공 하는 것이 카드는 모양과 느낌의 지정된 된 환경에 대 한 도구를를 만들 수 있습니다.

1. 렌더러 **해야 합니다** 노출 된 **호스트 구성** 앱을 호스트 하는 매개 변수
1. 모든 요소가 **해야** 해당 하는 호스트 구성 설정에 따라 스타일을 지정할 수

### <a name="native-platform-styling"></a>네이티브 플랫폼 스타일 지정

1. 각 요소 유형에 **SHOULD** 생성된 UI 요소를 사용 하 여 네이티브 플랫폼 스타일을 연결 합니다. 예를 들어 CSS 클래스의 요소 형식에 추가할에서는 html에서 및 XAML 특정 스타일을 할당.

## <a name="extensibility"></a>확장성 

1. 렌더러 **해야** 기본 요소 렌더러를 재정의 하려면 앱을 호스트할 수 있도록 합니다. 예를 들어 대체 `TextBlock` 자체 논리를 사용 하 여 렌더링 합니다.
1. 렌더러 **해야** 호스트 앱 사용자 지정 요소 유형이 등록을 허용 합니다. 예를 들어, 사용자 지정에 대 한 지원을 추가 `Rating` 요소
1. 렌더러 **해야** 기본 요소에 대 한 지원을 제거 하려면 앱을 호스트할 수 있도록 합니다. 예를 들어 제거 `Action.Submit` 지원 되지 않도록 합니다.

## <a name="actions"></a>동작

1. 경우 HostConfig `supportsInteractivity` 됩니다 `false`, 렌더러를 **MUST NOT** 모든 작업을 렌더링 합니다.
1. 합니다 `actions` 속성 **해야** 카드의 맨 아래에서 일반적으로 작업 표시줄의 몇 가지 종류의 단추와 렌더링 합니다. 
1. 단추를 탭 할 때 그 **해야** 호스트 응용 프로그램에서 이벤트를 처리할 수 있도록 합니다. 
1. 이벤트 **해야** 작업과 연결 된 모든 속성을 따라 전달
1. 이벤트 **해야 합니다** 전달 된 `AdaptiveCard` 실행 된는

작업 | 동작
--- | ---
**Action.OpenUrl** | 보기에 대 한 외부 URL 열기
**Action.ShowCard** | 사용자에 게 표시할 하위 카드를 요청 합니다.
**Action.Submit** | 호스트 응용 프로그램에서 정의 된 몇 가지 메서드를 통해 다음에 전송 되는 개체로 수집의 모든 입력된 요소에 대 한 요청 합니다.

### <a name="actionopenurl"></a>Action.OpenUrl
1. `Action.OpenUrl` **해야** 네이티브 플랫폼 메커니즘을 사용 하는 URL 열기
1. 가능 하지 않은 경우 해당 **해야** URL을 열어 처리 호스트 앱으로 이벤트를 발생 시킵니다. 이 이벤트 **해야** 호스트 앱 기본 동작을 재정의 하도록 허용 합니다. 예를 들어 수 있도록 자신의 앱 내에서 URL을 엽니다.

### <a name="actionshowcard"></a>Action.ShowCard

1. `Action.ShowCard` **해야** hostConfig 설정에 따라 몇 가지 방식으로 지원 합니다. 두 가지 모드가 있습니다: 인라인 및 팝업 합니다. 인라인 카드 **SHOULD** 카드 표시 여부를 자동으로 전환 합니다. 이벤트 팝업 모드로 **SHOULD** 호스트 응용 프로그램에서 어떤 방식으로든에서 카드를 표시 하려면 먼저 발생 시켜야 합니다.

### <a name="actionsubmit"></a>Action.Submit

전송 작업을 HTML 양식 제출 처럼, "전송"을 확인 하려면 각 호스트 응용 프로그램에 의미를 그대로 Adaptive Card는 HTTP post에 HTML 일반적으로 트리거 한다는 점을 제외 하면 합니다. 

1. 때이 **해야** 발생 이벤트는 사용자 작업 invokved를 탭 합니다.  
1. 합니다 `data` 속성 **해야** 콜백 페이로드에 포함 됩니다.
1. 에 대 한 `Action.Submit`, 렌더러 **해야** 카드에 모든 입력을 수집 하 고 해당 값을 검색 합니다. 

### <a name="selectaction"></a>selectAction

1. 하는 경우 호스트 구성 `supportedInteractivity` 됩니다 `false` 는 `selectAction` **MUST NOT** 터치 대상으로 렌더링 합니다.
1. `Image``ColumnSet`, 및 `Column` 제공을 `selectAction` 속성에는 **SHOULD** 사용자가 호출할 때, 예를 들어, 요소를 탭 하 여 실행할 수입니다.

## <a name="inputs"></a>입력

1. 경우 HostConfig `supportsInteractivity` 는 `false` 렌더러 **MUST NOT** 입력을 렌더링 합니다.
2. 입력 **SHOULD** 가능한 가장 높은 정확도 사용 하 여 렌더링 합니다. 예를 들어를 `Input.Date` 날짜 선택 UI 스택을, 다음 렌더러에 대 수 없는 경우이 있지만 사용자에 게 제공 이상적으로 **해야** 표준 텍스트 상자를 렌더링으로 대체 합니다.
3. 렌더러 **SHOULD** 표시는 `placeholderText` 가능한 경우
4. 렌더러 **아닙니다** 입력의 유효성 검사를 구현 해야 합니다. Adaptive Card의 사용자가 최종적으로 모든 수신 된 데이터의 유효성을 계획 해야 합니다.
5. 입력 값 바인딩 **해야** 는 적절히 이스케이프 되어야

6. 개체 **해야** 다음과 같이 호스트 응용 프로그램에 반환 합니다.

   에서는 없도록 입력된 유효성 검사의 모든 기능 adaptive card에 제대로 응답을 구문 분석 하려면 수신 파티에 달려 있으므로. 예를 들어, "hello"는 Input.Number 반환할 수 있습니다 및를 준비 하는 데 필요한 합니다.


## <a name="events"></a>이벤트

1. 렌더러 **SHOULD** 호스트 응용 프로그램에서 위치에 카드를 스크롤할 수 있도록 요소의 표시 유형을 변경 되었을 때 이벤트를 발생 합니다.
