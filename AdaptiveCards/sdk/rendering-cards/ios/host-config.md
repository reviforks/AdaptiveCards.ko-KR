---
title: 호스트 구성-iOS SDK
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

호스트는 JSON 문자열로 생성할 수 있는 HostConfig를 통해 구성할 수 있습니다.

```objective-c
ACOParseResult *hostconfigParseResult = [ACOHostConfig FromJson:self.hostconfig];
```

기본 HostConfig를 인스턴스화할 수 있습니다.

```objective-c
ACOHostConfig *defaultConfig = [[ACHostConfig alloc] init];
```

## <a name="render-a-card-using-host-config"></a>호스트 구성을 사용 하 여 카드 렌더링

렌더러는 적응형 카드와 호스트 구성을 사용합니다. HostConfig는 nil일 수 있으며, nil인 경우 기본값이 사용됩니다.

```objective-c
ACRRenderResult *renderResult;
renderResult = [ACRRenderer render:cardParseResult.card
                            config:hostconfigParseResult.config
                   widthConstraint:300.0];
```