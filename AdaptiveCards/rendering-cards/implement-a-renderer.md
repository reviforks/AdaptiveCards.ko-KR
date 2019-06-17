---
title: 렌더러 구현
author: matthidinger
ms.author: mahiding
ms.date: 09/15/2017
ms.topic: article
ms.openlocfilehash: b39493f82f3378e5a554abc6df890d6821869671
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67138026"
---
# <a name="adaptive-card-renderer-specification"></a><span data-ttu-id="c0e5c-102">Adaptive Card 렌더러 사양</span><span class="sxs-lookup"><span data-stu-id="c0e5c-102">Adaptive Card Renderer Specification</span></span>

<span data-ttu-id="c0e5c-103">다음 사양에 설명 모든 UI 플랫폼에서 Adaptive Card 렌더러를 구현 하는 방법을 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-103">The following specification describes how implement an Adaptive Card renderer on any UI platform.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="c0e5c-104">이 콘텐츠는 완료 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-104">This content is not finished yet.</span></span> <span data-ttu-id="c0e5c-105">잠시 후 확인해보세요.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-105">Check back shortly.</span></span>

## <a name="sdk-versioning"></a><span data-ttu-id="c0e5c-106">SDK 버전 관리</span><span class="sxs-lookup"><span data-stu-id="c0e5c-106">SDK Versioning</span></span>

1. <span data-ttu-id="c0e5c-107">SDK 주 및 부 버전 **SHOULD** 일치는 `schema` 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-107">The SDK major and minor version **SHOULD** match the `schema` version.</span></span> 
1. <span data-ttu-id="c0e5c-108">패치/build **SHOULD** 스키마 변경 되지 않은 렌더러 업데이트에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-108">Patch/build **SHOULD** be used for renderer updates that don't have schema changes.</span></span>

## <a name="parsing-json"></a><span data-ttu-id="c0e5c-109">JSON 구문 분석</span><span class="sxs-lookup"><span data-stu-id="c0e5c-109">Parsing JSON</span></span>

### <a name="error-conditions"></a><span data-ttu-id="c0e5c-110">오류 조건</span><span class="sxs-lookup"><span data-stu-id="c0e5c-110">Error conditions</span></span>
1. <span data-ttu-id="c0e5c-111">파서가 **해야** 유효한 JSON 콘텐츠가 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="c0e5c-111">A parser **MUST** check that it's valid JSON content</span></span>
1. <span data-ttu-id="c0e5c-112">파서가 **해야** 스키마 (필수 속성 등)에 대해 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="c0e5c-112">A parser **MUST** validate against the schema (required properties, etc)</span></span>
1. <span data-ttu-id="c0e5c-113">위의 오류 **해야** 호스트 앱 (예외 또는 이와 동등한)에 게 보고</span><span class="sxs-lookup"><span data-stu-id="c0e5c-113">The above errors **MUST** be reported to the host app (exception or equivalent)</span></span>

### <a name="unknown-types"></a><span data-ttu-id="c0e5c-114">알 수 없는 형식</span><span class="sxs-lookup"><span data-stu-id="c0e5c-114">Unknown types</span></span>
1. <span data-ttu-id="c0e5c-115">알 수 없는 "형식" 발생 하는 경우 이러한 **없어지면** 결과에서</span><span class="sxs-lookup"><span data-stu-id="c0e5c-115">If unknown "types" are encountered they **MUST BE DROPPED** from the result</span></span>
1. <span data-ttu-id="c0e5c-116">위에서 같이 페이로드의 영향 **SHOULD** 호스트 앱에는 경고로 보고</span><span class="sxs-lookup"><span data-stu-id="c0e5c-116">Any alterations of the payload (like above) **SHOULD** be reported as warnings to the host app</span></span>

### <a name="unknown-properties"></a><span data-ttu-id="c0e5c-117">알 수 없는 속성</span><span class="sxs-lookup"><span data-stu-id="c0e5c-117">Unknown properties</span></span>
1. <span data-ttu-id="c0e5c-118">파서가 **해야 합니다** 포함 **추가** 요소 속성</span><span class="sxs-lookup"><span data-stu-id="c0e5c-118">A parser **MUST** include **additional** properties on elements</span></span>

