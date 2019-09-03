---
title: 렌더러 구현
author: matthidinger
ms.author: mahiding
ms.date: 09/15/2017
ms.topic: article
ms.openlocfilehash: b39493f82f3378e5a554abc6df890d6821869671
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67138026"
---
# <a name="adaptive-card-renderer-specification"></a>적응형 카드 렌더러 사양

다음 사양은 모든 UI 플랫폼에서 적응형 카드 렌더러를 구현하는 방법에 대해 설명합니다.

> [!IMPORTANT]
> 
> 이 콘텐츠는 아직 완료되지 않았습니다. 곧 다시 확인해 보세요.

## <a name="sdk-versioning"></a>SDK 버전 관리

1. SDK 주 버전 및 부 버전은 `schema` 버전과 **일치해야 합니다**. 
1. 패치/빌드는 스키마 변경 내용이 없는 렌더러 업데이트에 **사용해야 합니다**.

## <a name="parsing-json"></a>JSON 구문 분석

### <a name="error-conditions"></a>오류 조건
1. 파서는 유효한 JSON 콘텐츠인지 **확인해야 합니다**.
1. 파서는 스키마(필수 속성 등)에 대해 **유효성을 검사해야 합니다**.
1. 위의 오류는 호스트 앱에 **보고되어야 합니다**(예외 등).

### <a name="unknown-types"></a>알 수 없는 형식
1. 알 수 없는 “형식”이 발견되면 결과에서 **삭제되어야 합니다**.
1. 위와 같은 페이로드 변경은 호스트 앱에 경고로 **보고되어야 합니다**.

### <a name="unknown-properties"></a>알 수 없는 속성
1. 파서는 요소에 대한 **추가** 속성을 **포함해야 합니다**.

### <a name="additional-considerations"></a>추가 고려 사항
1. `speak` 속성은 SSML 태그를 포함할 수 있으며 지정된 대로 호스트 앱에 **반환되어야 합니다**.

## <a name="parsing-host-config"></a>호스트 구성 구문 분석
1. TODO

## <a name="versioning"></a>버전 관리

1. 렌더러는 특정 스키마 버전을 **구현해야 합니다**. 
1. `AdaptiveCard` 생성자는 현재 스키마 버전에 따라 `version` 속성에 기본값을 **제공해야 합니다**. 
1. 렌더러는 지원되는 버전보다 높은 `version` 속성을 `AdaptiveCard`에서 발견하면 `fallbackText`을 대신 **반환해야 합니다**.

## <a name="rendering"></a>렌더링

`AdaptiveCard`는 `body` 및 `actions`로 구성됩니다. `body`는 렌더러가 순서대로 열거 및 렌더링할 `CardElement`의 컬렉션입니다. 

1. 각 요소는 부모의 너비까지 **확장되어야 합니다**(HTML에서는 `display: block` 고려).
1. 렌더러는 알 수 없는 요소 형식을 무시하고 나머지 페이로드 렌더링을 계속**해야 합니다**.

### <a name="spacing-and-separators"></a>간격 및 구분 기호

1. 모든 요소의 `spacing` 속성은 **현재** 요소와 그 **앞의** 요소 사이에 있는 간격의 크기에 영향을 줍니다.
1. 간격은 실제로 그 앞에 요소가 있는 경우**에만 적용되어야 합니다**. (예: 배열의 첫 번째 항목에는 적용되지 않음)
1. 렌더러는 현재 요소에 적용된 열거형 값에 대해 `hostConfig` 간격부터 사용할 간격의 크기를 **조회해야 합니다**.
1. 요소의 `separator` 값이 `true`이면 현재 요소와 그 앞의 요소 사이에 표시되는 선이 **그려져야 합니다**.
1. 구분선은 `container.style.default.foregroundColor`를 사용하여 **그려야 합니다**.
1. 항목이 배열의 첫 번째 항목이 **아닌** 경우에만 구분 기호를 **그려야 합니다**.

### <a name="columns"></a>열

1. `Column` `width`는 “자동”, “확장” 또는 가중 비율로 **해석되어야 합니다**.

### <a name="textblock"></a>TextBlock

