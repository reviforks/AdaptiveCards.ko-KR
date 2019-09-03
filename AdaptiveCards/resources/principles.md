---
title: 동기 부여 및 원칙
author: matthidinger
ms.author: mahiding
ms.date: 5/14/2018
ms.topic: article
ms.openlocfilehash: 78fe44463c4ddb832ba0cc72d456b6d21518bac4
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553155"
---
# <a name="motivations-and-principles"></a><span data-ttu-id="3a434-102">동기 부여 및 원칙</span><span class="sxs-lookup"><span data-stu-id="3a434-102">Motivations and Principles</span></span>

<span data-ttu-id="3a434-103">다음은 적응형 카드 형식의 개선을 관리하는 동기 부여 및 원칙입니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-103">Below are the motivations and principles govering the evolution of the Adaptive Card format.</span></span>

## <a name="motivations-behind-the-format"></a><span data-ttu-id="3a434-104">형식의 기반이 되는 동기 부여</span><span class="sxs-lookup"><span data-stu-id="3a434-104">Motivations behind the format</span></span>

<span data-ttu-id="3a434-105">2016년 초에 Outlook, Windows 및 Bot Framework 등 Microsoft의 여러 팀은 그들 모두가 매우 비슷한 어떤 것(“카드”)을 원하고 있고 각 팀이 자체 솔루션을 개별적으로 디자인하고 있다는 것을 인식하게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-105">In early 2016, several teams at Microsoft (including Outlook, Windows and the Bot Framework) came to the realization that they all wanted something extremely similar ("cards") and that each of them were designing their own solutions independently:</span></span>

- <span data-ttu-id="3a434-106">Windows에 자체 라이브 타일 및 알림 형식이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-106">Windows had its own Live Tiles and Notifications format</span></span>
-  <span data-ttu-id="3a434-107">Bot Framework는 개발자가 봇 메시지를 보낼 때 선택할 수 있는 미리 정의된 카드 템플릿 세트를 사용하고 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-107">The Bot framework was using a set of predefined card templates developers could choose from when sending Bot messages</span></span>
- <span data-ttu-id="3a434-108">Outlook이 실행 가능 메시지 기능에 고유한 MessageCard 형식을 사용하고 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-108">Outlook was using its own MessageCard format for its Actionable Messages feature</span></span>

<span data-ttu-id="3a434-109">동시에 LINE, FaceBook Messenger, Slack 등의 다른 플랫폼에서는 고유한 자체 “카드” 형식을 정의하고 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-109">At the same time, other platforms such as LINE, FaceBook Messenger, Slack and more were defining their own, proprietary "card" format.</span></span> <span data-ttu-id="3a434-110">따라서 일부 Microsoft 직원이 모여 다음과 같은 하나의 공개 카드 형식과 SDK 세트를 정의하는 작업을 시작했습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-110">So a few Microsoft employees gathered up and started an effort to define a single, open card format and a set of SDKs that:</span></span>

- <span data-ttu-id="3a434-111">호스트 간에 카드를 쉽게 교환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-111">Would facilitate the interchange of cards between hosts</span></span>
- <span data-ttu-id="3a434-112">각 호스트가 카드 스타일을 계속 제어할 수 있게 하여 시각적 일관성을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-112">Would allow each host to keep control over the styling of cards to ensure visual consistency</span></span>
- <span data-ttu-id="3a434-113">호스트 애플리케이션에서 바로 사용할 수 있는 SDK를 통해 최소한의 작업으로 손쉽게 카드를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-113">Would make it easy for a host application to display cards with minimum effort via ready-to-use SDKs</span></span>
- <span data-ttu-id="3a434-114">또한 타사에 가치를 제공하고 결국 업계에서 널리 채택됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-114">And that would also provide value to third parties and eventually get adopted widely by the industry</span></span>

## <a name="principles-governing-adaptive-cards"></a><span data-ttu-id="3a434-115">적응형 카드를 관리하는 원칙</span><span class="sxs-lookup"><span data-stu-id="3a434-115">Principles governing Adaptive Cards</span></span>

