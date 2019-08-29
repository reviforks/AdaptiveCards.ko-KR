---
title: 작업-.NET HTML SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 99bf6121489391c207a71b45264dc68aa2c6116e
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553315"
---
# <a name="actions---net-html"></a>작업-.NET HTML

최상위 카드 `actions` 는 HTML `<button>`로 렌더링 됩니다. 서버 쪽 라이브러리 이기 때문에 단추를 누르면 클라이언트 쪽 이벤트 처리기를 연결 하는 것이 가장 좋습니다. HTML `<button>` 의 각에는 적절 한 동작을 연결 하는 데 사용할 수 있는 특성이 있습니다.

일부 요소에는 `selectAction` 호출 가능 수 있도록 하는 속성 (컨테이너, 열, 이미지)이 있습니다. 요소에가 `selectAction` 있는 경우 렌더러는 아래 특성과 함께의 `ac-selectable`CSS 클래스를 추가 합니다.

동작 유형 | CSS 클래스 | 추가 특성
---|---|---
`Action.OpenUrl` | `ac-action-openUrl` | `data-ac-url`(카드의 속성) `url`
`Action.Submit` | `ac-action-submit` | `data-ac-data`(카드의 속성) `data`
`Action.ShowCard` | `ac-action-showCard` | `data-ac-showcardid`(내부 카드를 `<div>` 포함 하는 의)`id`