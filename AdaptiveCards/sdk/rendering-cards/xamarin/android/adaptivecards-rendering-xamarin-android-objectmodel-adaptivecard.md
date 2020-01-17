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
# <a name="adaptivecard"></a><span data-ttu-id="cacb8-102">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="cacb8-102">AdaptiveCard</span></span>

```csharp
public class AdaptiveCard : Java.Lang.Object 
```

<span data-ttu-id="cacb8-103">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="cacb8-103">**Namespace**</span></span>

```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.ObjectModel
```

## <a name="summary"></a><span data-ttu-id="cacb8-104">요약</span><span class="sxs-lookup"><span data-stu-id="cacb8-104">Summary</span></span>

| <span data-ttu-id="cacb8-105">특성</span><span class="sxs-lookup"><span data-stu-id="cacb8-105">Attributes</span></span> | |
| ---- | --- |
| <span data-ttu-id="cacb8-106">조치</span><span class="sxs-lookup"><span data-stu-id="cacb8-106">Actions</span></span> | <span data-ttu-id="cacb8-107">카드의 작업 모음에 표시 되는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-107">The Actions to show in the card’s action bar.</span></span> |
| <span data-ttu-id="cacb8-108">BackgroundImage</span><span class="sxs-lookup"><span data-stu-id="cacb8-108">BackgroundImage</span></span> | <span data-ttu-id="cacb8-109">카드의 배경 이미지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-109">Specifies the background image of the card.</span></span> |
| <span data-ttu-id="cacb8-110">Body</span><span class="sxs-lookup"><span data-stu-id="cacb8-110">Body</span></span> | <span data-ttu-id="cacb8-111">기본 카드 지역에 표시할 카드 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-111">The card elements to show in the primary card region.</span></span> |
| <span data-ttu-id="cacb8-112">ElementType</span><span class="sxs-lookup"><span data-stu-id="cacb8-112">ElementType</span></span> | <span data-ttu-id="cacb8-113">"AdaptiveCard" 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-113">Must be "AdaptiveCard".</span></span> |
| <span data-ttu-id="cacb8-114">FallbackText</span><span class="sxs-lookup"><span data-stu-id="cacb8-114">FallbackText</span></span> | <span data-ttu-id="cacb8-115">클라이언트에서 지정 된 버전을 지원 하지 않을 때 표시 되는 텍스트입니다 (markdown 포함).</span><span class="sxs-lookup"><span data-stu-id="cacb8-115">Text shown when the client doesn’t support the version specified (may contain markdown).</span></span> |
| <span data-ttu-id="cacb8-116">높이</span><span class="sxs-lookup"><span data-stu-id="cacb8-116">Height</span></span> | |
| <span data-ttu-id="cacb8-117">InputNecessityIndicators</span><span class="sxs-lookup"><span data-stu-id="cacb8-117">InputNecessityIndicators</span></span> | |
| <span data-ttu-id="cacb8-118">언어</span><span class="sxs-lookup"><span data-stu-id="cacb8-118">Language</span></span> | <span data-ttu-id="cacb8-119">카드에 사용 되는 2 자로 된 ISO-639-1 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-119">The 2-letter ISO-639-1 language used in the card.</span></span> <span data-ttu-id="cacb8-120">모든 날짜/시간 함수를 지역화 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-120">Used to localize any date/time functions.</span></span> |
| <span data-ttu-id="cacb8-121">MinHeight</span><span class="sxs-lookup"><span data-stu-id="cacb8-121">MinHeight</span></span> | <span data-ttu-id="cacb8-122">카드의 최소 높이를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-122">Specifies the minimum height of the card.</span></span> |
| <span data-ttu-id="cacb8-123">SelectAction</span><span class="sxs-lookup"><span data-stu-id="cacb8-123">SelectAction</span></span> | <span data-ttu-id="cacb8-124">카드를 누르거나 선택할 때 호출 되는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-124">An Action that will be invoked when the card is tapped or selected.</span></span> <span data-ttu-id="cacb8-125">작업. ShowCard는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-125">Action.ShowCard is not supported.</span></span> |
| <span data-ttu-id="cacb8-126">Speak</span><span class="sxs-lookup"><span data-stu-id="cacb8-126">Speak</span></span> | <span data-ttu-id="cacb8-127">이 전체 카드에 대해 말할 항목을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-127">Specifies what should be spoken for this entire card.</span></span> <span data-ttu-id="cacb8-128">단순 텍스트 또는 SSML 조각입니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-128">This is simple text or SSML fragment.</span></span> |
| <span data-ttu-id="cacb8-129">스타일을</span><span class="sxs-lookup"><span data-stu-id="cacb8-129">Style</span></span> | |
| <span data-ttu-id="cacb8-130">Version</span><span class="sxs-lookup"><span data-stu-id="cacb8-130">Version</span></span> | <span data-ttu-id="cacb8-131">이 카드에 필요한 스키마 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-131">Schema version that this card requires.</span></span> <span data-ttu-id="cacb8-132">클라이언트가이 버전 보다 낮으면 fallbackText가 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-132">If a client is lower than this version, the fallbackText will be rendered.</span></span> <span data-ttu-id="cacb8-133">참고: 작업 내의 카드에는 버전이 필요 하지 않습니다. ShowCard.</span><span class="sxs-lookup"><span data-stu-id="cacb8-133">NOTE: Version is not required for cards within an Action.ShowCard.</span></span> <span data-ttu-id="cacb8-134">그러나 최상위 카드의 경우에는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-134">However, it is required for the top-level card.</span></span> |
| <span data-ttu-id="cacb8-135">System.windows.controls.control.verticalcontentalignment</span><span class="sxs-lookup"><span data-stu-id="cacb8-135">VerticalContentAlignment</span></span> | <span data-ttu-id="cacb8-136">컨테이너 내에서 콘텐츠를 세로로 정렬 하는 방법을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-136">Defines how the content should be aligned vertically within the container.</span></span> <span data-ttu-id="cacb8-137">고정 높이 카드 또는 minHeight 지정 된 카드만 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-137">Only relevant for fixed-height cards, or cards with a minHeight specified.</span></span> |