1.  <span data-ttu-id="3a434-116">**적응형 카드는 ‘단순’하고 ‘선언적인’ 카드 형식입니다.**  </span><span class="sxs-lookup"><span data-stu-id="3a434-116">**Adaptive Card is a _simple_ and _declarative_ card format**</span></span>

    1.  <span data-ttu-id="3a434-117">HTML 또는 XAML을 대신하는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-117">It is not meant as an HTML or XAML replacement/alternative</span></span>
    2.  <span data-ttu-id="3a434-118">적응형 카드에는 **“코드 숨김”이 없습니다**.</span><span class="sxs-lookup"><span data-stu-id="3a434-118">There is **no "code behind"** with Adaptive Cards</span></span>
        1. <span data-ttu-id="3a434-119">카드 작성자는 페이로드와 함께 사용자 지정/임의 코드를 포함할 수 없으므로, 적응형 카드 호스트는 타사 코드를 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-119">Card authors cannot embed custom/arbitrary code with their payloads, and as a result an Adaptive Card host never needs to run third party code</span></span>
        2. <span data-ttu-id="3a434-120">동적 특성과 대화형 작업은 선언적 태그를 통해서만 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-120">Dynamism and interactivity are achieved solely via declarative markup</span></span>
    3.  <span data-ttu-id="3a434-121">따라서 새 플랫폼용 적응형 카드 SDK를 빌드하는 데 필요한 작업이 합리적으로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-121">This ensures that the effort necessary to build an Adaptive Card SDK for a new platform remains reasonable</span></span>

2.  <span data-ttu-id="3a434-122">**적응형 카드 형식은 특정 기본 기술을 사용할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="3a434-122">**The Adaptive Card format can't impose the use of any particular underlying technology**</span></span>

    1.  <span data-ttu-id="3a434-123">적응형 카드 형식은 JavaScript, C#, Python 또는 기타 언어를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-123">The Adaptive Card format does not rely on JavaScript, C#, Python or any other language</span></span>
    2.  <span data-ttu-id="3a434-124">마찬가지로 HTML이나 XAML 또는 기타 그래픽 /UI 프레임워크를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-124">Similarly it doesn't rely on HTML or XAML or any other graphic/UI framework</span></span>
    3.  <span data-ttu-id="3a434-125">따라서 적응형 카드는 렌더러가 존재하는 한 플랫폼에서 기본적으로 렌더링될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-125">This way, Adaptive Cards can be rendered natively on any platform for as long as a renderer exists</span></span>

3.  <span data-ttu-id="3a434-126">**적응형 카드 형식은 ‘공유 속성’입니다.** </span><span class="sxs-lookup"><span data-stu-id="3a434-126">**The Adaptive Card format is a _shared property_**</span></span>

    1.  <span data-ttu-id="3a434-127">해당 SDK와 함께 형식은 오픈 소스 및 해당 개선 커뮤니티를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-127">Along with its SDKs, the format is to be open source and its evolution community driven</span></span>
    2.  <span data-ttu-id="3a434-128">따라서 형식은 한 팀에서 소유하지도 추진하지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-128">The format is therefore not owned nor driven by any one team</span></span>

4.  <span data-ttu-id="3a434-129">**적응형 카드 형식은 “Microsoft 전용”으로 디자인되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="3a434-129">**The Adaptive Card format is not designed "just for Microsoft's use"**</span></span>

    1.  <span data-ttu-id="3a434-130">오히려 매우 다양한 애플리케이션 및 사용 사례의 요구 사항에 맞게 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-130">Instead it is designed to suit the needs of a wide variety of applications and use cases</span></span>

