---
title: RenderedAdaptiveCard 클래스-Xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: 608b28638ce6ed0a218cfc8dbbe73f22de1ab8cb
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145997"
---
# <a name="renderedadaptivecard"></a><span data-ttu-id="afe51-102">RenderedAdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="afe51-102">RenderedAdaptiveCard</span></span>

```csharp
public class RenderedAdaptiveCard : Java.Lang.Object
```

<span data-ttu-id="afe51-103">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="afe51-103">**Namespace**</span></span>

```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.Renderer
```

### <a name="summary"></a><span data-ttu-id="afe51-104">요약</span><span class="sxs-lookup"><span data-stu-id="afe51-104">Summary</span></span>

| <span data-ttu-id="afe51-105">특성</span><span class="sxs-lookup"><span data-stu-id="afe51-105">Attributes</span></span> | |
| ---- | --- |
| <span data-ttu-id="afe51-106">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="afe51-106">AdaptiveCard</span></span> | <span data-ttu-id="afe51-107">렌더링 된 적응 카드의 논리적 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="afe51-107">Logical representation of the rendered adaptive card.</span></span> |
| <span data-ttu-id="afe51-108">입력</span><span class="sxs-lookup"><span data-stu-id="afe51-108">Inputs</span></span> | <span data-ttu-id="afe51-109">사용자가 추가한 입력 요소의 사전 및 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="afe51-109">Dictionary of input element and information added by the user.</span></span> |
| <span data-ttu-id="afe51-110">&gt;</span><span class="sxs-lookup"><span data-stu-id="afe51-110">View</span></span> | <span data-ttu-id="afe51-111">렌더링 프로세스의 시각적 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="afe51-111">Visual result from the rendering process.</span></span> |
| <span data-ttu-id="afe51-112">경고</span><span class="sxs-lookup"><span data-stu-id="afe51-112">Warnings</span></span> | <span data-ttu-id="afe51-113">렌더링 프로세스에서 생성 된 경고 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="afe51-113">List of warnings produced from the rendering process.</span></span> |

&nbsp;

| <span data-ttu-id="afe51-114">public 메서드</span><span class="sxs-lookup"><span data-stu-id="afe51-114">Public methods</span></span> | |
| --- | ---- |
| ```void``` | [```AddWarning AdaptiveCards.Rendering.Xamarin.Android.Renderer.AdaptiveWarning warning)```](#addwarning) |

## <a name="public-methods"></a><span data-ttu-id="afe51-115">공용 메서드</span><span class="sxs-lookup"><span data-stu-id="afe51-115">Public Methods</span></span>

---

### <a id="addwarning"></a><span data-ttu-id="afe51-116">AddWarning</span><span class="sxs-lookup"><span data-stu-id="afe51-116">AddWarning</span></span>
<p style='text-align:right'><span data-ttu-id="afe51-117">버전 0.1에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="afe51-117">Added in version 0.1</span></span></p>

```csharp
public void AddWarning (AdaptiveWarning warning)

```

<span data-ttu-id="afe51-118">경고 목록에 경고를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="afe51-118">Adds a warning to the warning list.</span></span>

| <span data-ttu-id="afe51-119">매개 변수</span><span class="sxs-lookup"><span data-stu-id="afe51-119">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="afe51-120">경고</span><span class="sxs-lookup"><span data-stu-id="afe51-120">warning</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.Renderer.AdaptiveWarning``` |
