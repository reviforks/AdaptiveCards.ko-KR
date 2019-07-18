---
title: 적응형 카드 개요
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 487acab86d80d563210abe07968520ea7669498a
ms.sourcegitcommit: 8c8067206f283d97a5aa4ec65ba23d3fe18962f1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299544"
---
# <a name="adaptive-cards-overview"></a><span data-ttu-id="5653c-102">적응형 카드 개요</span><span class="sxs-lookup"><span data-stu-id="5653c-102">Adaptive Cards Overview</span></span> 

<span data-ttu-id="5653c-103">적응형 카드는 개발자가 일반적이고 일관된 방법으로 UI 콘텐츠를 교환할 수 있는 개방형 카드 교환 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-103">Adaptive Cards are an open card exchange format enabling developers to exchange UI content in a common and consistent way.</span></span>

<video controls width="100%" poster="./content/videoposter.png">
    <source src="https://adaptivecardsblob.blob.core.windows.net/assets/AdaptiveCardsOverviewVideo.mp4" type="video/mp4">
</video>

## <a name="how-they-work"></a><span data-ttu-id="5653c-104">작동 방식</span><span class="sxs-lookup"><span data-stu-id="5653c-104">How they work</span></span>

<span data-ttu-id="5653c-105">[**카드 작성자**](authoring-cards/getting-started.md)는 간단한 JSON 개체로 콘텐츠를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-105">[**Card Authors**](authoring-cards/getting-started.md) describe their content as a simple JSON object.</span></span> <span data-ttu-id="5653c-106">그런 다음, 해당 콘텐츠는 호스트의 모양과 느낌에 맞게 자동으로 조정되도록 [**호스트 애플리케이션**](rendering-cards/getting-started.md) 내부에서 고유하게 렌더링될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-106">That content can then be rendered natively inside a [**Host Application**](rendering-cards/getting-started.md), automatically adapting to the look and feel of the Host.</span></span>

<span data-ttu-id="5653c-107">예를 들어 Contoso Bot은 Bot Framework를 통해 적응형 카드를 작성할 수 있으며 Skype에 전달될 때 Skype 카드와 비슷한 모양과 느낌을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-107">For example, Contoso Bot can author an Adaptive Card through the Bot Framework, and when delivered to Skype, it will look and feel like a Skype card.</span></span> <span data-ttu-id="5653c-108">동일한 페이로드를 Microsoft Teams에 보낼 때는 Microsoft Teams와 비슷한 모양과 느낌을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-108">When that same payload is sent to Microsoft Teams, it will look and feel like Microsoft Teams.</span></span> <span data-ttu-id="5653c-109">더 많은 호스트 앱이 적응형 카드를 지원하기 시작하면 동일한 페이로드는 이러한 애플리케이션 내에서 자동으로 실행되며, 전부 원래 앱에 있었던 것처럼 느낄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-109">As more host apps start to support Adaptive Cards, that same payload will automatically light up inside these applications, yet still feel entirely native to the app.</span></span>

<span data-ttu-id="5653c-110">모든 것이 친숙하게 느껴지므로 사용자에게 이득입니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-110">Users win because everything feels familiar.</span></span> <span data-ttu-id="5653c-111">사용자 환경을 제어할 수 있으므로 앱 호스트에도 이득입니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-111">Host apps win because they control the user experience.</span></span> <span data-ttu-id="5653c-112">또한 자신의 콘텐츠를 추가 작업 없이 더 널리 퍼뜨릴 수 있으므로 카드 작성자에게도 이득입니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-112">And Card Authors win because their content gets broader reach without any additional work.</span></span>

## <a name="goals"></a><span data-ttu-id="5653c-113">목표</span><span class="sxs-lookup"><span data-stu-id="5653c-113">Goals</span></span> 

<span data-ttu-id="5653c-114">적응형 카드의 목표는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-114">The goals for Adaptive Cards are:</span></span>

* <span data-ttu-id="5653c-115">**이식 가능** - 모든 앱, 디바이스 및 UI 프레임워크</span><span class="sxs-lookup"><span data-stu-id="5653c-115">**Portable** - To any app, device, and UI framework</span></span>
* <span data-ttu-id="5653c-116">**개방성** - 오픈 소스이며 공유되는 라이브러리 및 스키마</span><span class="sxs-lookup"><span data-stu-id="5653c-116">**Open** - Libraries and schema are open source and shared</span></span>
* <span data-ttu-id="5653c-117">**저렴한 비용** - 손쉬운 정의, 손쉬운 사용</span><span class="sxs-lookup"><span data-stu-id="5653c-117">**Low cost** - Easy to define, easy to consume</span></span>
* <span data-ttu-id="5653c-118">**표현력** - 개발자가 생성하고자 하는 콘텐츠의 롱 테일(Long Tail)이 목표</span><span class="sxs-lookup"><span data-stu-id="5653c-118">**Expressive** - Targeted at the long tail of content that developers want to produce</span></span>
* <span data-ttu-id="5653c-119">**순수하게 선언적** - 코드가 필요하지 않거나 허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="5653c-119">**Purely declarative** - No code is needed or allowed</span></span>
* <span data-ttu-id="5653c-120">**자동으로 스타일 지정** - 호스트 애플리케이션 UX 및 브랜드 지침에 맞게</span><span class="sxs-lookup"><span data-stu-id="5653c-120">**Automatically styled** - To the Host application UX and brand guidelines</span></span>