5.  <span data-ttu-id="3a434-131">**‘적응형 카드 작업 그룹’은 형식 개선을 관리합니다.** </span><span class="sxs-lookup"><span data-stu-id="3a434-131">**The _Adaptive Card Working Group_ governs the evolution of the format**</span></span>

    1.  <span data-ttu-id="3a434-132">이 작업 그룹은 모두 형식의 성공에 깊이 관여하는 Microsoft 직원들로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-132">This working group is comprised of a set of Microsoft employees that are all deeply involved in the success of the format</span></span>
    2.  <span data-ttu-id="3a434-133">작업 그룹은 기능 제안을 검토하고, 열린 이슈를 논의 및 심사하고, vNext 작업 항목의 전체 진행 상황을 추적하는 주간 회의를 진행합니다(현재는 월요일에 진행).</span><span class="sxs-lookup"><span data-stu-id="3a434-133">The Working Group conducts weekly meetings (currently on Monday) during which feature proposals are reviewed, open issues are discussed and triaged and overall progress on vNext work items is tracked</span></span>
    3.  <span data-ttu-id="3a434-134">작업 그룹은 내부 Microsoft 팀을 포함한 전체적인 커뮤니티의 피드백을 사용하여 형식의 개선 방식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-134">The Working Group uses feedback from the community at large, including internal Microsoft teams, to decide how the format evolves</span></span>
        1. <span data-ttu-id="3a434-135">누구나 GitHub(아래 참조)에서 이슈를 열어 작업 그룹에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-135">Anyone can participate in the working group through opening issues in GitHub (see below)</span></span>
        2. <span data-ttu-id="3a434-136">적응형 카드 프레임워크의 실제 사용(호스트 또는 카드 작성자로서)을 기반으로 한 이슈/기능 요청이 향후 형식에 가장 많은 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-136">Issues/feature requests rooted in actual usage of the Adaptive Cards framework (either as a host or as a card author) have the most impact on the future of the format</span></span>
    4.  <span data-ttu-id="3a434-137">작업 그룹의 승인을 받으려면 제안된 기능이 다음을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-137">To be approved by the Working Group, proposed new features:</span></span>
        1. <span data-ttu-id="3a434-138">실제 사용 사례에서 증명되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-138">Must be justified by real life use cases</span></span>
        2. <span data-ttu-id="3a434-139">기능 사양을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-139">Must have a functional specification</span></span>
    5.  <span data-ttu-id="3a434-140">승인된 새로운 기능은 백로그에 추가되고 vNext에 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-140">Approved new feature are added to the backlog and considered for vNext</span></span>
        1. <span data-ttu-id="3a434-141">새로운 기능의 우선 순위를 지정하는 데 사용되는 기준에는 기능이 사용 가능한 시나리오 범위, 기능의 복잡성/유지 관리성 등이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-141">The criteria used to prioritize new features include the breadth of scenarios the feature enables, its complexity/maintainability and more</span></span>
        2. <span data-ttu-id="3a434-142">의문이 있다면 제외하세요.</span><span class="sxs-lookup"><span data-stu-id="3a434-142">When in doubt, keep it out!</span></span> <span data-ttu-id="3a434-143">실수를 영원히 포함하는 것보다는 잘 디자인된 기능을 나중에 도입하기가 훨씬 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-143">It's a lot easier to introduce a well designed feature later than to live with a mistake forever.</span></span>
    6.  <span data-ttu-id="3a434-144">모든 새로운 기능은 지원되는 모든 SDK에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-144">All new features are implemented in all supported SDKs</span></span>
    7.  <span data-ttu-id="3a434-145">모든 새로운 기능은 문서화되며 샘플 폴더에 게시된 테스트 카드와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-145">All new features are documented and associated with a test card published in the samples folder</span></span>
    8.  <span data-ttu-id="3a434-146">형식 및 SDK의 새 버전은 베타 단계를 거칩니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-146">New versions of the format and SDKs go through a beta phase</span></span>
    9.  <span data-ttu-id="3a434-147">적응형 카드 스키마 및 SDK 버전의 릴리스 일정은 날짜가 아닌 품질을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-147">The release schedule for Adaptive Card schema and SDK versions is driven by quality, not date</span></span>