### <a name="additional-considerations"></a><span data-ttu-id="c0e5c-119">추가 고려 사항</span><span class="sxs-lookup"><span data-stu-id="c0e5c-119">Additional considerations</span></span>
1. <span data-ttu-id="c0e5c-120">`speak` 속성 SSML 태그를 포함할 수 있습니다 하 고 **해야** 로 지정 된 호스트 응용 프로그램에 반환할</span><span class="sxs-lookup"><span data-stu-id="c0e5c-120">The `speak` property may contain SSML markup and **MUST** be returned to the host app as-specified</span></span>

## <a name="parsing-host-config"></a><span data-ttu-id="c0e5c-121">호스트 구성 구문 분석</span><span class="sxs-lookup"><span data-stu-id="c0e5c-121">Parsing Host Config</span></span>
1. <span data-ttu-id="c0e5c-122">TODO</span><span class="sxs-lookup"><span data-stu-id="c0e5c-122">TODO</span></span>

## <a name="versioning"></a><span data-ttu-id="c0e5c-123">버전 관리</span><span class="sxs-lookup"><span data-stu-id="c0e5c-123">Versioning</span></span>

1. <span data-ttu-id="c0e5c-124">렌더러 **해야** 스키마의 특정 버전을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-124">A renderer **MUST** implement a particular version of the schema.</span></span> 
1. <span data-ttu-id="c0e5c-125">`AdaptiveCard` 생성자 **해야 합니다** 제공 된 `version` 현재 스키마 버전에 따라 기본 값 속성</span><span class="sxs-lookup"><span data-stu-id="c0e5c-125">The `AdaptiveCard` constructor **MUST** give the `version` property a default value based on the current schema version</span></span> 
1. <span data-ttu-id="c0e5c-126">렌더러를 발견 하는 경우는 `version` 속성에는 `AdaptiveCard` 지원 되는 버전 보다 높은 것 **해야 합니다** 반환는 `fallbackText` 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-126">If a renderer encounters a `version` property in the `AdaptiveCard` that is higher than the supported version, it **MUST** return the `fallbackText` instead.</span></span>

## <a name="rendering"></a><span data-ttu-id="c0e5c-127">렌더링</span><span class="sxs-lookup"><span data-stu-id="c0e5c-127">Rendering</span></span>

<span data-ttu-id="c0e5c-128">`AdaptiveCard` 이루어져를 `body` 고 `actions`입니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-128">An `AdaptiveCard` consists of a `body` and `actions`.</span></span> <span data-ttu-id="c0e5c-129">`body` 컬렉션인 `CardElement`의렌더러를 열거 하 고 순서 대로 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-129">The `body` is a collection of `CardElement`s that a renderer will enumerate and render in order.</span></span> 

1. <span data-ttu-id="c0e5c-130">요소당 **해야 합니다** 부모의 너비를 확장 (생각 `display: block` html에서).</span><span class="sxs-lookup"><span data-stu-id="c0e5c-130">Each Element **MUST** stretch to the width of its parent (think `display: block` in HTML).</span></span>
1. <span data-ttu-id="c0e5c-131">렌더러 **해야** , 알 수 없는 요소 형식을 무시 하 고 페이로드의 나머지 부분 렌더링을 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-131">A renderer **MUST** ignore unknown element types, and continue rendering the rest of the payload.</span></span>

### <a name="spacing-and-separators"></a><span data-ttu-id="c0e5c-132">간격 및 구분 기호</span><span class="sxs-lookup"><span data-stu-id="c0e5c-132">Spacing and Separators</span></span>

