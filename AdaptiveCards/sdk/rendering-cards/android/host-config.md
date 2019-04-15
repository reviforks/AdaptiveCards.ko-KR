---
title: 호스트 구성-Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: c44cf609fd52423a1ca17988a875c6dc48550007
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553345"
---
# <a name="host-config---android"></a>호스트 구성-Android

렌더러에 맞게 HostConfig 개체의 인스턴스를 제공 합니다. (참조 [호스트 구성 스키마](../../../rendering-cards/host-config.md) 전체 설명 합니다.)

문자열에서 HostConfig 개체를 만들려면 DeserializeFromString 메서드를 사용 합니다.

```java
HostConfig hostConfig = HostConfig.DeserializeFromString(hostConfigText);
```