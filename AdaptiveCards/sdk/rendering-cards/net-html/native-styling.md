---
title: 기본 스타일 지정-.NET HTML SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 620940dee873742898d58979c61827320bc3c202
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552565"
---
# <a name="native-styling---net-html"></a><span data-ttu-id="f27f7-102">기본 스타일 지정-.NET HTML</span><span class="sxs-lookup"><span data-stu-id="f27f7-102">Native styling - .NET HTML</span></span>

<span data-ttu-id="f27f7-103">호스트 구성에는 각 플랫폼에 대 한 대부분의 방법이 있지만 각 플랫폼에서 기본 스타일 지정을 수행 해야 할 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f27f7-103">While Host Config will get you most of the way there on each platform, it's likely that you will have to do some native styling on each platform.</span></span> 

<span data-ttu-id="f27f7-104">HTML은 모든 요소에 CSS 클래스를 추가 하 여 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f27f7-104">HTML makes this easy by adding CSS classes to every element.</span></span>

| <span data-ttu-id="f27f7-105">요소</span><span class="sxs-lookup"><span data-stu-id="f27f7-105">Element</span></span> | <span data-ttu-id="f27f7-106">CSS 클래스</span><span class="sxs-lookup"><span data-stu-id="f27f7-106">CSS class</span></span> |
|---|---|
| <span data-ttu-id="f27f7-107">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="f27f7-107">AdaptiveCard</span></span> | <span data-ttu-id="f27f7-108">ac-adaptivecard</span><span class="sxs-lookup"><span data-stu-id="f27f7-108">ac-adaptivecard</span></span> |
| <span data-ttu-id="f27f7-109">모든 작업</span><span class="sxs-lookup"><span data-stu-id="f27f7-109">All Actions</span></span> | <span data-ttu-id="f27f7-110">ac 누름</span><span class="sxs-lookup"><span data-stu-id="f27f7-110">ac-pushButton</span></span> | 
| <span data-ttu-id="f27f7-111">작업 선택</span><span class="sxs-lookup"><span data-stu-id="f27f7-111">Select Actions</span></span> | <span data-ttu-id="f27f7-112">ac 선택 가능</span><span class="sxs-lookup"><span data-stu-id="f27f7-112">ac-selectable</span></span> |
| <span data-ttu-id="f27f7-113">작업. OpenUrl</span><span class="sxs-lookup"><span data-stu-id="f27f7-113">Action.OpenUrl</span></span>  | <span data-ttu-id="f27f7-114">ac 동작-openUrl</span><span class="sxs-lookup"><span data-stu-id="f27f7-114">ac-action-openUrl</span></span> |
| <span data-ttu-id="f27f7-115">작업. ShowCard</span><span class="sxs-lookup"><span data-stu-id="f27f7-115">Action.ShowCard</span></span> | <span data-ttu-id="f27f7-116">ac 작업-showCard</span><span class="sxs-lookup"><span data-stu-id="f27f7-116">ac-action-showCard</span></span> |
| <span data-ttu-id="f27f7-117">작업. 제출</span><span class="sxs-lookup"><span data-stu-id="f27f7-117">Action.Submit</span></span>  | <span data-ttu-id="f27f7-118">ac 작업-제출</span><span class="sxs-lookup"><span data-stu-id="f27f7-118">ac-action-submit</span></span>  |
| <span data-ttu-id="f27f7-119">ActionSet</span><span class="sxs-lookup"><span data-stu-id="f27f7-119">ActionSet</span></span> | <span data-ttu-id="f27f7-120">ac actionset</span><span class="sxs-lookup"><span data-stu-id="f27f7-120">ac-actionset</span></span> |
| <span data-ttu-id="f27f7-121">Column</span><span class="sxs-lookup"><span data-stu-id="f27f7-121">Column</span></span> | <span data-ttu-id="f27f7-122">ac 열</span><span class="sxs-lookup"><span data-stu-id="f27f7-122">ac-column</span></span> |
| <span data-ttu-id="f27f7-123">ColumnSet</span><span class="sxs-lookup"><span data-stu-id="f27f7-123">ColumnSet</span></span> | <span data-ttu-id="f27f7-124">ac-columnset</span><span class="sxs-lookup"><span data-stu-id="f27f7-124">ac-columnset</span></span> |
| <span data-ttu-id="f27f7-125">컨테이너</span><span class="sxs-lookup"><span data-stu-id="f27f7-125">Container</span></span> | <span data-ttu-id="f27f7-126">ac 컨테이너</span><span class="sxs-lookup"><span data-stu-id="f27f7-126">ac-container</span></span> |
| <span data-ttu-id="f27f7-127">모든 입력</span><span class="sxs-lookup"><span data-stu-id="f27f7-127">All Inputs</span></span> | <span data-ttu-id="f27f7-128">ac 입력</span><span class="sxs-lookup"><span data-stu-id="f27f7-128">ac-input</span></span> |
| <span data-ttu-id="f27f7-129">ChoiceSet</span><span class="sxs-lookup"><span data-stu-id="f27f7-129">Input.ChoiceSet</span></span> | <span data-ttu-id="f27f7-130">ac-multichoiceInput</span><span class="sxs-lookup"><span data-stu-id="f27f7-130">ac-multichoiceInput</span></span>  |
| <span data-ttu-id="f27f7-131">입력. 날짜</span><span class="sxs-lookup"><span data-stu-id="f27f7-131">Input.Date</span></span> | <span data-ttu-id="f27f7-132">ac dateInput</span><span class="sxs-lookup"><span data-stu-id="f27f7-132">ac-dateInput</span></span> |
| <span data-ttu-id="f27f7-133">입력. Number</span><span class="sxs-lookup"><span data-stu-id="f27f7-133">Input.Number</span></span> | <span data-ttu-id="f27f7-134">ac 번호 입력</span><span class="sxs-lookup"><span data-stu-id="f27f7-134">ac-numberInput</span></span> |
| <span data-ttu-id="f27f7-135">입력. 텍스트</span><span class="sxs-lookup"><span data-stu-id="f27f7-135">Input.Text</span></span> | <span data-ttu-id="f27f7-136">ac-textInput</span><span class="sxs-lookup"><span data-stu-id="f27f7-136">ac-textInput</span></span> |
| <span data-ttu-id="f27f7-137">입력. 시간</span><span class="sxs-lookup"><span data-stu-id="f27f7-137">Input.Time</span></span> | <span data-ttu-id="f27f7-138">ac timeInput</span><span class="sxs-lookup"><span data-stu-id="f27f7-138">ac-timeInput</span></span> |
| <span data-ttu-id="f27f7-139">입력. 전환</span><span class="sxs-lookup"><span data-stu-id="f27f7-139">Input.Toggle</span></span>| - |
| <span data-ttu-id="f27f7-140">이미지</span><span class="sxs-lookup"><span data-stu-id="f27f7-140">Image</span></span>  | <span data-ttu-id="f27f7-141">ac 이미지</span><span class="sxs-lookup"><span data-stu-id="f27f7-141">ac-image</span></span> |
| <span data-ttu-id="f27f7-142">ImageSet</span><span class="sxs-lookup"><span data-stu-id="f27f7-142">ImageSet</span></span>  | <span data-ttu-id="f27f7-143">ac imageset</span><span class="sxs-lookup"><span data-stu-id="f27f7-143">ac-imageset</span></span> |
| <span data-ttu-id="f27f7-144">FactSet</span><span class="sxs-lookup"><span data-stu-id="f27f7-144">FactSet</span></span> | <span data-ttu-id="f27f7-145">ac-factset</span><span class="sxs-lookup"><span data-stu-id="f27f7-145">ac-factset</span></span> |
| <span data-ttu-id="f27f7-146">TextBlock</span><span class="sxs-lookup"><span data-stu-id="f27f7-146">TextBlock</span></span>  | <span data-ttu-id="f27f7-147">ac textblock</span><span class="sxs-lookup"><span data-stu-id="f27f7-147">ac-textblock</span></span> |