6.  <span data-ttu-id="3a434-148">**상호 운용성**</span><span class="sxs-lookup"><span data-stu-id="3a434-148">**Interoperability**</span></span>
    1.  <span data-ttu-id="3a434-149">문서화된 형식에 따라 작성된 카드(예: 호스트별 확장을 사용하는 것이 아님)는 적응형 카드 가능 호스트에서 제대로 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-149">Cards authored in accordance with the documented format (e.g. not using any host-specific extensions) will render properly in any Adaptive Card-capable host</span></span>
    2.  <span data-ttu-id="3a434-150">이 원칙의 유일한 예외는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-150">The only exceptions to this principles are:</span></span>
        1.  <span data-ttu-id="3a434-151">일부 호스트에서는 대화형 작업을 허용하지 않으므로 입력 및 작업을 렌더링하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-151">Some hosts might not allow interactivity, and will therefore not render inputs nor actions</span></span>
        2.  <span data-ttu-id="3a434-152">Action.Submit 작업 실행은 호스트에 따라 달라지며 일부 호스트에서는 Action.Submit 페이로드를 제대로 처리하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-152">Execution of Action.Submit actions is at the discretion of the host, and not all hosts will necessarily properly handle all Action.Submit payloads.</span></span> <span data-ttu-id="3a434-153">또한 일부 호스트는 Action.Submit을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-153">Furthermore, some hosts might not support Action.Submit at all</span></span>

7.  <span data-ttu-id="3a434-154">**형식은 확장 가능해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3a434-154">**The format needs to be extensible**</span></span>

    1.  <span data-ttu-id="3a434-155">호스트는 형식이 수행할 수 있는 작업을 벗어나는 사용자 지정 요소나 사용자 지정 작업에 대한 지원을 자유롭게 추가할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-155">Hosts should have the freedom of adding support for custom elements or custom actions that go beyond what the format is capable of</span></span>
    2.  <span data-ttu-id="3a434-156">다양한 호스트가 동일한 작업 세트를 지원하지 않을 수 있으므로 작업의 경우 이 기능이 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-156">This is particularly important for actions, as various hosts don't necessarily support the same set of actions</span></span>
    3.  <span data-ttu-id="3a434-157">이 추가 기능은 호스트에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-157">These additions are at the discretion of the host</span></span>
        1. <span data-ttu-id="3a434-158">이는 적응형 카드 사양에 대한 ‘실질적인’ 추가 기능이 아닙니다. </span><span class="sxs-lookup"><span data-stu-id="3a434-158">They are not a *de facto* addition to the Adaptive Card specification</span></span>
        2. <span data-ttu-id="3a434-159">실제로 이 추가 기능은 일반 적응형 카드 형식과 호환되지 않는 추가 기능을 사용하는 페이로드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-159">As such, they make a payload that uses them incompatible with the mainstream Adaptive Card format</span></span>
        3. <span data-ttu-id="3a434-160">그러나 작업 그룹에 제공되며 5번 항목에 설명된 대로 향후 형식 버전의 새로운 기능으로 제안될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-160">They can however be presented to the Working Group and proposed as new features for a future version of the format, as described in point #5</span></span>

8.  <span data-ttu-id="3a434-161">**카드 작성자는 콘텐츠를 소유하고, 호스트 앱은 모양과 느낌을 소유합니다.**</span><span class="sxs-lookup"><span data-stu-id="3a434-161">**Card authors own the content, host apps own the look and feel**</span></span>

    1.  <span data-ttu-id="3a434-162">호스트 앱은 카드가 앱 환경의 네이티브 확장처럼 보이고 느껴지도록 스타일을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-162">Host apps impose their styling so cards look and feel like they are native extensions of the app's experience</span></span>
    2.  <span data-ttu-id="3a434-163">카드 작성자가 계속 스타일을 지정할 수 있지만 색, 크기 등의 의미 체계 식을 통해서만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-163">Card authors can still specify styling, but only via semantic expressions of colors, sizes, etc.</span></span>

9.  <span data-ttu-id="3a434-164">**가장 인기 있는 개발자 플랫폼용 SDK가 제공됩니다.**</span><span class="sxs-lookup"><span data-stu-id="3a434-164">**SDKs will be provided for the most popular developer platforms**</span></span>

    1.  <span data-ttu-id="3a434-165">SDK를 사용하면 모든 호스트에서 적응형 카드 페이로드를 쉽게 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-165">SDKs make it easy to render Adaptive Card payloads in any host</span></span>
    2.  <span data-ttu-id="3a434-166">이 덕분에 타사 개발자와 Microsoft 팀의 경우 모두 진입 장벽이 낮아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a434-166">This ensures the barrier to entry is as low as can be both for third party developers and Microsoft teams</span></span>