1. <span data-ttu-id="c0e5c-133">`spacing` 모든 요소에 대해 속성 사이의 공간 크기에 영향을 줍니다 합니다 **현재** 요소와 **BEFORE** 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-133">The `spacing` property on every element influences the amount of space between the **CURRENT** element and the one **BEFORE** it.</span></span>
1. <span data-ttu-id="c0e5c-134">간격 **만 해야** 있으면 실제로 앞에 요소를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-134">Spacing **MUST ONLY** apply when there actually is an element preceding it.</span></span> <span data-ttu-id="c0e5c-135">(예: 적용 되지 않습니다 배열에서 첫 번째 항목으로)</span><span class="sxs-lookup"><span data-stu-id="c0e5c-135">(E.g., won't apply to the first item in an array)</span></span>
1. <span data-ttu-id="c0e5c-136">렌더러 **해야 합니다** 에서 사용 하는 공간의 양을 조회를 `hostConfig` 현재 요소에 적용 되는 열거형 값에 대 한 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-136">A renderer **MUST** look up the amount of space to use from the `hostConfig` spacing for the enum value applied to the current element.</span></span>
1. <span data-ttu-id="c0e5c-137">요소에는 `separator` 값 `true`, 표시 줄 다음 **해야** 현재 요소 및 하기 전에 하나를 그릴 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-137">If the element has a `separator` value of `true`, then a visible line **MUST** be drawn between the current element and the one before it.</span></span>
1. <span data-ttu-id="c0e5c-138">구분선 **해야 합니다** 수를 사용 하 여는 `container.style.default.foregroundColor`합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-138">The separator line **MUST** be drawn using the `container.style.default.foregroundColor`.</span></span>
1. <span data-ttu-id="c0e5c-139">구분 기호 **만 해야** 경우 그릴 항목 **IS NOT** 배열의 첫 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-139">A separator **MUST ONLY** be drawn if the item **IS NOT** the first in the array.</span></span>

### <a name="columns"></a><span data-ttu-id="c0e5c-140">열</span><span class="sxs-lookup"><span data-stu-id="c0e5c-140">Columns</span></span>

1. <span data-ttu-id="c0e5c-141">`Column` `width` **해야** "auto", "stretch" 또는 중된 비율로 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-141">`Column` `width` **MUST** be interpreted by "auto", "stretch" or a weighted ratio.</span></span>

### <a name="textblock"></a><span data-ttu-id="c0e5c-142">TextBlock</span><span class="sxs-lookup"><span data-stu-id="c0e5c-142">TextBlock</span></span>

1. <span data-ttu-id="c0e5c-143">TextBlock **해야 합니다** 하지 않으면 한 줄을 차지 합니다 `wrap` 속성이 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-143">A TextBlock **MUST** take up a single line unless the `wrap` property is `true`.</span></span> 
1. <span data-ttu-id="c0e5c-144">텍스트 블록 **SHOULD** 줄임표 (...)를 사용 하 여 과도 한 모든 텍스트를 잘라내지</span><span class="sxs-lookup"><span data-stu-id="c0e5c-144">The text block **SHOULD** trim any excess text with an ellipsis (...)</span></span>

#### <a name="markdown"></a><span data-ttu-id="c0e5c-145">Markdown</span><span class="sxs-lookup"><span data-stu-id="c0e5c-145">Markdown</span></span>

1. <span data-ttu-id="c0e5c-146">Adaptive Card Markdown의 하위 집합을 허용 하 고 **SHOULD** 지원 `TextBlock`합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-146">Adaptive Cards allow for a subset of Markdown and **SHOULD** be supported in `TextBlock`.</span></span> 
1. <span data-ttu-id="c0e5c-147">전체 참조 [markdown 요구 사항](../authoring-cards/text-features.md)</span><span class="sxs-lookup"><span data-stu-id="c0e5c-147">See full [markdown requirements](../authoring-cards/text-features.md)</span></span>

#### <a name="formatting-functions"></a><span data-ttu-id="c0e5c-148">서식 지정 함수</span><span class="sxs-lookup"><span data-stu-id="c0e5c-148">Formatting functions</span></span>

1. <span data-ttu-id="c0e5c-149">`TextBlock` 허용 [날짜/시간 함수를 서식 지정](../authoring-cards/text-features.md) 하는 **해야** 모든 렌더러에서 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-149">`TextBlock` allows [DATE/TIME formatting functions](../authoring-cards/text-features.md) that **MUST** be supported on every renderer.</span></span>
1. <span data-ttu-id="c0e5c-150">**모든 실패 해야** 카드의 원시 문자열을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-150">**ALL FAILURES MUST** display the raw string in the card.</span></span> <span data-ttu-id="c0e5c-151">친숙 한 메시지를 시도 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-151">No friendly message attempted.</span></span> <span data-ttu-id="c0e5c-152">(개발자가 있는 즉시 인식할 수 있도록 되 목적은 문제)</span><span class="sxs-lookup"><span data-stu-id="c0e5c-152">(The goal being to make the developer immediately aware there is a problem)</span></span>

1. <span data-ttu-id="c0e5c-153">TODO: Regex를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-153">TODO: Include regex</span></span>