## <a name="for-card-authors"></a><span data-ttu-id="5653c-121">카드 작성자의 경우</span><span class="sxs-lookup"><span data-stu-id="5653c-121">For Card Authors</span></span>
<span data-ttu-id="5653c-122">적응형 카드는 카드 작성자에게 아주 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-122">Adaptive Cards are great for card authors:</span></span>

* <span data-ttu-id="5653c-123">**하나의 스키마** - 단일 형식으로 카드 생산 비용을 최소화하고 카드가 사용될 수 있는 장소의 수는 최대화합니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-123">**One schema** - You get a single format, minimizing the cost of creating a card and maximizing the number of places it can be used.</span></span>
* <span data-ttu-id="5653c-124">**풍부한 식** - 더 풍부한 팔레트를 통해 콘텐츠를 자신이 표현하고자 하는 것과 더 밀접하게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-124">**Richer expression** - Your content can more closely align with want you want to say because you have a richer palette to paint with.</span></span>
* <span data-ttu-id="5653c-125">**광범위한 도달률** - 콘텐츠는 광범위한 애플리케이션 세트에서 작동하지만, 새 스키마를 배울 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-125">**Broad reach** - Your content will work across a broader set of applications without you having to learn new schemas.</span></span>
* <span data-ttu-id="5653c-126">**입력 컨트롤** - 카드를 보는 사용자로부터 정보를 수집하기 위한 입력 제어를 카드에 포함시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-126">**Input controls** - Your card can include input controls for gathering information from the user that is viewing the card.</span></span>
* <span data-ttu-id="5653c-127">**더 나은 도구** - 오픈 카드 에코시스템은 모두가 공유하는 더 나은 도구를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-127">**Better tooling** - An open card ecosystem means better tooling that is shared by everyone.</span></span>

## <a name="for-experience-owners"></a><span data-ttu-id="5653c-128">환경 소유자의 경우</span><span class="sxs-lookup"><span data-stu-id="5653c-128">For Experience Owners</span></span>
<span data-ttu-id="5653c-129">타사 콘텐츠의 에코시스템으로 진입하려는 앱 개발자라면 다음과 같은 이유로 적응형 카드가 마음에 드실 겁니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-129">If you are an app developer who wants to tap into an ecosystem of third-party content you will love Adaptive Cards because:</span></span>

* <span data-ttu-id="5653c-130">**일관된 사용자 환경** - 렌더링된 카드의 스타일을 소유하므로 사용자에게 일관된 환경을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-130">**Consistent user experience** - You guarantee a consistent experience for your users, because you own the style of the rendered card.</span></span>
* <span data-ttu-id="5653c-131">**기본 성능** - UI 프레임워크를 직접 대상으로 하므로 기본 성능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-131">**Native performance** - You get native performance as it targets your UI framework directly.</span></span>
* <span data-ttu-id="5653c-132">**안전** - 콘텐츠는 안전한 페이로드로 제공되므로 UI 프레임워크를 원시 태그 및 스크립팅에 개방할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-132">**Safe** - Content is delivered in safe payloads so you don't have to open up your UI framework to raw markup and scripting.</span></span>
* <span data-ttu-id="5653c-133">**손쉬운 구현** - 라이브러리를 상용화하여 지원하는 플랫폼에서 손쉽게 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-133">**Easy to implement** - You get off the shelf libraries to easily integrate on any platform you support</span></span> 
* <span data-ttu-id="5653c-134">**무료 설명서** - 사유 스키마를 고안, 구현 및 문서화할 필요가 없으므로 시간이 절약됩니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-134">**Free documentation** - You save time because you don't have to invent, implement, and document a proprietary schema.</span></span>
* <span data-ttu-id="5653c-135">**공유 도구** - 사용자 지정 도구를 만들 필요가 없으므로 시간이 절약됩니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-135">**Shared tooling** - You save time because you don't have to create custom tooling.</span></span>

## <a name="core-design-principles"></a><span data-ttu-id="5653c-136">주요 디자인 원칙</span><span class="sxs-lookup"><span data-stu-id="5653c-136">Core Design Principles</span></span> 

