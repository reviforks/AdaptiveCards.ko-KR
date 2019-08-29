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

렌더러를 사용자 지정 하려면 HostConfig 개체의 인스턴스를 제공 합니다. 전체 설명은 [호스트 구성 스키마](../../../rendering-cards/host-config.md) 를 참조 하세요.

> HostConfig 개체는 기본값으로 인스턴스화되기 때문에 변경 하려는 속성만 설정할 수 있습니다.

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

> 또는 JSON 문자열에서 HostConfig를 로드할 수 있습니다.

예:

```csharp
var hostConfig = AdaptiveHostConfig.FromJsonString(jsonString); 

renderer.HostConfig = hostConfig;
```

UWPRenderer에 전달할 때 렌더링 하는 모든 카드에 사용할 기본 HostConfig를 설정 하 게 됩니다.