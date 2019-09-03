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
# <a name="adaptive-card-renderer-specification"></a><span data-ttu-id="d1c4f-102">적응형 카드 렌더러 사양</span><span class="sxs-lookup"><span data-stu-id="d1c4f-102">Adaptive Card Renderer Specification</span></span>

<span data-ttu-id="d1c4f-103">다음 사양은 모든 UI 플랫폼에서 적응형 카드 렌더러를 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-103">The following specification describes how implement an Adaptive Card renderer on any UI platform.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="d1c4f-104">이 콘텐츠는 아직 완료되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-104">This content is not finished yet.</span></span> <span data-ttu-id="d1c4f-105">곧 다시 확인해 보세요.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-105">Check back shortly.</span></span>

## <a name="sdk-versioning"></a><span data-ttu-id="d1c4f-106">SDK 버전 관리</span><span class="sxs-lookup"><span data-stu-id="d1c4f-106">SDK Versioning</span></span>

1. <span data-ttu-id="d1c4f-107">SDK 주 버전 및 부 버전은 `schema` 버전과 **일치해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-107">The SDK major and minor version **SHOULD** match the `schema` version.</span></span> 
1. <span data-ttu-id="d1c4f-108">패치/빌드는 스키마 변경 내용이 없는 렌더러 업데이트에 **사용해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-108">Patch/build **SHOULD** be used for renderer updates that don't have schema changes.</span></span>

## <a name="parsing-json"></a><span data-ttu-id="d1c4f-109">JSON 구문 분석</span><span class="sxs-lookup"><span data-stu-id="d1c4f-109">Parsing JSON</span></span>

### <a name="error-conditions"></a><span data-ttu-id="d1c4f-110">오류 조건</span><span class="sxs-lookup"><span data-stu-id="d1c4f-110">Error conditions</span></span>
1. <span data-ttu-id="d1c4f-111">파서는 유효한 JSON 콘텐츠인지 **확인해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-111">A parser **MUST** check that it's valid JSON content</span></span>
1. <span data-ttu-id="d1c4f-112">파서는 스키마(필수 속성 등)에 대해 **유효성을 검사해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-112">A parser **MUST** validate against the schema (required properties, etc)</span></span>
1. <span data-ttu-id="d1c4f-113">위의 오류는 호스트 앱에 **보고되어야 합니다**(예외 등).</span><span class="sxs-lookup"><span data-stu-id="d1c4f-113">The above errors **MUST** be reported to the host app (exception or equivalent)</span></span>

### <a name="unknown-types"></a><span data-ttu-id="d1c4f-114">알 수 없는 형식</span><span class="sxs-lookup"><span data-stu-id="d1c4f-114">Unknown types</span></span>
1. <span data-ttu-id="d1c4f-115">알 수 없는 “형식”이 발견되면 결과에서 **삭제되어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-115">If unknown "types" are encountered they **MUST BE DROPPED** from the result</span></span>
1. <span data-ttu-id="d1c4f-116">위와 같은 페이로드 변경은 호스트 앱에 경고로 **보고되어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-116">Any alterations of the payload (like above) **SHOULD** be reported as warnings to the host app</span></span>

### <a name="unknown-properties"></a><span data-ttu-id="d1c4f-117">알 수 없는 속성</span><span class="sxs-lookup"><span data-stu-id="d1c4f-117">Unknown properties</span></span>
1. <span data-ttu-id="d1c4f-118">파서는 요소에 대한 **추가** 속성을 **포함해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-118">A parser **MUST** include **additional** properties on elements</span></span>

### <a name="additional-considerations"></a><span data-ttu-id="d1c4f-119">추가 고려 사항</span><span class="sxs-lookup"><span data-stu-id="d1c4f-119">Additional considerations</span></span>
1. <span data-ttu-id="d1c4f-120">`speak` 속성은 SSML 태그를 포함할 수 있으며 지정된 대로 호스트 앱에 **반환되어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-120">The `speak` property may contain SSML markup and **MUST** be returned to the host app as-specified</span></span>

