---
title: AdaptiveCard 클래스-Xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: 0f64bf635023271d8b40bf55fce079300aae7652
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76146087"
---
# <a name="adaptivecard"></a>AdaptiveCard

```csharp
public class AdaptiveCard : Java.Lang.Object 
```

**Namespace**

```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.ObjectModel
```

## <a name="summary"></a>요약

| 특성 | |
| ---- | --- |
| 조치 | 카드의 작업 모음에 표시 되는 작업입니다. |
| BackgroundImage | 카드의 배경 이미지를 지정 합니다. |
| Body | 기본 카드 지역에 표시할 카드 요소입니다. |
| ElementType | "AdaptiveCard" 여야 합니다. |
| FallbackText | 클라이언트에서 지정 된 버전을 지원 하지 않을 때 표시 되는 텍스트입니다 (markdown 포함). |
| 높이 | |
| InputNecessityIndicators | |
| 언어 | 카드에 사용 되는 2 자로 된 ISO-639-1 언어입니다. 모든 날짜/시간 함수를 지역화 하는 데 사용 됩니다. |
| MinHeight | 카드의 최소 높이를 지정 합니다. |
| SelectAction | 카드를 누르거나 선택할 때 호출 되는 작업입니다. 작업. ShowCard는 지원 되지 않습니다. |
| Speak | 이 전체 카드에 대해 말할 항목을 지정 합니다. 단순 텍스트 또는 SSML 조각입니다. |
| 스타일을 | |
| Version | 이 카드에 필요한 스키마 버전입니다. 클라이언트가이 버전 보다 낮으면 fallbackText가 렌더링 됩니다. 참고: 작업 내의 카드에는 버전이 필요 하지 않습니다. ShowCard. 그러나 최상위 카드의 경우에는 필수입니다. |
| System.windows.controls.control.verticalcontentalignment | 컨테이너 내에서 콘텐츠를 세로로 정렬 하는 방법을 정의 합니다. 고정 높이 카드 또는 minHeight 지정 된 카드만 해당 합니다. |

&nbsp;

**Public 생성자**

---

<a href="#ctor0"><div>
```csharp
AdaptiveCard(string version, string fallbackText, BackgroundImage backgroundImage, ContainerStyle style, string speak, string language, VerticalContentAlignment verticalContentAlignment, HeightType height, long minHeight)
```
</div></a>

<a href="#ctor1"><div>
```csharp
AdaptiveCard(string version, string fallbackText, BackgroundImage backgroundImage, ContainerStyle style, string speak, string language, VerticalContentAlignment verticalContentAlignment, HeightType height, long minHeight, BaseCardElementVector body, BaseActionElementVector actions)
```
</div></a>

<a href="#ctor2"><div>
```csharp
AdaptiveCard(string version, string fallbackText, string backgroundImageUrl, ContainerStyle style, string speak, string language, VerticalContentAlignment verticalContentAlignment, HeightType height, long minHeight)
```
</div></a>

<a href="#ctor3"><div>
```csharp
AdaptiveCard(string version, string fallbackText, string backgroundImageUrl, ContainerStyle style, string speak, string language, VerticalContentAlignment verticalContentAlignment, HeightType height, long minHeight, BaseCardElementVector body, BaseActionElementVector actions)
```
</div></a>

