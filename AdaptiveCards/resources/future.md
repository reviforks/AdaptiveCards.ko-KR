---
title: 적응형 카드 로드맵
author: matthidinger
ms.author: mahiding
ms.date: 05/16/2018
ms.topic: article
ms.openlocfilehash: f879c164b3471347ba8fa058827b3d79b09be4cd
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67138006"
---
# <a name="future-work"></a><span data-ttu-id="2f8d1-102">향후 작업</span><span class="sxs-lookup"><span data-stu-id="2f8d1-102">Future work</span></span>

<span data-ttu-id="2f8d1-103">적응형 카드를 정의하는 작업을 완료했지만 아직도 수행할 할 작업이 많습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8d1-103">While we have made excellent progress defining adaptive cards, there is still lots of work to do.</span></span> <span data-ttu-id="2f8d1-104">Botness 같은 활발한 개발자 커뮤니티와 Slack 및 Kik 같은 멋진 파트너를 통해 플랫폼 간 카드의 멋진 에코시스템을 만들 수 있기를 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="2f8d1-104">Our hope is that through active developer communities like botness, and great partners like Slack and Kik, we can create a great ecosystem of cross-platform cards.</span></span>

## <a name="roadmap"></a><span data-ttu-id="2f8d1-105">로드맵</span><span class="sxs-lookup"><span data-stu-id="2f8d1-105">Roadmap</span></span>

