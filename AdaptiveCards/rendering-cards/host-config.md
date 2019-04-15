---
title: Adaptive Card에 대 한 HostConfig
author: paulcam206
ms.author: paulcam
ms.date: 09/18/2018
ms.topic: reference
ms.openlocfilehash: 46ba9987cf162e95ab86dcdafa55e10df29b1121
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552595"
---
# <a name="what-is-hostconfig"></a>HostConfig 란?
`HostConfig` **플랫폼 간 구성 개체** 적응 카드 렌더러는 UI를 생성 하는 방법을 지정 하는 합니다.

이렇게 하면 다양 한 플랫폼 및 장치에서 렌더러를 공유할 수 있도록 플랫폼을 알 수 없는 속성입니다. 또한 제공 하는 것이 카드는 모양과 느낌의 지정된 된 환경에 대 한 도구를를 만들 수 있습니다.

예를 보려면 [HostConfig.json](https://github.com/Microsoft/AdaptiveCards/blob/master/samples/HostConfig/sample.json) 그 내용에 대해 이해할 합니다.

---

   * [`AdaptiveCardConfig`](#schema-adaptivecardconfig) 에 대 한 최상위 옵션 `AdaptiveCards`
   * [`ActionsConfig`](#schema-actionsconfig) -에 대 한 옵션 `Action`s
   * [`ContainerStylesConfig`](#schema-containerstylesconfig) 컨트롤 컨테이너의 기본 인스턴스 및 강조 스타일 지정
   * [`FactSetConfig`](#schema-factsetconfig) --의 디스플레이 제어 하는 중 `FactSet`s
   * [`FontSizesConfig`](#schema-fontsizesconfig) -다른 텍스트 스타일에 대 한 글꼴 크기 메트릭을 제어합니다.
   * [`FontWeightsConfig`](#schema-fontweightsconfig) -글꼴 가중치 메트릭을 제어합니다.
   * [`ForegroundColorsConfig`](#schema-foregroundcolorsconfig) -다양 한 글꼴 색을 제어합니다.
   * [`ImageSetConfig`](#schema-imagesetconfig) -제어 방법을 `ImageSet`표시 됩니다
   * [`ImageSizesConfig`](#schema-imagesizesconfig) -제어 `Image` 크기
   * [`MediaConfig`](#schema-mediaconfig) -컨트롤의 표시 및 동작 `Media` 요소
   * [`SeparatorConfig`](#schema-separatorconfig) -구분 기호 표시 되는 방식을 제어합니다
   * [`ShowCardConfig`](#schema-showcardconfig) -컨트롤의 스타일 및 동작 `Action.ShowCard`
   * [`SpacingsConfig`](#schema-spacingsconfig) -요소를 배치 하는 방법을 제어합니다
   * [`TextBlockConfig`](#schema-textblockconfig) 매개 변수 텍스트의 표시 제어

# <a name="card-configuration"></a>카드 구성

<a name="schema-adaptivecardconfig"></a>
## <a name="adaptivecardconfig"></a>AdaptiveCardConfig

에 대 한 최상위 옵션 `AdaptiveCards`

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**allowCustomStyle**|`boolean`| 아니요, 기본값: `true`|사용자 지정 스타일 허용 되는지 여부를 제어 합니다.|1.0
|**supportsInteractivity**|`boolean`| 아니요, 기본값: `true`|대화형 제어 `Action`호출 될 수 있습니다|1.0
|**imageBaseUrl**|`string`| 아니요|리소스를 로드할 때 사용할 기본 URL|1.0
|**fontFamily**|`string`| 아니요, 기본값: `"Calibri"`|텍스트를 렌더링할 때 사용할 글꼴|1.0
|**actions**|`object`| 아니요|에 대 한 옵션 `Action`s|1.0
|**adaptiveCard**|`object`| 아니요|에 대 한 최상위 옵션 `AdaptiveCards`|1.0
|**containerStyles**|`object`| 아니요|컨트롤 컨테이너의 기본 인스턴스 및 강조 스타일 지정|1.0
|**imageSizes**|`object`| 아니요|컨트롤 `Image` 크기|1.0
|**imageSet**|`object`| 아니요|컨트롤 어떻게 `ImageSet`표시 됩니다|1.0
|**factSet**|`object`| 아니요|표시 제어 `FactSet`s|1.0
|**fontSizes**|`object`| 아니요|다른 텍스트 스타일에 대 한 글꼴 크기 메트릭을 제어합니다.|1.0
|**fontWeights**|`object`| 아니요|컨트롤의 글꼴 두께 메트릭|1.0
|**spacing**|`object`| 아니요|요소를 배치 하는 방법을 제어합니다|1.0
|**separator**|`object`| 아니요|구분 기호 표시 되는 방식을 제어 합니다.|1.0
|**media**|`object`| 아니요|표시 및 동작을 제어 `Media` 요소|1.1


<a name="schema-actionsconfig"></a>
## <a name="actionsconfig"></a>ActionsConfig

에 대 한 옵션 `Action`s

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**actionsOrientation**|`string`| 아니요, 기본값: `"horizontal"`|단추 레이아웃 되는 방법을 제어 합니다.|1.0
|**actionAlignment**|`string`| 아니요, 기본값: `"stretch"`|단추 컨트롤 레이아웃|1.0
|**buttonSpacing**|`integer`| 아니요, 기본값: `10`|얼마나 많은 간격 사이 단추 컨트롤|1.0
|**maxActions**|`integer`| 아니요, 기본값: `5`|얼마나 많은 작업 총에서 수를 제어 합니다.|1.0
|**spacing**|`string`| 아니요, 기본값: `"default"`|컨트롤 전체 action 요소 간격|1.0
|**showCard**|`object`| 아니요|컨트롤의 동작과의 스타일 지정 `Action.ShowCard`|1.0
|**iconPlacement**|`string`| 아니요, 기본값: `"aboveTitle"`|작업 아이콘을 배치할 위치를 제어 합니다.|1.0
|**iconSize**|`integer`| 아니요, 기본값: `30`|작업 아이콘의 크기 제어|1.0


<a name="schema-containerstylesconfig"></a>
## <a name="containerstylesconfig"></a>ContainerStylesConfig

컨트롤 컨테이너의 기본 인스턴스 및 강조 스타일 지정

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**default**|`object`| 아니요|기본 컨테이너 스타일|1.0
|**emphasis**|`object`| 아니요|컨테이너에 사용할 스타일을 강조|1.0


<a name="schema-factsetconfig"></a>
## <a name="factsetconfig"></a>FactSetConfig

표시 제어 `FactSet`s

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**title**|`object`| 아니요, 기본값: `{"weight":"bolder","size":"default","color":"default","isSubtle":false,"wrap":true,"maxWidth":150}`|텍스트 표시를 제어 하는 매개 변수|1.0
|**value**|`object`| 아니요, 기본값: `{"weight":"default","size":"default","color":"default","isSubtle":false,"wrap":true,"maxWidth":0}`|텍스트 표시를 제어 하는 매개 변수|1.0
|**spacing**|`integer`| 아니요, 기본값: `10`|&nbsp;|1.0


<a name="schema-fontsizesconfig"></a>
## <a name="fontsizesconfig"></a>FontSizesConfig

다른 텍스트 스타일에 대 한 글꼴 크기 메트릭을 제어합니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**small**|`integer`| 아니요, 기본값: `10`|작은 글꼴 크기|1.0
|**default**|`integer`| 아니요, 기본값: `12`|기본 글꼴 크기|1.0
|**medium**|`integer`| 아니요, 기본값: `14`|보통 글꼴 크기|1.0
|**large**|`integer`| 아니요, 기본값: `17`|큰 글꼴 크기|1.0
|**extraLarge**|`integer`| 아니요, 기본값: `20`|아주 큰 글꼴 크기|1.0


<a name="schema-fontweightsconfig"></a>
## <a name="fontweightsconfig"></a>FontWeightsConfig

컨트롤의 글꼴 두께 메트릭

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**lighter**|`integer`| 아니요, 기본값: `200`|&nbsp;|1.0
|**default**|`integer`| 아니요, 기본값: `400`|&nbsp;|1.0
|**bolder**|`integer`| 아니요, 기본값: `800`|&nbsp;|1.0


<a name="schema-foregroundcolorsconfig"></a>
## <a name="foregroundcolorsconfig"></a>ForegroundColorsConfig

다양 한 글꼴 색을 제어합니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**default**|`object`| 아니요, 기본값: `{"default":"#FF000000","subtle":"#B2000000"}`|&nbsp;|1.0
|**accent**|`object`| 아니요, 기본값: `{"default":"#FF0000FF","subtle":"#B20000FF"}`|&nbsp;|1.0
|**dark**|`object`| 아니요, 기본값: `{"default":"#FF101010","subtle":"#B2101010"}`|&nbsp;|1.0
|**light**|`object`| 아니요, 기본값: `{"default":"#FFFFFFFF","subtle":"#B2FFFFFF"}`|&nbsp;|1.0
|**good**|`object`| 아니요, 기본값: `{"default":"#FF008000","subtle":"#B2008000"}`|&nbsp;|1.0
|**warning**|`object`| 아니요, 기본값: `{"default":"#FFFFD700","subtle":"#B2FFD700"}`|&nbsp;|1.0
|**attention**|`object`| 아니요, 기본값: `{"default":"#FF8B0000","subtle":"#B28B0000"}`|&nbsp;|1.0


<a name="schema-imagesetconfig"></a>
## <a name="imagesetconfig"></a>ImageSetConfig

컨트롤 어떻게 `ImageSet`표시 됩니다

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**imageSize**|`string`| 아니요, 기본값: `"auto"`|컨트롤의 개별 이미지 크기 조정|1.0
|**maxImageHeight**|`integer`| 아니요, 기본값: `100`|이 값으로 이미지의 높이 제한 합니다.|1.0


<a name="schema-imagesizesconfig"></a>
## <a name="imagesizesconfig"></a>ImageSizesConfig

컨트롤 `Image` 크기

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**small**|`integer`| 아니요, 기본값: `80`|작은 이미지 크기 값|1.0
|**medium**|`integer`| 아니요, 기본값: `120`|중간 이미지 크기 값|1.0
|**large**|`integer`| 아니요, 기본값: `180`|큰 이미지 크기 값|1.0


<a name="schema-mediaconfig"></a>
## <a name="mediaconfig"></a>MediaConfig

표시 및 동작을 제어 `Media` 요소

#### <a name="introduced-in-version-11"></a>버전 1.1에에서 도입 된

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**defaultPoster**|`string`| 아니요|재생 단추는 호출 되지 않았습니다 하는 경우에 표시할 이미지 URI|1.1
|**playButton**|`string`| 아니요|재생 단추를 표시 하려면 이미지|1.1
|**allowInlinePlayback**|`boolean`| 아니요, 기본값: `true`|미디어 인라인으로 표시 하거나 외부에서 호출할 것인지|1.1


<a name="schema-separatorconfig"></a>
## <a name="separatorconfig"></a>SeparatorConfig

구분 기호 표시 되는 방식을 제어 합니다.

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**lineThickness**|`integer`| 아니요, 기본값: `1`|구분선의 두께|1.0
|**lineColor**|`string,null`| 아니요, 기본값: `#B2000000`|구분선을 그릴 때 사용할 색|1.0


<a name="schema-showcardconfig"></a>
## <a name="showcardconfig"></a>ShowCardConfig

컨트롤의 동작과의 스타일 지정 `Action.ShowCard`

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**actionMode**|`string`| 아니요, 기본값: `"inline"`|카드 표시 되는 방식을 제어 합니다.|1.0
|**style**|`object`| 아니요, 기본값: `emphasis`|컨테이너의 컨트롤 스타일 지정|1.0
|**inlineTopMargin**|`integer`| 아니요, 기본값: `16`|카드를 표시할 때 사용할 여백 크기|1.0


<a name="schema-spacingsconfig"></a>
## <a name="spacingsconfig"></a>SpacingsConfig

요소를 배치 하는 방법을 제어합니다

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**small**|`integer`| 아니요, 기본값: `3`|작은 간격 값|1.0
|**default**|`integer`| 아니요, 기본값: `8`|기본 간격 값|1.0
|**medium**|`integer`| 아니요, 기본값: `20`|보통 간격 값|1.0
|**large**|`integer`| 아니요, 기본값: `30`|큰 간격 값|1.0
|**extraLarge**|`integer`| 아니요, 기본값: `40`|초대형 간격 값|1.0
|**padding**|`integer`| 아니요, 기본값: `20`|안쪽 여백 값|1.0


<a name="schema-textblockconfig"></a>
## <a name="textblockconfig"></a>TextBlockConfig

텍스트 표시를 제어 하는 매개 변수

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**size**|`string`| 아니요, 기본값: `"default"`|카드를 지정 하지 않고 사용할 글꼴 크기|1.0
|**weight**|`string`| 아니요, 기본값: `"normal"`|글꼴 두께를 지정 하지 않고 카드를 사용 하 여|1.0
|**color**|`string`| 아니요, 기본값: `"default"`|카드를 지정 하지 않으면 때 사용할 글꼴색|1.0
|**isSubtle**|`boolean`| 아니요, 기본값: `false`|텍스트 카드를 지정 하지 않으면 미묘한 해야 합니까|1.0
|**wrap**|`boolean`| 아니요, 기본값: `true`|텍스트 줄 바꿈 카드를 지정 하지 않으면|1.0
|**maxWidth**|`integer`| 아니요, 기본값: `0`|사용할 카드 지정 하지 않으면 최대 너비|1.0
