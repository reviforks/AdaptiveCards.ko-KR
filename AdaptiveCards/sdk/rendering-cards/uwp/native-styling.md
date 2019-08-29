---
title: 기본 스타일 지정-UWP SDK
author: matthidinger
ms.author: mahiding
ms.date: 08/15/2018
ms.topic: article
ms.openlocfilehash: da3b95dc53c55c81fbbbbed6ee7605f86eb427a9
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552525"
---
# <a name="native-styling---uwp"></a><span data-ttu-id="5fde8-102">기본 스타일-UWP</span><span class="sxs-lookup"><span data-stu-id="5fde8-102">Native styling - UWP</span></span>

<span data-ttu-id="5fde8-103">호스트 구성에는 각 플랫폼에 대 한 대부분의 방법이 있지만 각 플랫폼에서 기본 스타일 지정을 수행 해야 할 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fde8-103">While Host Config will get you most of the way there on each platform, it's likely that you will have to do some native styling on each platform.</span></span> 

<span data-ttu-id="5fde8-104">UWP를 사용 하면 세분화 된 스타일, 동작, 애니메이션 등에 대해 ResourceDictionary를 전달할 수 있으므로이를 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fde8-104">UWP makes this easy by allowing you to pass a ResourceDictionary for fine-grained styling, behavior, animations, etc.</span></span>