1. `wrap` 속성이 `true`가 아니라면 TextBlock은 한 줄을 **사용해야 합니다**. 
1. 텍스트 블록은 줄임표(...)를 사용하여 초과 텍스트를 **잘라야 합니다**.

#### <a name="markdown"></a>Markdown

1. 적응형 카드는 Markdown의 하위 집합을 허용하며 `TextBlock`에서 **지원되어야 합니다**. 
1. 전체 [markdown 요구 사항](../authoring-cards/text-features.md)을 참조하세요.

#### <a name="formatting-functions"></a>형식 지정 함수

1. `TextBlock`은 모든 렌더러에서 **지원되어야 하는** [날짜/시간 형식 지정 함수](../authoring-cards/text-features.md)를 허용합니다.
1. **모든 오류는 카드에 원시 문자열을 표시해야 합니다**. 친숙한 메시지가 시도되지 않습니다. (목표는 개발자가 문제가 있음을 즉시 인식하도록 하는 것임)

1. TODO: regex 포함

### <a name="images"></a>이미지

1. 렌더러는 모든 HTTP 이미지가 다운로드되고 카드가 “완전히 렌더링”될 때 호스트 앱에 이를 알릴 수 **있어야 합니다**.
1. 렌더러는 HTTP 이미지를 다운로드할 때 호스트 구성 `maxImageSize` 매개 변수를 **검사해야 합니다**.
1. 렌더러는 `.png` 및 `.jpeg`를 **지원해야 합니다**.
1. 렌더러는 `.gif` 이미지를 **지원해야 합니다**.

### <a name="host-config"></a>호스트 구성

* TODO: 기본값은 무엇인가요? 모두 기본값을 공유해야 하나요? 일반적인 hostConfig.json 파일을 이진 파일에 포함해야 하나요?
* TODO: 구문 분석을 위해 HostConfig의 버전을 관리해야 하나요?

[`HostConfig`](host-config.md)는 적응형 카드 렌더러가 UI를 생성하는 방법을 지정하는 공유 구성 개체입니다.  

이를 사용하면 플랫폼에 독립적인 속성을 다양한 플랫폼 및 디바이스의 렌더러 간에 공유할 수 있습니다. 특정 환경에 대한 카드의 모양과 느낌에 대한 아이디어를 제공하는 도구를 만들 수도 있습니다.

1. 렌더러는 호스트 앱에 **호스트 구성** 매개 변수를 **공개해야 합니다**.
1. 모든 요소는 각 호스트 구성 설정에 따라 스타일을 **지정해야 합니다**.

### <a name="native-platform-styling"></a>네이티브 플랫폼 스타일 지정

1. 각 요소 형식은 네이티브 플랫폼 스타일을 생성된 UI 요소와 **연결해야 합니다**. 예를 들어 HTML에서는 CSS 클래스를 요소 형식에 추가하고 XAML에서는 특정 스타일을 할당합니다.

## <a name="extensibility"></a>확장성 

1. 렌더러는 호스트 앱이 기본 요소 렌더러를 재정의할 수 있도록 **해야 합니다**. 예를 들어 `TextBlock` 렌더링을 자체 논리로 바꿉니다.
1. 렌더러는 호스트 앱이 사용자 지정 요소 형식을 등록할 수 있도록 **해야 합니다**. 예를 들어 사용자 지정 `Rating` 요소의 지원을 추가합니다.
1. 렌더러는 호스트 앱이 기본 요소의 지원을 제거할 수 있도록 **해야 합니다**. 예를 들어 지원되지 않게 하려면 `Action.Submit`을 제거합니다.

## <a name="actions"></a>조치

1. HostConfig `supportsInteractivity`가 `false`인 경우 렌더러는 작업을 렌더링하지 **않아야 합니다**.
1. `actions` 속성은 일반적으로 카드 아래쪽에 있는 일종의 작업 모음에서 단추로 **렌더링되어야 합니다**. 
1. 단추를 탭하면 호스트 앱이 이벤트를 처리할 수 있도록 **해야 합니다**. 
1. 이벤트는 작업을 통해 모든 연결된 속성을 따라 **전달되어야 합니다**.
1. 이벤트는 실행된 `AdaptiveCard`를 따라 **전달되어야 합니다**.

