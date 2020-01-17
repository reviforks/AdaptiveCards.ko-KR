---
title: 호스트 구성-Xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: 554b32d9d088e82fb0fd48bec4b94340e843abeb
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76146127"
---
# <a name="host-config---android"></a>호스트 구성-Android

렌더러를 사용자 지정 하려면 HostConfig 개체의 인스턴스를 제공 합니다. 전체 설명은 [호스트 구성 스키마](../../../../rendering-cards/host-config.md) 를 참조 하세요.

문자열에서 ```HostConfig``` 개체를 만들려면 다음과 같이 ```DeserializeFromString``` 메서드를 사용 합니다.

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
// ...

HostConfig Config = HostConfig.DeserializeFromString(configJson);
```