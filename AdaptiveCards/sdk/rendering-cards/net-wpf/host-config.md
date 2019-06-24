---
title: 호스트 구성 - .NET WPF SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 9ca540cbbb445f306f073f1936af46f8c2def99b
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67134303"
---
# <a name="host-config---net-wpf"></a>호스트 구성 - .NET WPF

[호스트 구성](../../../rendering-cards/host-config.md)은 모든 렌더러가 이해하는 공유 구성 개체입니다. 이 구성을 사용하면 각 플랫폼 렌더러에서 자동으로 해석되는 공통 스타일(예: 글꼴 패밀리, 글꼴 크기, 기본 간격) 및 동작(예: 최대 작업 수)를 정의할 수 있습니다. 

사용자 작업을 최소화하면서 각 플랫폼 렌더러에서 생성하는 네이티브 UI를 최대한 비슷하게 만드는 것이 목표입니다.

```csharp
// Construct programmatically
renderer.HostConfig = new AdaptiveHostConfig()
{
    FontStyles = new FontStylesConfig()
    {
        Default = new FontStyleConfig()
        {
            FontFamily = "Consolas",
            FontSizes = {
                Small = 15,
                Default = 20,
                Medium = 25,
                Large = 30,
                ExtraLarge= 40
            }
        },
    }
};

// Or parse from JSON
renderer.HostConfig = AdaptiveHostConfig.FromJson(@"{
    ""fontStyles"": {
        ""default"": {
            ""fontFamily"": ""Consolas"",
            ""fontSizes"": {
                ""small"": 15,
                ""default"": 20,
                ""medium"": 25,
                ""large"": 30,
                ""extraLarge"": 40
            }
        }
    }}");
```
