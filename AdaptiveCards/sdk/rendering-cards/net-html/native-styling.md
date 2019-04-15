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
# <a name="native-styling---net-html"></a><span data-ttu-id="e0ad2-102">기본 스타일 지정-.NET HTML</span><span class="sxs-lookup"><span data-stu-id="e0ad2-102">Native styling - .NET HTML</span></span>

<span data-ttu-id="e0ad2-103">호스트 구성 것입니다 얻게 하면 대부분의 정도 각 플랫폼에서 가능성이 각 플랫폼에서 몇 가지 기본 스타일 지정을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0ad2-103">While Host Config will get you most of the way there on each platform, it's likely that you will have to do some native styling on each platform.</span></span> 

<span data-ttu-id="e0ad2-104">HTML을 쉽게이 모든 요소에 CSS 클래스를 추가 하 여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0ad2-104">HTML makes this easy by adding CSS classes to every element.</span></span>

| <span data-ttu-id="e0ad2-105">요소</span><span class="sxs-lookup"><span data-stu-id="e0ad2-105">Element</span></span> | <span data-ttu-id="e0ad2-106">CSS 클래스</span><span class="sxs-lookup"><span data-stu-id="e0ad2-106">CSS class</span></span> |
|---|---|
| <span data-ttu-id="e0ad2-107">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="e0ad2-107">AdaptiveCard</span></span> | <span data-ttu-id="e0ad2-108">ac-adaptivecard</span><span class="sxs-lookup"><span data-stu-id="e0ad2-108">ac-adaptivecard</span></span> |
| <span data-ttu-id="e0ad2-109">모든 작업</span><span class="sxs-lookup"><span data-stu-id="e0ad2-109">All Actions</span></span> | <span data-ttu-id="e0ad2-110">ac-pushButton</span><span class="sxs-lookup"><span data-stu-id="e0ad2-110">ac-pushButton</span></span> | 
| <span data-ttu-id="e0ad2-111">작업 선택</span><span class="sxs-lookup"><span data-stu-id="e0ad2-111">Select Actions</span></span> | <span data-ttu-id="e0ad2-112">ac-selectable</span><span class="sxs-lookup"><span data-stu-id="e0ad2-112">ac-selectable</span></span> |
| <span data-ttu-id="e0ad2-113">Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="e0ad2-113">Action.OpenUrl</span></span>  | <span data-ttu-id="e0ad2-114">ac-action-openUrl</span><span class="sxs-lookup"><span data-stu-id="e0ad2-114">ac-action-openUrl</span></span> |
| <span data-ttu-id="e0ad2-115">Action.ShowCard</span><span class="sxs-lookup"><span data-stu-id="e0ad2-115">Action.ShowCard</span></span> | <span data-ttu-id="e0ad2-116">ac-action-showCard</span><span class="sxs-lookup"><span data-stu-id="e0ad2-116">ac-action-showCard</span></span> |
| <span data-ttu-id="e0ad2-117">Action.Submit</span><span class="sxs-lookup"><span data-stu-id="e0ad2-117">Action.Submit</span></span>  | <span data-ttu-id="e0ad2-118">ac-action-submit</span><span class="sxs-lookup"><span data-stu-id="e0ad2-118">ac-action-submit</span></span>  |
| <span data-ttu-id="e0ad2-119">ActionSet</span><span class="sxs-lookup"><span data-stu-id="e0ad2-119">ActionSet</span></span> | <span data-ttu-id="e0ad2-120">ac-actionset</span><span class="sxs-lookup"><span data-stu-id="e0ad2-120">ac-actionset</span></span> |
| <span data-ttu-id="e0ad2-121">Column</span><span class="sxs-lookup"><span data-stu-id="e0ad2-121">Column</span></span> | <span data-ttu-id="e0ad2-122">ac-column</span><span class="sxs-lookup"><span data-stu-id="e0ad2-122">ac-column</span></span> |
| <span data-ttu-id="e0ad2-123">ColumnSet</span><span class="sxs-lookup"><span data-stu-id="e0ad2-123">ColumnSet</span></span> | <span data-ttu-id="e0ad2-124">ac-columnset</span><span class="sxs-lookup"><span data-stu-id="e0ad2-124">ac-columnset</span></span> |
| <span data-ttu-id="e0ad2-125">컨테이너</span><span class="sxs-lookup"><span data-stu-id="e0ad2-125">Container</span></span> | <span data-ttu-id="e0ad2-126">ac-container</span><span class="sxs-lookup"><span data-stu-id="e0ad2-126">ac-container</span></span> |
| <span data-ttu-id="e0ad2-127">모든 입력</span><span class="sxs-lookup"><span data-stu-id="e0ad2-127">All Inputs</span></span> | <span data-ttu-id="e0ad2-128">ac-input</span><span class="sxs-lookup"><span data-stu-id="e0ad2-128">ac-input</span></span> |
| <span data-ttu-id="e0ad2-129">Input.ChoiceSet</span><span class="sxs-lookup"><span data-stu-id="e0ad2-129">Input.ChoiceSet</span></span> | <span data-ttu-id="e0ad2-130">ac-multichoiceInput</span><span class="sxs-lookup"><span data-stu-id="e0ad2-130">ac-multichoiceInput</span></span>  |
| <span data-ttu-id="e0ad2-131">Input.Date</span><span class="sxs-lookup"><span data-stu-id="e0ad2-131">Input.Date</span></span> | <span data-ttu-id="e0ad2-132">ac-dateInput</span><span class="sxs-lookup"><span data-stu-id="e0ad2-132">ac-dateInput</span></span> |
| <span data-ttu-id="e0ad2-133">Input.Number</span><span class="sxs-lookup"><span data-stu-id="e0ad2-133">Input.Number</span></span> | <span data-ttu-id="e0ad2-134">ac-numberInput</span><span class="sxs-lookup"><span data-stu-id="e0ad2-134">ac-numberInput</span></span> |
| <span data-ttu-id="e0ad2-135">Input.Text</span><span class="sxs-lookup"><span data-stu-id="e0ad2-135">Input.Text</span></span> | <span data-ttu-id="e0ad2-136">ac-textInput</span><span class="sxs-lookup"><span data-stu-id="e0ad2-136">ac-textInput</span></span> |
| <span data-ttu-id="e0ad2-137">Input.Time</span><span class="sxs-lookup"><span data-stu-id="e0ad2-137">Input.Time</span></span> | <span data-ttu-id="e0ad2-138">ac-timeInput</span><span class="sxs-lookup"><span data-stu-id="e0ad2-138">ac-timeInput</span></span> |
| <span data-ttu-id="e0ad2-139">Input.Toggle</span><span class="sxs-lookup"><span data-stu-id="e0ad2-139">Input.Toggle</span></span>| - |
| <span data-ttu-id="e0ad2-140">image</span><span class="sxs-lookup"><span data-stu-id="e0ad2-140">Image</span></span>  | <span data-ttu-id="e0ad2-141">ac-image</span><span class="sxs-lookup"><span data-stu-id="e0ad2-141">ac-image</span></span> |
| <span data-ttu-id="e0ad2-142">ImageSet</span><span class="sxs-lookup"><span data-stu-id="e0ad2-142">ImageSet</span></span>  | <span data-ttu-id="e0ad2-143">ac-imageset</span><span class="sxs-lookup"><span data-stu-id="e0ad2-143">ac-imageset</span></span> |
| <span data-ttu-id="e0ad2-144">FactSet</span><span class="sxs-lookup"><span data-stu-id="e0ad2-144">FactSet</span></span> | <span data-ttu-id="e0ad2-145">ac-factset</span><span class="sxs-lookup"><span data-stu-id="e0ad2-145">ac-factset</span></span> |
| <span data-ttu-id="e0ad2-146">TextBlock</span><span class="sxs-lookup"><span data-stu-id="e0ad2-146">TextBlock</span></span>  | <span data-ttu-id="e0ad2-147">ac-textblock</span><span class="sxs-lookup"><span data-stu-id="e0ad2-147">ac-textblock</span></span> |