## <a name="parsing-host-config"></a><span data-ttu-id="d1c4f-121">호스트 구성 구문 분석</span><span class="sxs-lookup"><span data-stu-id="d1c4f-121">Parsing Host Config</span></span>
1. <span data-ttu-id="d1c4f-122">TODO</span><span class="sxs-lookup"><span data-stu-id="d1c4f-122">TODO</span></span>

## <a name="versioning"></a><span data-ttu-id="d1c4f-123">버전 관리</span><span class="sxs-lookup"><span data-stu-id="d1c4f-123">Versioning</span></span>

1. <span data-ttu-id="d1c4f-124">렌더러는 특정 스키마 버전을 **구현해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-124">A renderer **MUST** implement a particular version of the schema.</span></span> 
1. <span data-ttu-id="d1c4f-125">`AdaptiveCard` 생성자는 현재 스키마 버전에 따라 `version` 속성에 기본값을 **제공해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-125">The `AdaptiveCard` constructor **MUST** give the `version` property a default value based on the current schema version</span></span> 
1. <span data-ttu-id="d1c4f-126">렌더러는 지원되는 버전보다 높은 `version` 속성을 `AdaptiveCard`에서 발견하면 `fallbackText`을 대신 **반환해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-126">If a renderer encounters a `version` property in the `AdaptiveCard` that is higher than the supported version, it **MUST** return the `fallbackText` instead.</span></span>

## <a name="rendering"></a><span data-ttu-id="d1c4f-127">렌더링</span><span class="sxs-lookup"><span data-stu-id="d1c4f-127">Rendering</span></span>

<span data-ttu-id="d1c4f-128">`AdaptiveCard`는 `body` 및 `actions`로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-128">An `AdaptiveCard` consists of a `body` and `actions`.</span></span> <span data-ttu-id="d1c4f-129">`body`는 렌더러가 순서대로 열거 및 렌더링할 `CardElement`의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-129">The `body` is a collection of `CardElement`s that a renderer will enumerate and render in order.</span></span> 

1. <span data-ttu-id="d1c4f-130">각 요소는 부모의 너비까지 **확장되어야 합니다**(HTML에서는 `display: block` 고려).</span><span class="sxs-lookup"><span data-stu-id="d1c4f-130">Each Element **MUST** stretch to the width of its parent (think `display: block` in HTML).</span></span>
1. <span data-ttu-id="d1c4f-131">렌더러는 알 수 없는 요소 형식을 무시하고 나머지 페이로드 렌더링을 계속**해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-131">A renderer **MUST** ignore unknown element types, and continue rendering the rest of the payload.</span></span>

### <a name="spacing-and-separators"></a><span data-ttu-id="d1c4f-132">간격 및 구분 기호</span><span class="sxs-lookup"><span data-stu-id="d1c4f-132">Spacing and Separators</span></span>

1. <span data-ttu-id="d1c4f-133">모든 요소의 `spacing` 속성은 **현재** 요소와 그 **앞의** 요소 사이에 있는 간격의 크기에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-133">The `spacing` property on every element influences the amount of space between the **CURRENT** element and the one **BEFORE** it.</span></span>
1. <span data-ttu-id="d1c4f-134">간격은 실제로 그 앞에 요소가 있는 경우**에만 적용되어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-134">Spacing **MUST ONLY** apply when there actually is an element preceding it.</span></span> <span data-ttu-id="d1c4f-135">(예: 배열의 첫 번째 항목에는 적용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="d1c4f-135">(E.g., won't apply to the first item in an array)</span></span>
1. <span data-ttu-id="d1c4f-136">렌더러는 현재 요소에 적용된 열거형 값에 대해 `hostConfig` 간격부터 사용할 간격의 크기를 **조회해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-136">A renderer **MUST** look up the amount of space to use from the `hostConfig` spacing for the enum value applied to the current element.</span></span>
1. <span data-ttu-id="d1c4f-137">요소의 `separator` 값이 `true`이면 현재 요소와 그 앞의 요소 사이에 표시되는 선이 **그려져야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-137">If the element has a `separator` value of `true`, then a visible line **MUST** be drawn between the current element and the one before it.</span></span>
1. <span data-ttu-id="d1c4f-138">구분선은 `container.style.default.foregroundColor`를 사용하여 **그려야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-138">The separator line **MUST** be drawn using the `container.style.default.foregroundColor`.</span></span>
1. <span data-ttu-id="d1c4f-139">항목이 배열의 첫 번째 항목이 **아닌** 경우에만 구분 기호를 **그려야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-139">A separator **MUST ONLY** be drawn if the item **IS NOT** the first in the array.</span></span>