작업 | 동작
--- | ---
**Action.OpenUrl** | 보려는 외부 URL을 엽니다.
**Action.ShowCard** | 사용자에게 표시될 하위 카드를 요청합니다.
**Action.Submit** | 모든 입력 요소를 하나의 개체로 합친 후 호스트 애플리케이션이 정의한 일부 메서드를 통해 사용자에게 전송하도록 요청합니다.

### <a name="actionopenurl"></a>Action.OpenUrl
1. `Action.OpenUrl`은 네이티브 플랫폼 메커니즘을 사용하여 URL을 **열어야 합니다**.
1. 열 수 없는 경우에는 호스트 앱이 URL 열기를 처리하도록 이벤트를 **발생시켜야 합니다**. 이 이벤트는 호스트 앱이 기본 동작을 재정의할 수 있도록 **해야 합니다**. 예를 들어 고유한 앱 내에서 URL을 열도록 합니다.

### <a name="actionshowcard"></a>Action.ShowCard

1. `Action.ShowCard`는 hostConfig 설정에 따라 어떤 방법으로든 **지원되어야 합니다**. 인라인 및 팝업 모드가 있습니다. 인라인 카드는 카드 표시 여부를 자동으로 **전환해야 합니다**. 팝업 모드에서는 어떤 방법으로든 호스트 앱이 카드를 표시하도록 이벤트를 **실행해야 합니다**.

### <a name="actionsubmit"></a>Action.Submit

제출 작업은 HTML 양식 제출과 비슷하게 동작합니다. 단, 일반적으로 HTML이 HTTP 게시물을 트리거하는 경우, 적응형 카드는 각 호스트 앱이 “제출”의 의미를 결정하도록 한다는 점만 다릅니다. 

1. 이 작업이 이벤트를 **발생시켜야 하는** 경우 사용자는 호출되는 작업을 탭합니다.  
1. `data` 속성은 콜백 페이로드에 **포함되어야 합니다**.
1. `Action.Submit`의 경우 렌더러는 카드에서 모든 입력을 수집하고 해당 값을 검색**해야 합니다**. 

### <a name="selectaction"></a>selectAction

1. 호스트 구성 `supportedInteractivity`가 `false`이면 `selectAction`은 터치 대상으로 **렌더링되지 않아야 합니다**.
1. `Image`, `ColumnSet` 및 `Column`은 요소를 탭하는 등의 작업으로 사용자가 호출할 때 **실행되어야 하는** `selectAction` 속성을 제공합니다.

## <a name="inputs"></a>입력

1. HostConfig `supportsInteractivity`가 `false`인 경우 렌더러는 입력을 렌더링하지 **않아야 합니다**.
2. 입력은 가능한 최고 정밀도로 **렌더링되어야 합니다**. 예를 들어 `Input.Date`는 사용자에게 날짜 선택기를 제공하지만, UI 스택에서 제공할 수 없는 경우 렌더러는 표준 텍스트 상자 렌더링으로 **대체되어야 합니다**.
3. 렌더러는 가능한 경우 `placeholderText`를 **표시해야 합니다**.
4. 렌더러는 입력의 유효성 검사를 구현할 필요가 **없습니다**. 적응형 카드의 사용자는 사용자 쪽에서 수신된 모든 데이터의 유효성을 검사할 계획을 세워야 합니다.
5. 입력 값 바인딩은 적절하게 **이스케이프되어야 합니다**.

6. 개체는 다음과 같이 호스트 앱에 **반환되어야 합니다**.

   적응형 카드에서 입력 유효성 검사를 약속하지 않으므로 수신 당사자가 응답을 제대로 구문 분석해야 합니다. 예를 들어 Input.Number는 “hello”를 반환할 수 있으며 수신 당사자가 이를 준비해야 합니다.


## <a name="events"></a>이벤트

1. 렌더러는 요소의 표시 여부가 변경될 때 이벤트를 실행하여 호스트 앱이 카드를 제 위치로 스크롤할 수 있도록 **해야 합니다**.
