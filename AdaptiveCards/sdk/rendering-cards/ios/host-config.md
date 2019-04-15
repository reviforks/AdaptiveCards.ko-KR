---
title: Host config - iOS SDK
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: b788ecc5c2371d2575e0165296365238535dd7c5
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553705"
---
# <a name="host-config---ios"></a>호스트 구성-iOS

JSON 문자열에 의해 생성 될 수 있는 HostConfig 통해 호스트를 구성할 수 있습니다.

```objective-c
ACOParseResult *hostconfigParseResult = [ACOHostConfig FromJson:self.hostconfig];
```

기본 HostConfig은 인스턴스화할 수 있습니다.

```objective-c
ACOHostConfig *defaultConfig = [[ACHostConfig alloc] init];
```

## <a name="render-a-card-using-host-config"></a>호스트 구성을 사용 하 여 카드를 렌더링 합니다.

Rederer는 적응 카드 및 호스트 구성 합니다. HostConfig nil, 수 및 nil 기본값이 사용 됩니다.

```objective-c
ACRRenderResult *renderResult;
renderResult = [ACRRenderer render:cardParseResult.card
                            config:hostconfigParseResult.config
                   widthConstraint:300.0];
```