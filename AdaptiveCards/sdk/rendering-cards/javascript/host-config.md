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

세 가지 방법으로 적응 카드 렌더링을 사용자 지정할 수 있습니다. 
1. 호스트 구성
2. CSS 스타일 지정
3. 사용자 지정 요소 렌더링

### <a name="hostconfig"></a>HostConfig 

A [호스트 구성](../../../rendering-cards/host-config.md) 은 일부 렌더러에서 이해 하는 공유 구성 개체입니다. 이 옵션을 사용 하면 (예: 글꼴 패밀리, 글꼴 크기를 기본 간격) 공통 스타일 및 각 플랫폼 렌더러를 통해 자동으로 해석 될 동작 (예: 작업의 최대 수)를 정의할 수 있습니다. 

목표는 각 플랫폼 렌더러에 의해 생성 된 네이티브 UI를 사용자의 최소한의 작업 에서도 이와 비슷한 방법이 표시 됩니다.

```javascript
var renderOptions = {
    ...
    hostConfig: {
        // Define your host config object here
        // See the HostConfig docs for details
    }
};
```