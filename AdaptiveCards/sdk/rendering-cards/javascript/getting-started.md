---
title: JavaScript SDK
author: matthidinger
ms.author: mahiding
ms.date: 11/28/2017
ms.topic: article
ms.openlocfilehash: 4a6030dda12ab8d9a1e5c387cec63d45e84660d8
ms.sourcegitcommit: aa044167fd0b32b485ea2ce014afcf0b332bf1a2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69529838"
---
# <a name="getting-started---javascript"></a>시작 하기-JavaScript

[시작](../../../authoring-cards/getting-started.md) 페이지에서 설명한 대로 적응 카드는 JSON 직렬화 카드 개체 모델입니다. 이는 브라우저에서 클라이언트 쪽 HTML을 생성 하기 위한 JavaScript SDK입니다.

## <a name="install"></a>Install

### <a name="node"></a>노드

[![npm 설치](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards)

```console
npm install adaptivecards
```

### <a name="cdn"></a>CDN

```html
<script src="https://unpkg.com/adaptivecards/dist/adaptivecards.js"></script>
```

## <a name="usage"></a>사용법

### <a name="import-the-module"></a>모듈 가져오기

```js
// import the module
import * as AdaptiveCards from "adaptivecards";

// or require it
var AdaptiveCards = require("adaptivecards");

// or use the global variable if loaded from CDN
AdaptiveCards.renderCard(...);
```

## <a name="next-steps"></a>다음 단계

[카드 렌더링](render-a-card.md)에서 다음 단계를 확인합니다.