&nbsp;
| public 메서드 | |
| --- | ---- |
| ```static ParseResult``` | [```DeserializeFromString(string jsonString, string rendererVersion)```](#deserializefromstring0) |
| ```static ParseResult``` | [```DeserializeFromString(string jsonString, string rendererVersion, ParseContext context)```](#deserializefromstring1) |
| ```static AdaptiveCard``` | [```MakeFallbackTextCard(string fallbackText, string language, string speak)```](#makefallbacktextcard) |
| ```string``` | [```Serialize()```](#serialize) |
| ```JsonValue``` | [```SerializeToJsonValue()```](#serializetojsonvalue) |

&nbsp;
## <a name="public-constructors"></a>공용 생성자
---

### <a id="ctor0"></a>AdaptiveCard
<p style='text-align:right'>버전 0.1에 추가 됨</p>

```csharp
public AdaptiveCard (string version, 
                    string fallbackText, 
                    BackgroundImage backgroundImage, 
                    ContainerStyle style, 
                    string speak, 
                    string language, 
                    VerticalContentAlignment verticalContentAlignment, 
                    HeightType height, 
                    long minHeight) 
```

| 매개 변수 | |
| --- | --- |
| version | ```string``` |
| fallbackText | ```string``` |
| backgroundImage | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BackgroundImage``` |
| 스타일 | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ContainerStyle``` |
| speak | ```string``` |
| language | ```string``` |
| System.windows.controls.control.verticalcontentalignment | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.VerticalContentAlignment``` |
| height | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HeightType``` |
| minHeight | ```long``` |

&nbsp;&nbsp;

### <a id="ctor1"></a>AdaptiveCard
<p style='text-align:right'>버전 0.1에 추가 됨</p>

```csharp
public AdaptiveCard (string version, 
                    string fallbackText, 
                    BackgroundImage backgroundImage, 
                    ContainerStyle style, 
                    string speak, 
                    string language, 
                    VerticalContentAlignment verticalContentAlignment, 
                    HeightType height, 
                    long minHeight, 
                    BaseCardElementVector body, 
                    BaseActionElementVector actions)
```

| 매개 변수 | |
| --- | --- |
| version | ```string``` |
| fallbackText | ```string``` |
| backgroundImage | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BackgroundImage``` |
| 스타일 | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ContainerStyle``` |
| speak | ```string``` |
| language | ```string``` |
| System.windows.controls.control.verticalcontentalignment | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.VerticalContentAlignment``` |
| height | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HeightType``` |
| minHeight | ```long``` |
| 본문 | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseCardElementVector``` |
| 작업 | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseActionElementVector``` |

&nbsp;&nbsp;

### <a id="ctor2"></a>AdaptiveCard
<p style='text-align:right'>버전 0.1에 추가 됨</p>

```csharp
public AdaptiveCard (string version, 
                    string fallbackText, 
                    string backgroundImageUrl, 
                    ContainerStyle style, 
                    string speak, 
                    string language, 
                    VerticalContentAlignment verticalContentAlignment,
                    HeightType height, 
                    long minHeight) 
```

| 매개 변수 | |
| --- | --- |
| version | ```string``` |
| fallbackText | ```string``` |
| backgroundImage | ```string``` |
| 스타일 | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ContainerStyle``` |
| speak | ```string``` |
| language | ```string``` |
| System.windows.controls.control.verticalcontentalignment | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.VerticalContentAlignment``` |
| height | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HeightType``` |
| minHeight | ```long``` |

&nbsp;&nbsp;

### <a id="ctor3"></a>AdaptiveCard
<p style='text-align:right'>버전 0.1에 추가 됨</p>

```csharp
public AdaptiveCard (string version, 
                    string fallbackText, 
                    string backgroundImageUrl, 
                    ContainerStyle style, 
                    string speak, 
                    string language, 
                    VerticalContentAlignment verticalContentAlignment,
                    HeightType height, 
                    long minHeight, 
                    BaseCardElementVector body,
                    BaseActionElementVector actions)

```

| 매개 변수 | |
| --- | --- |
| version | ```string``` |
| fallbackText | ```string``` |
| backgroundImage | ```string``` |
| 스타일 | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ContainerStyle``` |
| speak | ```string``` |
| language | ```string``` |
| System.windows.controls.control.verticalcontentalignment | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.VerticalContentAlignment``` |
| height | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HeightType``` |
| minHeight | ```long``` |
| 본문 | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseCardElementVector``` |
| 작업 | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseActionElementVector``` |

&nbsp;

## <a name="public-methods"></a>공용 메서드
---
### <a id="deserializefromstring0"></a>DeserializeFromString
<p style='text-align:right'>버전 0.1.0에 추가 됨</p>

```csharp
public static ParseResult DeserializeFromString (string jsonString, string rendererVersion)
```

지정 된 적응 카드를 지정 된 렌더러 버전에 대 한 json 문자열로 deserialize 합니다.

| 매개 변수 | |
| --- | --- |
| jsonString | ```string``` |
| rendererVersion | ```string``` |

| Returns | |
| --- | --- |
| ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ParseResult``` | |

#### <a name="sample"></a>샘플

```csharp
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version);
```

--- 
### <a id="deserializefromstring1"></a>DeserializeFromString
<p style='text-align:right'>버전 0.1.0에 추가 됨</p>

```csharp
public static ParseResult DeserializeFromString(string jsonString, string rendererVersion, ParseContext context)
```

사용자 지정 요소 구문 분석을 처리 하기 위해 [ParseContext]() 개체를 사용 하 여 지정 된 렌더러 버전에 대 한 json 문자열로 지정 된 적응 카드를 deserialize 합니다.

| 매개 변수 | |
| --- | --- |
| jsonString | ```string``` |
| rendererVersion | ```string``` |
| 컨텍스트 | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ParseContext``` |

| Returns | |
| --- | --- |
| ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ParseResult``` | |

#### <a name="sample"></a>샘플

```csharp
ParseContext parseContext = new ParseContext(elementParserRegistration, actionParserRegistration);
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version, parseContext);
```

---

### <a id="makefallbacktextcard"></a>MakeFallbackTextCard
<p style='text-align:right'>버전 0.1.0에 추가 됨</p>

```csharp
public static AdaptiveCard MakeFallbackTextCard (string fallbackText, string language, string speak)
```

지정 된 적응 카드를 지정 된 렌더러 버전에 대 한 json 문자열로 deserialize 합니다.

| 매개 변수 | |
| --- | --- |
| fallbackText | ```string``` |
| language | ```string``` |
| speak | ```string``` |

| Returns | |
| --- | --- |
| ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.AdaptiveCard``` | Unrendereable 카드의 대체 텍스트를 포함 하는 적응 카드 |

#### <a name="sample"></a>샘플

```csharp
AdaptiveCard adaptiveCard = AdaptiveCard.MakeFallbackTextCard("This card failed to render", "es", "Unrendereable card");
```

---

### <a id="serialize"></a>스트림으로
<p style='text-align:right'>버전 0.1.0에 추가 됨</p>

```csharp
public string Serialize ()
```

적응 카드를 json 문자열 형식으로 직렬화 합니다.

| Returns | |
| --- | --- |
| ```string``` | Json 문자열로 적응 카드 |

#### <a name="sample"></a>샘플

```csharp
string jsonString = parseResult.AdaptiveCard.Serialize();
```

---

### <a id="serializetojsonvalue"></a>SerializeToJsonValue
<p style='text-align:right'>버전 0.1.0에 추가 됨</p>

```csharp
public JsonValue SerializeToJsonValue ()
```

적응 카드를 json 값 개체로 serialize 합니다.

| Returns | |
| --- | --- |
| ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.JsonValue``` | |

#### <a name="sample"></a>샘플

```csharp
JsonValue value = parseResult.AdaptiveCard.SerializeToJsonValue();
```