<span data-ttu-id="5653c-137">적응형 카드는 디자인이 제대로 진행되도록 하는 데 유용한 [기본 원칙](resources/principles.md) 세트에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-137">Adaptive Cards are driven by a set of [guiding principles](resources/principles.md) that have been useful for keeping the design on track.</span></span> 

### <a name="semantic-instead-of-pixel-perfect"></a><span data-ttu-id="5653c-138">정확한 픽셀 대신 의미 체계</span><span class="sxs-lookup"><span data-stu-id="5653c-138">Semantic instead of pixel-perfect</span></span>
<span data-ttu-id="5653c-139">Microsoft는 정확한 픽셀 레이아웃과는 대조적으로 의미 체계 값과 개념을 위해 가능한 한 많은 노력을 해왔습니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-139">We have striven as much as possible for semantic values and concepts as opposed to pure pixel-perfect layout.</span></span> <span data-ttu-id="5653c-140">의미 체계 식의 예제는 색상, 크기 및 FactSet와 ImageSet 같은 요소에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-140">Examples of semantic expression show up in colors, sizes, and in elements like FactSet and ImageSet.</span></span> <span data-ttu-id="5653c-141">이 모든 것은 호스트 애플리케이션이 실제 모양과 느낌에 대해 더 나은 결정을 내릴 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-141">These all allow the host application to make better decisions about the actual look and feel.</span></span>

### <a name="card-authors-own-the-content-host-app-owns-the-look-and-feel"></a><span data-ttu-id="5653c-142">카드 작성자는 콘텐츠를 소유하고, 호스트 앱은 모양과 느낌을 소유합니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-142">Card Authors own the content, Host App owns the look and feel</span></span>
<span data-ttu-id="5653c-143">카드 작성자는 자신들이 말하고자 하는 내용을 소유하지만, 그것을 표시하는 애플리케이션은 작성자 애플리케이션의 컨텍스트에서 카드의 모양과 느낌을 소유합니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-143">The card authors own what they want to say, but the application displaying it owns the look and feel of the card in the context of their application.</span></span>

### <a name="keep-it-simple-but-expressive"></a><span data-ttu-id="5653c-144">간단하면서 다양한 표현</span><span class="sxs-lookup"><span data-stu-id="5653c-144">Keep it simple, but expressive</span></span>
<span data-ttu-id="5653c-145">적응형 카드가 다양한 표현을 하고 범용적이길 원하지만 UI 프레임워크를 빌드하고 싶지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-145">We want Adaptive Cards to be expressive and general purpose, but we don't want to build a UI framework.</span></span>  <span data-ttu-id="5653c-146">목표는 문서에서 Markdown이 충분히 표현되는 것과 동일한 방법으로 “충분히 다양한 표현을 구현”하는 중간 계층을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-146">The goal is to create an intermediate layer which is "expressive enough" in the same way Markdown is expressive enough for documents.</span></span>

<span data-ttu-id="5653c-147">Markdown은 간단하고 다양한 표현에 초점을 맞추면서 문서 콘텐츠에 대한 쉽고 일관된 설명을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-147">By focusing on keeping it simple and expressive, Markdown created an easy and consistent description of document content.</span></span>  <span data-ttu-id="5653c-148">동일한 방법으로 적응형 카드도 카드 콘텐츠를 설명하는 간단하고 효과적인 수단을 만들 수 있다고 생각합니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-148">In the same way, we believe that Adaptive Cards can create a simple, expressive means of describing card content.</span></span>

### <a name="when-in-doubt-keep-it-out"></a><span data-ttu-id="5653c-149">의문이 있다면 제외</span><span class="sxs-lookup"><span data-stu-id="5653c-149">When in doubt, keep it out</span></span>
<span data-ttu-id="5653c-150">실수를 감수하며 사는 것보다 나중에 추가하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-150">It is easier to add later then it is to live with a mistake.</span></span> <span data-ttu-id="5653c-151">만약 무언가를 추가해야 할지 말지를 논쟁한다면 그대로 놔두기로 결정했습니다.  지원하지 않아도 되는 레거시가 잇는 것보다 속성을 추가하는 것이 항상 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-151">If we found ourselves debating whether we should add something or not, we opted to leave it out.  It is always easier to add a property than to live with a legacy we wish we didn't have to support.</span></span>


## <a name="build-2018-session"></a><span data-ttu-id="5653c-152">빌드 2018 세션</span><span class="sxs-lookup"><span data-stu-id="5653c-152">Build 2018 Session</span></span>

<span data-ttu-id="5653c-153">빌드 2018에서 이루어진 다음 세션에서는 봇, Cortana, Outlook 및 Windows에서의 적응형 카드를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="5653c-153">The following session at Build 2018 showcases Adaptive Cards in Bots, Cortana, Outlook, and Windows.</span></span> 

<iframe src="https://medius.studios.ms/Embed/Video/BRK2401?SFYT=true" width="960" height="540" allowFullScreen frameBorder="0"></iframe>
