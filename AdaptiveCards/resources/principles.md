---
title: 동기 및 원칙
author: matthidinger
ms.author: mahiding
ms.date: 5/14/2018
ms.topic: article
ms.openlocfilehash: 78fe44463c4ddb832ba0cc72d456b6d21518bac4
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553155"
---
# <a name="motivations-and-principles"></a><span data-ttu-id="a0842-102">동기 및 원칙</span><span class="sxs-lookup"><span data-stu-id="a0842-102">Motivations and Principles</span></span>

<span data-ttu-id="a0842-103">다음은 동기 및 원칙 govering Adaptive Card 형식의 진화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-103">Below are the motivations and principles govering the evolution of the Adaptive Card format.</span></span>

## <a name="motivations-behind-the-format"></a><span data-ttu-id="a0842-104">동기 형식</span><span class="sxs-lookup"><span data-stu-id="a0842-104">Motivations behind the format</span></span>

<span data-ttu-id="a0842-105">초기 2016에서 여러 Microsoft 팀에 (Outlook, Windows 및 Bot Framework 포함)는 모두 원했습니다 매우 비슷한 ("카드") 및는 각각 된 솔루션을 설계 하지 자체 독립적으로 인식으로 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-105">In early 2016, several teams at Microsoft (including Outlook, Windows and the Bot Framework) came to the realization that they all wanted something extremely similar ("cards") and that each of them were designing their own solutions independently:</span></span>

- <span data-ttu-id="a0842-106">Windows가 자체 라이브 타일, 알림 형식</span><span class="sxs-lookup"><span data-stu-id="a0842-106">Windows had its own Live Tiles and Notifications format</span></span>
-  <span data-ttu-id="a0842-107">Bot framework에 봇 메시지를 보낼 때 개발자에서 선택할 수는 미리 정의 된 카드 템플릿 집합을 사용한</span><span class="sxs-lookup"><span data-stu-id="a0842-107">The Bot framework was using a set of predefined card templates developers could choose from when sending Bot messages</span></span>
- <span data-ttu-id="a0842-108">Outlook은 MessageCard 형식 자체를 사용 하 여 해당 실행 가능한 메시지 기능에 대 한가</span><span class="sxs-lookup"><span data-stu-id="a0842-108">Outlook was using its own MessageCard format for its Actionable Messages feature</span></span>

<span data-ttu-id="a0842-109">동시에, 줄, FaceBook Messenger, Slack 등 다른 플랫폼 자체적으로 소유 "카드" 형식으로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-109">At the same time, other platforms such as LINE, FaceBook Messenger, Slack and more were defining their own, proprietary "card" format.</span></span> <span data-ttu-id="a0842-110">몇 가지 Microsoft 직원 수집 하 고 하나를 열어 카드 형식 및 Sdk 집합을 정의 하기 위해 시작 하는:</span><span class="sxs-lookup"><span data-stu-id="a0842-110">So a few Microsoft employees gathered up and started an effort to define a single, open card format and a set of SDKs that:</span></span>

- <span data-ttu-id="a0842-111">호스트 간에 카드 교환을 활용 하는 것</span><span class="sxs-lookup"><span data-stu-id="a0842-111">Would facilitate the interchange of cards between hosts</span></span>
- <span data-ttu-id="a0842-112">각 호스트에 시각적 일관성을 유지 하는 카드의 스타일에 대 한 제어를 유지 하면</span><span class="sxs-lookup"><span data-stu-id="a0842-112">Would allow each host to keep control over the styling of cards to ensure visual consistency</span></span>
- <span data-ttu-id="a0842-113">쉽게 즉시 사용할 Sdk 통해 최소한의 노력으로 카드를 표시 하는 호스트 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="a0842-113">Would make it easy for a host application to display cards with minimum effort via ready-to-use SDKs</span></span>
- <span data-ttu-id="a0842-114">타사에 값을 제공 될 수도 있는 및 결국 가져오기 채택 널리 업계에서</span><span class="sxs-lookup"><span data-stu-id="a0842-114">And that would also provide value to third parties and eventually get adopted widely by the industry</span></span>

## <a name="principles-governing-adaptive-cards"></a><span data-ttu-id="a0842-115">Adaptive Card를 제어 하는 원칙</span><span class="sxs-lookup"><span data-stu-id="a0842-115">Principles governing Adaptive Cards</span></span>

