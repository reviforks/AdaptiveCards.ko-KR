---
title: 시작
author: matthidinger
ms.author: mahiding
ms.date: 11/9/2017
ms.topic: article
ms.openlocfilehash: 9d363da0c10b242e23d2594984292fcc1f31382f
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2019
ms.locfileid: "59552685"
---
# <a name="getting-started"></a>시작 

적응형 카드는 JSON 직렬화된 카드 개체 모델입니다.

## <a name="adaptive-card-structure"></a>적응형 카드 구조

카드의 기본 구조는 다음과 같습니다.

* `AdaptiveCard` - 루트 개체는 적응형 카드의 요소 구성, 동작, 말하기 방식, 렌더링하는 데 필요한 스키마 버전을 포함한 적응형 카드 자체를 설명합니다.
* `body` - 카드의 본문은 `elements`로 알려진 빌딩 블록으로 구성됩니다. 요소를 거의 무한의 정렬로 구성하여 여러 종류의 카드를 만들 수 있습니다. 
* `actions` - 여러 카드에 사용자가 취할 수 있는 일련의 동작이 있습니다. 이 속성은 일반적으로 하단의 "작업 모음"에서 렌더링되는 작업을 설명합니다.

### <a name="example-card"></a>카드 예

텍스트 한 줄 다음에 이미지가 오는 이 샘플 카드입니다.

```json
{
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Here is a ninja cat"
        },
        {
            "type": "Image",
            "url": "http://adaptivecards.io/content/cats/1.png"
        }
    ]
}
```

## <a name="type-property"></a>`Type` 속성

각 요소에는 개체의 유형을 식별하는 `type` 속성이 있습니다. 위의 카드를 보면 `TextBlock` 및 `Image`라는 두 가지 요소가 있는 것을 볼 수 있습니다.

모든 적응형 카드 요소는 **가로로 스택되며** **부모 항목의 너비에 맞게 확장**됩니다(예: HTML의 `display: block`). 하지만 `ColumnSet`를 사용하여 컨테이너 열을 만들 수 있습니다.

## <a name="adaptive-elements"></a>적응형 요소

가장 기본적인 요소는 다음과 같습니다.

* **TextBlock** - 텍스트의 모양을 제어하는 속성을 사용하여 텍스트 블록을 추가합니다.
* **Image** - 이미지의 모양을 제어하는 속성을 사용하여 이미지를 추가합니다.

## <a name="container-elements"></a>컨테이너 요소

카드에 자식 요소의 컬렉션을 정렬하는 컨테이너가 포함될 수도 있습니다.

* **Container** - 요소 컬렉션을 정의합니다.
* **ColumnSet/Column** - 열 컬렉션을 정의하며, 각 열이 컨테이너입니다.
* **FactSet** - 팩트의 컨테이너입니다.
* **ImageSet** - 이미지 컬렉션의 적절한 사진 갤러리 환경이 UI에 표시될 수 있도록 하는 이미지 컨테이너입니다.

## <a name="input-elements"></a>입력 요소

입력 요소를 사용하여 네이티브 UI에 간단한 양식을 빌드하도록 요청할 수 있습니다.

* **Input.Text** - 사용자로부터 텍스트 콘텐츠를 가져옵니다.
* **Input.Date** - 사용자로부터 날짜를 가져옵니다.
* **Input.Time** - 사용자로부터 시간을 가져옵니다.
* **Input.Number** - 사용자로부터 숫자를 가져옵니다.
* **Input.ChoiceSet** - 사용자에게 일련의 옵션을 제공하고 선택하도록 합니다.
* **Input.Toggle** - 사용자에게 두 가지 옵션을 제공하고 선택하도록 합니다.

## <a name="actions"></a>조치

카드에 단추를 추가하는 작업입니다. URL 열기 또는 일부 데이터 제출과 같은 다양한 작업을 수행할 수 있습니다.

* **Action.OpenUrl** - 단추를 누르면 외부 URL이 열리고 볼 수 있습니다.
* **Action.ShowCard** - 사용자에게 표시할 하위 카드를 요청합니다.
* **Action.Submit** - 모든 입력 요소를 하나의 개체로 합친 후 호스트 애플리케이션이 정의한 일부 메서드를 통해 사용자에게 전송하도록 요청합니다.

> **Example Action.Submit**: Action.Submit가 Skype를 통해 모든 입력 데이터가 합쳐진 개체가 포함된 **Value** 속성을 사용하여 Bot Framework 봇 활동 작업을 봇에 다시 전송합니다.

## <a name="learn-more"></a>자세히 알아보기

* 영감을 얻기 위해 [샘플 카드 찾아보기](http://adaptivecards.io/samples/)
* [스키마 탐색기](http://adaptivecards.io/explorer)를 사용하여 사용 가능한 요소 찾아보기
* [대화형 비주얼라이저](http://adaptivecards.io/visualizer/)를 사용하여 카드 작성
* 모든 피드백과 [연결 유지](http://adaptivecards.io/connect)
