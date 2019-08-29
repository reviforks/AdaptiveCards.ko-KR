---
title: 호스트 구성-JavaScript SDK
author: matthidinger
ms.author: mahiding
ms.date: 11/28/2017
ms.topic: article
ms.openlocfilehash: 1809a022481e4fb28d2db454cfe90e07d09279ff
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553605"
---
# <a name="host-config---javascript"></a>호스트 구성-JavaScript

```js
// Create an AdaptiveCard instance
var adaptiveCard = new AdaptiveCards.AdaptiveCard();

// Set its hostConfig property unless you want to use the default Host Config
// Host Config defines the style and behavior of a card
adaptiveCard.hostConfig = new AdaptiveCards.HostConfig({
    fontFamily: "Segoe UI, Helvetica Neue, sans-serif"
    // More host config options
});

// Render the card to an HTML element:
var renderedCard = adaptiveCard.render();
```

## <a name="customization"></a>사용자 지정

적응 카드 렌더링을 사용자 지정 하는 방법에는 3 가지가 있습니다. 
1. 호스트 구성
2. CSS 스타일 지정
3. 사용자 지정 요소 렌더링

### <a name="hostconfig"></a>HostConfig 

[호스트 구성](../../../rendering-cards/host-config.md)은 모든 렌더러가 이해하는 공유 구성 개체입니다. 이 구성을 사용하면 각 플랫폼 렌더러에서 자동으로 해석되는 공통 스타일(예: 글꼴 패밀리, 글꼴 크기, 기본 간격) 및 동작(예: 최대 작업 수)를 정의할 수 있습니다. 

사용자 작업을 최소화하면서 각 플랫폼 렌더러에서 생성하는 네이티브 UI를 최대한 비슷하게 만드는 것이 목표입니다.

```javascript
var renderOptions = {
    ...
    hostConfig: {
        // Define your host config object here
        // See the HostConfig docs for details
    }
};
```