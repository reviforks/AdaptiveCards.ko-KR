---
title: 음성 처리
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 64eeaefbc2ac775b69bd48cc853beb729cb2c37f
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67137996"
---
# <a name="handling-speech"></a>음성 처리

음성을 지원하기 위해 적응형 카드에는 사용자에게 카드를 소리 내어 읽어주는 방법에 대한 정보를 포함하는 `speak` 속성이 있습니다.

음성 태그는 [SSML 태그](https://msdn.microsoft.com/en-us/library/office/hh361578(v=office.14).aspx)를 사용하여 주석으로 처리할 수 있습니다. SSML은 음성의 속도, 어조, 억양을 제어하는 기능을 제공합니다.  이 속성을 이용하면 자체 서비스에서 오디오를 스트리밍하거나 TTS 오디오 스트림을 렌더링할 수 있으므로 사용자 지정의 폭이 넓습니다.

호스트 애플리케이션의 speak 속성 사용 패턴은 두 가지가 있습니다.
* **제공 시** - 카드가 제공될 때 클라이언트가 카드의 speak 속성을 읽어서 카드 내용 전체를 설명할지 선택할 수 있습니다.
* **요청 시** - 더 풍부한 접근성 모델을 지원하기 위해 스키마에서 요소별 음성 태그를 지원합니다.  
이를 통해 클라이언트가 접근성 요구 사항이 있는 수신자에게 각 요소를 읽어줄 수 있습니다.