1.  <span data-ttu-id="a0842-116">**Adaptive Card는를 _단순_ 하 고 _선언적_ 카드 형식**</span><span class="sxs-lookup"><span data-stu-id="a0842-116">**Adaptive Card is a _simple_ and _declarative_ card format**</span></span>

    1.  <span data-ttu-id="a0842-117">HTML 또는 XAML 대체/대신 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-117">It is not meant as an HTML or XAML replacement/alternative</span></span>
    2.  <span data-ttu-id="a0842-118">있기 **"코드 숨김이"** Adaptive Card를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="a0842-118">There is **no "code behind"** with Adaptive Cards</span></span>
        1. <span data-ttu-id="a0842-119">카드 작성자가 해당 페이로드를 사용 하 여 사용자 지정/임의 코드를 포함할 수 없습니다 및 결과적으로 Adaptive Card 호스트는 필요 하지 않습니다 제 3 자 코드를 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="a0842-119">Card authors cannot embed custom/arbitrary code with their payloads, and as a result an Adaptive Card host never needs to run third party code</span></span>
        2. <span data-ttu-id="a0842-120">활력과 상호 작용은 전적으로 선언적 태그를 통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-120">Dynamism and interactivity are achieved solely via declarative markup</span></span>
    3.  <span data-ttu-id="a0842-121">이렇게 하면 새 플랫폼에 대 한 적응 카드 SDK를 빌드하는 데 필요한 노력이 적절 한 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-121">This ensures that the effort necessary to build an Adaptive Card SDK for a new platform remains reasonable</span></span>

2.  <span data-ttu-id="a0842-122">**Adaptive Card 형식은 특정 기본 기술은 사용 강요할 수도 없습니다**</span><span class="sxs-lookup"><span data-stu-id="a0842-122">**The Adaptive Card format can't impose the use of any particular underlying technology**</span></span>

    1.  <span data-ttu-id="a0842-123">Adaptive Card 형식을 JavaScript에 의존 하지 않는 C#, Python 또는 기타 언어</span><span class="sxs-lookup"><span data-stu-id="a0842-123">The Adaptive Card format does not rely on JavaScript, C#, Python or any other language</span></span>
    2.  <span data-ttu-id="a0842-124">마찬가지로 HTML 또는 XAML 또는 다른 그래픽/UI 프레임 워크에 의존 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-124">Similarly it doesn't rely on HTML or XAML or any other graphic/UI framework</span></span>
    3.  <span data-ttu-id="a0842-125">이러한 방식으로 Adaptive Card에서 렌더링할 수 기본적으로 모든 플랫폼에 대 한 렌더러를 존재</span><span class="sxs-lookup"><span data-stu-id="a0842-125">This way, Adaptive Cards can be rendered natively on any platform for as long as a renderer exists</span></span>

3.  <span data-ttu-id="a0842-126">**Adaptive Card 형식은 _속성 공유_**</span><span class="sxs-lookup"><span data-stu-id="a0842-126">**The Adaptive Card format is a _shared property_**</span></span>

    1.  <span data-ttu-id="a0842-127">해당 Sdk와 함께 형식은 오픈 소스 및 해당 진화 커뮤니티 중심의 수</span><span class="sxs-lookup"><span data-stu-id="a0842-127">Along with its SDKs, the format is to be open source and its evolution community driven</span></span>
    2.  <span data-ttu-id="a0842-128">형식 따라서 하지 소유 않으며 모든 한 팀에 기반 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-128">The format is therefore not owned nor driven by any one team</span></span>

4.  <span data-ttu-id="a0842-129">**Adaptive Card 형식으로 설계 되지 않았습니다 "바로"Microsoft의 사용**</span><span class="sxs-lookup"><span data-stu-id="a0842-129">**The Adaptive Card format is not designed "just for Microsoft's use"**</span></span>

    1.  <span data-ttu-id="a0842-130">사용 사례 및 다양 한 응용 프로그램의 요구를 충족 하도록 설계 되었습니다 대신</span><span class="sxs-lookup"><span data-stu-id="a0842-130">Instead it is designed to suit the needs of a wide variety of applications and use cases</span></span>