### <a name="images"></a><span data-ttu-id="c0e5c-154">이미지</span><span class="sxs-lookup"><span data-stu-id="c0e5c-154">Images</span></span>

1. <span data-ttu-id="c0e5c-155">렌더러 **SHOULD** 알고 있어야 모든 HTTP 이미지 다운로드 된 경우 앱을 호스트할 수 있도록 카드 "완벽 하 게 되 고"</span><span class="sxs-lookup"><span data-stu-id="c0e5c-155">A renderer **SHOULD** allow host apps to know when all HTTP images have been downloaded and the card is "fully rendered"</span></span>
1. <span data-ttu-id="c0e5c-156">렌더러 **해야 합니다** 호스트 구성 검사 `maxImageSize` HTTP 이미지를 다운로드 하는 경우 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c0e5c-156">A renderer **MUST** inspect the Host Config `maxImageSize` param when downloading HTTP images</span></span>
1. <span data-ttu-id="c0e5c-157">렌더러 **해야 합니다** 지원 `.png` 및 `.jpeg`</span><span class="sxs-lookup"><span data-stu-id="c0e5c-157">A renderer **MUST** support `.png` and `.jpeg`</span></span>
1. <span data-ttu-id="c0e5c-158">렌더러 **SHOULD** 지원 `.gif` 이미지</span><span class="sxs-lookup"><span data-stu-id="c0e5c-158">A renderer **SHOULD** support `.gif` images</span></span>

### <a name="host-config"></a><span data-ttu-id="c0e5c-159">호스트 구성</span><span class="sxs-lookup"><span data-stu-id="c0e5c-159">Host Config</span></span>

* <span data-ttu-id="c0e5c-160">TODO: 기본값은 무엇을 해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="c0e5c-160">TODO: What should the defaults be?</span></span> <span data-ttu-id="c0e5c-161">모두 공유 합니까?</span><span class="sxs-lookup"><span data-stu-id="c0e5c-161">Should they all share it?</span></span> <span data-ttu-id="c0e5c-162">일반적인 hostConfig.json 파일 이진 파일에 포함할 해야?</span><span class="sxs-lookup"><span data-stu-id="c0e5c-162">Should we embed a common hostConfig.json file in the binaries?</span></span>
* <span data-ttu-id="c0e5c-163">TODO: 생각해 HostConfig 구문 분석에 대해서는 물론 버전을 관리 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="c0e5c-163">TODO: I think HostConfig needs to be versioned as well for parsing?</span></span>

<span data-ttu-id="c0e5c-164">[`HostConfig`](host-config.md) 적응 카드 렌더러는 UI를 생성 하는 방법을 지정 하는 공유 구성 개체가입니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-164">[`HostConfig`](host-config.md) is a shared configuration object that specifies how an Adaptive Card Renderer generates UI.</span></span>  

<span data-ttu-id="c0e5c-165">이렇게 하면 다양 한 플랫폼 및 장치에서 렌더러를 공유할 수 있도록 플랫폼을 알 수 없는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-165">This allows properties which are platform agnostic to be shared among renderers on different platforms and devices.</span></span> <span data-ttu-id="c0e5c-166">또한 제공 하는 것이 카드는 모양과 느낌의 지정된 된 환경에 대 한 도구를를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-166">It also allows tooling to be created which gives you an idea of the look and feel that card would have for a given environment.</span></span>

1. <span data-ttu-id="c0e5c-167">렌더러 **해야 합니다** 노출 된 **호스트 구성** 앱을 호스트 하는 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c0e5c-167">Renderers **MUST** expose a **Host Config** parameter to host apps</span></span>
1. <span data-ttu-id="c0e5c-168">모든 요소가 **해야** 해당 하는 호스트 구성 설정에 따라 스타일을 지정할 수</span><span class="sxs-lookup"><span data-stu-id="c0e5c-168">All elements **MUST** be styled according to their respective Host Config settings</span></span>

### <a name="native-platform-styling"></a><span data-ttu-id="c0e5c-169">네이티브 플랫폼 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="c0e5c-169">Native platform styling</span></span>

