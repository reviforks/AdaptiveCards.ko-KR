---
title: 기본 스타일 지정-.NET WPF SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: ee5bec1a11f39ad69d40e57410c105b50ba45981
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552725"
---
# <a name="native-styling---net-wpf"></a><span data-ttu-id="eb3af-102">기본 스타일 지정-.NET WPF</span><span class="sxs-lookup"><span data-stu-id="eb3af-102">Native styling - .NET WPF</span></span>

<span data-ttu-id="eb3af-103">호스트 구성에는 각 플랫폼에 대 한 대부분의 방법이 있지만 각 플랫폼에서 기본 스타일 지정을 수행 해야 할 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3af-103">While Host Config will get you most of the way there on each platform, it's likely that you will have to do some native styling on each platform.</span></span> 

<span data-ttu-id="eb3af-104">WPF를 사용 하면 세분화 된 스타일, 동작, 애니메이션 등에 대해 ResourceDictionary를 전달할 수 있으므로이를 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3af-104">WPF makes this easy by allowing you to pass a ResourceDictionary for fine-grained styling, behavior, animations, etc.</span></span>

| <span data-ttu-id="eb3af-105">요소</span><span class="sxs-lookup"><span data-stu-id="eb3af-105">Element</span></span> | <span data-ttu-id="eb3af-106">스타일 이름</span><span class="sxs-lookup"><span data-stu-id="eb3af-106">Style names</span></span> |
|---|---|
| <span data-ttu-id="eb3af-107">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="eb3af-107">AdaptiveCard</span></span> | <span data-ttu-id="eb3af-108">적응 카드</span><span class="sxs-lookup"><span data-stu-id="eb3af-108">Adaptive.Card</span></span>| 
| <span data-ttu-id="eb3af-109">작업. OpenUrl</span><span class="sxs-lookup"><span data-stu-id="eb3af-109">Action.OpenUrl</span></span>  | <span data-ttu-id="eb3af-110">적응. Action. OpenUrl</span><span class="sxs-lookup"><span data-stu-id="eb3af-110">Adaptive.Action.OpenUrl</span></span>  |
| <span data-ttu-id="eb3af-111">작업. ShowCard</span><span class="sxs-lookup"><span data-stu-id="eb3af-111">Action.ShowCard</span></span> | <span data-ttu-id="eb3af-112">적응. 작업 ... ShowCard</span><span class="sxs-lookup"><span data-stu-id="eb3af-112">Adaptive.Action.ShowCard</span></span> |
| <span data-ttu-id="eb3af-113">작업. 제출</span><span class="sxs-lookup"><span data-stu-id="eb3af-113">Action.Submit</span></span>  | <span data-ttu-id="eb3af-114">적응. 작업. 제출</span><span class="sxs-lookup"><span data-stu-id="eb3af-114">Adaptive.Action.Submit</span></span>  |
| <span data-ttu-id="eb3af-115">Column</span><span class="sxs-lookup"><span data-stu-id="eb3af-115">Column</span></span> | <span data-ttu-id="eb3af-116">적응형 열, 적응. 동작 탭</span><span class="sxs-lookup"><span data-stu-id="eb3af-116">Adaptive.Column, Adaptive.Action.Tap</span></span> |
| <span data-ttu-id="eb3af-117">ColumnSet</span><span class="sxs-lookup"><span data-stu-id="eb3af-117">ColumnSet</span></span> | <span data-ttu-id="eb3af-118">ColumnSet, VerticalSeparator</span><span class="sxs-lookup"><span data-stu-id="eb3af-118">Adaptive.ColumnSet, Adaptive.VerticalSeparator</span></span> |
| <span data-ttu-id="eb3af-119">컨테이너</span><span class="sxs-lookup"><span data-stu-id="eb3af-119">Container</span></span> | <span data-ttu-id="eb3af-120">적응 컨테이너</span><span class="sxs-lookup"><span data-stu-id="eb3af-120">Adaptive.Container</span></span>|
| <span data-ttu-id="eb3af-121">ChoiceSet</span><span class="sxs-lookup"><span data-stu-id="eb3af-121">Input.ChoiceSet</span></span> | <span data-ttu-id="eb3af-122">ChoiceSet, ChoiceSet, ChoiceSet, ChoiceSet, ComboBoxItem,, .입니다. .입니다.</span><span class="sxs-lookup"><span data-stu-id="eb3af-122">Adaptive.Input.ChoiceSet,  Adaptive.Input.ChoiceSet.ComboBox, Adaptive.Input.ChoiceSet.CheckBox,  Adaptive.Input.ChoiceSet.Radio,  Adaptive.Input.ChoiceSet.ComboBoxItem</span></span> |
| <span data-ttu-id="eb3af-123">입력. 날짜</span><span class="sxs-lookup"><span data-stu-id="eb3af-123">Input.Date</span></span> | <span data-ttu-id="eb3af-124">적응형. 텍스트. 날짜</span><span class="sxs-lookup"><span data-stu-id="eb3af-124">Adaptive.Input.Text.Date</span></span>
| <span data-ttu-id="eb3af-125">입력. Number</span><span class="sxs-lookup"><span data-stu-id="eb3af-125">Input.Number</span></span> | <span data-ttu-id="eb3af-126">적응형. 텍스트 번호</span><span class="sxs-lookup"><span data-stu-id="eb3af-126">Adaptive.Input.Text.Number</span></span> |
| <span data-ttu-id="eb3af-127">입력. 텍스트</span><span class="sxs-lookup"><span data-stu-id="eb3af-127">Input.Text</span></span> | <span data-ttu-id="eb3af-128">적응형. 입력. 텍스트</span><span class="sxs-lookup"><span data-stu-id="eb3af-128">Adaptive.Input.Text</span></span> |
| <span data-ttu-id="eb3af-129">입력. 시간</span><span class="sxs-lookup"><span data-stu-id="eb3af-129">Input.Time</span></span> | <span data-ttu-id="eb3af-130">적응. 텍스트. 시간</span><span class="sxs-lookup"><span data-stu-id="eb3af-130">Adaptive.Input.Text.Time</span></span> |
| <span data-ttu-id="eb3af-131">입력. 전환</span><span class="sxs-lookup"><span data-stu-id="eb3af-131">Input.Toggle</span></span>| <span data-ttu-id="eb3af-132">적응형. 입력. 전환</span><span class="sxs-lookup"><span data-stu-id="eb3af-132">Adaptive.Input.Toggle</span></span>|
| <span data-ttu-id="eb3af-133">이미지</span><span class="sxs-lookup"><span data-stu-id="eb3af-133">Image</span></span>  | <span data-ttu-id="eb3af-134">적응. 이미지</span><span class="sxs-lookup"><span data-stu-id="eb3af-134">Adaptive.Image</span></span> |
| <span data-ttu-id="eb3af-135">ImageSet</span><span class="sxs-lookup"><span data-stu-id="eb3af-135">ImageSet</span></span>  | <span data-ttu-id="eb3af-136">적응 ImageSet</span><span class="sxs-lookup"><span data-stu-id="eb3af-136">Adaptive.ImageSet</span></span> |
| <span data-ttu-id="eb3af-137">FactSet</span><span class="sxs-lookup"><span data-stu-id="eb3af-137">FactSet</span></span> | <span data-ttu-id="eb3af-138">FactSet, 적응. fact.-Value</span><span class="sxs-lookup"><span data-stu-id="eb3af-138">Adaptive.FactSet, Adaptive.Fact.Title, Adaptive.Fact.Value</span></span> |
| <span data-ttu-id="eb3af-139">TextBlock</span><span class="sxs-lookup"><span data-stu-id="eb3af-139">TextBlock</span></span>  | <span data-ttu-id="eb3af-140">적응형. TextBlock</span><span class="sxs-lookup"><span data-stu-id="eb3af-140">Adaptive.TextBlock</span></span> |

