---
title: 호스트 구성-.NET WPF SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: c3414860ee9822a02dbf36ff11fd83488fedf34e
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552915"
---
# <a name="host-config---net-wpf"></a>호스트 구성-.NET WPF

A [호스트 구성](../../../rendering-cards/host-config.md) 은 일부 렌더러에서 이해 하는 공유 구성 개체입니다. 이 옵션을 사용 하면 (예: 글꼴 패밀리, 글꼴 크기를 기본 간격) 공통 스타일 및 각 플랫폼 렌더러를 통해 자동으로 해석 될 동작 (예: 작업의 최대 수)를 정의할 수 있습니다. 

목표는 각 플랫폼 렌더러에 의해 생성 된 네이티브 UI를 사용자의 최소한의 작업 에서도 이와 비슷한 방법이 표시 됩니다.

```csharp
// Construct programmatically
renderer.HostConfig = new AdaptiveHostConfig() 
{
    FontFamily = "Comic Sans",
    FontSizes = {
        Small = 15,
        Default = 20,
        Medium = 25,
        Large = 30,
        ExtraLarge= 40
    }
};

// Or parse from JSON
renderer.HostConfig  = AdaptiveHostConfig.FromJson(@"{
    ""fontFamily"": ""Comic Sans"",
    ""fontSizes"": {
        ""small"": 25,
        ""default"": 26,
        ""medium"": 27,
        ""large"": 28,
        ""extraLarge"": 29
    }
}");
```