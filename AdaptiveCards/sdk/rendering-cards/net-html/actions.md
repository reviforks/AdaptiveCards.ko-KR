---
title: 작업-HTML.NET SDK
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
# <a name="actions---net-html"></a>작업을.NET HTML

최상위 카드 `actions` 는 HTML로 렌더링 될 `<button>`합니다. 서버 쪽 라이브러리 이기 때문에 달려 단추를 누르면 클라이언트 쪽 이벤트 처리기를 연결 하는 데 있습니다. 각 `<button>` HTML의 특성을 갖습니다 사용할 수 있는 적절 한 동작을 연결 합니다.

일부 요소는 `selectAction` 호출 되도록 하는 속성 (열, 컨테이너 이미지). 요소에 있는 경우는 `selectAction` 렌더러의 CSS 클래스를 추가 합니다 `ac-selectable`, 함께 특성 아래.

동작 유형 | CSS 클래스 | 추가 특성
---|---|---
`Action.OpenUrl` | `ac-action-openUrl` | `data-ac-url` (의 `url` 카드에서 속성)
`Action.Submit` | `ac-action-submit` | `data-ac-data` (의 `data` 카드에서 속성)
`Action.ShowCard` | `ac-action-showCard` | `data-ac-showcardid` (합니다 `id` 의 `<div>` 내부 카드 포함)