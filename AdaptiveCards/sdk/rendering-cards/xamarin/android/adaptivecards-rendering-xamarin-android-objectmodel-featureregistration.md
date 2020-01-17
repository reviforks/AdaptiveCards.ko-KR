---
title: FeatureRegistration 클래스-Xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: c1975197996e54626b464abe9181f0b02895ee4d
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76146147"
---
# <a name="feature-registration"></a><span data-ttu-id="2dc09-102">기능 등록</span><span class="sxs-lookup"><span data-stu-id="2dc09-102">Feature Registration</span></span>

```csharp
public class FeatureRegistration : Java.Lang.Object 
```

<span data-ttu-id="2dc09-103">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="2dc09-103">**Namespace**</span></span>
```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.ObjectModel
```

## <a name="summary"></a><span data-ttu-id="2dc09-104">요약</span><span class="sxs-lookup"><span data-stu-id="2dc09-104">Summary</span></span>

| <span data-ttu-id="2dc09-105">public 메서드</span><span class="sxs-lookup"><span data-stu-id="2dc09-105">Public methods</span></span> | |
| --- | ---- |
| ```void``` | [```AddFeature(string featureName, string featureVersion)```](#addfeature) |
| ```string``` | [```GetFeatureVersion(string featureName)```](#getfeatureversion) |
| ```void``` | [```RemoveFeature (string featureName)```](#removefeature) |

## <a name="public-methods"></a><span data-ttu-id="2dc09-106">공용 메서드</span><span class="sxs-lookup"><span data-stu-id="2dc09-106">Public Methods</span></span>

---

### <a id="addfeature"></a><span data-ttu-id="2dc09-107">AddFeature</span><span class="sxs-lookup"><span data-stu-id="2dc09-107">AddFeature</span></span>
<p style='text-align:right'><span data-ttu-id="2dc09-108">버전 0.1.0에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="2dc09-108">Added in version 0.1.0</span></span></p>

```csharp
public void AddFeature (string featureName, 
                        string featureVersion)
```

<span data-ttu-id="2dc09-109">이름 및 버전이 포함 된 기능을 렌더러 기능 등록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dc09-109">Adds a feature containing its name and version to the renderer feature registration.</span></span>

| <span data-ttu-id="2dc09-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2dc09-110">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="2dc09-111">featureName</span><span class="sxs-lookup"><span data-stu-id="2dc09-111">featureName</span></span> | ```string``` |
| <span data-ttu-id="2dc09-112">featureVersion</span><span class="sxs-lookup"><span data-stu-id="2dc09-112">featureVersion</span></span> | ```string``` |

#### <a name="sample"></a><span data-ttu-id="2dc09-113">샘플</span><span class="sxs-lookup"><span data-stu-id="2dc09-113">Sample</span></span>

```csharp
FeatureRegistration featureRegistration = new FeatureRegistration();
featureRegistration.AddFeature("MyFeature", "1.2.0");
CardRendererRegistration.Instance.RegisterFeatureRegistration(featureRegistration);
```

---

### <a id="getfeatureversion"></a><span data-ttu-id="2dc09-114">GetFeatureVersion</span><span class="sxs-lookup"><span data-stu-id="2dc09-114">GetFeatureVersion</span></span>
<p style='text-align:right'><span data-ttu-id="2dc09-115">버전 0.1.0에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="2dc09-115">Added in version 0.1.0</span></span></p>

```csharp
public string GetFeatureVersion (string featureName)
```

<span data-ttu-id="2dc09-116">지정 된 기능의 버전을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dc09-116">Retrieves the version for a given feature.</span></span> 

| <span data-ttu-id="2dc09-117">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2dc09-117">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="2dc09-118">featureName</span><span class="sxs-lookup"><span data-stu-id="2dc09-118">featureName</span></span> | ```string``` |

| <span data-ttu-id="2dc09-119">Returns</span><span class="sxs-lookup"><span data-stu-id="2dc09-119">Returns</span></span> | |
| --- | --- |
| ```string``` | <span data-ttu-id="2dc09-120">지정 된 기능의 기능 버전</span><span class="sxs-lookup"><span data-stu-id="2dc09-120">Feature version for the given feature</span></span> |

#### <a name="sample"></a><span data-ttu-id="2dc09-121">샘플</span><span class="sxs-lookup"><span data-stu-id="2dc09-121">Sample</span></span>

```csharp
FeatureRegistration featureRegistration = new FeatureRegistration();
featureRegistration.AddFeature("MyFeature", "1.2.0");
string featureVersion = featureRegistration.GetFeatureVersion("MyFeature"); // 1.2.0
```

---

### <a id="removefeature"></a><span data-ttu-id="2dc09-122">RemoveFeature</span><span class="sxs-lookup"><span data-stu-id="2dc09-122">RemoveFeature</span></span>
<p style='text-align:right'><span data-ttu-id="2dc09-123">버전 0.1.0에 추가 됨</span><span class="sxs-lookup"><span data-stu-id="2dc09-123">Added in version 0.1.0</span></span></p>

```csharp
public void RemoveFeature (string featureName)
```

<span data-ttu-id="2dc09-124">기능 사전에서 지정 된 기능을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dc09-124">Removes the given feature from the feature dictionary.</span></span>

| <span data-ttu-id="2dc09-125">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2dc09-125">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="2dc09-126">featureName</span><span class="sxs-lookup"><span data-stu-id="2dc09-126">featureName</span></span> | ```string``` |

#### <a name="sample"></a><span data-ttu-id="2dc09-127">샘플</span><span class="sxs-lookup"><span data-stu-id="2dc09-127">Sample</span></span>

```csharp
FeatureRegistration featureRegistration = new FeatureRegistration();
featureRegistration.AddFeature("MyFeature", "1.2.0");
featureRegistration.RemoveFeature("MyFeature");
```