1. <span data-ttu-id="c0e5c-170">각 요소 유형에 **SHOULD** 생성된 UI 요소를 사용 하 여 네이티브 플랫폼 스타일을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-170">Each element type **SHOULD** attach a native platform style with the generated UI element.</span></span> <span data-ttu-id="c0e5c-171">예를 들어 CSS 클래스의 요소 형식에 추가할에서는 html에서 및 XAML 특정 스타일을 할당.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-171">E.g., in HTML we added a CSS class to the element types, and in XAML we assign a specific Style.</span></span>

## <a name="extensibility"></a><span data-ttu-id="c0e5c-172">확장성</span><span class="sxs-lookup"><span data-stu-id="c0e5c-172">Extensibility</span></span> 

1. <span data-ttu-id="c0e5c-173">렌더러 **해야** 기본 요소 렌더러를 재정의 하려면 앱을 호스트할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-173">A renderer **MUST** allow host apps to override default element renderers.</span></span> <span data-ttu-id="c0e5c-174">예를 들어 대체 `TextBlock` 자체 논리를 사용 하 여 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-174">E.g., replace `TextBlock` rendering with their own logic.</span></span>
1. <span data-ttu-id="c0e5c-175">렌더러 **해야** 호스트 앱 사용자 지정 요소 유형이 등록을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-175">A renderer **MUST** allow host apps to register custom element types.</span></span> <span data-ttu-id="c0e5c-176">예를 들어, 사용자 지정에 대 한 지원을 추가 `Rating` 요소</span><span class="sxs-lookup"><span data-stu-id="c0e5c-176">E.g., add support for a custom `Rating` element</span></span>
1. <span data-ttu-id="c0e5c-177">렌더러 **해야** 기본 요소에 대 한 지원을 제거 하려면 앱을 호스트할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-177">A renderer **MUST** allow host apps to remove support for a default element.</span></span> <span data-ttu-id="c0e5c-178">예를 들어 제거 `Action.Submit` 지원 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-178">E.g., remove `Action.Submit` if they don't want it supported.</span></span>

## <a name="actions"></a><span data-ttu-id="c0e5c-179">동작</span><span class="sxs-lookup"><span data-stu-id="c0e5c-179">Actions</span></span>

1. <span data-ttu-id="c0e5c-180">경우 HostConfig `supportsInteractivity` 됩니다 `false`, 렌더러를 **MUST NOT** 모든 작업을 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-180">If HostConfig `supportsInteractivity` is `false`, a renderer **MUST NOT** render any actions.</span></span>
1. <span data-ttu-id="c0e5c-181">합니다 `actions` 속성 **해야** 카드의 맨 아래에서 일반적으로 작업 표시줄의 몇 가지 종류의 단추와 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-181">The `actions` property **MUST** be rendered as buttons in some kind of action bar, usually at the bottom of the card.</span></span> 
1. <span data-ttu-id="c0e5c-182">단추를 탭 할 때 그 **해야** 호스트 응용 프로그램에서 이벤트를 처리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-182">When a button is tapped it **MUST** allow the host app to handle the event.</span></span> 
1. <span data-ttu-id="c0e5c-183">이벤트 **해야** 작업과 연결 된 모든 속성을 따라 전달</span><span class="sxs-lookup"><span data-stu-id="c0e5c-183">The event **MUST** pass along all associated properties with the action</span></span>
1. <span data-ttu-id="c0e5c-184">이벤트 **해야 합니다** 전달 된 `AdaptiveCard` 실행 된는</span><span class="sxs-lookup"><span data-stu-id="c0e5c-184">The event **MUST** pass along the `AdaptiveCard` which was executed</span></span>

<span data-ttu-id="c0e5c-185">작업</span><span class="sxs-lookup"><span data-stu-id="c0e5c-185">Action</span></span> | <span data-ttu-id="c0e5c-186">동작</span><span class="sxs-lookup"><span data-stu-id="c0e5c-186">Behavior</span></span>
--- | ---
<span data-ttu-id="c0e5c-187">**Action.OpenUrl**</span><span class="sxs-lookup"><span data-stu-id="c0e5c-187">**Action.OpenUrl**</span></span> | <span data-ttu-id="c0e5c-188">보기에 대 한 외부 URL 열기</span><span class="sxs-lookup"><span data-stu-id="c0e5c-188">Open an external URL for viewing</span></span>
<span data-ttu-id="c0e5c-189">**Action.ShowCard**</span><span class="sxs-lookup"><span data-stu-id="c0e5c-189">**Action.ShowCard**</span></span> | <span data-ttu-id="c0e5c-190">사용자에 게 표시할 하위 카드를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-190">Requests a sub-card to be shown to the user.</span></span>
<span data-ttu-id="c0e5c-191">**Action.Submit**</span><span class="sxs-lookup"><span data-stu-id="c0e5c-191">**Action.Submit**</span></span> | <span data-ttu-id="c0e5c-192">호스트 응용 프로그램에서 정의 된 몇 가지 메서드를 통해 다음에 전송 되는 개체로 수집의 모든 입력된 요소에 대 한 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-192">Ask for all of the input elements to be gathered up into an object which is then sent to you through some method defined by the host application.</span></span>

