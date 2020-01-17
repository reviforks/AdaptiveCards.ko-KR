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
# <a name="feature-registration"></a>기능 등록

```csharp
public class FeatureRegistration : Java.Lang.Object 
```

**Namespace**
```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.ObjectModel
```

## <a name="summary"></a>요약

| public 메서드 | |
| --- | ---- |
| ```void``` | [```AddFeature(string featureName, string featureVersion)```](#addfeature) |
| ```string``` | [```GetFeatureVersion(string featureName)```](#getfeatureversion) |
| ```void``` | [```RemoveFeature (string featureName)```](#removefeature) |

## <a name="public-methods"></a>공용 메서드

---

### <a id="addfeature"></a>AddFeature
<p style='text-align:right'>버전 0.1.0에 추가 됨</p>

```csharp
public void AddFeature (string featureName, 
                        string featureVersion)
```

이름 및 버전이 포함 된 기능을 렌더러 기능 등록에 추가 합니다.

| 매개 변수 | |
| --- | --- |
| featureName | ```string``` |
| featureVersion | ```string``` |

#### <a name="sample"></a>샘플

```csharp
FeatureRegistration featureRegistration = new FeatureRegistration();
featureRegistration.AddFeature("MyFeature", "1.2.0");
CardRendererRegistration.Instance.RegisterFeatureRegistration(featureRegistration);
```

---

### <a id="getfeatureversion"></a>GetFeatureVersion
<p style='text-align:right'>버전 0.1.0에 추가 됨</p>

```csharp
public string GetFeatureVersion (string featureName)
```

지정 된 기능의 버전을 검색 합니다. 

| 매개 변수 | |
| --- | --- |
| featureName | ```string``` |

| Returns | |
| --- | --- |
| ```string``` | 지정 된 기능의 기능 버전 |

#### <a name="sample"></a>샘플

```csharp
FeatureRegistration featureRegistration = new FeatureRegistration();
featureRegistration.AddFeature("MyFeature", "1.2.0");
string featureVersion = featureRegistration.GetFeatureVersion("MyFeature"); // 1.2.0
```

---

### <a id="removefeature"></a>RemoveFeature
<p style='text-align:right'>버전 0.1.0에 추가 됨</p>

```csharp
public void RemoveFeature (string featureName)
```

기능 사전에서 지정 된 기능을 제거 합니다.

| 매개 변수 | |
| --- | --- |
| featureName | ```string``` |

#### <a name="sample"></a>샘플

```csharp
FeatureRegistration featureRegistration = new FeatureRegistration();
featureRegistration.AddFeature("MyFeature", "1.2.0");
featureRegistration.RemoveFeature("MyFeature");
```