5.  <span data-ttu-id="a0842-131">**합니다 _적응 카드 Working Group_ 형식의 진화를 제어 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a0842-131">**The _Adaptive Card Working Group_ governs the evolution of the format**</span></span>

    1.  <span data-ttu-id="a0842-132">이 작업 그룹은 형식의 성공 모든 깊이 관여 하는 Microsoft 직원의 집합 구성</span><span class="sxs-lookup"><span data-stu-id="a0842-132">This working group is comprised of a set of Microsoft employees that are all deeply involved in the success of the format</span></span>
    2.  <span data-ttu-id="a0842-133">작업 그룹 수행 주간 회의 (월요일)에 현재 기능 하는 동안 제안 된 문제 검토를 엽니다는 설명 심사 및 vNext 작업 항목의 전반적인 진행 상황 추적</span><span class="sxs-lookup"><span data-stu-id="a0842-133">The Working Group conducts weekly meetings (currently on Monday) during which feature proposals are reviewed, open issues are discussed and triaged and overall progress on vNext work items is tracked</span></span>
    3.  <span data-ttu-id="a0842-134">작업 그룹은 커뮤니티, 내부 Microsoft teams 등의 피드백을를 사용 하 여 형식으로 발전 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-134">The Working Group uses feedback from the community at large, including internal Microsoft teams, to decide how the format evolves</span></span>
        1. <span data-ttu-id="a0842-135">GitHub (아래 참조)에서 문제를 열고 통해 작업 그룹에 참여할 수 있습니다 누구나</span><span class="sxs-lookup"><span data-stu-id="a0842-135">Anyone can participate in the working group through opening issues in GitHub (see below)</span></span>
        2. <span data-ttu-id="a0842-136">Adaptive Card framework (호스트로 또는 카드 작성자)의 실제 사용량을 기반으로 하는 문제 또는 기능 요청 형식으로의 미래에 대 한 가장 큰 영향</span><span class="sxs-lookup"><span data-stu-id="a0842-136">Issues/feature requests rooted in actual usage of the Adaptive Cards framework (either as a host or as a card author) have the most impact on the future of the format</span></span>
    4.  <span data-ttu-id="a0842-137">에 새로운 기능 제안 된 작업 그룹에 의해 승인 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-137">To be approved by the Working Group, proposed new features:</span></span>
        1. <span data-ttu-id="a0842-138">실제 사용 사례 맞춰 정당화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-138">Must be justified by real life use cases</span></span>
        2. <span data-ttu-id="a0842-139">기능 사양이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-139">Must have a functional specification</span></span>
    5.  <span data-ttu-id="a0842-140">승인 된 새로운 기능 백로그에 추가 되며 vNext에 대 한 것으로 간주</span><span class="sxs-lookup"><span data-stu-id="a0842-140">Approved new feature are added to the backlog and considered for vNext</span></span>
        1. <span data-ttu-id="a0842-141">새 기능의 순위를 지정 하는 데 사용할 조건 광범위 한 복잡성/유지 관리 효율 기능을 사용 하는 시나리오 등 포함</span><span class="sxs-lookup"><span data-stu-id="a0842-141">The criteria used to prioritize new features include the breadth of scenarios the feature enables, its complexity/maintainability and more</span></span>
        2. <span data-ttu-id="a0842-142">의문이 있으면 계속!</span><span class="sxs-lookup"><span data-stu-id="a0842-142">When in doubt, keep it out!</span></span> <span data-ttu-id="a0842-143">나중에 계속 존재 하는 실수를 사용 하 여 보다 잘 설계 된 기능을 소개 하기 훨씬 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-143">It's a lot easier to introduce a well designed feature later than to live with a mistake forever.</span></span>
    6.  <span data-ttu-id="a0842-144">모든 지원 되는 Sdk의 새로운 기능을 모두 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-144">All new features are implemented in all supported SDKs</span></span>
    7.  <span data-ttu-id="a0842-145">새로운 기능을 모두 문서화 되 고 samples 폴더에 게시 된 테스트 카드를 사용 하 여 연결</span><span class="sxs-lookup"><span data-stu-id="a0842-145">All new features are documented and associated with a test card published in the samples folder</span></span>
    8.  <span data-ttu-id="a0842-146">새 버전의 형식 및 Sdk 베타 단계 진행</span><span class="sxs-lookup"><span data-stu-id="a0842-146">New versions of the format and SDKs go through a beta phase</span></span>
    9.  <span data-ttu-id="a0842-147">Adaptive Card 스키마 및 SDK 버전에 대 한 릴리스 일정 날짜가 아닌 품질에 의해 좌우 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-147">The release schedule for Adaptive Card schema and SDK versions is driven by quality, not date</span></span>

