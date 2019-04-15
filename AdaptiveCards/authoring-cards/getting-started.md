---
title: 시작하기
author: matthidinger
ms.author: mahiding
ms.date: 11/9/2017
ms.topic: article
ms.openlocfilehash: 9d363da0c10b242e23d2594984292fcc1f31382f
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552685"
---
# <a name="getting-started"></a>시작하기 

Adaptive Card는 카드 JSON 직렬화 된 개체 모델.

## <a name="adaptive-card-structure"></a>적응 카드 구조

카드의 기본 구조는 다음과 같습니다.

* `AdaptiveCard` 해당 요소 구성을, 해당 작업, 어떻게 해당 음성으로 변환 되어야 합니다 및 렌더링 하는 데 필요한 스키마 버전 포함 한 AdaptiveCard 자체를 설명 하는-루트 개체입니다.
* `body` -카드의 본문으로 이루어집니다 빌딩 블록으로 알려진 `elements`합니다. 다양 한 유형의 카드를 만들려면 거의 무한에 요소를 구성할 수 있습니다. 
* `actions` -많은 카드는 일련의 작업에 사용자가 수행할 수 있습니다. 이 속성의 맨 아래에서 "작업 모음" 렌더링 일반적으로 이러한 작업을 설명 합니다.

### <a name="example-card"></a>예제에서는 카드

이미지 뒤에 텍스트 한 줄을 포함 하는이 샘플 카드.

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

모든 요소에는 `type` 해당 개체의 종류를 식별 하는 속성입니다. 위의 카드를 살펴보면 보면 두 가지 요소인 것을 `TextBlock` 및 `Image`합니다.

모든 Adaptive Card 요소 **세로로** 하 고 **는 부모의 너비를 확장 하 고** (생각 `display: block` html에서). 사용할 수 있습니다는 `ColumnSet` 컨테이너의 side-by-side-열을 만듭니다.

## <a name="adaptive-elements"></a>적응 요소

가장 기본적인 요소입니다.

* **TextBlock** -텍스트의 모양을 제어 하는 속성을 사용 하 여 텍스트 블록을 추가 합니다.
* **이미지** -이미지의 모양을 제어 하는 속성을 사용 하 여 이미지를 추가 합니다.

## <a name="container-elements"></a>컨테이너 요소

카드는 자식 요소의 컬렉션을 정렬 하는 컨테이너를 포함할 수도 있습니다.

* **컨테이너** -정의 된 요소의 컬렉션
* **ColumnSet/열** -컬렉션을 정의의 열을 각 열은 컨테이너
* **FactSet** -팩트의 컨테이너
* **ImageSet** -컨테이너의 이미지 해당 UI는 적절 한 표시할 수 있도록 사진 이미지의 컬렉션에 대 한 갤러리 환경입니다.

## <a name="input-elements"></a>입력된 요소

입력된 요소를 사용 하면 간단한 양식을 작성 하는 네이티브 UI에 대 한 문의할 수 있습니다.

* **Input.Text** -사용자의 텍스트 콘텐츠 가져오기
* **Input.Date** -사용자의 날짜 가져오기
* **Input.Time** -사용자의 시간 가져오기
* **Input.Number** -여러 사용자에서 가져오기
* **Input.ChoiceSet** -선택 항목 집합이 사용자에 게 제공 하 고 선택
* **Input.Toggle** -사용자에 게 두 항목 사이 단일 선택 항목을 제공 하 고 선택

## <a name="actions"></a>동작

카드에 단추를 추가 하는 작업입니다. 이러한 다양 한 URL을 열거나 일부 데이터 전송 등의 작업을 수행할 수 있습니다.

* **Action.OpenUrl** -보기에 대 한 외부 URL이 단추를 클릭
* **Action.ShowCard** -사용자에 게 표시할 하위 카드를 요청 합니다.
* **Action.Submit** -호스트 응용 프로그램에서 정의 된 몇 가지 메서드를 통해 다음에 전송 되는 개체로 수집의 모든 입력된 요소에 대 한 요청입니다.

> **예제 Action.Submit**: Skype를 사용 하 여는 Action.Submit는 보내기 Bot Framework 봇 활동 다시 사용 하 여 봇에 합니다 **값** 에 입력된 데이터의 모든 개체를 포함 하는 속성입니다.

## <a name="learn-more"></a>자세히 알아보기

* [샘플 카드 찾아보기](http://adaptivecards.io/samples/) 영감
* 사용 된 [스키마 탐색기](http://adaptivecards.io/explorer) 사용 가능한 요소를 찾아보려면
* 카드를 통해 빌드를 [대화형 시각화 도우미](http://adaptivecards.io/visualizer/)
* [연락](http://adaptivecards.io/connect) 피드백을 사용 하 여
