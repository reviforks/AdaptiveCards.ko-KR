---
title: 음성 처리
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 64eeaefbc2ac775b69bd48cc853beb729cb2c37f
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67137996"
---
# <a name="handling-speech"></a>음성 처리

Adaptive Card는 지원 음성는 `speak` 어떻게 카드 읽어야 소리 내어 사용자에 대 한 정보를 포함 하는 속성입니다.

음성 태그를 사용 하 여 주석을 추가할 수 있습니다 [SSML 태그](https://msdn.microsoft.com/en-us/library/office/hh361578(v=office.14).aspx)합니다. SSML 음성의 변 곡점 기능 컨트롤 톤 속도 제공합니다.  도 수 있도록 스트림에 오디오를 렌더링 하 TTS 오디오 스트림 자체 서비스에서 많은 양의 사용자 지정을 제공 합니다.

2 패턴에 대 한 호스트 응용 프로그램 속성의 사용을 말하고 있습니다.
* **배송** 카드는 클라이언트에 전달 될 때-전체적으로 카드를 설명 하는 카드에 대 한 읽기 속성 읽기를 바꿀 수 있습니다.
* **주문형** -요소당를 말하기 태그에서 스키마에서 지 원하는 다양 한 내게 필요한 옵션 모델을 지원 하기 위해.  
이렇게 하면 클라이언트가 접근성 요구 사항 사용 하 여 각 요소를 읽을 수 있습니다.