<span data-ttu-id="2f8d1-106">[여기에서 현재(마지막이 아님) 로드맵](https://portal.productboard.com/adaptivecards/1-adaptive-cards-portal/tabs/1-backlog)을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8d1-106">You can see our [current (non-final) roadmap here](https://portal.productboard.com/adaptivecards/1-adaptive-cards-portal/tabs/1-backlog).</span></span> <span data-ttu-id="2f8d1-107">여기에 있는 내용은 변경될 수 있으며 제공을 보장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8d1-107">Note that anything on here is subject to change, and is not a guarantee of shipping.</span></span>

## <a name="future-ideas"></a><span data-ttu-id="2f8d1-108">향후 아이디어</span><span class="sxs-lookup"><span data-stu-id="2f8d1-108">Future ideas</span></span>

<span data-ttu-id="2f8d1-109">다음은 브레인스토밍 단계에 있는 몇 가지 향후 아이디어입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8d1-109">The following are some future ideas we have, which are simply in the brainstorm stage.</span></span> <span data-ttu-id="2f8d1-110">이 아이디어에 관심이 있는 경우 댓글로 알려 주세요.</span><span class="sxs-lookup"><span data-stu-id="2f8d1-110">If you're interested in any of these, let us know in a comment.</span></span>

### <a name="great-looking-cards-from-data"></a><span data-ttu-id="2f8d1-111">데이터에서 생성되는 멋진 카드</span><span class="sxs-lookup"><span data-stu-id="2f8d1-111">Great looking Cards from Data</span></span>

<span data-ttu-id="2f8d1-112">많은 카드 작성자는 카드의 기반이 되는 잘 정의된 데이터를 이미 보유하고 있음을 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8d1-112">We know many card authors already have well-defined data behind their cards.</span></span> <span data-ttu-id="2f8d1-113">여기서는 데이터 및 잘 정의되고 사용자 지정 가능한 템플릿 리포지토리를 기반으로 서버 쪽 또는 클라이언트 쪽에서 카드를 생성할 수 있는 템플릿 모델을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8d1-113">Our plan is to explore a templating model that would allow cards to be generated (server side or client side) based on the data and a repository of well-defined and customizable templates.</span></span>

### <a name="make-cards-responsive"></a><span data-ttu-id="2f8d1-114">반응형 카드 만들기</span><span class="sxs-lookup"><span data-stu-id="2f8d1-114">Make cards responsive</span></span>

<span data-ttu-id="2f8d1-115">카드 레이아웃은 사용 가능한 공간에 반응해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8d1-115">Card layouts should be reactive to available space.</span></span> <span data-ttu-id="2f8d1-116">적응형 카드는 다른 디바이스, UX 스타일 및 UI 프레임워크에 따라 조정되지만 아직 반응형은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2f8d1-116">Adaptive cards are adaptable to different devices, ux styles and and ui frameworks, but they are not reactive yet.</span></span> <span data-ttu-id="2f8d1-117">카드 생산자가 렌더링 라이브러리에 필요한 힌트를 제공할 수 있도록 요소에 대한 추가 속성을 정의해야 합니다. 이를 통해 렌더링 라이브러리는 카드의 의도를 유지하는 방식으로 레이아웃을 지능적으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8d1-117">Additional properties must be defined on elements which allow card producers to provide the necessary hints to the rendering libraries so that they can intelligently change the layout in a way which maintains the intent of the card.</span></span>

### <a name="responsive-exploration"></a><span data-ttu-id="2f8d1-118">반응형 탐색</span><span class="sxs-lookup"><span data-stu-id="2f8d1-118">Responsive exploration</span></span>

* <span data-ttu-id="2f8d1-119">콘텐츠의 중요도에 대한 주석을 다는 **중요도** 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8d1-119">Add an **importance** property which annotates importance of content.</span></span> <span data-ttu-id="2f8d1-120">덜 중요한 콘텐츠는 사용 가능한 공간에 맞게 삭제될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8d1-120">Less important content can be dropped to fit available space</span></span>
* <span data-ttu-id="2f8d1-121">제약 조건을 충족할 수 없을 때 반응하는 방법을 설명하는 **제약 조건** 및 **정책** 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8d1-121">Add **constraints** and **policy** properties describing how to react when constraints can't be met.</span></span> 
  * <span data-ttu-id="2f8d1-122">콘텐츠를 숨기거나 더 작은 크기로 축소합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8d1-122">Hide content or collapse content to smaller size.</span></span>
  * <span data-ttu-id="2f8d1-123">초과될 경우 `columnSet`를 회전식 열로 변경하는 임계값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8d1-123">Add a threshold that, when exceeded, changes `columnSet` to carousel of columns.</span></span>

### <a name="new-element-types"></a><span data-ttu-id="2f8d1-124">새 요소 형식</span><span class="sxs-lookup"><span data-stu-id="2f8d1-124">New element types</span></span>

* <span data-ttu-id="2f8d1-125">맵이란?</span><span class="sxs-lookup"><span data-stu-id="2f8d1-125">Maps?</span></span> <span data-ttu-id="2f8d1-126">- 카드에 대화식 또는 비트맵으로 대체 방식으로 맵 포함</span><span class="sxs-lookup"><span data-stu-id="2f8d1-126">- embed a map into a card with interactivity or fallback to bitmap</span></span>
* <span data-ttu-id="2f8d1-127">‘원하거나 필요한 요소는 무엇인가요?’ </span><span class="sxs-lookup"><span data-stu-id="2f8d1-127">*What elements do you want or need*?</span></span>

### <a name="new-rendering-libraries"></a><span data-ttu-id="2f8d1-128">새 렌더링 라이브러리</span><span class="sxs-lookup"><span data-stu-id="2f8d1-128">New rendering libraries</span></span>

* <span data-ttu-id="2f8d1-129">반응이란?</span><span class="sxs-lookup"><span data-stu-id="2f8d1-129">React?</span></span>
* <span data-ttu-id="2f8d1-130">Xamarin이란?</span><span class="sxs-lookup"><span data-stu-id="2f8d1-130">Xamarin?</span></span>
* <span data-ttu-id="2f8d1-131">‘원하는 프레임워크는 무엇인가요?’ </span><span class="sxs-lookup"><span data-stu-id="2f8d1-131">*What frameworks do you want?*</span></span>
