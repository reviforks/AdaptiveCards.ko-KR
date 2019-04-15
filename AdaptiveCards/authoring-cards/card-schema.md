---
title: 카드 스키마
author: paulcam206
ms.author: paulcam
ms.date: 09/18/2018
ms.topic: reference
ms.openlocfilehash: 76a21affcd26798acb52e2bcf1168121838ed00a
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553725"
---
# <a name="card-schema"></a>카드 스키마

카드
   * [`AdaptiveCard`](#schema-adaptivecard) Adaptive Card의 루트 요소입니다.

카드 요소
   * [`TextBlock`](#schema-textblock) -글꼴 크기, 두께 및 색에 대 한 제어를 허용 하는 텍스트를 표시 합니다.
   * [`Image`](#schema-image) -이미지를 표시 합니다.
   * [`Media`](#schema-media) -오디오 또는 비디오 콘텐츠에 대 한 미디어 플레이어를 표시 합니다.
   * [`MediaSource`](#schema-mediasource) --Media 요소에 대 한 소스를 정의 하는 중

컨테이너
   * [`Container`](#schema-container) -컨테이너 항목을 함께 그룹화합니다.
   * [`ColumnSet`](#schema-columnset) -ColumnSet 요소를 사용 하 여 나란히 앉아 있는 열에는 영역을 나눕니다.
   * [`Column`](#schema-column) -열 집합의 일부인 컨테이너를 정의 합니다.
   * [`FactSet`](#schema-factset) -FactSet 요소는 테이블 형식에 일련의 팩트 (즉, 이름/값 쌍)을 표시합니다.
   * [`Fact`](#schema-fact) -키/값 쌍으로 된 FactSet에서 팩트를 설명합니다.
   * [`ImageSet`](#schema-imageset) -ImageSet 이미지 갤러리에 유사한 컬렉션을 표시합니다.

동작
   * [`Action.OpenUrl`](#schema-action.openurl) -호출 되 면 표시할 지정된 된 url 외부 웹 브라우저 또는 보여 주는 내부 포함 된 웹 브라우저를 사용 하 여 시작 하 여 합니다.
   * [`Action.Submit`](#schema-action.submit) --입력된 필드를 수집 하는 중, 선택적 데이터 필드를 사용 하 여 병합 하 고 클라이언트에 이벤트를 보냅니다. 이 데이터를 처리 하는 방법을 결정 하는 클라이언트에 게는 것입니다. 예를 들어 다음과 같은 가치를 제공해야 합니다. BotFramework 봇을 사용 하 여 클라이언트는 봇에 메시징 미디어를 통해 작업을 보냅니다.
   * [`Action.ShowCard`](#schema-action.showcard) -단추 또는 링크를 클릭할 때 사용자에 게 표시 되는 AdaptiveCard 정의 합니다.

입력
   * [`Input.Text`](#schema-input.text) -텍스트를 입력 하는 사용자 수 있습니다.
   * [`Input.Number`](#schema-input.number) -사용자를 숫자를 입력할 수 있습니다.
   * [`Input.Date`](#schema-input.date) -는 사용자를 날짜를 선택할 수 있습니다.
   * [`Input.Time`](#schema-input.time) -시간을 선택할 수 있습니다.
   * [`Input.Toggle`](#schema-input.toggle) -사용자를 두 옵션 중에서 선택할 수 있습니다.
   * [`Input.ChoiceSet`](#schema-input.choiceset) -는 사용자를 입력 선택할 수 있습니다.
   * [`Input.Choice`](#schema-input.choice) -는 ChoiceSet에서 사용 하기 위해 선택을 설명합니다.

# <a name="cards"></a>카드

<a name="schema-adaptivecard"></a>
## <a name="adaptivecard"></a>AdaptiveCard

Adaptive Card의 루트 요소입니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**type**|`"AdaptiveCard"`|예|`"AdaptiveCard"`여야 합니다.|1.0
|**actions**|`Action[]`| 아니요|카드의 작업 표시줄에 표시할 작업.|1.0
|**body**|`array[]`| 아니요|기본 카드 영역에 표시할 카드 요소입니다.|1.0
|**selectAction**|`object`| 아니요|카드를 탭 하거나 선택 하는 경우 호출 되는 동작입니다. `Action.ShowCard`은 지원되지 않습니다.|1.0
|**version**|`string`|예|이 카드는 스키마 버전입니다. 클라이언트는 **낮은** 이 버전 보다는 `fallbackText` 렌더링 됩니다.|1.0
|**fallbackText**|`string`| 아니요|클라이언트에서 지정 된 버전을 지원 하지 않습니다는 경우 표시 되는 텍스트 (markdown을 포함할 수 있습니다).|1.0
|**backgroundImage**|`string`| 아니요|카드의 배경으로 사용할 이미지입니다.|1.0
|**speak**|`string`| 아니요|이 전체 카드에 대 한 읽을 해야 지정 합니다. 간단한 텍스트 또는 SSML 조각입니다.|1.0
|**lang**|`string`| 아니요|카드에 사용 되는 2 자 ISO-639-1 언어입니다. 모든 날짜/시간 함수를 지역화 하는 데 사용 합니다.|1.0


# <a name="card-elements"></a>카드 요소

<a name="schema-textblock"></a>
## <a name="textblock"></a>TextBlock

글꼴 크기, 두께 및 색에 대 한 제어를 허용 하는 텍스트를 표시 합니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**color**|`string`| 아니요|색을 제어 합니다 `TextBlock` 요소입니다.|1.0
|**horizontalAlignment**|`string`| 아니요, 기본값: `"left"`|해당 컨테이너 내에서 가로로 배치 하는 요소 방식을 제어 합니다.|1.0
|**isSubtle**|`boolean`| 아니요, 기본값: `false`|경우 `true`, 약간 덜 띄는 표시할 toned 텍스트를 표시 합니다.|1.0
|**maxLines**|`number`| 아니요|표시할 줄의 최대 수를 지정 합니다.|1.0
|**size**|`string`| 아니요|텍스트의 크기를 제어 합니다.|1.0
|**text**|`string`|예|표시할 텍스트입니다.|1.0
|**type**|`"TextBlock"`|예|`"TextBlock"`여야 합니다.|1.0
|**weight**|`string`| 아니요|컨트롤의 가중치 `TextBlock` 요소입니다.|1.0
|**wrap**|`boolean`| 아니요, 기본값: `false`|경우 `true`, 텍스트 줄 바꿈이 허용 합니다. 그렇지 않으면 텍스트가 잘립니다.|1.0
|**id**|`string`| 아니요|요소에 연결 된 고유 식별자입니다.|1.0
|**spacing**|`string`| 아니요|이 요소는 이전 요소 사이의 간격 크기를 제어합니다.|1.0
|**separator**|`boolean`| 아니요, 기본값: `false`|때 `true`, 요소의 맨 위에 있는 구분 선을 그립니다.|1.0


<a name="schema-image"></a>
## <a name="image"></a>image

이미지를 표시합니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**altText**|`string`| 아니요|이미지를 설명 하는 대체 텍스트입니다.|1.0
|**horizontalAlignment**|`string`| 아니요, 기본값: `"left"`|해당 컨테이너 내에서 가로로 배치 하는 요소 방식을 제어 합니다.|1.0
|**selectAction**|`object`| 아니요|될 액션 될 때 호출 된 `Image` 을 탭 하거나 선택 합니다. `Action.ShowCard`은 지원되지 않습니다.|1.0
|**size**|`string`| 아니요, 기본값: `"auto"`|이미지의 대략적인 크기를 제어합니다. 실제 크기는 호스트 마다 달라 집니다. 지정할 `"auto"` 실제 이미지 차원에 대 한 또는 `"stretch"` 컨테이너를 입력 하도록 합니다.|1.0
|**style**|`string`| 아니요|컨트롤 어떻게이 `Image` 표시 됩니다.|1.0
|**type**|`"Image"`|예|`"Image"`여야 합니다.|1.0
|**url**|`string`|예|이미지에 대한 URL입니다.|1.0
|**id**|`string`| 아니요|요소에 연결 된 고유 식별자입니다.|1.0
|**spacing**|`string`| 아니요|이 요소는 이전 요소 사이의 간격 크기를 제어합니다.|1.0
|**separator**|`boolean`| 아니요, 기본값: `false`|때 `true`, 요소의 맨 위에 있는 구분 선을 그립니다.|1.0


<a name="schema-media"></a>
## <a name="media"></a>미디어

오디오 또는 비디오 콘텐츠에 대 한 미디어 플레이어를 표시합니다.

#### <a name="introduced-in-version-11"></a>버전 1.1에에서 도입 된

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**type**|`"Media"`|예|`"Media"`여야 합니다.|1.1
|**sources**|`object` `[]`| 아니요|재생 하려고 하는 미디어 소스의 배열입니다.|1.1
|**poster**|`string`| 아니요|재생 하기 전에 표시할 이미지의 URL입니다.|1.1
|**altText**|`string`| 아니요|오디오 또는 비디오를 설명 하는 대체 텍스트입니다.|1.1
|**id**|`string`| 아니요|요소에 연결 된 고유 식별자입니다.|1.1
|**spacing**|`string`| 아니요|이 요소는 이전 요소 사이의 간격 크기를 제어합니다.|1.1
|**separator**|`boolean`| 아니요, 기본값: `false`|때 `true`, 요소의 맨 위에 있는 구분 선을 그립니다.|1.1


<a name="schema-mediasource"></a>
## <a name="mediasource"></a>MediaSource

미디어 요소에 대 한 소스를 정의합니다.

#### <a name="introduced-in-version-11"></a>버전 1.1에에서 도입 된

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**mimeType**|`string`|예|Mime 미디어 연결 형식 (예: `"video/mp4"`).|1.1
|**url**|`string`|예|미디어 URL입니다.|1.1


# <a name="containers"></a>컨테이너

<a name="schema-container"></a>
## <a name="container"></a>컨테이너

컨테이너 항목을 함께 그룹화합니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**type**|`"Container"`|예|`"Container"`여야 합니다.|1.0
|**items**|`array[]`|예|내에서 렌더링 하는 카드 요소는 `Container`합니다.|1.0
|**selectAction**|`object`| 아니요|될 액션 될 때 호출 된 `Container` 을 탭 하거나 선택 합니다. `Action.ShowCard`은 지원되지 않습니다.|1.0
|**style**|`string`| 아니요|에 대 한 스타일 힌트 `Container`합니다.|1.0
|**verticalContentAlignment**|`string`| 아니요, 기본값: `"top"`|콘텐츠를 정렬 하는 방법을 세로로 컨테이너 내에서 정의 합니다.|1.1
|**id**|`string`| 아니요|요소에 연결 된 고유 식별자입니다.|1.0
|**spacing**|`string`| 아니요|이 요소는 이전 요소 사이의 간격 크기를 제어합니다.|1.0
|**separator**|`boolean`| 아니요, 기본값: `false`|때 `true`, 요소의 맨 위에 있는 구분 선을 그립니다.|1.0


<a name="schema-columnset"></a>
## <a name="columnset"></a>ColumnSet

ColumnSet 요소를 사용 하 여 나란히 앉아 있는 열에는 영역을 나눕니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**columns**|`Column[]`| 아니요|배열을 `Columns` 에 영역을 분할 합니다.|1.0
|**selectAction**|`object`| 아니요|될 액션 될 때 호출 된 `ColumnSet` 을 탭 하거나 선택 합니다. `Action.ShowCard`은 지원되지 않습니다.|1.0
|**type**|`"ColumnSet"`|예|`"ColumnSet"`여야 합니다.|1.0
|**id**|`string`| 아니요|요소에 연결 된 고유 식별자입니다.|1.0
|**spacing**|`string`| 아니요|이 요소는 이전 요소 사이의 간격 크기를 제어합니다.|1.0
|**separator**|`boolean`| 아니요, 기본값: `false`|때 `true`, 요소의 맨 위에 있는 구분 선을 그립니다.|1.0


<a name="schema-column"></a>
## <a name="column"></a>Column

열 집합의 일부인 컨테이너를 정의 합니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**items**|`array[]`|예|카드 요소에 포함 된 `Column`합니다.|1.0
|**selectAction**|`object`| 아니요|될 액션 될 때 호출 된 `Column` 을 탭 하거나 선택 합니다. `Action.ShowCard`은 지원되지 않습니다.|1.0
|**style**|`string`| 아니요|에 대 한 스타일 힌트 `Column`합니다.|1.0
|**width**|`string,number`| 아니요|`"auto"``"stretch"`, 또는 열 그룹의 열의 상대 너비를 나타내는 숫자입니다.|1.0
|**type**|`"Column"`| 아니요|`"Column"`여야 합니다.|1.0
|**id**|`string`| 아니요|요소에 연결 된 고유 식별자입니다.|1.0
|**spacing**|`string`| 아니요|이 요소는 이전 요소 사이의 간격 크기를 제어합니다.|1.0
|**separator**|`boolean`| 아니요, 기본값: `false`|때 `true`, 요소의 맨 위에 있는 구분 선을 그립니다.|1.0


<a name="schema-factset"></a>
## <a name="factset"></a>FactSet

FactSet 요소는 테이블 형식에 일련의 팩트 (즉, 이름/값 쌍)을 표시합니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**facts**|`Fact[]`|예|배열을 `Fact`s입니다.|1.0
|**type**|`"FactSet"`|예|`"FactSet"`여야 합니다.|1.0
|**id**|`string`| 아니요|요소에 연결 된 고유 식별자입니다.|1.0
|**spacing**|`string`| 아니요|이 요소는 이전 요소 사이의 간격 크기를 제어합니다.|1.0
|**separator**|`boolean`| 아니요, 기본값: `false`|때 `true`, 요소의 맨 위에 있는 구분 선을 그립니다.|1.0


<a name="schema-fact"></a>
## <a name="fact"></a>팩트

키/값 쌍으로 된 FactSet에서 팩트를 설명합니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**type**|`"Fact"`| 아니요|&nbsp;|1.0
|**title**|`string`|예|팩트의 제목입니다.|1.0
|**value**|`string`|예|팩트의 값입니다.|1.0


<a name="schema-imageset"></a>
## <a name="imageset"></a>ImageSet

ImageSet 이미지 갤러리에 유사한 컬렉션을 표시합니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**images**|`Image[]`|예|배열을 `Image` 요소를 표시 합니다.|1.0
|**imageSize**|`string`| 아니요, 기본값: `"auto"`|이미지의 대략적인 크기를 제어합니다. 실제 크기는 호스트 마다 달라 집니다. 지정할 `"auto"` 실제 이미지 차원에 대 한 또는 `"stretch"` 컨테이너를 입력 하도록 합니다.|1.0
|**type**|`"ImageSet"`|예|`"ImageSet"`여야 합니다.|1.0
|**id**|`string`| 아니요|요소에 연결 된 고유 식별자입니다.|1.0
|**spacing**|`string`| 아니요|이 요소는 이전 요소 사이의 간격 크기를 제어합니다.|1.0
|**separator**|`boolean`| 아니요, 기본값: `false`|때 `true`, 요소의 맨 위에 있는 구분 선을 그립니다.|1.0


# <a name="actions"></a>동작

<a name="schema-action.openurl"></a>
## <a name="actionopenurl"></a>Action.OpenUrl

를 호출 하면 표시할 지정된 된 url 외부 웹 브라우저 또는 보여 주는 내부 포함 된 웹 브라우저를 사용 하 여 시작 하 여 합니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**type**|`"Action.OpenUrl"`|예|`"Action.OpenUrl"`여야 합니다.|1.0
|**title**|`string`|예|이 작업을 나타내는 단추 또는 링크에 대 한 레이블.|1.0
|**iconUrl**|`string`| 아니요|제목와 함께에서 작업에 표시할 선택적 아이콘|1.1
|**url**|`string`|예|열려는 URL입니다.|1.0


<a name="schema-action.submit"></a>
## <a name="actionsubmit"></a>Action.Submit

입력된 필드를 수집 하 고, 선택적 데이터 필드를 사용 하 여 병합 및 클라이언트에 이벤트를 보냅니다. 이 데이터를 처리 하는 방법을 결정 하는 클라이언트에 게는 것입니다. 예를 들어 다음과 같은 가치를 제공해야 합니다. BotFramework 봇을 사용 하 여 클라이언트는 봇에 메시징 미디어를 통해 작업을 보냅니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**type**|`"Action.Submit"`|예|`"Action.Submit"`여야 합니다.|1.0
|**title**|`string`|예|이 작업을 나타내는 단추 또는 링크에 대 한 레이블.|1.0
|**iconUrl**|`string`| 아니요|제목와 함께에서 작업에 표시할 선택적 아이콘|1.1
|**data**|`string,object`| 아니요|초기 데이터 입력 필드를 사용 하 여 결합 됩니다. 이들은 기본적으로 '숨겨진된' 속성입니다.|1.0


<a name="schema-action.showcard"></a>
## <a name="actionshowcard"></a>Action.ShowCard

단추 또는 링크를 클릭할 때 사용자에 게 표시 되는 AdaptiveCard를 정의 합니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**type**|`"Action.ShowCard"`|예|`"Action.ShowCard"`여야 합니다.|1.0
|**title**|`string`|예|이 작업을 나타내는 단추 또는 링크에 대 한 레이블.|1.0
|**iconUrl**|`string`| 아니요|제목와 함께에서 작업에 표시할 선택적 아이콘|1.1
|**card**|`object`|예|Adaptive Card의 루트 요소입니다.|1.0


# <a name="inputs"></a>입력

<a name="schema-input.text"></a>
## <a name="inputtext"></a>Input.Text

텍스트를 입력 하는 사용자 수 있습니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**id**|`string`|예|값에 대 한 고유 식별자입니다. 전송 작업을 수행할 때 수집 된 입력을 식별 하는 데 사용 합니다.|1.0
|**isMultiline**|`boolean`| 아니요, 기본값: `false`|경우 `true`, 여러 줄 입력을 허용 합니다.|1.0
|**maxLength**|`number`| 아니요|최대 길이 수집 하는 문자 힌트 (일부 클라이언트에 의해 무시 될 수 있습니다).|1.0
|**placeholder**|`string`| 아니요|원하는 입력의 설명입니다. 텍스트가 입력 된 때를 표시 합니다.|1.0
|**style**|`string`| 아니요, 기본값: `"text"`|에 대 한 스타일 힌트 `Input.Text`합니다.|1.0
|**type**|`"Input.Text"`|예|`"Input.Text"`여야 합니다.|1.0
|**value**|`string`| 아니요|이 필드에 대 한 초기 값입니다.|1.0
|**spacing**|`string`| 아니요|이 요소는 이전 요소 사이의 간격 크기를 제어합니다.|1.0
|**separator**|`boolean`| 아니요, 기본값: `false`|때 `true`, 요소의 맨 위에 있는 구분 선을 그립니다.|1.0


<a name="schema-input.number"></a>
## <a name="inputnumber"></a>Input.Number

숫자를 입력할 수 있도록 허용 합니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**id**|`string`|예|값에 대 한 고유 식별자입니다. 전송 작업을 수행할 때 수집 된 입력을 식별 하는 데 사용 합니다.|1.0
|**max**|`number`| 아니요|힌트 (일부 클라이언트에 의해 무시 될 수 있습니다) 최 댓 값입니다.|1.0
|**min**|`number`| 아니요|힌트 (일부 클라이언트에 의해 무시 될 수 있습니다) 최 솟 값입니다.|1.0
|**placeholder**|`string`| 아니요|원하는 입력의 설명입니다. 선택 영역이 없는 이루어졌을 때를 표시 합니다.|1.0
|**type**|`"Input.Number"`|예|`"Input.Number"`여야 합니다.|1.0
|**value**|`number`| 아니요|이 필드에 대 한 초기 값입니다.|1.0
|**spacing**|`string`| 아니요|이 요소는 이전 요소 사이의 간격 크기를 제어합니다.|1.0
|**separator**|`boolean`| 아니요, 기본값: `false`|때 `true`, 요소의 맨 위에 있는 구분 선을 그립니다.|1.0


<a name="schema-input.date"></a>
## <a name="inputdate"></a>Input.Date

사용자를 날짜를 선택할 수 있습니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**id**|`string`|예|값에 대 한 고유 식별자입니다. 전송 작업을 수행할 때 수집 된 입력을 식별 하는 데 사용 합니다.|1.0
|**max**|`string`| 아니요|힌트 (일부 클라이언트에 의해 무시 될 수 있습니다)는 ISO-8601 형식으로 표현 된 최 댓 값입니다.|1.0
|**min**|`string`| 아니요|힌트 (일부 클라이언트에 의해 무시 될 수 있습니다)는 ISO-8601 형식으로 표현 된 최소 값입니다.|1.0
|**placeholder**|`string`| 아니요|원하는 입력의 설명입니다. 선택 영역이 없는 이루어졌을 때를 표시 합니다.|1.0
|**type**|`"Input.Date"`|예|`"Input.Date"`여야 합니다.|1.0
|**value**|`string`| 아니요|ISO-8601 형식으로 표현 된이 필드에 대 한 초기 값입니다.|1.0
|**spacing**|`string`| 아니요|이 요소는 이전 요소 사이의 간격 크기를 제어합니다.|1.0
|**separator**|`boolean`| 아니요, 기본값: `false`|때 `true`, 요소의 맨 위에 있는 구분 선을 그립니다.|1.0


<a name="schema-input.time"></a>
## <a name="inputtime"></a>Input.Time

시간을 선택 하는 사용자 수 있습니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**id**|`string`|예|값에 대 한 고유 식별자입니다. 전송 작업을 수행할 때 수집 된 입력을 식별 하는 데 사용 합니다.|1.0
|**max**|`string`| 아니요|힌트 (일부 클라이언트에 의해 무시 될 수 있습니다) 최 댓 값입니다.|1.0
|**min**|`string`| 아니요|힌트 (일부 클라이언트에 의해 무시 될 수 있습니다) 최 솟 값입니다.|1.0
|**placeholder**|`string`| 아니요|원하는 입력의 설명입니다. 시간 선택 했을 때를 표시 합니다.|1.0
|**type**|`"Input.Time"`|예|`"Input.Time"`여야 합니다.|1.0
|**value**|`string`| 아니요|ISO-8601 형식으로 표현 된이 필드에 대 한 초기 값입니다.|1.0
|**spacing**|`string`| 아니요|이 요소는 이전 요소 사이의 간격 크기를 제어합니다.|1.0
|**separator**|`boolean`| 아니요, 기본값: `false`|때 `true`, 요소의 맨 위에 있는 구분 선을 그립니다.|1.0


<a name="schema-input.toggle"></a>
## <a name="inputtoggle"></a>Input.Toggle

두 옵션 중에서 선택할 사용자를 수 있습니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**id**|`string`|예|값에 대 한 고유 식별자입니다. 전송 작업을 수행할 때 수집 된 입력을 식별 하는 데 사용 합니다.|1.0
|**title**|`string`|예|제목 설정/해제|1.0
|**type**|`"Input.Toggle"`|예|Input.Toggle|1.0
|**value**|`string`| 아니요, 기본값: `"false"`|현재 선택한 값입니다. "ValueOn" 사용 되는 항목을 선택한 경우이 고 그렇지 "valueOff"|1.0
|**valueOff**|`string`| 아니요, 기본값: `"false"`|토글이 꺼진 경우 값|1.0
|**valueOn**|`string`| 아니요, 기본값: `"true"`|토글이 켜진 경우 값|1.0
|**spacing**|`string`| 아니요|이 요소는 이전 요소 사이의 간격 크기를 제어합니다.|1.0
|**separator**|`boolean`| 아니요, 기본값: `false`|때 `true`, 요소의 맨 위에 있는 구분 선을 그립니다.|1.0


<a name="schema-input.choiceset"></a>
## <a name="inputchoiceset"></a>Input.ChoiceSet

선택 하는 입력할 수 있습니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**choices**|`Input.Choice[]`|예|`Choice` 옵션.|1.0
|**id**|`string`|예|값에 대 한 고유 식별자입니다. 전송 작업을 수행할 때 수집 된 입력을 식별 하는 데 사용 합니다.|1.0
|**isMultiSelect**|`boolean`| 아니요, 기본값: `false`|여러 선택 항목을 선택할 수 있습니다.|1.0
|**style**|`string`| 아니요, 기본값: `"compact"`|에 대 한 스타일 힌트 `Input.ChoiceSet`합니다.|1.0
|**type**|`"Input.ChoiceSet"`|예|`"Input.ChoiceInput"`여야 합니다.|1.0
|**value**|`string`| 아니요|초기 선택 항목 (또는 선택 항목 집합)를 선택 해야 합니다. 다중 선택에 대 한 값의 쉼표로 구분 된 문자열을 지정 합니다.|1.0
|**spacing**|`string`| 아니요|이 요소는 이전 요소 사이의 간격 크기를 제어합니다.|1.0
|**separator**|`boolean`| 아니요, 기본값: `false`|때 `true`, 요소의 맨 위에 있는 구분 선을 그립니다.|1.0


<a name="schema-input.choice"></a>
## <a name="inputchoice"></a>Input.Choice

적합을 한를 ChoiceSet에서 사용 하 여 설명합니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**type**|`"Input.Choice"`| 아니요|&nbsp;|1.0
|**title**|`string`|예|표시할 텍스트입니다.|1.0
|**value**|`string`|예|선택에 대 한 원시 값입니다. **참고:** 사용 하지 마십시오는 `,` 값으로 하므로 `ChoiceSet` 사용 하 여 `isMultiSelect` 로 `true` 선택한 값의 쉼표로 구분 된 문자열을 반환 합니다.|1.0
