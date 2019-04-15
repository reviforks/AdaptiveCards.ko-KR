---
title: 동작
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 42ba1ca4ba2ecd508bdee2f04061293d48349aab
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553375"
---
# <a name="actions"></a>동작

기본적으로 카드에서 단추도 렌더링 됩니다. 작업 되지만 예상 대로 작동 되도록 할 앱에 달려 있습니다. 각 SDK에 해당 하는 `OnAction` 처리 해야 하는 이벤트입니다.

* **Action.OpenUrl** -지정 된 열 `url`합니다.  
* **Action.Submit** -제출 결과 및 원본에 전송 합니다. 전적으로 사용자가 어떻게 보내기 카드의 원본입니다.
* **Action.ShowCard** -대화 상자를 호출 하 고 해당 대화 상자에 하위 카드를 렌더링 합니다. 참고만 할 경우이 처리할 `ShowCardActionMode` 로 설정 된 `popup`합니다.