---
title: 호스트 구성-.NET HTML SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: dc5b6767d5f8611111b56f30f05a7b5fc8d1cbf4
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552415"
---
# <a name="host-config---net-html"></a>호스트 구성-.NET HTML

[호스트 구성](../../../rendering-cards/host-config.md)은 모든 렌더러가 이해하는 공유 구성 개체입니다. 이 구성을 사용하면 각 플랫폼 렌더러에서 자동으로 해석되는 공통 스타일(예: 글꼴 패밀리, 글꼴 크기, 기본 간격) 및 동작(예: 최대 작업 수)를 정의할 수 있습니다. 

사용자 작업을 최소화하면서 각 플랫폼 렌더러에서 생성하는 네이티브 UI를 최대한 비슷하게 만드는 것이 목표입니다.

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