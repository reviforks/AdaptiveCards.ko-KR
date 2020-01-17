---
title: 적응 카드 템플릿 언어
author: matthidinger
ms.author: mahiding
ms.date: 08/01/2019
ms.topic: article
ms.openlocfilehash: 2c583f774451e60f825cd8fd2c38f2ea34c2f8de
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145403"
---
# <a name="adaptive-cards-template-language"></a>적응 카드 템플릿 언어

템플릿을 사용 하면 적응 카드의 **레이아웃** 에서 **데이터** 를 분리할 수 있습니다. 템플릿 언어는 템플릿을 작성 하는 데 사용 되는 구문입니다. 

> [적응 카드 템플릿 개요](index.md) 는이 내용을 참조 하세요.

> [!IMPORTANT] 
> 
> 이러한 기능은 **미리 보기 상태이며 변경될 수 있습니다**. 사용자 의견은 언제나 환영이며, **사용자**에게 필요한 기능을 제공하는 데 중요합니다.

템플릿을 제작할 때 템플릿 [sdk](sdk.md)를 사용 하 여 `AdaptiveCard` 페이로드를 사용 하거나 런타임에 데이터를 인라인으로 지정할 수 있습니다.

## <a name="specify-data-within-the-card"></a>카드 내에서 데이터 지정

카드 페이로드 내에서 직접 데이터를 제공 하려면 `AdaptiveCard`에 `$data` 특성을 추가 하면 됩니다 (아래 참조).

## <a name="binding-to-the-data"></a>데이터에 바인딩

카드의 `body` 또는 `actions` 내에서 데이터에 바인딩할 수 있습니다.

* 바인딩 구문은 `{` 시작 하 여 `}`로 끝납니다. 예: `{myProperty}`
* 하위 개체에 액세스 하는 점 표기법
* 배열에서 키 또는 항목으로 속성을 검색 하는 인덱서 구문
* 딥 계층에 대 한 정상적인 null 처리
* *곧 제공 될 이스케이프 구문 설명서*

```json
{
    "type": "AdaptiveCard",
    "$data": {
        "employee": {
            "name": "Matt",
            "manager": { "name": "Thomas" },
            "peers": [{
                "name": "Andrew" 
            }, { 
                "name": "Lei"
            }, { 
                "name": "Mary Anne"
            }, { 
                "name": "Adam"
            }]
        }
    },
    "body": [
        {
            "type": "TextBlock",
            "text": "Hi {employee.name}! Here's a bit about your org..."
        },
        {
            "type": "TextBlock",
            "text": "Your manager is: {employee.manager.name}"
        },
        {
            "type": "TextBlock",
            "text": "3 of your peers are: {employee.peers[0].name}, {employee.peers[1].name}, {employee.peers[2].name}"
        }
    ]
}
```

## <a name="separating-the-template-from-the-data"></a>데이터에서 템플릿 구분

또는 데이터를 포함 하지 않고 다시 사용할 수 있는 카드 "템플릿"을 만드는 것이 좋습니다. 이 템플릿을 파일로 저장 하 고 소스 제어에 추가할 수 있습니다.

**EmployeeCardTemplate.json**

```json
{
    "type": "AdaptivCard",
    "body": [
        {
            "type": "TextBlock",
            "text": "Hi {employee.name}! Here's a bit about your org..."
        },
        {
            "type": "TextBlock",
            "text": "Your manager is: {employee.manager.name}"
        },
        {
            "type": "TextBlock",
            "text": "3 of your peers are: {employee.peers[0].name}, {employee.peers[1].name}, {employee.peers[2].name}"
        }
    ]
}
```

그런 다음 [템플릿 sdk](sdk.md)를 사용 하 여 런타임에 데이터를 로드 하 고 제공 합니다.

**JavaScript 예제**

