---
title: Adaptive Card 로드맵
author: matthidinger
ms.author: mahiding
ms.date: 05/16/2018
ms.topic: article
ms.openlocfilehash: f879c164b3471347ba8fa058827b3d79b09be4cd
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67138006"
---
# <a name="future-work"></a><span data-ttu-id="82826-102">후속 작업</span><span class="sxs-lookup"><span data-stu-id="82826-102">Future work</span></span>

<span data-ttu-id="82826-103">Adaptive card를 정의 하는 훌륭한 진행률, 만들었습니다는 여전히 많은 작업을 수행 하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="82826-103">While we have made excellent progress defining adaptive cards, there is still lots of work to do.</span></span> <span data-ttu-id="82826-104">계측이 botness, 및 Slack 같은 뛰어난 파트너 Kik 등 현재 개발자 커뮤니티를 통해 플랫폼 간 카드의 뛰어난 에코 시스템을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82826-104">Our hope is that through active developer communities like botness, and great partners like Slack and Kik, we can create a great ecosystem of cross-platform cards.</span></span>

## <a name="roadmap"></a><span data-ttu-id="82826-105">로드맵</span><span class="sxs-lookup"><span data-stu-id="82826-105">Roadmap</span></span>

<span data-ttu-id="82826-106">보시 우리의 [여기에서 현재 (최종이 아닌) 로드맵](https://portal.productboard.com/adaptivecards/1-adaptive-cards-portal/tabs/1-backlog)합니다.</span><span class="sxs-lookup"><span data-stu-id="82826-106">You can see our [current (non-final) roadmap here](https://portal.productboard.com/adaptivecards/1-adaptive-cards-portal/tabs/1-backlog).</span></span> <span data-ttu-id="82826-107">에 불과하며 여기에서 아무 것도 변경 될 수의 전달 보장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82826-107">Note that anything on here is subject to change, and is not a guarantee of shipping.</span></span>

## <a name="future-ideas"></a><span data-ttu-id="82826-108">향후 아이디어</span><span class="sxs-lookup"><span data-stu-id="82826-108">Future ideas</span></span>

<span data-ttu-id="82826-109">향후 아이디어를 단순히 브레인스토밍 단계에에서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="82826-109">The following are some future ideas we have, which are simply in the brainstorm stage.</span></span> <span data-ttu-id="82826-110">이러한 템플릿 중 하나에 관심이 있다면 주석에 알려 주십시오.</span><span class="sxs-lookup"><span data-stu-id="82826-110">If you're interested in any of these, let us know in a comment.</span></span>

### <a name="great-looking-cards-from-data"></a><span data-ttu-id="82826-111">데이터에서 유용한 보이는 카드</span><span class="sxs-lookup"><span data-stu-id="82826-111">Great looking Cards from Data</span></span>

<span data-ttu-id="82826-112">잘 정의 된 카드 데이터가 이미 카드 저자를 많이 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82826-112">We know many card authors already have well-defined data behind their cards.</span></span> <span data-ttu-id="82826-113">현재 계획으로 생성 되는 카드를 허용 하는 템플릿 모델을 탐색 하는 데이터에 잘 정의 된 템플릿과 사용자 지정 가능한의 리포지토리 (서버 쪽 또는 클라이언트 쪽) 기반 합니다.</span><span class="sxs-lookup"><span data-stu-id="82826-113">Our plan is to explore a templating model that would allow cards to be generated (server side or client side) based on the data and a repository of well-defined and customizable templates.</span></span>

### <a name="make-cards-responsive"></a><span data-ttu-id="82826-114">카드를 반응 형으로 만들기</span><span class="sxs-lookup"><span data-stu-id="82826-114">Make cards responsive</span></span>

<span data-ttu-id="82826-115">카드 레이아웃에 사용 가능한 공간에 반응 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82826-115">Card layouts should be reactive to available space.</span></span> <span data-ttu-id="82826-116">Adaptive card는 다른 장치에 ux 스타일 융통성 및 ui 프레임 워크 있지만 아직 안 된 반응 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82826-116">Adaptive cards are adaptable to different devices, ux styles and and ui frameworks, but they are not reactive yet.</span></span> <span data-ttu-id="82826-117">추가 속성은 카드의 의도 유지 관리 하는 방식으로 레이아웃 지능적으로 변경할 수 있도록 렌더링 라이브러리에 필요한 힌트를 제공 하는 카드 생산자를 허용 하는 요소에 정의 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82826-117">Additional properties must be defined on elements which allow card producers to provide the necessary hints to the rendering libraries so that they can intelligently change the layout in a way which maintains the intent of the card.</span></span>

### <a name="responsive-exploration"></a><span data-ttu-id="82826-118">반응 형 탐색</span><span class="sxs-lookup"><span data-stu-id="82826-118">Responsive exploration</span></span>

* <span data-ttu-id="82826-119">추가 된 **중요도** 콘텐츠의 중요도 주석을 달고 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="82826-119">Add an **importance** property which annotates importance of content.</span></span> <span data-ttu-id="82826-120">사용 가능한 공간에 맞게 덜 중요 한 콘텐츠를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82826-120">Less important content can be dropped to fit available space</span></span>
* <span data-ttu-id="82826-121">추가 **제약 조건** 하 고 **정책** 제약 조건을 충족할 수 없는 경우 대처 하는 방법을 설명 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="82826-121">Add **constraints** and **policy** properties describing how to react when constraints can't be met.</span></span> 
  * <span data-ttu-id="82826-122">콘텐츠를 더 작은 크기로 축소 하거나 콘텐츠를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="82826-122">Hide content or collapse content to smaller size.</span></span>
  * <span data-ttu-id="82826-123">임계값을 추가, 초과 되 면 변경 `columnSet` 회전식 열에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82826-123">Add a threshold that, when exceeded, changes `columnSet` to carousel of columns.</span></span>

### <a name="new-element-types"></a><span data-ttu-id="82826-124">새 요소 형식</span><span class="sxs-lookup"><span data-stu-id="82826-124">New element types</span></span>

* <span data-ttu-id="82826-125">Maps?</span><span class="sxs-lookup"><span data-stu-id="82826-125">Maps?</span></span> <span data-ttu-id="82826-126">-상호 작용 또는 비트맵 대체 (fallback)를 사용 하 여 카드에 지도 포함</span><span class="sxs-lookup"><span data-stu-id="82826-126">- embed a map into a card with interactivity or fallback to bitmap</span></span>
* <span data-ttu-id="82826-127">*요소 수행 하려고 하거나 생성 해야*?</span><span class="sxs-lookup"><span data-stu-id="82826-127">*What elements do you want or need*?</span></span>

### <a name="new-rendering-libraries"></a><span data-ttu-id="82826-128">새 렌더링 라이브러리</span><span class="sxs-lookup"><span data-stu-id="82826-128">New rendering libraries</span></span>

* <span data-ttu-id="82826-129">React?</span><span class="sxs-lookup"><span data-stu-id="82826-129">React?</span></span>
* <span data-ttu-id="82826-130">Xamarin?</span><span class="sxs-lookup"><span data-stu-id="82826-130">Xamarin?</span></span>
* <span data-ttu-id="82826-131">*어떤 프레임 워크를 사용 하 시겠습니까?*</span><span class="sxs-lookup"><span data-stu-id="82826-131">*What frameworks do you want?*</span></span>