### <a name="actionopenurl"></a><span data-ttu-id="c0e5c-193">Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="c0e5c-193">Action.OpenUrl</span></span>
1. <span data-ttu-id="c0e5c-194">`Action.OpenUrl` **해야** 네이티브 플랫폼 메커니즘을 사용 하는 URL 열기</span><span class="sxs-lookup"><span data-stu-id="c0e5c-194">`Action.OpenUrl` **SHOULD** open a URL using the native platform mechanism</span></span>
1. <span data-ttu-id="c0e5c-195">가능 하지 않은 경우 해당 **해야** URL을 열어 처리 호스트 앱으로 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-195">If this is not possible it **MUST** raise an event to the host app to handle opening the URL.</span></span> <span data-ttu-id="c0e5c-196">이 이벤트 **해야** 호스트 앱 기본 동작을 재정의 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-196">This event **MUST** allow the host app to override the default behavior.</span></span> <span data-ttu-id="c0e5c-197">예를 들어 수 있도록 자신의 앱 내에서 URL을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-197">E.g., let them open the URL within their own app.</span></span>

### <a name="actionshowcard"></a><span data-ttu-id="c0e5c-198">Action.ShowCard</span><span class="sxs-lookup"><span data-stu-id="c0e5c-198">Action.ShowCard</span></span>

1. <span data-ttu-id="c0e5c-199">`Action.ShowCard` **해야** hostConfig 설정에 따라 몇 가지 방식으로 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-199">`Action.ShowCard` **MUST** be supported in some way, based on the hostConfig setting.</span></span> <span data-ttu-id="c0e5c-200">두 가지 모드가 있습니다: 인라인 및 팝업 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-200">There are two modes: inline, and popup.</span></span> <span data-ttu-id="c0e5c-201">인라인 카드 **SHOULD** 카드 표시 여부를 자동으로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-201">Inline cards **SHOULD** toggle the card visibility automatically.</span></span> <span data-ttu-id="c0e5c-202">이벤트 팝업 모드로 **SHOULD** 호스트 응용 프로그램에서 어떤 방식으로든에서 카드를 표시 하려면 먼저 발생 시켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-202">In popup mode, an event **SHOULD** be fired to the host app to show the card in some way.</span></span>

### <a name="actionsubmit"></a><span data-ttu-id="c0e5c-203">Action.Submit</span><span class="sxs-lookup"><span data-stu-id="c0e5c-203">Action.Submit</span></span>

<span data-ttu-id="c0e5c-204">전송 작업을 HTML 양식 제출 처럼, "전송"을 확인 하려면 각 호스트 응용 프로그램에 의미를 그대로 Adaptive Card는 HTTP post에 HTML 일반적으로 트리거 한다는 점을 제외 하면 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-204">The Submit Action behaves like an HTML form submit, except that where HTML typically triggers an HTTP post, Adaptive Cards leaves it up to each host app to determine what "submit" means to them.</span></span> 

1. <span data-ttu-id="c0e5c-205">때이 **해야** 사용자가 호출 되는 동작 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-205">When this **MUST** raise an event the user taps the action invoked.</span></span>  
1. <span data-ttu-id="c0e5c-206">합니다 `data` 속성 **해야** 콜백 페이로드에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-206">The `data` property **MUST** be included in the callback payload.</span></span>
1. <span data-ttu-id="c0e5c-207">에 대 한 `Action.Submit`, 렌더러 **해야** 카드에 모든 입력을 수집 하 고 해당 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-207">For `Action.Submit`, a renderer **MUST** gather all inputs on the card and retrieve their values.</span></span> 

