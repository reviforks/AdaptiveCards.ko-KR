---
title: 기본 스타일 지정-JavaScript SDK
author: matthidinger
ms.author: mahiding
ms.date: 11/28/2017
ms.topic: article
ms.openlocfilehash: 6f086d268abcaeb7fa159b74708597e89aafaf53
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552895"
---
# <a name="native-styling---javascript"></a><span data-ttu-id="4384c-102">기본 스타일 지정-JavaScript</span><span class="sxs-lookup"><span data-stu-id="4384c-102">Native styling - JavaScript</span></span>

<span data-ttu-id="4384c-103">카드 HTML의 세부적인 스타일을 지정 하려면 CSS를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4384c-103">Use CSS for fine-grained styling of the card HTML.</span></span>

<span data-ttu-id="4384c-104">다음 CSS 클래스는 다양 한 요소에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4384c-104">The following CSS classes will be added to various elements.</span></span>

| <span data-ttu-id="4384c-105">CSS 클래스</span><span class="sxs-lookup"><span data-stu-id="4384c-105">CSS class</span></span> | <span data-ttu-id="4384c-106">사용법</span><span class="sxs-lookup"><span data-stu-id="4384c-106">Usage</span></span> |
|---|---|
| <span data-ttu-id="4384c-107">. ac-컨테이너</span><span class="sxs-lookup"><span data-stu-id="4384c-107">.ac-container</span></span> | <span data-ttu-id="4384c-108">컨테이너가</span><span class="sxs-lookup"><span data-stu-id="4384c-108">containers</span></span> |
| <span data-ttu-id="4384c-109">. ac를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4384c-109">.ac-selectable</span></span>  | <span data-ttu-id="4384c-110">요소`selectAction`</span><span class="sxs-lookup"><span data-stu-id="4384c-110">elements with `selectAction`</span></span> |
| <span data-ttu-id="4384c-111">. ac 이미지</span><span class="sxs-lookup"><span data-stu-id="4384c-111">.ac-image</span></span> | <span data-ttu-id="4384c-112">image</span><span class="sxs-lookup"><span data-stu-id="4384c-112">image</span></span> |
| <span data-ttu-id="4384c-113">. ac-누름</span><span class="sxs-lookup"><span data-stu-id="4384c-113">.ac-pushButton</span></span> | <span data-ttu-id="4384c-114">단추 처럼 렌더링 된 작업</span><span class="sxs-lookup"><span data-stu-id="4384c-114">actions rendered like buttons</span></span> |
| <span data-ttu-id="4384c-115">. ac-linkButton</span><span class="sxs-lookup"><span data-stu-id="4384c-115">.ac-linkButton</span></span>  | <span data-ttu-id="4384c-116">링크와 같이 렌더링 된 작업</span><span class="sxs-lookup"><span data-stu-id="4384c-116">actions rendered like links</span></span> |
| <span data-ttu-id="4384c-117">. ac 입력</span><span class="sxs-lookup"><span data-stu-id="4384c-117">.ac-input</span></span> | <span data-ttu-id="4384c-118">입력 컨트롤</span><span class="sxs-lookup"><span data-stu-id="4384c-118">input controls</span></span>|
| <span data-ttu-id="4384c-119">. ac-textInput</span><span class="sxs-lookup"><span data-stu-id="4384c-119">.ac-textInput</span></span>| <span data-ttu-id="4384c-120">텍스트 입력</span><span class="sxs-lookup"><span data-stu-id="4384c-120">text input</span></span> |
| <span data-ttu-id="4384c-121">. ac-여러 줄</span><span class="sxs-lookup"><span data-stu-id="4384c-121">.ac-multiline</span></span> | <span data-ttu-id="4384c-122">여러 줄 텍스트 입력</span><span class="sxs-lookup"><span data-stu-id="4384c-122">multiline text input</span></span> |
| <span data-ttu-id="4384c-123">. ac 번호 입력</span><span class="sxs-lookup"><span data-stu-id="4384c-123">.ac-numberInput</span></span> | <span data-ttu-id="4384c-124">숫자 입력</span><span class="sxs-lookup"><span data-stu-id="4384c-124">number input</span></span>|
| <span data-ttu-id="4384c-125">. ac dateInput</span><span class="sxs-lookup"><span data-stu-id="4384c-125">.ac-dateInput</span></span> | <span data-ttu-id="4384c-126">날짜 입력</span><span class="sxs-lookup"><span data-stu-id="4384c-126">date input</span></span>|
| <span data-ttu-id="4384c-127">. ac timeInput</span><span class="sxs-lookup"><span data-stu-id="4384c-127">.ac-timeInput</span></span> | <span data-ttu-id="4384c-128">시간 입력</span><span class="sxs-lookup"><span data-stu-id="4384c-128">time input</span></span> |
| <span data-ttu-id="4384c-129">. ac-multichoiceInput</span><span class="sxs-lookup"><span data-stu-id="4384c-129">.ac-multichoiceInput</span></span> | <span data-ttu-id="4384c-130">multichoice 입력</span><span class="sxs-lookup"><span data-stu-id="4384c-130">multichoice input</span></span>|