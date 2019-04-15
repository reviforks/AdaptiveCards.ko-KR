---
title: 기본 스타일-UWP SDK
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
# <a name="native-styling---uwp"></a><span data-ttu-id="58a74-102">기본 스타일-UWP</span><span class="sxs-lookup"><span data-stu-id="58a74-102">Native styling - UWP</span></span>

<span data-ttu-id="58a74-103">호스트 구성 것입니다 얻게 하면 대부분의 정도 각 플랫폼에서 가능성이 각 플랫폼에서 몇 가지 기본 스타일 지정을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58a74-103">While Host Config will get you most of the way there on each platform, it's likely that you will have to do some native styling on each platform.</span></span> 

<span data-ttu-id="58a74-104">UWP 쉽게이 세분화 된 스타일, 동작, 애니메이션 등 ResourceDictionary를 전달할 수 있도록 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="58a74-104">UWP makes this easy by allowing you to pass a ResourceDictionary for fine-grained styling, behavior, animations, etc.</span></span>

| <span data-ttu-id="58a74-105">요소</span><span class="sxs-lookup"><span data-stu-id="58a74-105">Element</span></span> | <span data-ttu-id="58a74-106">유형 이름</span><span class="sxs-lookup"><span data-stu-id="58a74-106">Style names</span></span> |
|---|---|
| <span data-ttu-id="58a74-107">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="58a74-107">AdaptiveCard</span></span> | <span data-ttu-id="58a74-108">Adaptive.Card</span><span class="sxs-lookup"><span data-stu-id="58a74-108">Adaptive.Card</span></span>| 
| <span data-ttu-id="58a74-109">Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="58a74-109">Action.OpenUrl</span></span>  | <span data-ttu-id="58a74-110">Adaptive.Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="58a74-110">Adaptive.Action.OpenUrl</span></span>  |
| <span data-ttu-id="58a74-111">Action.ShowCard</span><span class="sxs-lookup"><span data-stu-id="58a74-111">Action.ShowCard</span></span> | <span data-ttu-id="58a74-112">Adaptive.Action.ShowCard</span><span class="sxs-lookup"><span data-stu-id="58a74-112">Adaptive.Action.ShowCard</span></span> |
| <span data-ttu-id="58a74-113">Action.Submit</span><span class="sxs-lookup"><span data-stu-id="58a74-113">Action.Submit</span></span>  | <span data-ttu-id="58a74-114">Adaptive.Action.Submit</span><span class="sxs-lookup"><span data-stu-id="58a74-114">Adaptive.Action.Submit</span></span>  |
| <span data-ttu-id="58a74-115">Column</span><span class="sxs-lookup"><span data-stu-id="58a74-115">Column</span></span> | <span data-ttu-id="58a74-116">Adaptive.Column, Adaptive.Action.Tap</span><span class="sxs-lookup"><span data-stu-id="58a74-116">Adaptive.Column, Adaptive.Action.Tap</span></span> |
| <span data-ttu-id="58a74-117">ColumnSet</span><span class="sxs-lookup"><span data-stu-id="58a74-117">ColumnSet</span></span> | <span data-ttu-id="58a74-118">Adaptive.ColumnSet, Adaptive.VerticalSeparator</span><span class="sxs-lookup"><span data-stu-id="58a74-118">Adaptive.ColumnSet, Adaptive.VerticalSeparator</span></span> |
| <span data-ttu-id="58a74-119">컨테이너</span><span class="sxs-lookup"><span data-stu-id="58a74-119">Container</span></span> | <span data-ttu-id="58a74-120">Adaptive.Container</span><span class="sxs-lookup"><span data-stu-id="58a74-120">Adaptive.Container</span></span>|
| <span data-ttu-id="58a74-121">Input.ChoiceSet</span><span class="sxs-lookup"><span data-stu-id="58a74-121">Input.ChoiceSet</span></span> | <span data-ttu-id="58a74-122">Adaptive.Input.ChoiceSet,  Adaptive.Input.ChoiceSet.ComboBox, Adaptive.Input.ChoiceSet.CheckBox,  Adaptive.Input.ChoiceSet.Radio,  Adaptive.Input.ChoiceSet.ComboBoxItem</span><span class="sxs-lookup"><span data-stu-id="58a74-122">Adaptive.Input.ChoiceSet,  Adaptive.Input.ChoiceSet.ComboBox, Adaptive.Input.ChoiceSet.CheckBox,  Adaptive.Input.ChoiceSet.Radio,  Adaptive.Input.ChoiceSet.ComboBoxItem</span></span> |
| <span data-ttu-id="58a74-123">Input.Date</span><span class="sxs-lookup"><span data-stu-id="58a74-123">Input.Date</span></span> | <span data-ttu-id="58a74-124">Adaptive.Input.Text.Date</span><span class="sxs-lookup"><span data-stu-id="58a74-124">Adaptive.Input.Text.Date</span></span>
| <span data-ttu-id="58a74-125">Input.Number</span><span class="sxs-lookup"><span data-stu-id="58a74-125">Input.Number</span></span> | <span data-ttu-id="58a74-126">Adaptive.Input.Text.Number</span><span class="sxs-lookup"><span data-stu-id="58a74-126">Adaptive.Input.Text.Number</span></span> |
| <span data-ttu-id="58a74-127">Input.Text</span><span class="sxs-lookup"><span data-stu-id="58a74-127">Input.Text</span></span> | <span data-ttu-id="58a74-128">Adaptive.Input.Text</span><span class="sxs-lookup"><span data-stu-id="58a74-128">Adaptive.Input.Text</span></span> |
| <span data-ttu-id="58a74-129">Input.Time</span><span class="sxs-lookup"><span data-stu-id="58a74-129">Input.Time</span></span> | <span data-ttu-id="58a74-130">Adaptive.Input.Text.Time</span><span class="sxs-lookup"><span data-stu-id="58a74-130">Adaptive.Input.Text.Time</span></span> |
| <span data-ttu-id="58a74-131">Input.Toggle</span><span class="sxs-lookup"><span data-stu-id="58a74-131">Input.Toggle</span></span>| <span data-ttu-id="58a74-132">Adaptive.Input.Toggle</span><span class="sxs-lookup"><span data-stu-id="58a74-132">Adaptive.Input.Toggle</span></span>|
| <span data-ttu-id="58a74-133">image</span><span class="sxs-lookup"><span data-stu-id="58a74-133">Image</span></span>  | <span data-ttu-id="58a74-134">Adaptive.Image</span><span class="sxs-lookup"><span data-stu-id="58a74-134">Adaptive.Image</span></span> |
| <span data-ttu-id="58a74-135">ImageSet</span><span class="sxs-lookup"><span data-stu-id="58a74-135">ImageSet</span></span>  | <span data-ttu-id="58a74-136">Adaptive.ImageSet</span><span class="sxs-lookup"><span data-stu-id="58a74-136">Adaptive.ImageSet</span></span> |
| <span data-ttu-id="58a74-137">FactSet</span><span class="sxs-lookup"><span data-stu-id="58a74-137">FactSet</span></span> | <span data-ttu-id="58a74-138">Adaptive.FactSet, Adaptive.Fact.Title, Adaptive.Fact.Value</span><span class="sxs-lookup"><span data-stu-id="58a74-138">Adaptive.FactSet, Adaptive.Fact.Title, Adaptive.Fact.Value</span></span> |
| <span data-ttu-id="58a74-139">TextBlock</span><span class="sxs-lookup"><span data-stu-id="58a74-139">TextBlock</span></span>  | <span data-ttu-id="58a74-140">Adaptive.TextBlock</span><span class="sxs-lookup"><span data-stu-id="58a74-140">Adaptive.TextBlock</span></span> |

<span data-ttu-id="58a74-141">모든 Textblock의 배경색을 바다색으로 설정 된이 샘플 XAML 리소스 사전입니다.</span><span class="sxs-lookup"><span data-stu-id="58a74-141">This sample XAML Resource dictionary that sets the background of all TextBlocks to Aqua.</span></span> <span data-ttu-id="58a74-142">싶을 것이 보다 고급 항목 😁</span><span class="sxs-lookup"><span data-stu-id="58a74-142">You will probably want something more advanced than this 😁</span></span>

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