### <a name="selectaction"></a><span data-ttu-id="c0e5c-208">selectAction</span><span class="sxs-lookup"><span data-stu-id="c0e5c-208">selectAction</span></span>

1. <span data-ttu-id="c0e5c-209">하는 경우 호스트 구성 `supportedInteractivity` 됩니다 `false` 는 `selectAction` **MUST NOT** 터치 대상으로 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-209">If Host Config `supportedInteractivity` is `false` then a `selectAction` **MUST NOT** render as a touch target.</span></span>
1. <span data-ttu-id="c0e5c-210">`Image``ColumnSet`, 및 `Column` 제공을 `selectAction` 속성에는 **SHOULD** 사용자가 호출할 때, 예를 들어, 요소를 탭 하 여 실행할 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-210">`Image`, `ColumnSet`, and `Column` offer a `selectAction` property, which **SHOULD** be executed when the user invokes it, e.g., by tapping the element.</span></span>

## <a name="inputs"></a><span data-ttu-id="c0e5c-211">입력</span><span class="sxs-lookup"><span data-stu-id="c0e5c-211">Inputs</span></span>

1. <span data-ttu-id="c0e5c-212">경우 HostConfig `supportsInteractivity` 는 `false` 렌더러 **MUST NOT** 입력을 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-212">If HostConfig `supportsInteractivity` is `false` a renderer **MUST NOT** render any inputs.</span></span>
2. <span data-ttu-id="c0e5c-213">입력 **SHOULD** 가능한 가장 높은 정확도 사용 하 여 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-213">Inputs **SHOULD** render with the highest fidelity possible.</span></span> <span data-ttu-id="c0e5c-214">예를 들어를 `Input.Date` 날짜 선택 UI 스택을, 다음 렌더러에 대 수 없는 경우이 있지만 사용자에 게 제공 이상적으로 **해야** 표준 텍스트 상자를 렌더링으로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-214">For example, an `Input.Date` would ideally offer a date picker to a user, but if this isn't possible on your UI stack, then the renderer **MUST** fall back to rendering a standard text box.</span></span>
3. <span data-ttu-id="c0e5c-215">렌더러 **SHOULD** 표시는 `placeholderText` 가능한 경우</span><span class="sxs-lookup"><span data-stu-id="c0e5c-215">A renderer **SHOULD** display the `placeholderText` if possible</span></span>
4. <span data-ttu-id="c0e5c-216">렌더러 **아닙니다** 입력의 유효성 검사를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-216">A renderer **DOES NOT** have to implement validation of the input.</span></span> <span data-ttu-id="c0e5c-217">Adaptive Card 사용자 측에서 받은 데이터의 유효성을 검사 하려면 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-217">Users of Adaptive Cards must plan to validate any received data on their end.</span></span>
5. <span data-ttu-id="c0e5c-218">입력 값 바인딩 **해야** 는 적절히 이스케이프 되어야</span><span class="sxs-lookup"><span data-stu-id="c0e5c-218">Input value binding **MUST** be properly escaped</span></span>

6. <span data-ttu-id="c0e5c-219">개체 **해야** 다음과 같이 호스트 응용 프로그램에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-219">The object **MUST** be returned to the host app as follows:</span></span>

   <span data-ttu-id="c0e5c-220">에서는 없도록 입력된 유효성 검사의 모든 기능 adaptive card에 제대로 응답을 구문 분석 하려면 수신 파티에 달려 있으므로.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-220">We do not make any promises of input validation in adaptive cards, so it's up to the receiving party to properly parse the response.</span></span> <span data-ttu-id="c0e5c-221">예를 들어, "hello"는 Input.Number 반환할 수 있습니다 및를 준비 하는 데 필요한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-221">E.g., a Input.Number could return "hello" and they need to be prepared for that.</span></span>


## <a name="events"></a><span data-ttu-id="c0e5c-222">이벤트</span><span class="sxs-lookup"><span data-stu-id="c0e5c-222">Events</span></span>

1. <span data-ttu-id="c0e5c-223">렌더러 **SHOULD** 호스트 응용 프로그램에서 위치에 카드를 스크롤할 수 있도록 요소의 표시 유형을 변경 되었을 때 이벤트를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e5c-223">A renderer **SHOULD** fire an event when an element's visibility has changed, allowing the host app to scroll the card into position.</span></span>
