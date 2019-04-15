---
title: JavaScript SDK
author: matthidinger
ms.author: mahiding
ms.date: 11/28/2017
ms.topic: article
ms.openlocfilehash: 9684b96bba5168a1f07549468274ce5d74c01820
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553465"
---
# <a name="getting-started---javascript"></a>가져오기 시작-JavaScript

설명 했 듯이 [Getting Started](../../../authoring-cards/getting-started.md) 페이지 Adaptive Card는 JSON 직렬화 된 카드 개체 모델입니다. 이것이 브라우저에서 클라이언트 쪽 HTML을 생성 하는 것에 대 한 JavaScript SDK입니다.

> [!IMPORTANT]
> **주요 v0.5에서 변경 내용**
> 
> 1. 패키지에서 이름이 `microsoft-adaptivecards` 를 `adaptivecards`
> 1. 정적 `AdaptiveCards.setHostConfig()` 의 인스턴스 멤버를 이동 되었습니다 `AdaptiveCard`합니다. 예를 들어, `myCard.hostConfig = {}` 
> 1. `HostConfig` 다양 한 이름 바꾸기 및 이동 하지만 발생 했습니다. 참조 된 [sample.json](https://github.com/Microsoft/AdaptiveCards/blob/master/samples/HostConfig/sample.json) 현재 구조에 대 한 호스트 구성
> 1. 또한 일부 스키마 변경 내용이 있었는지 v0.5 미리 보기에서는 [여기에 설명 된](https://github.com/Microsoft/AdaptiveCards/pull/633)
> 1. 정적 `renderCard()` 함수 처럼 클래스 메서드를 사용 하 여 중복 제거 되었습니다. 사용 하 여 `adaptiveCard.render()` 아래 설명 된 대로 합니다. 


## <a name="install"></a>Install

### <a name="node"></a>노드

[![npm 설치](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards)

```console
npm install adaptivecards --save
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

참조 [카드를 렌더링할](render-a-card.md) 다음 단계!