<span data-ttu-id="eb3af-141">이 샘플 XAML 리소스 사전은 모든 Textblock의 배경을 바다색으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3af-141">This sample XAML Resource dictionary that sets the background of all TextBlocks to Aqua.</span></span> <span data-ttu-id="eb3af-142">이 작업 보다 더 고급 작업을 원하는 경우😁</span><span class="sxs-lookup"><span data-stu-id="eb3af-142">You will probably want something more advanced than this 😁</span></span>

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

// ... or load it from a file path
// USE this if rendering from a server
renderer.ResourcesPath = <path-to-my-resource-dictionary.xaml>;
```

> [!IMPORTANT]
> <span data-ttu-id="eb3af-143">**서버 쪽 이미지 생성에 대 한 참고 사항** WPF 렌더러는 서버측 이미지 `RenderCardToImageAsync` 생성에 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3af-143">**A note about server-side image generation** The WPF renderer provides a `RenderCardToImageAsync` method that can be used for server-side image generation.</span></span> <span data-ttu-id="eb3af-144">이 환경에서 사용 하 `ResourcesPath` 는 경우에만 속성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3af-144">You must only use the `ResourcesPath` property if used in this environment.</span></span> <span data-ttu-id="eb3af-145">자세한 내용은 [이미지 렌더링](../net-image/getting-started.md) 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eb3af-145">See the [Image Rendering](../net-image/getting-started.md) docs for more</span></span>