&nbsp;

<span data-ttu-id="cacb8-138">**Public 생성자**</span><span class="sxs-lookup"><span data-stu-id="cacb8-138">**Public Constructors**</span></span>

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
| <span data-ttu-id="cacb8-139">public 메서드</span><span class="sxs-lookup"><span data-stu-id="cacb8-139">Public methods</span></span> | |
| --- | ---- |
| ```static ParseResult``` | [```DeserializeFromString(string jsonString, string rendererVersion)```](#deserializefromstring0) |
| ```static ParseResult``` | [```DeserializeFromString(string jsonString, string rendererVersion, ParseContext context)```](#deserializefromstring1) |
| ```static AdaptiveCard``` | [```MakeFallbackTextCard(string fallbackText, string language, string speak)```](#makefallbacktextcard) |
| ```string``` | [```Serialize()```](#serialize) |
| ```JsonValue``` | [```SerializeToJsonValue()```](#serializetojsonvalue) |

&nbsp;
## <a name="public-constructors"></a><span data-ttu-id="cacb8-140">공용 생성자</span><span class="sxs-lookup"><span data-stu-id="cacb8-140">Public Constructors</span></span>
---

### <a id="ctor0"></a><span data-ttu-id="cacb8-141">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="cacb8-141">AdaptiveCard</span></span>
<p style='text-align:right'><span data-ttu-id="cacb8-142">버전 0.1에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="cacb8-142">Added in version 0.1</span></span></p>

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

| <span data-ttu-id="cacb8-143">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cacb8-143">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="cacb8-144">version</span><span class="sxs-lookup"><span data-stu-id="cacb8-144">version</span></span> | ```string``` |
| <span data-ttu-id="cacb8-145">fallbackText</span><span class="sxs-lookup"><span data-stu-id="cacb8-145">fallbackText</span></span> | ```string``` |
| <span data-ttu-id="cacb8-146">backgroundImage</span><span class="sxs-lookup"><span data-stu-id="cacb8-146">backgroundImage</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BackgroundImage``` |
| <span data-ttu-id="cacb8-147">스타일</span><span class="sxs-lookup"><span data-stu-id="cacb8-147">style</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ContainerStyle``` |
| <span data-ttu-id="cacb8-148">speak</span><span class="sxs-lookup"><span data-stu-id="cacb8-148">speak</span></span> | ```string``` |
| <span data-ttu-id="cacb8-149">language</span><span class="sxs-lookup"><span data-stu-id="cacb8-149">language</span></span> | ```string``` |
| <span data-ttu-id="cacb8-150">System.windows.controls.control.verticalcontentalignment</span><span class="sxs-lookup"><span data-stu-id="cacb8-150">verticalContentAlignment</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.VerticalContentAlignment``` |
| <span data-ttu-id="cacb8-151">height</span><span class="sxs-lookup"><span data-stu-id="cacb8-151">height</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HeightType``` |
| <span data-ttu-id="cacb8-152">minHeight</span><span class="sxs-lookup"><span data-stu-id="cacb8-152">minHeight</span></span> | ```long``` |

&nbsp;&nbsp;

### <a id="ctor1"></a><span data-ttu-id="cacb8-153">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="cacb8-153">AdaptiveCard</span></span>
<p style='text-align:right'><span data-ttu-id="cacb8-154">버전 0.1에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="cacb8-154">Added in version 0.1</span></span></p>

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

| <span data-ttu-id="cacb8-155">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cacb8-155">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="cacb8-156">version</span><span class="sxs-lookup"><span data-stu-id="cacb8-156">version</span></span> | ```string``` |
| <span data-ttu-id="cacb8-157">fallbackText</span><span class="sxs-lookup"><span data-stu-id="cacb8-157">fallbackText</span></span> | ```string``` |
| <span data-ttu-id="cacb8-158">backgroundImage</span><span class="sxs-lookup"><span data-stu-id="cacb8-158">backgroundImage</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BackgroundImage``` |
| <span data-ttu-id="cacb8-159">스타일</span><span class="sxs-lookup"><span data-stu-id="cacb8-159">style</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ContainerStyle``` |
| <span data-ttu-id="cacb8-160">speak</span><span class="sxs-lookup"><span data-stu-id="cacb8-160">speak</span></span> | ```string``` |
| <span data-ttu-id="cacb8-161">language</span><span class="sxs-lookup"><span data-stu-id="cacb8-161">language</span></span> | ```string``` |
| <span data-ttu-id="cacb8-162">System.windows.controls.control.verticalcontentalignment</span><span class="sxs-lookup"><span data-stu-id="cacb8-162">verticalContentAlignment</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.VerticalContentAlignment``` |
| <span data-ttu-id="cacb8-163">height</span><span class="sxs-lookup"><span data-stu-id="cacb8-163">height</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HeightType``` |
| <span data-ttu-id="cacb8-164">minHeight</span><span class="sxs-lookup"><span data-stu-id="cacb8-164">minHeight</span></span> | ```long``` |
| <span data-ttu-id="cacb8-165">본문</span><span class="sxs-lookup"><span data-stu-id="cacb8-165">body</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseCardElementVector``` |
| <span data-ttu-id="cacb8-166">작업</span><span class="sxs-lookup"><span data-stu-id="cacb8-166">actions</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseActionElementVector``` |

&nbsp;&nbsp;

### <a id="ctor2"></a><span data-ttu-id="cacb8-167">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="cacb8-167">AdaptiveCard</span></span>
<p style='text-align:right'><span data-ttu-id="cacb8-168">버전 0.1에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="cacb8-168">Added in version 0.1</span></span></p>

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

| <span data-ttu-id="cacb8-169">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cacb8-169">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="cacb8-170">version</span><span class="sxs-lookup"><span data-stu-id="cacb8-170">version</span></span> | ```string``` |
| <span data-ttu-id="cacb8-171">fallbackText</span><span class="sxs-lookup"><span data-stu-id="cacb8-171">fallbackText</span></span> | ```string``` |
| <span data-ttu-id="cacb8-172">backgroundImage</span><span class="sxs-lookup"><span data-stu-id="cacb8-172">backgroundImage</span></span> | ```string``` |
| <span data-ttu-id="cacb8-173">스타일</span><span class="sxs-lookup"><span data-stu-id="cacb8-173">style</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ContainerStyle``` |
| <span data-ttu-id="cacb8-174">speak</span><span class="sxs-lookup"><span data-stu-id="cacb8-174">speak</span></span> | ```string``` |
| <span data-ttu-id="cacb8-175">language</span><span class="sxs-lookup"><span data-stu-id="cacb8-175">language</span></span> | ```string``` |
| <span data-ttu-id="cacb8-176">System.windows.controls.control.verticalcontentalignment</span><span class="sxs-lookup"><span data-stu-id="cacb8-176">verticalContentAlignment</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.VerticalContentAlignment``` |
| <span data-ttu-id="cacb8-177">height</span><span class="sxs-lookup"><span data-stu-id="cacb8-177">height</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HeightType``` |
| <span data-ttu-id="cacb8-178">minHeight</span><span class="sxs-lookup"><span data-stu-id="cacb8-178">minHeight</span></span> | ```long``` |

&nbsp;&nbsp;

### <a id="ctor3"></a><span data-ttu-id="cacb8-179">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="cacb8-179">AdaptiveCard</span></span>
<p style='text-align:right'><span data-ttu-id="cacb8-180">버전 0.1에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="cacb8-180">Added in version 0.1</span></span></p>

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

| <span data-ttu-id="cacb8-181">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cacb8-181">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="cacb8-182">version</span><span class="sxs-lookup"><span data-stu-id="cacb8-182">version</span></span> | ```string``` |
| <span data-ttu-id="cacb8-183">fallbackText</span><span class="sxs-lookup"><span data-stu-id="cacb8-183">fallbackText</span></span> | ```string``` |
| <span data-ttu-id="cacb8-184">backgroundImage</span><span class="sxs-lookup"><span data-stu-id="cacb8-184">backgroundImage</span></span> | ```string``` |
| <span data-ttu-id="cacb8-185">스타일</span><span class="sxs-lookup"><span data-stu-id="cacb8-185">style</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ContainerStyle``` |
| <span data-ttu-id="cacb8-186">speak</span><span class="sxs-lookup"><span data-stu-id="cacb8-186">speak</span></span> | ```string``` |
| <span data-ttu-id="cacb8-187">language</span><span class="sxs-lookup"><span data-stu-id="cacb8-187">language</span></span> | ```string``` |
| <span data-ttu-id="cacb8-188">System.windows.controls.control.verticalcontentalignment</span><span class="sxs-lookup"><span data-stu-id="cacb8-188">verticalContentAlignment</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.VerticalContentAlignment``` |
| <span data-ttu-id="cacb8-189">height</span><span class="sxs-lookup"><span data-stu-id="cacb8-189">height</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HeightType``` |
| <span data-ttu-id="cacb8-190">minHeight</span><span class="sxs-lookup"><span data-stu-id="cacb8-190">minHeight</span></span> | ```long``` |
| <span data-ttu-id="cacb8-191">본문</span><span class="sxs-lookup"><span data-stu-id="cacb8-191">body</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseCardElementVector``` |
| <span data-ttu-id="cacb8-192">작업</span><span class="sxs-lookup"><span data-stu-id="cacb8-192">actions</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseActionElementVector``` |

&nbsp;

## <a name="public-methods"></a><span data-ttu-id="cacb8-193">공용 메서드</span><span class="sxs-lookup"><span data-stu-id="cacb8-193">Public Methods</span></span>
---
### <a id="deserializefromstring0"></a><span data-ttu-id="cacb8-194">DeserializeFromString</span><span class="sxs-lookup"><span data-stu-id="cacb8-194">DeserializeFromString</span></span>
<p style='text-align:right'><span data-ttu-id="cacb8-195">버전 0.1.0에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="cacb8-195">Added in version 0.1.0</span></span></p>

```csharp
public static ParseResult DeserializeFromString (string jsonString, string rendererVersion)
```

<span data-ttu-id="cacb8-196">지정 된 적응 카드를 지정 된 렌더러 버전에 대 한 json 문자열로 deserialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-196">Deserializes the given adaptive card as a json string for the specified renderer version.</span></span>

| <span data-ttu-id="cacb8-197">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cacb8-197">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="cacb8-198">jsonString</span><span class="sxs-lookup"><span data-stu-id="cacb8-198">jsonString</span></span> | ```string``` |
| <span data-ttu-id="cacb8-199">rendererVersion</span><span class="sxs-lookup"><span data-stu-id="cacb8-199">rendererVersion</span></span> | ```string``` |

| <span data-ttu-id="cacb8-200">Returns</span><span class="sxs-lookup"><span data-stu-id="cacb8-200">Returns</span></span> | |
| --- | --- |
| ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ParseResult``` | |

#### <a name="sample"></a><span data-ttu-id="cacb8-201">샘플</span><span class="sxs-lookup"><span data-stu-id="cacb8-201">Sample</span></span>

```csharp
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version);
```

--- 
### <a id="deserializefromstring1"></a><span data-ttu-id="cacb8-202">DeserializeFromString</span><span class="sxs-lookup"><span data-stu-id="cacb8-202">DeserializeFromString</span></span>
<p style='text-align:right'><span data-ttu-id="cacb8-203">버전 0.1.0에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="cacb8-203">Added in version 0.1.0</span></span></p>

```csharp
public static ParseResult DeserializeFromString(string jsonString, string rendererVersion, ParseContext context)
```

<span data-ttu-id="cacb8-204">사용자 지정 요소 구문 분석을 처리 하기 위해 [ParseContext]() 개체를 사용 하 여 지정 된 렌더러 버전에 대 한 json 문자열로 지정 된 적응 카드를 deserialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-204">Deserializes the given adaptive card as a json string for the specified renderer version using a [ParseContext]() object to handle custom element parsing.</span></span>

| <span data-ttu-id="cacb8-205">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cacb8-205">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="cacb8-206">jsonString</span><span class="sxs-lookup"><span data-stu-id="cacb8-206">jsonString</span></span> | ```string``` |
| <span data-ttu-id="cacb8-207">rendererVersion</span><span class="sxs-lookup"><span data-stu-id="cacb8-207">rendererVersion</span></span> | ```string``` |
| <span data-ttu-id="cacb8-208">컨텍스트</span><span class="sxs-lookup"><span data-stu-id="cacb8-208">context</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ParseContext``` |

| <span data-ttu-id="cacb8-209">Returns</span><span class="sxs-lookup"><span data-stu-id="cacb8-209">Returns</span></span> | |
| --- | --- |
| ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ParseResult``` | |

#### <a name="sample"></a><span data-ttu-id="cacb8-210">샘플</span><span class="sxs-lookup"><span data-stu-id="cacb8-210">Sample</span></span>

```csharp
ParseContext parseContext = new ParseContext(elementParserRegistration, actionParserRegistration);
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version, parseContext);
```

---

### <a id="makefallbacktextcard"></a><span data-ttu-id="cacb8-211">MakeFallbackTextCard</span><span class="sxs-lookup"><span data-stu-id="cacb8-211">MakeFallbackTextCard</span></span>
<p style='text-align:right'><span data-ttu-id="cacb8-212">버전 0.1.0에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="cacb8-212">Added in version 0.1.0</span></span></p>

```csharp
public static AdaptiveCard MakeFallbackTextCard (string fallbackText, string language, string speak)
```

<span data-ttu-id="cacb8-213">지정 된 적응 카드를 지정 된 렌더러 버전에 대 한 json 문자열로 deserialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-213">Deserializes the given adaptive card as a json string for the specified renderer version.</span></span>

| <span data-ttu-id="cacb8-214">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cacb8-214">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="cacb8-215">fallbackText</span><span class="sxs-lookup"><span data-stu-id="cacb8-215">fallbackText</span></span> | ```string``` |
| <span data-ttu-id="cacb8-216">language</span><span class="sxs-lookup"><span data-stu-id="cacb8-216">language</span></span> | ```string``` |
| <span data-ttu-id="cacb8-217">speak</span><span class="sxs-lookup"><span data-stu-id="cacb8-217">speak</span></span> | ```string``` |

| <span data-ttu-id="cacb8-218">Returns</span><span class="sxs-lookup"><span data-stu-id="cacb8-218">Returns</span></span> | |
| --- | --- |
| ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.AdaptiveCard``` | <span data-ttu-id="cacb8-219">Unrendereable 카드의 대체 텍스트를 포함 하는 적응 카드</span><span class="sxs-lookup"><span data-stu-id="cacb8-219">Adaptive card that contains the fallback text for an unrendereable card</span></span> |

#### <a name="sample"></a><span data-ttu-id="cacb8-220">샘플</span><span class="sxs-lookup"><span data-stu-id="cacb8-220">Sample</span></span>

```csharp
AdaptiveCard adaptiveCard = AdaptiveCard.MakeFallbackTextCard("This card failed to render", "es", "Unrendereable card");
```

---

### <a id="serialize"></a><span data-ttu-id="cacb8-221">스트림으로</span><span class="sxs-lookup"><span data-stu-id="cacb8-221">Serialize</span></span>
<p style='text-align:right'><span data-ttu-id="cacb8-222">버전 0.1.0에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="cacb8-222">Added in version 0.1.0</span></span></p>

```csharp
public string Serialize ()
```

<span data-ttu-id="cacb8-223">적응 카드를 json 문자열 형식으로 직렬화 합니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-223">Serializes the adaptive card into it's json string form.</span></span>

| <span data-ttu-id="cacb8-224">Returns</span><span class="sxs-lookup"><span data-stu-id="cacb8-224">Returns</span></span> | |
| --- | --- |
| ```string``` | <span data-ttu-id="cacb8-225">Json 문자열로 적응 카드</span><span class="sxs-lookup"><span data-stu-id="cacb8-225">Adaptive card as a json string</span></span> |

#### <a name="sample"></a><span data-ttu-id="cacb8-226">샘플</span><span class="sxs-lookup"><span data-stu-id="cacb8-226">Sample</span></span>

```csharp
string jsonString = parseResult.AdaptiveCard.Serialize();
```

---

### <a id="serializetojsonvalue"></a><span data-ttu-id="cacb8-227">SerializeToJsonValue</span><span class="sxs-lookup"><span data-stu-id="cacb8-227">SerializeToJsonValue</span></span>
<p style='text-align:right'><span data-ttu-id="cacb8-228">버전 0.1.0에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="cacb8-228">Added in version 0.1.0</span></span></p>

```csharp
public JsonValue SerializeToJsonValue ()
```

<span data-ttu-id="cacb8-229">적응 카드를 json 값 개체로 serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="cacb8-229">Serializes the adaptive card into a json value object.</span></span>

| <span data-ttu-id="cacb8-230">Returns</span><span class="sxs-lookup"><span data-stu-id="cacb8-230">Returns</span></span> | |
| --- | --- |
| ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.JsonValue``` | |

#### <a name="sample"></a><span data-ttu-id="cacb8-231">샘플</span><span class="sxs-lookup"><span data-stu-id="cacb8-231">Sample</span></span>

```csharp
JsonValue value = parseResult.AdaptiveCard.SerializeToJsonValue();
```