### <a name="columns"></a><span data-ttu-id="d1c4f-140">열</span><span class="sxs-lookup"><span data-stu-id="d1c4f-140">Columns</span></span>

1. <span data-ttu-id="d1c4f-141">`Column` `width`는 “자동”, “확장” 또는 가중 비율로 **해석되어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-141">`Column` `width` **MUST** be interpreted by "auto", "stretch" or a weighted ratio.</span></span>

### <a name="textblock"></a><span data-ttu-id="d1c4f-142">TextBlock</span><span class="sxs-lookup"><span data-stu-id="d1c4f-142">TextBlock</span></span>

1. <span data-ttu-id="d1c4f-143">`wrap` 속성이 `true`가 아니라면 TextBlock은 한 줄을 **사용해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-143">A TextBlock **MUST** take up a single line unless the `wrap` property is `true`.</span></span> 
1. <span data-ttu-id="d1c4f-144">텍스트 블록은 줄임표(...)를 사용하여 초과 텍스트를 **잘라야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-144">The text block **SHOULD** trim any excess text with an ellipsis (...)</span></span>

#### <a name="markdown"></a><span data-ttu-id="d1c4f-145">Markdown</span><span class="sxs-lookup"><span data-stu-id="d1c4f-145">Markdown</span></span>

1. <span data-ttu-id="d1c4f-146">적응형 카드는 Markdown의 하위 집합을 허용하며 `TextBlock`에서 **지원되어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-146">Adaptive Cards allow for a subset of Markdown and **SHOULD** be supported in `TextBlock`.</span></span> 
1. <span data-ttu-id="d1c4f-147">전체 [markdown 요구 사항](../authoring-cards/text-features.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-147">See full [markdown requirements](../authoring-cards/text-features.md)</span></span>

#### <a name="formatting-functions"></a><span data-ttu-id="d1c4f-148">형식 지정 함수</span><span class="sxs-lookup"><span data-stu-id="d1c4f-148">Formatting functions</span></span>

1. <span data-ttu-id="d1c4f-149">`TextBlock`은 모든 렌더러에서 **지원되어야 하는** [날짜/시간 형식 지정 함수](../authoring-cards/text-features.md)를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-149">`TextBlock` allows [DATE/TIME formatting functions](../authoring-cards/text-features.md) that **MUST** be supported on every renderer.</span></span>
1. <span data-ttu-id="d1c4f-150">**모든 오류는 카드에 원시 문자열을 표시해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-150">**ALL FAILURES MUST** display the raw string in the card.</span></span> <span data-ttu-id="d1c4f-151">친숙한 메시지가 시도되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-151">No friendly message attempted.</span></span> <span data-ttu-id="d1c4f-152">(목표는 개발자가 문제가 있음을 즉시 인식하도록 하는 것임)</span><span class="sxs-lookup"><span data-stu-id="d1c4f-152">(The goal being to make the developer immediately aware there is a problem)</span></span>

1. <span data-ttu-id="d1c4f-153">TODO: regex 포함</span><span class="sxs-lookup"><span data-stu-id="d1c4f-153">TODO: Include regex</span></span>

### <a name="images"></a><span data-ttu-id="d1c4f-154">이미지</span><span class="sxs-lookup"><span data-stu-id="d1c4f-154">Images</span></span>

1. <span data-ttu-id="d1c4f-155">렌더러는 모든 HTTP 이미지가 다운로드되고 카드가 “완전히 렌더링”될 때 호스트 앱에 이를 알릴 수 **있어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-155">A renderer **SHOULD** allow host apps to know when all HTTP images have been downloaded and the card is "fully rendered"</span></span>
1. <span data-ttu-id="d1c4f-156">렌더러는 HTTP 이미지를 다운로드할 때 호스트 구성 `maxImageSize` 매개 변수를 **검사해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-156">A renderer **MUST** inspect the Host Config `maxImageSize` param when downloading HTTP images</span></span>
1. <span data-ttu-id="d1c4f-157">렌더러는 `.png` 및 `.jpeg`를 **지원해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-157">A renderer **MUST** support `.png` and `.jpeg`</span></span>
1. <span data-ttu-id="d1c4f-158">렌더러는 `.gif` 이미지를 **지원해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-158">A renderer **SHOULD** support `.gif` images</span></span>

### <a name="host-config"></a><span data-ttu-id="d1c4f-159">호스트 구성</span><span class="sxs-lookup"><span data-stu-id="d1c4f-159">Host Config</span></span>

* <span data-ttu-id="d1c4f-160">TODO: 기본값은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="d1c4f-160">TODO: What should the defaults be?</span></span> <span data-ttu-id="d1c4f-161">모두 기본값을 공유해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="d1c4f-161">Should they all share it?</span></span> <span data-ttu-id="d1c4f-162">일반적인 hostConfig.json 파일을 이진 파일에 포함해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="d1c4f-162">Should we embed a common hostConfig.json file in the binaries?</span></span>
* <span data-ttu-id="d1c4f-163">TODO: 구문 분석을 위해 HostConfig의 버전을 관리해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="d1c4f-163">TODO: I think HostConfig needs to be versioned as well for parsing?</span></span>

<span data-ttu-id="d1c4f-164">[`HostConfig`](host-config.md)는 적응형 카드 렌더러가 UI를 생성하는 방법을 지정하는 공유 구성 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-164">[`HostConfig`](host-config.md) is a shared configuration object that specifies how an Adaptive Card Renderer generates UI.</span></span>  

<span data-ttu-id="d1c4f-165">이를 사용하면 플랫폼에 독립적인 속성을 다양한 플랫폼 및 디바이스의 렌더러 간에 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-165">This allows properties which are platform agnostic to be shared among renderers on different platforms and devices.</span></span> <span data-ttu-id="d1c4f-166">특정 환경에 대한 카드의 모양과 느낌에 대한 아이디어를 제공하는 도구를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-166">It also allows tooling to be created which gives you an idea of the look and feel that card would have for a given environment.</span></span>

1. <span data-ttu-id="d1c4f-167">렌더러는 호스트 앱에 **호스트 구성** 매개 변수를 **공개해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-167">Renderers **MUST** expose a **Host Config** parameter to host apps</span></span>
1. <span data-ttu-id="d1c4f-168">모든 요소는 각 호스트 구성 설정에 따라 스타일을 **지정해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-168">All elements **MUST** be styled according to their respective Host Config settings</span></span>

### <a name="native-platform-styling"></a><span data-ttu-id="d1c4f-169">네이티브 플랫폼 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="d1c4f-169">Native platform styling</span></span>

1. <span data-ttu-id="d1c4f-170">각 요소 형식은 네이티브 플랫폼 스타일을 생성된 UI 요소와 **연결해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-170">Each element type **SHOULD** attach a native platform style with the generated UI element.</span></span> <span data-ttu-id="d1c4f-171">예를 들어 HTML에서는 CSS 클래스를 요소 형식에 추가하고 XAML에서는 특정 스타일을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-171">E.g., in HTML we added a CSS class to the element types, and in XAML we assign a specific Style.</span></span>

## <a name="extensibility"></a><span data-ttu-id="d1c4f-172">확장성</span><span class="sxs-lookup"><span data-stu-id="d1c4f-172">Extensibility</span></span> 

1. <span data-ttu-id="d1c4f-173">렌더러는 호스트 앱이 기본 요소 렌더러를 재정의할 수 있도록 **해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-173">A renderer **MUST** allow host apps to override default element renderers.</span></span> <span data-ttu-id="d1c4f-174">예를 들어 `TextBlock` 렌더링을 자체 논리로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-174">E.g., replace `TextBlock` rendering with their own logic.</span></span>
1. <span data-ttu-id="d1c4f-175">렌더러는 호스트 앱이 사용자 지정 요소 형식을 등록할 수 있도록 **해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-175">A renderer **MUST** allow host apps to register custom element types.</span></span> <span data-ttu-id="d1c4f-176">예를 들어 사용자 지정 `Rating` 요소의 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-176">E.g., add support for a custom `Rating` element</span></span>
1. <span data-ttu-id="d1c4f-177">렌더러는 호스트 앱이 기본 요소의 지원을 제거할 수 있도록 **해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-177">A renderer **MUST** allow host apps to remove support for a default element.</span></span> <span data-ttu-id="d1c4f-178">예를 들어 지원되지 않게 하려면 `Action.Submit`을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-178">E.g., remove `Action.Submit` if they don't want it supported.</span></span>

## <a name="actions"></a><span data-ttu-id="d1c4f-179">조치</span><span class="sxs-lookup"><span data-stu-id="d1c4f-179">Actions</span></span>

1. <span data-ttu-id="d1c4f-180">HostConfig `supportsInteractivity`가 `false`인 경우 렌더러는 작업을 렌더링하지 **않아야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-180">If HostConfig `supportsInteractivity` is `false`, a renderer **MUST NOT** render any actions.</span></span>
1. <span data-ttu-id="d1c4f-181">`actions` 속성은 일반적으로 카드 아래쪽에 있는 일종의 작업 모음에서 단추로 **렌더링되어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-181">The `actions` property **MUST** be rendered as buttons in some kind of action bar, usually at the bottom of the card.</span></span> 
1. <span data-ttu-id="d1c4f-182">단추를 탭하면 호스트 앱이 이벤트를 처리할 수 있도록 **해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-182">When a button is tapped it **MUST** allow the host app to handle the event.</span></span> 
1. <span data-ttu-id="d1c4f-183">이벤트는 작업을 통해 모든 연결된 속성을 따라 **전달되어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-183">The event **MUST** pass along all associated properties with the action</span></span>
1. <span data-ttu-id="d1c4f-184">이벤트는 실행된 `AdaptiveCard`를 따라 **전달되어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-184">The event **MUST** pass along the `AdaptiveCard` which was executed</span></span>

<span data-ttu-id="d1c4f-185">작업</span><span class="sxs-lookup"><span data-stu-id="d1c4f-185">Action</span></span> | <span data-ttu-id="d1c4f-186">동작</span><span class="sxs-lookup"><span data-stu-id="d1c4f-186">Behavior</span></span>
--- | ---
<span data-ttu-id="d1c4f-187">**Action.OpenUrl**</span><span class="sxs-lookup"><span data-stu-id="d1c4f-187">**Action.OpenUrl**</span></span> | <span data-ttu-id="d1c4f-188">보려는 외부 URL을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-188">Open an external URL for viewing</span></span>
<span data-ttu-id="d1c4f-189">**Action.ShowCard**</span><span class="sxs-lookup"><span data-stu-id="d1c4f-189">**Action.ShowCard**</span></span> | <span data-ttu-id="d1c4f-190">사용자에게 표시될 하위 카드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-190">Requests a sub-card to be shown to the user.</span></span>
<span data-ttu-id="d1c4f-191">**Action.Submit**</span><span class="sxs-lookup"><span data-stu-id="d1c4f-191">**Action.Submit**</span></span> | <span data-ttu-id="d1c4f-192">모든 입력 요소를 하나의 개체로 합친 후 호스트 애플리케이션이 정의한 일부 메서드를 통해 사용자에게 전송하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-192">Ask for all of the input elements to be gathered up into an object which is then sent to you through some method defined by the host application.</span></span>

### <a name="actionopenurl"></a><span data-ttu-id="d1c4f-193">Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="d1c4f-193">Action.OpenUrl</span></span>
1. <span data-ttu-id="d1c4f-194">`Action.OpenUrl`은 네이티브 플랫폼 메커니즘을 사용하여 URL을 **열어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-194">`Action.OpenUrl` **SHOULD** open a URL using the native platform mechanism</span></span>
1. <span data-ttu-id="d1c4f-195">열 수 없는 경우에는 호스트 앱이 URL 열기를 처리하도록 이벤트를 **발생시켜야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-195">If this is not possible it **MUST** raise an event to the host app to handle opening the URL.</span></span> <span data-ttu-id="d1c4f-196">이 이벤트는 호스트 앱이 기본 동작을 재정의할 수 있도록 **해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-196">This event **MUST** allow the host app to override the default behavior.</span></span> <span data-ttu-id="d1c4f-197">예를 들어 고유한 앱 내에서 URL을 열도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-197">E.g., let them open the URL within their own app.</span></span>

### <a name="actionshowcard"></a><span data-ttu-id="d1c4f-198">Action.ShowCard</span><span class="sxs-lookup"><span data-stu-id="d1c4f-198">Action.ShowCard</span></span>

1. <span data-ttu-id="d1c4f-199">`Action.ShowCard`는 hostConfig 설정에 따라 어떤 방법으로든 **지원되어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-199">`Action.ShowCard` **MUST** be supported in some way, based on the hostConfig setting.</span></span> <span data-ttu-id="d1c4f-200">인라인 및 팝업 모드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-200">There are two modes: inline, and popup.</span></span> <span data-ttu-id="d1c4f-201">인라인 카드는 카드 표시 여부를 자동으로 **전환해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-201">Inline cards **SHOULD** toggle the card visibility automatically.</span></span> <span data-ttu-id="d1c4f-202">팝업 모드에서는 어떤 방법으로든 호스트 앱이 카드를 표시하도록 이벤트를 **실행해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-202">In popup mode, an event **SHOULD** be fired to the host app to show the card in some way.</span></span>

### <a name="actionsubmit"></a><span data-ttu-id="d1c4f-203">Action.Submit</span><span class="sxs-lookup"><span data-stu-id="d1c4f-203">Action.Submit</span></span>

<span data-ttu-id="d1c4f-204">제출 작업은 HTML 양식 제출과 비슷하게 동작합니다. 단, 일반적으로 HTML이 HTTP 게시물을 트리거하는 경우, 적응형 카드는 각 호스트 앱이 “제출”의 의미를 결정하도록 한다는 점만 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-204">The Submit Action behaves like an HTML form submit, except that where HTML typically triggers an HTTP post, Adaptive Cards leaves it up to each host app to determine what "submit" means to them.</span></span> 

1. <span data-ttu-id="d1c4f-205">이 작업이 이벤트를 **발생시켜야 하는** 경우 사용자는 호출되는 작업을 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-205">When this **MUST** raise an event the user taps the action invoked.</span></span>  
1. <span data-ttu-id="d1c4f-206">`data` 속성은 콜백 페이로드에 **포함되어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-206">The `data` property **MUST** be included in the callback payload.</span></span>
1. <span data-ttu-id="d1c4f-207">`Action.Submit`의 경우 렌더러는 카드에서 모든 입력을 수집하고 해당 값을 검색**해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-207">For `Action.Submit`, a renderer **MUST** gather all inputs on the card and retrieve their values.</span></span> 

### <a name="selectaction"></a><span data-ttu-id="d1c4f-208">selectAction</span><span class="sxs-lookup"><span data-stu-id="d1c4f-208">selectAction</span></span>

1. <span data-ttu-id="d1c4f-209">호스트 구성 `supportedInteractivity`가 `false`이면 `selectAction`은 터치 대상으로 **렌더링되지 않아야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-209">If Host Config `supportedInteractivity` is `false` then a `selectAction` **MUST NOT** render as a touch target.</span></span>
1. <span data-ttu-id="d1c4f-210">`Image`, `ColumnSet` 및 `Column`은 요소를 탭하는 등의 작업으로 사용자가 호출할 때 **실행되어야 하는** `selectAction` 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-210">`Image`, `ColumnSet`, and `Column` offer a `selectAction` property, which **SHOULD** be executed when the user invokes it, e.g., by tapping the element.</span></span>

## <a name="inputs"></a><span data-ttu-id="d1c4f-211">입력</span><span class="sxs-lookup"><span data-stu-id="d1c4f-211">Inputs</span></span>

1. <span data-ttu-id="d1c4f-212">HostConfig `supportsInteractivity`가 `false`인 경우 렌더러는 입력을 렌더링하지 **않아야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-212">If HostConfig `supportsInteractivity` is `false` a renderer **MUST NOT** render any inputs.</span></span>
2. <span data-ttu-id="d1c4f-213">입력은 가능한 최고 정밀도로 **렌더링되어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-213">Inputs **SHOULD** render with the highest fidelity possible.</span></span> <span data-ttu-id="d1c4f-214">예를 들어 `Input.Date`는 사용자에게 날짜 선택기를 제공하지만, UI 스택에서 제공할 수 없는 경우 렌더러는 표준 텍스트 상자 렌더링으로 **대체되어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-214">For example, an `Input.Date` would ideally offer a date picker to a user, but if this isn't possible on your UI stack, then the renderer **MUST** fall back to rendering a standard text box.</span></span>
3. <span data-ttu-id="d1c4f-215">렌더러는 가능한 경우 `placeholderText`를 **표시해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-215">A renderer **SHOULD** display the `placeholderText` if possible</span></span>
4. <span data-ttu-id="d1c4f-216">렌더러는 입력의 유효성 검사를 구현할 필요가 **없습니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-216">A renderer **DOES NOT** have to implement validation of the input.</span></span> <span data-ttu-id="d1c4f-217">적응형 카드의 사용자는 사용자 쪽에서 수신된 모든 데이터의 유효성을 검사할 계획을 세워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-217">Users of Adaptive Cards must plan to validate any received data on their end.</span></span>
5. <span data-ttu-id="d1c4f-218">입력 값 바인딩은 적절하게 **이스케이프되어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-218">Input value binding **MUST** be properly escaped</span></span>

6. <span data-ttu-id="d1c4f-219">개체는 다음과 같이 호스트 앱에 **반환되어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-219">The object **MUST** be returned to the host app as follows:</span></span>

   <span data-ttu-id="d1c4f-220">적응형 카드에서 입력 유효성 검사를 약속하지 않으므로 수신 당사자가 응답을 제대로 구문 분석해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-220">We do not make any promises of input validation in adaptive cards, so it's up to the receiving party to properly parse the response.</span></span> <span data-ttu-id="d1c4f-221">예를 들어 Input.Number는 “hello”를 반환할 수 있으며 수신 당사자가 이를 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-221">E.g., a Input.Number could return "hello" and they need to be prepared for that.</span></span>


## <a name="events"></a><span data-ttu-id="d1c4f-222">이벤트</span><span class="sxs-lookup"><span data-stu-id="d1c4f-222">Events</span></span>

1. <span data-ttu-id="d1c4f-223">렌더러는 요소의 표시 여부가 변경될 때 이벤트를 실행하여 호스트 앱이 카드를 제 위치로 스크롤할 수 있도록 **해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="d1c4f-223">A renderer **SHOULD** fire an event when an element's visibility has changed, allowing the host app to scroll the card into position.</span></span>
