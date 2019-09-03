---
title: 적응형 카드의 HostConfig
author: paulcam206
ms.author: paulcam
ms.date: 09/18/2018
ms.topic: reference
ms.openlocfilehash: 46ba9987cf162e95ab86dcdafa55e10df29b1121
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552595"
---
# <a name="what-is-hostconfig"></a>HostConfig란 무엇인가요?
`HostConfig`는 적응형 카드 렌더러가 UI를 생성하는 방법을 지정하는 **플랫폼 간 구성 개체**입니다.

이를 사용하면 플랫폼에 독립적인 속성을 다양한 플랫폼 및 디바이스의 렌더러 간에 공유할 수 있습니다. 특정 환경에 대한 카드의 모양과 느낌에 대한 아이디어를 제공하는 도구를 만들 수도 있습니다.

콘텐츠에 대한 느낌을 얻으려면 샘플 [HostConfig.json](https://github.com/Microsoft/AdaptiveCards/blob/master/samples/HostConfig/sample.json)을 참조하세요.

---

   * [`AdaptiveCardConfig`](#schema-adaptivecardconfig) - `AdaptiveCards`의 최상위 옵션
   * [`ActionsConfig`](#schema-actionsconfig) - `Action`의 옵션
   * [`ContainerStylesConfig`](#schema-containerstylesconfig) - 기본 및 강조 컨테이너의 스타일 지정 제어
   * [`FactSetConfig`](#schema-factsetconfig) - `FactSet`의 표시 제어
   * [`FontSizesConfig`](#schema-fontsizesconfig) - 다양한 텍스트 스타일의 글꼴 크기 메트릭 제어
   * [`FontWeightsConfig`](#schema-fontweightsconfig) - 글꼴 두께 메트릭 제어
   * [`ForegroundColorsConfig`](#schema-foregroundcolorsconfig) - 다양한 글꼴 색 제어
   * [`ImageSetConfig`](#schema-imagesetconfig) - `ImageSet` 표시 방법 제어
   * [`ImageSizesConfig`](#schema-imagesizesconfig) - `Image` 크기 제어
   * [`MediaConfig`](#schema-mediaconfig) - `Media` 요소의 표시 및 동작 제어
   * [`SeparatorConfig`](#schema-separatorconfig) - 구분 기호 표시 방법 제어
   * [`ShowCardConfig`](#schema-showcardconfig) - `Action.ShowCard`의 동작 및 스타일 제어
   * [`SpacingsConfig`](#schema-spacingsconfig) - 요소 배치 방법 제어
   * [`TextBlockConfig`](#schema-textblockconfig) - 텍스트 표시를 제어하는 매개 변수

# <a name="card-configuration"></a>카드 구성

<a name="schema-adaptivecardconfig"></a>
## <a name="adaptivecardconfig"></a>AdaptiveCardConfig

`AdaptiveCards`의 최상위 옵션

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**allowCustomStyle**|`boolean`| 아니요. 기본값: `true`|사용자 지정 스타일이 허용되는지 여부 제어|1.0
|**supportsInteractivity**|`boolean`| 아니요. 기본값: `true`|대화형 `Action`을 호출할 수 있는지 여부 제어|1.0
|**imageBaseUrl**|`string`| 아니오|리소스를 로드할 때 사용되는 기준 URL|1.0
|**fontFamily**|`string`| 아니요. 기본값: `"Calibri"`|텍스트를 렌더링할 때 사용할 글꼴|1.0
|**actions**|`object`| 아니오|`Action`의 옵션|1.0
|**adaptiveCard**|`object`| 아니오|`AdaptiveCards`의 최상위 옵션|1.0
|**containerStyles**|`object`| 아니오|기본 및 강조 컨테이너의 스타일 지정 제어|1.0
|**imageSizes**|`object`| 아니오|`Image` 크기 제어|1.0
|**imageSet**|`object`| 아니오|`ImageSet` 표시 방법 제어|1.0
|**factSet**|`object`| 아니오|`FactSet`의 표시 제어|1.0
|**fontSizes**|`object`| 아니오|다양한 텍스트 스타일의 글꼴 크기 메트릭 제어|1.0
|**fontWeights**|`object`| 아니오|글꼴 두께 메트릭 제어|1.0
|**spacing**|`object`| 아니오|요소 배치 방법 제어|1.0
|**separator**|`object`| 아니오|구분 기호 표시 방법 제어|1.0
|**media**|`object`| 아니오|`Media` 요소의 표시 및 동작 제어|1.1


<a name="schema-actionsconfig"></a>
## <a name="actionsconfig"></a>ActionsConfig

`Action`의 옵션

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**actionsOrientation**|`string`| 아니요. 기본값: `"horizontal"`|단추 배치 방법 제어|1.0
|**actionAlignment**|`string`| 아니요. 기본값: `"stretch"`|단추 레이아웃 제어|1.0
|**buttonSpacing**|`integer`| 아니요. 기본값: `10`|단추 사이에 사용할 간격 크기 제어|1.0
|**maxActions**|`integer`| 아니요. 기본값: `5`|허용되는 총 작업 수 제어|1.0
|**spacing**|`string`| 아니요. 기본값: `"default"`|작업 요소의 전체 간격 제어|1.0
|**showCard**|`object`| 아니오|`Action.ShowCard`의 동작 및 스타일 제어|1.0
|**iconPlacement**|`string`| 아니요. 기본값: `"aboveTitle"`|작업 아이콘을 배치할 위치 제어|1.0
|**iconSize**|`integer`| 아니요. 기본값: `30`|작업 아이콘의 크기 제어|1.0


<a name="schema-containerstylesconfig"></a>
## <a name="containerstylesconfig"></a>ContainerStylesConfig

기본 및 강조 컨테이너의 스타일 지정 제어

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**default**|`object`| 아니오|기본 컨테이너 스타일|1.0
|**emphasis**|`object`| 아니오|강조에 사용할 컨테이너 스타일|1.0


<a name="schema-factsetconfig"></a>
## <a name="factsetconfig"></a>FactSetConfig

`FactSet`의 표시 제어

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**title**|`object`| 아니요. 기본값: `{"weight":"bolder","size":"default","color":"default","isSubtle":false,"wrap":true,"maxWidth":150}`|텍스트 표시를 제어하는 매개 변수|1.0
|**value**|`object`| 아니요. 기본값: `{"weight":"default","size":"default","color":"default","isSubtle":false,"wrap":true,"maxWidth":0}`|텍스트 표시를 제어하는 매개 변수|1.0
|**spacing**|`integer`| 아니요. 기본값: `10`|&nbsp;|1.0


<a name="schema-fontsizesconfig"></a>
## <a name="fontsizesconfig"></a>FontSizesConfig

다양한 텍스트 스타일의 글꼴 크기 메트릭 제어

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**small**|`integer`| 아니요. 기본값: `10`|작은 글꼴 크기|1.0
|**default**|`integer`| 아니요. 기본값: `12`|기본 글꼴 크기|1.0
|**medium**|`integer`| 아니요. 기본값: `14`|중간 글꼴 크기|1.0
|**large**|`integer`| 아니요. 기본값: `17`|큰 글꼴 크기|1.0
|**extraLarge**|`integer`| 아니요. 기본값: `20`|매우 큰 글꼴 크기|1.0


<a name="schema-fontweightsconfig"></a>
## <a name="fontweightsconfig"></a>FontWeightsConfig

글꼴 두께 메트릭 제어

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**lighter**|`integer`| 아니요. 기본값: `200`|&nbsp;|1.0
|**default**|`integer`| 아니요. 기본값: `400`|&nbsp;|1.0
|**bolder**|`integer`| 아니요. 기본값: `800`|&nbsp;|1.0


<a name="schema-foregroundcolorsconfig"></a>
## <a name="foregroundcolorsconfig"></a>ForegroundColorsConfig

다양한 글꼴 색 제어

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**default**|`object`| 아니요. 기본값: `{"default":"#FF000000","subtle":"#B2000000"}`|&nbsp;|1.0
|**accent**|`object`| 아니요. 기본값: `{"default":"#FF0000FF","subtle":"#B20000FF"}`|&nbsp;|1.0
|**dark**|`object`| 아니요. 기본값: `{"default":"#FF101010","subtle":"#B2101010"}`|&nbsp;|1.0
|**light**|`object`| 아니요. 기본값: `{"default":"#FFFFFFFF","subtle":"#B2FFFFFF"}`|&nbsp;|1.0
|**good**|`object`| 아니요. 기본값: `{"default":"#FF008000","subtle":"#B2008000"}`|&nbsp;|1.0
|**warning**|`object`| 아니요. 기본값: `{"default":"#FFFFD700","subtle":"#B2FFD700"}`|&nbsp;|1.0
|**attention**|`object`| 아니요. 기본값: `{"default":"#FF8B0000","subtle":"#B28B0000"}`|&nbsp;|1.0


<a name="schema-imagesetconfig"></a>
## <a name="imagesetconfig"></a>ImageSetConfig

`ImageSet` 표시 방법 제어

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**imageSize**|`string`| 아니요. 기본값: `"auto"`|개별 이미지 크기 제어|1.0
|**maxImageHeight**|`integer`| 아니요. 기본값: `100`|이미지 높이를 이 값으로 제한|1.0


<a name="schema-imagesizesconfig"></a>
## <a name="imagesizesconfig"></a>ImageSizesConfig

`Image` 크기 제어

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**small**|`integer`| 아니요. 기본값: `80`|작은 이미지 크기 값|1.0
|**medium**|`integer`| 아니요. 기본값: `120`|중간 이미지 크기 값|1.0
|**large**|`integer`| 아니요. 기본값: `180`|큰 이미지 크기 값|1.0


<a name="schema-mediaconfig"></a>
## <a name="mediaconfig"></a>MediaConfig

`Media` 요소의 표시 및 동작 제어

#### <a name="introduced-in-version-11"></a>버전 1.1에서 도입됨

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**defaultPoster**|`string`| 아니오|재생 단추가 호출되지 않았을 때 표시할 이미지의 URI|1.1
|**playButton**|`string`| 아니오|재생 단추로 표시할 이미지|1.1
|**allowInlinePlayback**|`boolean`| 아니요. 기본값: `true`|미디어를 인라인으로 표시하거나 외부에서 호출할지 여부|1.1


<a name="schema-separatorconfig"></a>
## <a name="separatorconfig"></a>SeparatorConfig

구분 기호 표시 방법 제어

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**lineThickness**|`integer`| 아니요. 기본값: `1`|구분선 두께|1.0
|**lineColor**|`string,null`| 아니요. 기본값: `#B2000000`|구분선을 그릴 때 사용할 색|1.0


<a name="schema-showcardconfig"></a>
## <a name="showcardconfig"></a>ShowCardConfig

`Action.ShowCard`의 동작 및 스타일 제어

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**actionMode**|`string`| 아니요. 기본값: `"inline"`|카드 표시 방법 제어|1.0
|**style**|`object`| 아니요. 기본값: `emphasis`|컨테이너의 스타일 제어|1.0
|**inlineTopMargin**|`integer`| 아니요. 기본값: `16`|카드를 표시할 때 사용할 여백 크기|1.0


<a name="schema-spacingsconfig"></a>
## <a name="spacingsconfig"></a>SpacingsConfig

요소 배치 방법 제어

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**small**|`integer`| 아니요. 기본값: `3`|작은 간격 값|1.0
|**default**|`integer`| 아니요. 기본값: `8`|기본 간격 값|1.0
|**medium**|`integer`| 아니요. 기본값: `20`|중간 간격 값|1.0
|**large**|`integer`| 아니요. 기본값: `30`|큰 간격 값|1.0
|**extraLarge**|`integer`| 아니요. 기본값: `40`|매우 큰 간격 값|1.0
|**padding**|`integer`| 아니요. 기본값: `20`|안쪽 여백 값|1.0


<a name="schema-textblockconfig"></a>
## <a name="textblockconfig"></a>TextBlockConfig

텍스트 표시를 제어하는 매개 변수

|속성|형식|필수|설명|버전|
|--------|----|--------|-----------|-------|
|**size**|`string`| 아니요. 기본값: `"default"`|카드에서 지정하지 않을 때 사용할 글꼴 크기|1.0
|**weight**|`string`| 아니요. 기본값: `"normal"`|카드에서 지정하지 않을 때 사용할 글꼴 두께|1.0
|**color**|`string`| 아니요. 기본값: `"default"`|카드에서 지정하지 않을 때 사용할 글꼴 색|1.0
|**isSubtle**|`boolean`| 아니요. 기본값: `false`|카드에서 지정하지 않는 경우 텍스트가 흐리게 표시됨|1.0
|**wrap**|`boolean`| 아니요. 기본값: `true`|카드에서 지정하지 않는 경우 텍스트를 줄 바꿈함|1.0
|**maxWidth**|`integer`| 아니요. 기본값: `0`|카드에서 지정되지 않는 경우 사용할 최대 너비|1.0