| <span data-ttu-id="5fde8-105">요소</span><span class="sxs-lookup"><span data-stu-id="5fde8-105">Element</span></span> | <span data-ttu-id="5fde8-106">스타일 이름</span><span class="sxs-lookup"><span data-stu-id="5fde8-106">Style names</span></span> |
|---|---|
| <span data-ttu-id="5fde8-107">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="5fde8-107">AdaptiveCard</span></span> | <span data-ttu-id="5fde8-108">적응 카드</span><span class="sxs-lookup"><span data-stu-id="5fde8-108">Adaptive.Card</span></span>| 
| <span data-ttu-id="5fde8-109">작업. OpenUrl</span><span class="sxs-lookup"><span data-stu-id="5fde8-109">Action.OpenUrl</span></span>  | <span data-ttu-id="5fde8-110">적응. Action. OpenUrl</span><span class="sxs-lookup"><span data-stu-id="5fde8-110">Adaptive.Action.OpenUrl</span></span>  |
| <span data-ttu-id="5fde8-111">작업. ShowCard</span><span class="sxs-lookup"><span data-stu-id="5fde8-111">Action.ShowCard</span></span> | <span data-ttu-id="5fde8-112">적응. 작업 ... ShowCard</span><span class="sxs-lookup"><span data-stu-id="5fde8-112">Adaptive.Action.ShowCard</span></span> |
| <span data-ttu-id="5fde8-113">작업. 제출</span><span class="sxs-lookup"><span data-stu-id="5fde8-113">Action.Submit</span></span>  | <span data-ttu-id="5fde8-114">적응. 작업. 제출</span><span class="sxs-lookup"><span data-stu-id="5fde8-114">Adaptive.Action.Submit</span></span>  |
| <span data-ttu-id="5fde8-115">Column</span><span class="sxs-lookup"><span data-stu-id="5fde8-115">Column</span></span> | <span data-ttu-id="5fde8-116">적응형 열, 적응. 동작 탭</span><span class="sxs-lookup"><span data-stu-id="5fde8-116">Adaptive.Column, Adaptive.Action.Tap</span></span> |
| <span data-ttu-id="5fde8-117">ColumnSet</span><span class="sxs-lookup"><span data-stu-id="5fde8-117">ColumnSet</span></span> | <span data-ttu-id="5fde8-118">ColumnSet, VerticalSeparator</span><span class="sxs-lookup"><span data-stu-id="5fde8-118">Adaptive.ColumnSet, Adaptive.VerticalSeparator</span></span> |
| <span data-ttu-id="5fde8-119">컨테이너</span><span class="sxs-lookup"><span data-stu-id="5fde8-119">Container</span></span> | <span data-ttu-id="5fde8-120">적응 컨테이너</span><span class="sxs-lookup"><span data-stu-id="5fde8-120">Adaptive.Container</span></span>|
| <span data-ttu-id="5fde8-121">ChoiceSet</span><span class="sxs-lookup"><span data-stu-id="5fde8-121">Input.ChoiceSet</span></span> | <span data-ttu-id="5fde8-122">ChoiceSet, ChoiceSet, ChoiceSet, ChoiceSet, ComboBoxItem,, .입니다. .입니다.</span><span class="sxs-lookup"><span data-stu-id="5fde8-122">Adaptive.Input.ChoiceSet,  Adaptive.Input.ChoiceSet.ComboBox, Adaptive.Input.ChoiceSet.CheckBox,  Adaptive.Input.ChoiceSet.Radio,  Adaptive.Input.ChoiceSet.ComboBoxItem</span></span> |
| <span data-ttu-id="5fde8-123">입력. 날짜</span><span class="sxs-lookup"><span data-stu-id="5fde8-123">Input.Date</span></span> | <span data-ttu-id="5fde8-124">적응형. 텍스트. 날짜</span><span class="sxs-lookup"><span data-stu-id="5fde8-124">Adaptive.Input.Text.Date</span></span>
| <span data-ttu-id="5fde8-125">입력. Number</span><span class="sxs-lookup"><span data-stu-id="5fde8-125">Input.Number</span></span> | <span data-ttu-id="5fde8-126">적응형. 텍스트 번호</span><span class="sxs-lookup"><span data-stu-id="5fde8-126">Adaptive.Input.Text.Number</span></span> |
| <span data-ttu-id="5fde8-127">입력. 텍스트</span><span class="sxs-lookup"><span data-stu-id="5fde8-127">Input.Text</span></span> | <span data-ttu-id="5fde8-128">적응형. 입력. 텍스트</span><span class="sxs-lookup"><span data-stu-id="5fde8-128">Adaptive.Input.Text</span></span> |
| <span data-ttu-id="5fde8-129">입력. 시간</span><span class="sxs-lookup"><span data-stu-id="5fde8-129">Input.Time</span></span> | <span data-ttu-id="5fde8-130">적응. 텍스트. 시간</span><span class="sxs-lookup"><span data-stu-id="5fde8-130">Adaptive.Input.Text.Time</span></span> |
| <span data-ttu-id="5fde8-131">입력. 전환</span><span class="sxs-lookup"><span data-stu-id="5fde8-131">Input.Toggle</span></span>| <span data-ttu-id="5fde8-132">적응형. 입력. 전환</span><span class="sxs-lookup"><span data-stu-id="5fde8-132">Adaptive.Input.Toggle</span></span>|
| <span data-ttu-id="5fde8-133">이미지</span><span class="sxs-lookup"><span data-stu-id="5fde8-133">Image</span></span>  | <span data-ttu-id="5fde8-134">적응. 이미지</span><span class="sxs-lookup"><span data-stu-id="5fde8-134">Adaptive.Image</span></span> |
| <span data-ttu-id="5fde8-135">ImageSet</span><span class="sxs-lookup"><span data-stu-id="5fde8-135">ImageSet</span></span>  | <span data-ttu-id="5fde8-136">적응 ImageSet</span><span class="sxs-lookup"><span data-stu-id="5fde8-136">Adaptive.ImageSet</span></span> |
| <span data-ttu-id="5fde8-137">FactSet</span><span class="sxs-lookup"><span data-stu-id="5fde8-137">FactSet</span></span> | <span data-ttu-id="5fde8-138">FactSet, 적응. fact.-Value</span><span class="sxs-lookup"><span data-stu-id="5fde8-138">Adaptive.FactSet, Adaptive.Fact.Title, Adaptive.Fact.Value</span></span> |
| <span data-ttu-id="5fde8-139">TextBlock</span><span class="sxs-lookup"><span data-stu-id="5fde8-139">TextBlock</span></span>  | <span data-ttu-id="5fde8-140">적응형. TextBlock</span><span class="sxs-lookup"><span data-stu-id="5fde8-140">Adaptive.TextBlock</span></span> |

<span data-ttu-id="5fde8-141">이 샘플 XAML 리소스 사전은 모든 Textblock의 배경을 바다색으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fde8-141">This sample XAML Resource dictionary that sets the background of all TextBlocks to Aqua.</span></span> <span data-ttu-id="5fde8-142">이 작업 보다 더 고급 작업을 원하는 경우😁</span><span class="sxs-lookup"><span data-stu-id="5fde8-142">You will probably want something more advanced than this 😁</span></span>

```xml
<ResourceDictionary
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" 
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
    <Style x:Key="Adaptive.TextBlock" TargetType="TextBlock">
        <Setter Property="Background" Value="Aqua"></Setter>
    </Style>
</ResourceDictionary>
```
```csharp
// Use a ResourceDictionary instance
// DON'T use this property if rendering from a server
renderer.Resources = myResourceDictionary;
```