[Adaptivecards](https://npmjs.com/package/adaptivecards-templating) 패키지를 사용 합니다.

```js
var template = new ACData.Template({ 
    // EmployeeCardTemplate goes here
});

// Specify data at runtime
var dataContext = new ACData.EvaluationContext();
dataContext.$root = {
    "employee": {
        "name": "Matt",
        "manager": { "name": "Thomas" },
        "peers": [{
            "name": "Andrew" 
        }, { 
            "name": "Lei"
        }, { 
            "name": "Mary Anne"
        }, { 
            "name": "Adam"
        }]
    }
};

var card = template.expand(dataContext);
// Now you have an AdaptiveCard ready to render!
```

## <a name="designer-support"></a>디자이너 지원

적응 카드 디자이너가 템플릿을 지원 하도록 업데이트 되었습니다. 

> 사용해 보기:  **[https://adaptivecards.io/designer](https://adaptivecards.io/designer)**

[![이미지](https://user-images.githubusercontent.com/1432195/53214462-88d46980-3601-11e9-908d-253a1bb940a8.png)](https://adaptivecards.io/designer)

* **샘플 데이터 편집기** -"미리 보기 모드"에 있는 경우 데이터 바인딩된 카드를 보려면 여기에 샘플 데이터를 지정 합니다. 이 창에는 기존 샘플 데이터의 데이터 구조를 채우는 작은 단추가 있습니다.
* **데이터 구조** -샘플 데이터의 구조입니다. 필드를 디자인 화면으로 끌어 해당 필드에 대 한 바인딩을 만들 수 있습니다. 
* **미리 보기 모드** -도구 모음 단추를 눌러 편집 환경과 샘플 데이터 미리 보기 환경 사이를 전환 합니다.
* **샘플 열기** -이 단추를 클릭 하 여 다양 한 샘플 페이로드를 엽니다.

## <a name="advanced-binding"></a>고급 바인딩

### <a name="binding-scopes"></a>바인딩 범위

다양 한 바인딩 범위에 액세스 하기 위한 몇 가지 예약 된 키워드가 있습니다. 

*참고:* 이러한 일부는 미리 보기에서 구현 되지 않습니다.

```json
{
    "{<property>}": "Implicitly binds to `$data.<property>`",
    "$data": "The current data object",
    "$root": "The root data object. Useful when iterating to escape to parent object",
    "$index": "The current index when iterating",
    "$host": "Access properties of the host *(not working yet)*"
}
```

### <a name="assigning-a-data-context-to-elements"></a>요소에 데이터 컨텍스트 할당

모든 요소에 "데이터 컨텍스트"를 할당 하려면 `$data` 특성을 요소에 추가 합니다.

```json
{
    "type": "Container",
    "$data": "{mySubObject}",
    "items": [
        {
            "type": "TextBlock",
            "text": "This TextBlock is now scoped directly to 'mySubObject': {mySubObjectProperty}"
        },
        {
            "type": "TextBlock",
            "text": "To break-out and access the root data, use: {$root}"
        }
    ]
}
```

## <a name="repeating-items-in-an-array"></a>배열의 반복 항목

이 부분은 약간의 "진한 매직"입니다. 사용자 의견을 환영 합니다.

* 적응 카드 요소의 `$data` 속성이 **배열**에 바인딩되어 있으면 **배열의 각 항목에 대해 요소 자체가 반복 됩니다.** 
* 속성 값에 사용 되는 모든 바인딩 식 (`{myProperty}`)은 배열 내의 **개별 항목** 으로 범위가 지정 됩니다.
* 문자열 배열에 바인딩하는 경우 `{$data}`를 사용 하 여 개별 문자열 요소에 액세스 합니다. 예: `"text": "{$data}"`

예를 들어 아래 `TextBlock`는 배열 `$data` 이므로 3 번 반복 됩니다. `text` 속성이 배열 내 개별 개체의 `name` 속성에 바인딩되는 방법을 확인 합니다. 

```json
{
    "type": "Container",
    "items": [
        {
            "type": "TextBlock",
            "$data": [
                { "name": "Matt" }, 
                { "name": "David" }, 
                { "name": "Thomas" }
            ],
            "text": "{name}"
        }
    ]
}
```

**결과:**

```json
{
    "type": "Container",
    "items": [ 
        {
            "type": "TextBlock",
            "text": "Matt"
        },
        {
            "type": "TextBlock",
            "text": "David"
        }
        {
            "type": "TextBlock",
            "text": "Thomas"
        }
    ]
}
```

## <a name="functions"></a>함수

일부 도우미 함수 없이 템플릿 언어가 완전 하지 않습니다. 모든 SDK에서 작동 하는 표준 함수 집합을 제공 합니다. 

여기에 나와 있는 구문은 계속 해 서 계속 해 서 제공 될 것 이므로 곧 다시 확인 하세요. 여기서는 계획 중인 작업을 시작 합니다.

### <a name="string-functions"></a>문자열 함수

* substr
* indexOf *(아직 작동 하지 않음)*
* toUpper *(아직 작동 하지 않음)*
* toLower *(아직 작동 하지 않음)*

### <a name="number-functions"></a>Number 함수

* 서식 (통화, 10 진수 등) *(아직 작동 하지 않음)*

### <a name="date-functions"></a>날짜 함수

* 잘 알려진 날짜 문자열 형식 구문 분석 *(아직 작동 하지 않음)*
* 잘 알려진 날짜/시간 표현에 대 한 서식 지정 *(아직 작동 하지 않음)*

### <a name="conditional-functions"></a>조건부 함수

* if (*expression*, *trueValue*, *falseValue*)

**`if` 예제**

```json
{
    "type": "TextBlock",
    "color": "{if(priceChange >= 0, 'good', 'attention')}"
}
```

### <a name="data-manipulation"></a>데이터 조작

* JSON-JSON 문자열을 구문 분석 하는 기능 

**`JSON.parse` 예제**

이는 `message` 속성이 JSON 직렬화 문자열인 Azure DevOps 응답입니다. 문자열 내의 값에 액세스 하려면 템플릿에서 `JSON.parse` 함수를 사용 해야 합니다.

**데이터** 

```json
{
    "id": "1291525457129548",
    "status": 4,
    "author": "Matt Hidinger",
    "message": "{\"type\":\"Deployment\",\"buildId\":\"9542982\",\"releaseId\":\"129\",\"buildNumber\":\"20180504.3\",\"releaseName\":\"Release-104\",\"repoProvider\":\"GitHub\"}",
    "start_time": "2018-05-04T18:05:33.3087147Z",
    "end_time": "2018-05-04T18:05:33.3087147Z"
}
```

**Usage**

```json
{
    "type": "TextBlock",
    "text": "{JSON.parse(message).releaseName}"
}
```

**결과**

```json
{
    "type": "TextBlock",
    "text": "Release-104"
}
```

### <a name="custom-functions"></a>사용자 지정 함수

호스트가 사용자 지정 함수를 추가할 수 있는지 확인 하려고 합니다. 즉, 함수가 지원 되지 않는 경우에는 대체 지원이 강력 하 게 지원 되어야 합니다. 계속 평가 하 고 있습니다.

## <a name="conditional-layout"></a>조건부 레이아웃

조건이 충족 될 경우 전체 요소를 삭제 하려면 `$when` 속성을 사용 합니다. `$when`이 `false`으로 계산 되 면 요소가 사용자에 게 표시 되지 않습니다.

```json
{
    "type": "AdaptiveCard",
    "$data": {
        "price": "35"
    },
    "body": [
        {
            "type": "TextBlock",
            "$when": "{price > 30}",
            "text": "This thing is pricy!",
            "color": "attention",
        },
         {
            "type": "TextBlock",
            "$when": "{price <= 30}",
            "text": "Dang, this thing is cheap!",
            "color": "good"
        }
    ]
}
```

### <a name="composing-templates"></a>템플릿 작성

현재는 템플릿 "파트"를 함께 작성할 수 없습니다. 그러나이 옵션을 탐색 하 고 더 빨리 공유 하려고 합니다. 여기에서 모든 생각을 환영 합니다!


## <a name="examples"></a>예

업데이트 된 [샘플 페이지](https://adaptivecards.io/samples) 에서 모든 종류의 템플릿 기반 카드를 탐색할 수 있습니다.
