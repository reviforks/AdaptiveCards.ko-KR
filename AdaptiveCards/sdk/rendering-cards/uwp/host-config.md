---
title: 호스트 구성-UWP SDK
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 85c8807d2a368e00b414b427fae8a9f0253873c8
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553675"
---
# <a name="host-config---uwp"></a>호스트 구성-UWP

렌더러에 맞게 HostConfig 개체의 인스턴스를 제공 합니다. (참조 [호스트 구성 스키마](../../../rendering-cards/host-config.md) 전체 설명 합니다.)

> HostConfig 개체를 변경 하려는 속성만 설정할 수 있는 기본값을 사용 하 여 인스턴스화할 수 있습니다.

예:

```csharp
var hostConfig = new AdaptiveHostConfig() 
{
    FontSizes = {
        Small = 15,
        Normal = 20,
        Medium = 25,
        Large = 30,
        ExtraLarge= 40
    }
};
renderer.HostConfig = hostConfig;
```

> 또는 JSON 문자열에서는 HostConfig를 로드할 수 있습니다.

예:

```csharp
var hostConfig = AdaptiveHostConfig.FromJsonString(jsonString); 

renderer.HostConfig = hostConfig;
```

UWPRenderer에 전달할 때 HostConfig 모든 카드를 렌더링 하는 데 기본을 설정 됩니다.