6.  <span data-ttu-id="a0842-148">**상호 운용성**</span><span class="sxs-lookup"><span data-stu-id="a0842-148">**Interoperability**</span></span>
    1.  <span data-ttu-id="a0842-149">문서화 된 형식 (예: 사용 하지 않음 호스트별 확장)에 따라 작성 하는 카드가 적응 카드-지원 되는 모든 호스트에서 제대로 렌더링</span><span class="sxs-lookup"><span data-stu-id="a0842-149">Cards authored in accordance with the documented format (e.g. not using any host-specific extensions) will render properly in any Adaptive Card-capable host</span></span>
    2.  <span data-ttu-id="a0842-150">이 원칙의 유일한 예외는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-150">The only exceptions to this principles are:</span></span>
        1.  <span data-ttu-id="a0842-151">몇 가지 호스트 상호 작용을 허용 하지 않을 수 있습니다 하 고 입력도 작업 렌더링 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-151">Some hosts might not allow interactivity, and will therefore not render inputs nor actions</span></span>
        2.  <span data-ttu-id="a0842-152">Action.Submit 작업의 실행 호스트의 판단에 있고 일부 호스트에서 반드시 올바르게 모든 Action.Submit 페이로드를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-152">Execution of Action.Submit actions is at the discretion of the host, and not all hosts will necessarily properly handle all Action.Submit payloads.</span></span> <span data-ttu-id="a0842-153">또한 일부 호스트 지원 하지 않을 수 Action.Submit 전혀</span><span class="sxs-lookup"><span data-stu-id="a0842-153">Furthermore, some hosts might not support Action.Submit at all</span></span>

7.  <span data-ttu-id="a0842-154">**형식 가능 해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a0842-154">**The format needs to be extensible**</span></span>

    1.  <span data-ttu-id="a0842-155">호스트를 자유롭게 사용자 지정 요소 또는 어떤 형식 인지 수 뿐만 아니라 사용자 지정 작업에 대 한 지원을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-155">Hosts should have the freedom of adding support for custom elements or custom actions that go beyond what the format is capable of</span></span>
    2.  <span data-ttu-id="a0842-156">즉 작업의 경우 특히 중요 한 다양 한 호스트에 동일한 작업 집합을 반드시 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-156">This is particularly important for actions, as various hosts don't necessarily support the same set of actions</span></span>
    3.  <span data-ttu-id="a0842-157">호스트의 판단에 따라 이러한 추가</span><span class="sxs-lookup"><span data-stu-id="a0842-157">These additions are at the discretion of the host</span></span>
        1. <span data-ttu-id="a0842-158">하지 않은 한 *사실상* Adaptive Card 사양에 추가</span><span class="sxs-lookup"><span data-stu-id="a0842-158">They are not a *de facto* addition to the Adaptive Card specification</span></span>
        2. <span data-ttu-id="a0842-159">이와 같이 할 페이로드를 사용 하는 주류 Adaptive Card 형식과 호환 되지 않는</span><span class="sxs-lookup"><span data-stu-id="a0842-159">As such, they make a payload that uses them incompatible with the mainstream Adaptive Card format</span></span>
        3. <span data-ttu-id="a0842-160">그러나 수 있는 작업 그룹에 게 제공 하 고 # 5에 설명 된 대로 형식의 이후 버전에 대 한 새 기능으로 제안</span><span class="sxs-lookup"><span data-stu-id="a0842-160">They can however be presented to the Working Group and proposed as new features for a future version of the format, as described in point #5</span></span>

8.  <span data-ttu-id="a0842-161">**콘텐츠를 소유 하는 카드 작성자, 모양 및 느낌을 소유 하는 앱 호스트**</span><span class="sxs-lookup"><span data-stu-id="a0842-161">**Card authors own the content, host apps own the look and feel**</span></span>

    1.  <span data-ttu-id="a0842-162">카드 표시 되므로 해당 스타일 지정, 앱의 환경의 기본 확장은 이러한 생각을 적용 하는 앱 호스트</span><span class="sxs-lookup"><span data-stu-id="a0842-162">Host apps impose their styling so cards look and feel like they are native extensions of the app's experience</span></span>
    2.  <span data-ttu-id="a0842-163">카드 작성자가 스타일, 색, 크기 등의 의미 체계 식을 통해만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-163">Card authors can still specify styling, but only via semantic expressions of colors, sizes, etc.</span></span>

9.  <span data-ttu-id="a0842-164">**Sdk는 가장 인기 있는 개발자 플랫폼에 대해 제공 될 예정**</span><span class="sxs-lookup"><span data-stu-id="a0842-164">**SDKs will be provided for the most popular developer platforms**</span></span>

    1.  <span data-ttu-id="a0842-165">Sdk를 쉽게 모든 호스트에서 Adaptive Card 페이로드를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0842-165">SDKs make it easy to render Adaptive Card payloads in any host</span></span>
    2.  <span data-ttu-id="a0842-166">이렇게 하면 항목에 대 한 장벽을 최저 타사 개발자가 Microsoft teams에 둘 다 수</span><span class="sxs-lookup"><span data-stu-id="a0842-166">This ensures the barrier to entry is as low as can be both for third party developers and Microsoft teams</span></span>
